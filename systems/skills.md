# Skills

## Hệ Thống Skill Slot (từ bản Advanced Class)

Mỗi nhân vật có **Skill Pool** (tất cả skill đã unlock) và có thể **trang bị tối đa 4 skill** để dùng trong battle.

| Khái niệm | Mô tả |
|---|---|
| **Skill Pool** | Toàn bộ skill đã unlock của nhân vật |
| **Equipped Skills** | Tối đa 4 skill chọn từ pool để dùng trong battle |
| **Swap** | Dùng `/skill equip/unequip <id>` bất cứ lúc nào ngoài battle |

### Loại Skill (Role)

| Role | Emoji | Mô tả |
|---|---|---|
| **active** | ⚔️ | Single-target attack, dùng trên cooldown |
| **aoe** | 🌀 | Đánh tất cả kẻ địch |
| **extra** | 🔥 | Skill đặc biệt (bounce, v.v.) |
| **passive** | 🌙 | Luôn hoạt động khi được lắp, không chiếm lượt |
| **buff** | ✨ | Buff bản thân, dùng một lượt |
| **heal** | 💚 | Hồi HP bản thân |
| **party** | 👥 | Hiệu ứng nhóm — chỉ có tác dụng trong co-op party |

### Ưu Tiên Skill Trong Battle

```
Heal (HP < 40%) → AoE (≥2 địch) → Buff (chưa active) → Single target → Đánh thường
```

**Party co-op:** Group skill được kích hoạt đầu tiên (trước cả Heal), rồi mới theo thứ tự thông thường.

---

## Base Classes

Mỗi base class có **pool cố định 3–4 skill** từ Lv1/Lv10. Xem chi tiết bên dưới.

---

## Công Thức Sát Thương

```
rawDmg = ATK ± 20% (ngẫu nhiên) × dmgMult
```

- **Xuyên giáp:** `dealt = max(1, rawDmg)` — bỏ qua toàn bộ DEF kẻ địch
- **Bình thường:** `dealt = takeDamage(rawDmg)` — trừ DEF kẻ địch

---

## ⚔️ Chiến Binh

### Active — Chém Mạnh
> Đánh mạnh một kẻ địch

| | |
|---|---|
| **Sát thương** | 150% ATK |
| **Chi phí MP** | 15 |
| **Cooldown** | 3 lượt |
| **Xuyên giáp** | Không |

**Công thức:** `dealt = max(1, floor(ATK ± 20%) × 1.5) − DEF_địch`

---

### AOE — Chém Vòng *(Lv10)*
> Quét tất cả kẻ địch xung quanh

| | |
|---|---|
| **Sát thương** | 100% ATK mỗi mục tiêu |
| **Chi phí MP** | 20 |
| **Cooldown** | 4 lượt |
| **Xuyên giáp** | Không |

**Ưu tiên dùng** khi có ≥2 kẻ địch.

---

### Passive — Trụ Cột
> Trở nên mạnh hơn khi chiến đấu liên tục

| | |
|---|---|
| **ATK từ HP** | +0.5% maxHP dưới dạng ATK phẳng |
| **DEF Stack** | Mỗi lần bị đánh: +5% giảm ST, tối đa 3 stack (tổng -15%) |
| **Heavy Resist** | Mặc Giáp Nặng: +10% Resist |

**Công thức ATK:** `attack += floor(maxHP × 0.005)`
**Công thức stack:** `dealt_cuối = max(1, floor(dealt × (1 − stacks×0.05)))` — áp dụng trước Mana Shield.

---

## 🗡️ Thích Khách

### Active — Đâm Hiểm
> Cú đâm cực mạnh vào một mục tiêu

| | |
|---|---|
| **Sát thương** | 200% ATK |
| **Chi phí MP** | 20 |
| **Cooldown** | 4 lượt |
| **Xuyên giáp** | Không |

**Công thức:** `dealt = max(1, floor(ATK ± 20%) × 2.0) − DEF_địch`

---

### AOE — Vũ Bão Dao *(Lv10)*
> Tung lưỡi dao vào tất cả kẻ địch

| | |
|---|---|
| **Sát thương** | 80% ATK mỗi mục tiêu |
| **Chi phí MP** | 20 |
| **Cooldown** | 4 lượt |
| **Xuyên giáp** | Không |

---

### Passive — Sát Thương Chí Mạng
> Tăng sát thương chí mạng cố định, không bị ảnh hưởng bởi diminishing return

| | |
|---|---|
| **Bonus Crit DMG** | +50% flat |
| **Crit Rate** | DEX × 0.25%, hard cap **60%** |
| **Crit DMG** | Hard cap **300%** tổng |
| **EVA** | DEX × 0.3%, hard cap **65%** |

**Công thức crit DMG:** `critMult = min(3.0, critDmgMult() + 0.5)` — +50% flat sau soft cap trang bị, giới hạn tổng 300%.

---

## 🔮 Pháp Sư

### Active — Cầu Lửa
> Cầu lửa xuyên thủng giáp kẻ địch

| | |
|---|---|
| **Sát thương** | 175% ATK |
| **Chi phí MP** | 25 |
| **Cooldown** | 4 lượt |
| **Xuyên giáp** | **Có** |

**Công thức:** `dealt = max(1, floor(ATK ± 20%) × 1.75)` — bỏ qua DEF hoàn toàn.

---

### AOE — Bão Lửa *(Lv10)*
> Bùng nổ lửa đốt toàn bộ kẻ địch, xuyên giáp

| | |
|---|---|
| **Sát thương** | 120% ATK mỗi mục tiêu |
| **Chi phí MP** | 30 |
| **Cooldown** | 4 lượt |
| **Xuyên giáp** | **Có** |

**Công thức:** `dealt = max(1, floor(ATK ± 20%) × 1.2)` cho mỗi kẻ địch.

---

### Extra — Chuỗi Lửa *(Lv10)*
> Phóng lửa rồi bắn tiếp vào mục tiêu thứ hai

| | |
|---|---|
| **Sát thương** | 160% ATK vào mục tiêu chính |
| **Bắn tiếp** | 60% sát thương vừa gây vào mục tiêu ngẫu nhiên khác |
| **Chi phí MP** | 20 |
| **Cooldown** | 3 lượt |
| **Xuyên giáp** | **Có** |

**Công thức:**
```
rawDmg   = floor(ATK ± 20%) × 1.6
dealt    = max(1, rawDmg)          ← mục tiêu HP thấp nhất
bounceDmg = max(1, floor(rawDmg × 0.6))  ← mục tiêu ngẫu nhiên còn lại
```

> Chuỗi Lửa chỉ dùng khi Active (Cầu Lửa) đang cooldown. Nếu cả hai đều sẵn, ưu tiên Cầu Lửa.

---

### Passive — Mana Shield & Penetration
> Chuyển hóa sát thương thành MP; spell xuyên phá kháng phép kẻ địch

| | |
|---|---|
| **Mana Shield** | 40% sát thương nhận hấp thụ bằng MP |
| **MP Regen** | +5 MP cuối mỗi lượt |
| **Spell Crit** | Không — spell cho damage ổn định thay vì crit |
| **MAG Penetration** | `pen = min(50%, MAG×0.5%)` giảm Resist kẻ địch |

**Công thức pen:** `effectiveResist = max(0, enemy.resist − pen)` — áp dụng cho mọi skill magical.

Ví dụ: MAG 60 → pen 30% → kẻ địch Resist 40% chỉ còn hiệu quả 10%.

---

## Tổng Kết — Base Classes

| Class | Active | AOE (Lv10) | Extra (Lv10) | Passive |
|---|---|---|---|---|
| ⚔️ Chiến Binh | Chém Mạnh 150% | Chém Vòng 100% | — | ATK+HP, DEF Stack, Heavy+Resist |
| 🗡️ Thích Khách | Đâm Hiểm 200% | Vũ Bão Dao 80% | — | +50% Crit DMG flat, cap 300% |
| 🔮 Pháp Sư | Cầu Lửa 175% ⚡ | Bão Lửa 120% ⚡ | Chuỗi Lửa 160%+60% ⚡ | Mana Shield 40%, MAG Pen |

*⚡ = xuyên giáp*

---

## Advanced Classes (Chiến Binh · Lv20+)

Xem trang đầy đủ: [Advanced Classes](advanced-classes.md)

| Class | Passive Mod | Cơ chế đặc biệt |
|---|---|---|
| ⚔️ **Berserker** | +15% ATK / −30% DEF | Rage mult: càng ít HP → ATK càng cao (tối đa +40% khi HP ≤ 40%) |
| 🛡️ **Paladin** | −30% ATK / +30% DEF | Thorn passive: phản floor(DEF × 20%) mỗi đòn nhận |
| 👑 **Royal Knight** | +7% ATK / +7% DEF | Bỏ qua stat req; +2% ATK+DEF per item đang đeo |

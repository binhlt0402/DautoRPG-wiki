# Advanced Classes

Advanced class là bước nâng cấp từ base class ở **Lv20+**, mở khoá cơ chế và skill mới. Việc advance **không thể hoàn tác**.

## Cách Advance

```
/advance <class>
```

Yêu cầu: Lv20+, đang là base class tương ứng.

Sau khi advance:
- Class đổi vĩnh viễn
- Passive stat modifier áp dụng ngay (ATK/DEF tổng thay đổi)
- Skill pool nhận thêm 4 skill mới (giữ lại skill cũ)
- 4 skill mới được tự động lắp vào slot — có thể swap bất cứ lúc nào

---

## Hệ Thống Skill Slot

Mỗi nhân vật có **Skill Pool** (tất cả skill đã unlock) và **tối đa 4 skill equipped** để dùng trong battle.

| Lệnh | Tác dụng |
|---|---|
| `/skill list` | Xem pool + equipped (✅ = đang lắp) |
| `/skill equip <id>` | Lắp skill (max 4) |
| `/skill unequip <id>` | Tháo skill |

Chiến Binh base có 3 skill. Sau khi advance có thêm 4 skill → pool 7, chọn 4 để dùng.

---

## ⚔️ Berserker

> *"Càng gần chết càng nguy hiểm."*

**Yêu cầu:** Chiến Binh Lv20+

### Passive Vĩnh Viễn

| | |
|---|---|
| ATK tổng | **+15%** |
| DEF tổng | **−30%** |
| Rage Scale | Khi HP < 100%, bonus ATK scale tuyến tính đến **+40% khi HP ≤ 40%** |

**Công thức Rage:**
```
hpPct = hp / maxHp
t     = clamp((1.0 − hpPct) / (1.0 − 0.40), 0, 1)
rageMult = 1 + t × 0.40
```
Nếu HP = 40% → `rageMult = 1.40` (tổng ATK tăng 40% so với ATK đã tính passive mod).

### Skill Pool Mới Khi Advance

| ID | Tên | Role | Mô tả | CD | MP |
|---|---|---|---|---|---|
| `berserker_lifesteal` | Hút Máu | ⚔️ active | 150% ATK, hồi HP = 30% dmg gây ra | 3 | 18 |
| `berserker_rampage` | Cơn Điên | 🌀 aoe | 110% ATK tất cả địch, xuyên 20% DEF | 4 | 25 |
| `berserker_rage` | Rage | ✨ buff | Immune hiệu ứng + +50% ATK 2 lượt; sau đó −20% ATK/−20% DEF 2 lượt | 7 | 30 |
| `berserker_sacrifice` | Chém Tuyệt Vọng | ⚔️ active | Tốn 15% HP hiện tại, 260% ATK xuyên giáp hoàn toàn | 5 | 10 |

**Pool đầy đủ (7 skill):** `warrior_slash`, `warrior_cleave`, `warrior_pillar`, + 4 skill Berserker.

### Mẹo Chơi

- Giữ HP thấp → Rage Scale cộng thêm ATK đáng kể
- **Rage** buff → dùng ngay đầu trận để vừa buff vừa immune debuff
- **Chém Tuyệt Vọng** mạnh nhất khi HP đã thấp (tốn HP nhưng không thể tự giết)
- Lifesteal giúp tự hồi trong lúc stack Rage — synergy với Rage Scale

---

## 🛡️ Paladin

> *"Phòng thủ là vũ khí tốt nhất."*

**Yêu cầu:** Chiến Binh Lv20+

### Passive Vĩnh Viễn

| | |
|---|---|
| ATK tổng | **−30%** |
| DEF tổng | **+30%** |
| Thorn | Mỗi đòn nhận từ địch → phản `floor(DEF_hiệu_quả × 20%)` cho kẻ tấn công |

**Công thức Thorn:**
```
reflect = floor(effectiveDef × 0.20)
enemy.hp -= reflect   ← mỗi đòn nhận
```
`effectiveDef` bao gồm Holy Shield buff nếu đang active.

### Skill Pool Mới Khi Advance

| ID | Tên | Role | Mô tả | CD | MP |
|---|---|---|---|---|---|
| `paladin_strike` | Thánh Kích | ⚔️ active | 140% ATK phép xuyên giáp, hồi 25% dmg gây ra | 3 | 20 |
| `paladin_judgment` | Phán Quyết | 🌀 aoe | 100% ATK phép tất cả, địch trúng nhận +20% dmg lượt tiếp | 4 | 30 |
| `paladin_heal` | Thánh Hộ | 💚 heal | Hồi 30% maxHP, xóa toàn bộ debuff | 5 | 25 |
| `paladin_shield` | Thánh Thuẫn | ✨ buff | Block 2 đòn tiếp theo hoàn toàn, +25% DEF 3 lượt | 6 | 20 |

**Pool đầy đủ (7 skill):** `warrior_slash`, `warrior_cleave`, `warrior_pillar`, + 4 skill Paladin.

### Mẹo Chơi

- **DEF càng cao → Thorn càng mạnh** — đầu tư trang bị DEF cao
- **Thánh Thuẫn** tăng DEF buff → Thorn reflect cũng tăng theo trong thời gian buff
- **Thánh Hộ** dùng khi HP < 40% để hồi + xóa bleed/debuff
- **Phán Quyết** đánh dấu tất cả địch → lượt sau chúng nhận +20% dmg (kể cả từ Thorn)
- ATK thấp → dùng build MAG equip để Thánh Kích đủ dmg

---

## 👑 Royal Knight

> *"Không giới hạn, không ràng buộc."*

**Yêu cầu:** Chiến Binh Lv20+

### Passive Vĩnh Viễn

| | |
|---|---|
| ATK tổng | **+7%** |
| DEF tổng | **+7%** |
| Bypass Stat Req | Bỏ qua **toàn bộ** yêu cầu STR/DEX/MAG khi trang bị armor, helmet, offhand |
| Item Bonus | Mỗi slot đang đeo item → +2% ATK+DEF (tối đa +14% khi 7/7 slot đầy) |

**Công thức Item Bonus:**
```
filledSlots = số slot đang đeo item (0–7)
bonus       = filledSlots × 0.02
attack  = round(attack  × (1 + bonus))
defense = round(defense × (1 + bonus))
```

### Skill Pool Mới Khi Advance

| ID | Tên | Role | Mô tả | CD | MP |
|---|---|---|---|---|---|
| `royalknight_slash` | Kiếm Hiệp Sĩ | ⚔️ active | 170% ATK, xuyên 25% DEF địch | 3 | 18 |
| `royalknight_charge` | Đột Kích | 🌀 aoe | 90% ATK tất cả, 35% stun mỗi mục tiêu 1 lượt | 4 | 25 |
| `royalknight_aura` | Hào Quang | ✨ buff | Giảm 25% dmg nhận + +10% ATK trong 3 lượt | 5 | 20 |
| `royalknight_prestige` | Phong Hầu | 🌙 passive | Mỗi crit → +1% ATK/+1% DEF vĩnh viễn trong battle (max 10 stack, reset sau battle) | — | — |

**Pool đầy đủ (7 skill):** `warrior_slash`, `warrior_cleave`, `warrior_pillar`, + 4 skill Royal Knight.

### Mẹo Chơi

- **Bypass stat req** cho phép mặc Giáp Nhẹ (EVA cao) hoặc Áo Phép dù thiếu DEX/MAG
- Đeo đủ 7 slot → +14% ATK+DEF thêm — ưu tiên trang bị đầy các slot
- **Phong Hầu** passive + crit rate cao → snowball mạnh cuối dungeon
- **Hào Quang** dùng sớm đầu trận để cộng dồn với Prestige stacks
- **Đột Kích** stun 35% chance → rất hiệu quả trong dungeon multi-enemy

---

## So Sánh 3 Advanced Classes

| | ⚔️ Berserker | 🛡️ Paladin | 👑 Royal Knight |
|---|---|---|---|
| **ATK** | +15% (+ rage mult) | −30% | +7% (+ item bonus) |
| **DEF** | −30% | +30% (+ thorn) | +7% (+ item bonus) |
| **Phong cách** | Liều lĩnh, high risk/reward | Tank, phản đòn | Linh hoạt, full-item |
| **Điểm mạnh** | Burst dmg, lifesteal | Sustain, phản dmg | Không giới hạn trang bị |
| **Điểm yếu** | DEF thấp, nguy cơ chết | ATK thấp | Không có cơ chế đặc biệt |
| **Build đề xuất** | STR + VIT, Giáp Nặng | STR + VIT, DEF cao nhất | Bất kỳ — ưu tiên đầy slot |

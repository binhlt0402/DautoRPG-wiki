# Skills

Mỗi class có **2–3 skill** chia làm 4 loại:

| Loại | Mô tả |
|---|---|
| **Active** | Single-target, dùng được từ Lv1, tốn MP + cooldown |
| **AOE** | Đánh toàn bộ kẻ địch, mở khóa Lv10 |
| **Extra** | Pháp Sư độc quyền, mở khóa Lv10 |
| **Passive** | Luôn hoạt động, không cần kích hoạt |

**Ưu tiên dùng skill trong trận:** AOE (khi ≥2 kẻ địch) > Extra > Active > Đánh thường

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

### Passive — Dày Mặt
> Giảm 15% sát thương nhận vào (không xuyên giáp)

**Công thức:** `dealt = max(1, floor(rawDmg_địch × 0.85))` — áp dụng sau khi trừ DEF, chỉ với đòn không xuyên giáp.

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

### Passive — Phản Công
> 25% cơ hội phản đòn khi bị tấn công

| | |
|---|---|
| **Xác suất** | 25% mỗi đòn nhận |
| **Sát thương phản** | 50% ATK − DEF_địch |

**Công thức:** `counterDmg = max(1, floor(ATK × 0.5) − DEF_địch)` — xảy ra ngay sau mỗi đòn của kẻ địch.

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

### Passive — Hồi Năng Lượng
> Tự động hồi MP cuối mỗi lượt

| | |
|---|---|
| **Hồi phục** | +8 MP / lượt |

Giúp Pháp Sư duy trì spam skill liên tục mà không cần lo cạn MP.

---

## Tổng Kết

| Class | Active | AOE (Lv10) | Extra (Lv10) | Passive |
|---|---|---|---|---|
| ⚔️ Chiến Binh | Chém Mạnh 150% | Chém Vòng 100% | — | Giảm 15% ST nhận |
| 🗡️ Thích Khách | Đâm Hiểm 200% | Vũ Bão Dao 80% | — | 25% phản 50% ATK |
| 🔮 Pháp Sư | Cầu Lửa 175% ⚡ | Bão Lửa 120% ⚡ | Chuỗi Lửa 160%+60% ⚡ | +8 MP/lượt |

*⚡ = xuyên giáp*

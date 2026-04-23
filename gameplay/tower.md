# Tháp Thử Thách

## Tổng Quan

Tháp Thử Thách gồm **100 tầng** liên tiếp, mỗi tầng đánh 2–3 quái. Tầng thứ 10, 20, 30... là tầng Boss (Mini-Boss), tầng 100 là Final Boss.

```
/tower start    ← bắt đầu leo từ tầng đầu tiên chưa vượt
/tower status   ← xem tiến trình hiện tại
/tower next     ← đánh tầng tiếp theo
/tower skip     ← bỏ qua tầng hiện tại (mất tiến trình tầng đó)
```

---

## Quái & Cấp Độ

| Tầng | Level quái (ước tính) | Ghi chú |
|---|---|---|
| 1 | ~40 | Bắt đầu yêu cầu Lv40+ |
| 50 | ~75 | Tầng giữa |
| 100 | ~110 | Final Boss |

Tầng ×10 (boss floor): 1 Mini-Boss + 2 quái phụ yếu hơn.
Tầng 100: 1 Boss chính + 2 quái phụ.

---

## Nguyên Liệu Rớt

Tầng 81+ không rớt nguyên liệu.

| Tầng | Loại tầng | Nguyên liệu | Tỉ lệ |
|---|---|---|---|
| 1–40 | Thường | 🔷 Mảnh Tháp ×1 | 70% |
| 1–40 | Boss (×10) | 💠 Lõi Tháp ×1 + 🔷 Mảnh Tháp ×2–3 | 100% |
| 41–80 | Thường | 🔶 Tinh Hoa Tháp ×1 | 70% |
| 41–80 | Boss (×10) | 🌟 Ngọc Tháp ×1 + 🔶 Tinh Hoa Tháp ×2–3 | 100% |

---

## Công Thức Craft (Lv50)

Dùng nguyên liệu tầng 1–40: 🔷 Mảnh Tháp + 💠 Lõi Tháp.

| Item | Rarity | Nguyên liệu |
|---|---|---|
| Vũ Khí / Giáp / Mũ / Tay Phụ | 🟠 Epic Lv50 | 🔷×10 + 💠×3 |
| Vũ Khí / Giáp / Mũ / Tay Phụ | 🔴 Ancient Lv50 | 🔷×15 + 💠×5 |
| Trang Sức | 🟠 Epic Lv50 | 🔷×8 + 💠×2 |
| Trang Sức | 🔴 Ancient Lv50 | 🔷×12 + 💠×4 |

---

## Công Thức Craft (Lv60)

Dùng nguyên liệu tầng 41–80: 🔶 Tinh Hoa Tháp + 🌟 Ngọc Tháp.

| Item | Rarity | Nguyên liệu |
|---|---|---|
| Vũ Khí / Giáp / Mũ / Tay Phụ | 🟠 Epic Lv60 | 🔶×10 + 🌟×3 |
| Vũ Khí / Giáp / Mũ / Tay Phụ | 🔴 Ancient Lv60 | 🔶×15 + 🌟×5 |
| Trang Sức | 🟠 Epic Lv60 | 🔶×8 + 🌟×2 |
| Trang Sức | 🔴 Ancient Lv60 | 🔶×12 + 🌟×4 |

> Giáp có 3 loại: 🗡️ Nặng (req STR) · 🌬️ Nhẹ (req DEX) · 🔮 Phép (req MAG) — cùng công thức.
> Tay Phụ có 3 loại: 🛡️ Khiên · 🗡️ Dao Phụ · 🔮 Cầu Phép — cùng công thức.

---

## Cơ Chế Đặc Biệt — Debuff Tích Lũy

Mỗi tầng boss vượt qua → tích lũy **1 debuff ngẫu nhiên** cho các tầng tiếp theo trong cùng run:

| Debuff | Hiệu ứng |
|---|---|
| ATK -22% | Giảm sát thương |
| DEF -22% | Giảm phòng thủ |
| EVA -25% | Giảm né tránh |
| CRIT -25% | Giảm tỉ lệ chí mạng |
| CRIT DMG -20% | Giảm sát thương chí mạng |

> Debuff reset khi bắt đầu run mới.

---

## Best Score

Điểm cao nhất (tầng vượt được xa nhất) được lưu lại. Dùng `/tower status` để xem.

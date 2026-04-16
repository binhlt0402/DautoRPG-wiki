# Explore & Zones

## Cách Dùng

```
/explore <zone> [turns]
```

* Mặc định: **100 lượt** (tối đa)
* Mỗi lượt: ~6 giây chiến đấu + 2 giây nghỉ
* Kết quả cập nhật realtime trong Discord

## Cơ Chế

* Mỗi lượt tự động chiến đấu với 1–3 quái (tùy cấp độ)
* Thắng: nhận EXP + vàng + 30% chance drop nguyên liệu
* Thua hoặc kiệt sức (fatigue): **bất tỉnh 10 phút**
* HP/MP hồi đầy **khi bắt đầu** và khi kết thúc mỗi session explore

## Vùng Explore

| Zone | Emoji | Cấp độ | Nguyên liệu |
|---|---|---|---|
| Rừng Xanh | 🌲 | Lv 1–5 | 🌿 Dược Thảo |
| Đồng Bằng | 🌾 | Lv 3–8 | 🦴 Xương Quái |
| Hang Động | ⛏️ | Lv 6–12 | 🪨 Đá Thô |
| Núi Tuyết | ⛰️ | Lv 10–18 | 🪨 Đá Thô, ⛏️ Quặng Sắt |
| Sa Mạc | 🏜️ | Lv 15–25 | ⛏️ Quặng Sắt |
| Núi Lửa | 🌋 | Lv 22–32 | ⛏️ Quặng Sắt, ⚡ Sấm Thạch |
| Vực Tối | 🌑 | Lv 30–42 | ⚡ Sấm Thạch, 👑 Tinh Linh Cổ |
| Thánh Địa | 🏛️ | Lv 40–55 | 👑 Tinh Linh Cổ |
| Hư Không | 🌀 | Lv 52–65 | 👑 Tinh Linh Cổ |
| Cõi Hỗn Nguồn | 💠 | Lv 62–75 | 👑 Tinh Linh Cổ |
| Thiên Đường | 🌤️ | Lv 72–80 | 👑 Tinh Linh Cổ |

> **Tip:** Chọn zone có cấp độ quái gần với cấp nhân vật để nhận EXP tối ưu.

## Fatigue (Kiệt Sức)

Mỗi lượt thắng bị trừ một lượng HP nhỏ tăng dần theo số lượt. Nếu HP về 0 vì fatigue hoặc thua trận → bất tỉnh 10 phút.

## Số Lượng Quái

| Cấp nhân vật | Số quái mỗi lượt |
|---|---|
| < 10 | 1 quái |
| 10–15 | 75% 1 quái / 25% 2 quái |
| 16+ | 60% 1 / 30% 2 / 10% 3 |

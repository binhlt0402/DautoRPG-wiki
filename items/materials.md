# Nguyên Liệu

## Danh Sách Nguyên Liệu

| ID | Tên | Nguồn |
|---|---|---|
| `herb` | 🌿 Dược Thảo | Explore Rừng Xanh (30%) |
| `bone` | 🦴 Xương Quái | Explore Đồng Bằng (30%) |
| `stone` | 🪨 Đá Thô | Explore Hang Động / Núi Tuyết (30%) |
| `ore` | ⛏️ Quặng Sắt | Explore Núi Tuyết / Sa Mạc / Núi Lửa (30%) |
| `crystal_magic` | 💠 Tinh Thể Ma | Dungeon T1 |
| `blood_essence` | ❤️ Tinh Huyết | Dungeon T2 |
| `thunder_gem` | ⚡ Sấm Thạch | Explore Núi Lửa / Vực Tối (30%) + Dungeon T3 |
| `ancient_spirit` | 👑 Tinh Linh Cổ | Explore Vực Tối / Thánh Địa / Hư Không / Cõi Hỗn Nguồn / Thiên Đường (30%) + Dungeon T4 |
| `shadow_crystal` | 🌑 Pha Lê Bóng Tối | Dungeon T5 |
| `dragon_bone` | 🐉 Xương Rồng | Dungeon T6 |
| `void_essence` | 🌀 Tinh Chất Hư Vô | Dungeon T7 |
| `ancient_gem` | 💎 Ngọc Cổ Đại | Dungeon T8 |
| `tower_shard_50` | 🔷 Mảnh Tháp | Tháp Thử Thách tầng 1–40 (thường) |
| `tower_core_50` | 💠 Lõi Tháp | Tháp Thử Thách tầng 1–40 (Boss) |
| `tower_shard_60` | 🔶 Tinh Hoa Tháp | Tháp Thử Thách tầng 41–80 (thường) |
| `tower_core_60` | 🌟 Ngọc Tháp | Tháp Thử Thách tầng 41–80 (Boss) |

> **Lưu ý:** Nguyên liệu Tower **không thể Break/Combine** và chỉ dùng để craft đồ Lv50/60.

## Chuỗi Nguyên Liệu (Break/Combine)

```
💠 → ❤️ → ⚡ → 👑 → 🌑 → 🐉 → 🌀 → 💎
(thấp)                                  (cao)
```

### Rã Nguyên Liệu (Break)

Rã **1 nguyên liệu tier cao** → nhận **3 nguyên liệu tier thấp hơn**

```
/craft break <id_nguyên_liệu> [số lượng]
```

Ví dụ: `/craft break blood_essence 2` → tốn 2 ❤️ + 400g → nhận 6 💠

**Chi phí:** 200g / lần rã

### Ghép Nguyên Liệu (Combine)

Ghép **3 nguyên liệu tier thấp** → nhận **1 nguyên liệu tier cao hơn**

```
/craft combine <id_nguyên_liệu> [số lần]
```

Ví dụ: `/craft combine crystal_magic 1` → tốn 3 💠 + 300g → nhận 1 ❤️

**Chi phí:** 300g / lần ghép

> **Tip:** Break khi thừa nguyên liệu cao mà cần thấp. Combine khi tích đủ 3x nguyên liệu thấp.

## Xem Kho Nguyên Liệu

```
/craft materials
```

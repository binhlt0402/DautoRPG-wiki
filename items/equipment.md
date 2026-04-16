# Loại Trang Bị

Có **4 slot** trang bị, mỗi slot ảnh hưởng đến chỉ số theo cách khác nhau.

## Các Slot

| Slot | Main Stat | Sub Stats | Nguồn |
|---|---|---|---|
| ⚔️ **Vũ Khí** | ★ **ATK** (cố định) | Random từ 10 stats | Drop, Shop, Craft |
| 🛡️ **Giáp** | ★ **DEF** (cố định) | Random từ 10 stats | Drop, Shop, Craft |
| 🪖 **Mũ** | ★ **DEF** (cố định) | Random từ 10 stats | Drop, Shop, Craft |
| 💍 **Trang Sức** | ★ **Random** (hoặc chọn khi craft) | Random từ 10 stats | **Craft only** (không drop) |

> **Lưu ý:** Trang Sức **không drop** từ quái hay dungeon — chỉ có thể craft hoặc mua từ chợ người chơi.

## Hệ Thống Stats

Mỗi trang bị có **1 main stat (★)** và **0–3 sub stats (·)** tùy theo rarity:

| Rarity | Sub Stats |
|---|---|
| ⚪ Common | 0 |
| 🔵 Magic | 1 |
| 🟡 Rare | 2 |
| 🟠 Epic | 3 |
| 🔴 Ancient | 3 |

**10 stats có thể xuất hiện trên trang bị:**

| Stat | Ký hiệu | Tác dụng |
|---|---|---|
| HP | HP | Tăng máu tối đa |
| DEF | DEF | Tăng phòng thủ vật lý |
| ATK | ATK | Tăng tấn công trực tiếp |
| CRIT% | CRIT% | Tăng tỷ lệ chí mạng |
| CDMG% | CDMG% | Tăng sát thương chí mạng |
| EVA% | EVA% | Tăng né tránh |
| PEN% | PEN% | Xuyên kháng phép (Pháp Sư) |
| RES% | RES% | Tăng kháng phép |
| CRIT-RES% | CRIT-RES% | Giảm xác suất bị chí mạng |
| MP/TRN | MP/TRN | Hồi MP mỗi lượt chiến đấu |

## Reroll Sub Stat

```
/reroll <id>    ← Hiển thị nút reroll từng dòng sub stat
```

- **Main stat không thể reroll** — cố định khi tạo đồ
- Mỗi lần reroll tốn **vàng + nguyên liệu** theo levelReq
- Sub stat mới được roll hoàn toàn ngẫu nhiên (cả loại lẫn giá trị)

## Loại Giáp (Armor Type)

Giáp và Mũ chia 3 loại, ảnh hưởng đến **EVA cap** và **yêu cầu chỉ số** để mặc:

| Loại | Yêu cầu stat | EVA Cap | Stat pool |
|---|---|---|---|
| 🗡️ **Giáp Nặng (Heavy)** | STR ≥ ngưỡng | **5%** | DEF cao, HP |
| 🌬️ **Giáp Nhẹ (Light)** | DEX ≥ ngưỡng | **80%** | EVA, DEX |
| 🔮 **Áo Phép (Robe)** | MAG ≥ ngưỡng | **40%** | Resist, MAG |

**Ngưỡng stat theo cấp đồ:**

| Lv đồ | Stat yêu cầu |
|---|---|
| Lv5 | ≥ 5 |
| Lv10 | ≥ 8 |
| Lv15 | ≥ 12 |
| Lv20 | ≥ 18 |
| Lv25 | ≥ 25 |
| Lv30 | ≥ 32 |
| Lv35 | ≥ 38 |
| Lv40 | ≥ 45 |

Loại giáp được xác định lúc drop (ngẫu nhiên) hoặc lúc craft (chọn theo recipe). Đồ cũ đã có trong túi đồ trước khi hệ thống này ra đời đã được tự động gán loại ngẫu nhiên.

## Quản Lý Trang Bị

```
/inventory list          ← Xem túi đồ (ID từng món)
/equip <id>              ← Mặc đồ (hiển thị thay đổi ATK/DEF/HP)
/unequip <slot>          ← Tháo đồ (hiển thị thay đổi)
/autoequip               ← Tự động mặc đồ có PR cao nhất
```

Tất cả thao tác mặc/tháo/bán/cất đồ đều có thể thực hiện trên **Dashboard web**.

Khi `/equip` hoặc `/unequip`, bot sẽ hiển thị chênh lệch chỉ số, ví dụ:
```
⚔️ ATK: 245 (+38) | 🛡️ DEF: 120 (+12) | ❤️ HP: 1850 (+150)
```

## Power Rating của Item

Mỗi item có **PR riêng** tính từ tổng chỉ số:

```
PR = STR×3 + DEX×3 + MAG×3 + VIT×2
   + ATK×2 + DEF×1.5 + HP×0.2
   + EVA×2 + RES×2 + CRIT×2 + CDMG×1.5
   + PEN×2 + CRIT-RES×1.5 + MP/TRN×3
```

`/autoequip` dùng PR này để chọn đồ tốt nhất cho từng slot.

## Cửa Hàng (Common)

```
/shop list      ← Xem đồ + stat range
/shop buy <đồ>  ← Mua (stats roll ngẫu nhiên)
```

Shop bán đồ ⚪ Common Lv5/10/15/20 cho: Vũ Khí, Giáp, Mũ, Trang Sức.

### Bán Hàng Loạt

```
/shop sell common    ← Bán tất cả Common không mặc
/shop sell magic     ← Bán Common + Magic
/shop sell rare      ← Bán Common + Magic + Rare
/shop sell epic      ← Bán tất cả (kể cả Epic, trừ Ancient)
```

> ⚠️ Ancient items **không bị bán** qua lệnh này. Dùng `/chest deposit` để bảo vệ thêm.

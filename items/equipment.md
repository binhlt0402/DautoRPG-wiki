# Loại Trang Bị

Có **4 slot** trang bị, mỗi slot ảnh hưởng đến chỉ số theo cách khác nhau.

## Các Slot

| Slot | Emoji | Tác dụng chính | Nguồn |
|---|---|---|---|
| ⚔️ **Vũ Khí** | Weapon | +ATK, +Crit, +CritDMG | Drop, Shop, Craft |
| 🛡️ **Giáp** | Armor | +DEF, +HP, +EVA, +Resist (tùy loại) | Drop, Shop, Craft |
| 🪖 **Mũ** | Helmet | +DEF, +HP, +EVA, +Resist (tùy loại) | Drop, Shop, Craft |
| 💍 **Trang Sức** | Accessory | +STR/DEX/VIT/MAG | **Craft only** (không drop) |

> **Lưu ý:** Trang Sức **không drop** từ quái hay dungeon — chỉ có thể craft hoặc mua từ chợ người chơi.

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
PR = STR×3 + DEX×3 + MAG×3 + VIT×2 + ATK×2 + DEF×1.5 + HP×0.2 + EVA×2 + Crit×2 + CritDMG×1 + Resist×2
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

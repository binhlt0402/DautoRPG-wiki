# Loại Trang Bị

Có **4 slot** trang bị, mỗi slot ảnh hưởng đến chỉ số theo cách khác nhau.

## Các Slot

| Slot | Emoji | Tác dụng chính | Nguồn |
|---|---|---|---|
| ⚔️ **Vũ Khí** | Weapon | +STR/DEX/MAG, +ATK | Drop, Shop, Craft |
| 🛡️ **Giáp** | Armor | +DEF, +HP, +EVA, +VIT | Drop, Shop, Craft |
| 🪖 **Mũ** | Helmet | +DEF, +HP, +EVA, +VIT | Drop, Shop, Craft |
| 💍 **Trang Sức** | Accessory | +STR/DEX/VIT/MAG | **Craft only** (không drop) |

> **Lưu ý:** Trang Sức **không drop** từ quái hay dungeon — chỉ có thể craft hoặc mua từ chợ người chơi.

## Quản Lý Trang Bị

```
/inventory list          ← Xem túi đồ (ID từng món)
/equip <id>              ← Mặc đồ (hiển thị thay đổi ATK/DEF/HP)
/unequip <slot>          ← Tháo đồ (hiển thị thay đổi)
/autoequip               ← Tự động mặc đồ có PR cao nhất
```

Khi `/equip` hoặc `/unequip`, bot sẽ hiển thị chênh lệch chỉ số, ví dụ:
```
⚔️ ATK: 245 (+38) | 🛡️ DEF: 120 (+12) | ❤️ HP: 1850 (+150)
```

## Power Rating của Item

Mỗi item có **PR riêng** tính từ tổng chỉ số:

```
PR = STR×3 + DEX×3 + MAG×3 + VIT×2 + ATK×2 + DEF×1.5 + HP×0.2 + EVA×2 + ACC×2
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

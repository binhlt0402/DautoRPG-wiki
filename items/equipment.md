# Loại Trang Bị

Có **5 slot** trang bị, mỗi slot ảnh hưởng đến chỉ số theo cách khác nhau.

## Các Slot

| Slot | Main Stat | Sub Stats | Nguồn |
|---|---|---|---|
| ⚔️ **Vũ Khí** | ★ **ATK** (cố định) | Random từ 7 stats | Drop, Shop, Craft |
| 🗡️ **Tay Phụ** | ★ Theo loại phụ (xem bên dưới) | Random theo loại | Drop, Craft |
| 🛡️ **Giáp** | ★ **DEF** (cố định) | Random từ 7 stats | Drop, Shop, Craft |
| 🪖 **Mũ** | ★ **DEF** (cố định) | Random từ 6 stats | Drop, Shop, Craft |
| 💍 **Trang Sức** | ★ **Random** (hoặc chọn khi craft) | Random từ 9 stats | **Craft only** (không drop) |

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

## Sub Stats Pool theo Loại Đồ

Sub stats được roll **ngẫu nhiên từ pool** riêng của từng loại — không phải tất cả stats đều có thể xuất hiện trên mọi đồ:

| Loại đồ | Sub stats có thể roll |
|---|---|
| ⚔️ Vũ Khí | ATK, CRIT%, CRIT-DMG%, PEN%, STR, DEX, MAG |
| 🛡️ Giáp | DEF, HP, EVA%, RES%, CRIT-RES%, VIT, STR |
| 🪖 Mũ | DEF, HP, EVA%, RES%, CRIT-RES%, VIT |
| 💍 Trang Sức | Tất cả stats trong pool |
| 🛡️ Khiên | DEF, HP, RES%, VIT, STR, CRIT-RES% |
| 🗡️ Dao Phụ | ATK, CRIT%, CRIT-DMG%, PEN%, DEX |
| 🔮 Cầu Phép | MAG, RES%, MP/TRN, PEN%, CRIT-DMG% |

> **Lưu ý PEN%:** Chỉ có tác dụng với **Pháp Sư và các advanced class phép** (Archmage, Ice Mage, Fire Mage). Xem thêm ở phần [Hệ thống chiến đấu](../systems/combat.md).

## Phong Ấn (Enchant) — Stats có thể thêm

Phong ấn cho phép **thêm 1 điểm stat** vào đồ hiện có. Mỗi lần enchant roll ngẫu nhiên trong pool riêng theo loại:

| Loại đồ | Stats enchant được |
|---|---|
| ⚔️ Vũ Khí | STR, DEX, MAG, ATK, CRIT%, CRIT-DMG% |
| 🛡️ Giáp / 🪖 Mũ | DEF, HP, VIT, EVA%, RES% |
| 💍 Trang Sức | STR, DEX, VIT, MAG |
| 🗡️🛡️🔮 Tay Phụ (mọi loại) | DEF, HP, ATK, MAG, VIT, RES%, CRIT%, CRIT-DMG% |

Xem chi tiết về tỷ lệ thành công và chi phí tại [Phong Ấn](enchanting.md).

## Vũ Khí 2 Tay [2H]

Vũ khí có thể là **1 tay (1H)** hoặc **2 tay (2H)**:

- **40% vũ khí drop** từ explore/dungeon là 2H
- **2H stat cao hơn 1H ×1.4** (main stat + sub stats đều được nhân)
- Trang bị 2H → **tự động tháo tay phụ**
- Đang dùng 2H → **không thể trang bị tay phụ**

> 2H phù hợp khi không có offhand tốt. Ngược lại 1H + offhand cho tổng stat cao hơn nếu offhand rarity cao.

## Slot Tay Phụ (Offhand)

Slot tay phụ có **3 loại**, mỗi loại có main stat và yêu cầu khác nhau:

| Loại | Main Stat | Yêu cầu | Sub Stats |
|---|---|---|---|
| 🛡️ **Khiên (Shield)** | ★ DEF | STR ≥ ngưỡng | def, hp, resist, vit, str, critResist |
| 🗡️ **Dao Phụ (Dagger)** | ★ DEX | DEX ≥ ngưỡng | atk, crit, critDmg, pen, dex |
| 🔮 **Cầu Phép (Orb)** | ★ MAG | MAG ≥ ngưỡng | mag, resist, mpRegen, pen, critDmg |

**Ngưỡng stat** theo cấp đồ (giống giáp):

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

**Nguồn:** Drop từ explore/dungeon (random loại) hoặc craft (chọn loại qua recipe).  
Recipe ID format: `shield_<rarity>_oh<lv>`, `dagger_<rarity>_oh<lv>`, `orb_<rarity>_oh<lv>`.

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
/unequip <slot>          ← Tháo đồ — slot: weapon, offhand, armor, helmet, accessory
/autoequip               ← Tự động mặc đồ có PR cao nhất (tự xử lý 2H vs 1H+offhand)
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

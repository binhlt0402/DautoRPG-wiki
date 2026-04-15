# Chỉ Số Quái

Tất cả quái trong game đều được scale theo cấp độ khi xuất hiện.

**Công thức scale:**
```
HP / ATK / DEF_thực = base × (1 + (enemy_level - 1) × 0.05) × zone_mult
EXP                 = base × (1 + (enemy_level - 1) × 0.10) × zone_mult
```

---

## Quái Explore (theo Zone)

Mỗi zone có 4 loại quái riêng biệt. Chỉ số dưới đây là **base** (level 1, zone_mult = 1.0).

### 🌲 Rừng Xanh — Lv 1–5 (×1.0)

| Tên | HP | ATK | DEF | EXP | Gold |
|---|---|---|---|---|---|
| Green Slime | 90 | 5 | 0 | 15 | 3 |
| Forest Rabbit | 70 | 6 | 0 | 12 | 2 |
| Wild Boar | 130 | 7 | 1 | 22 | 5 |
| Imp | 100 | 8 | 1 | 20 | 4 |

### 🌾 Đồng Bằng — Lv 3–8 (×1.1)

| Tên | HP | ATK | DEF | EXP | Gold |
|---|---|---|---|---|---|
| Goblin | 180 | 10 | 2 | 30 | 8 |
| Bandit | 200 | 11 | 2 | 35 | 12 |
| Stray Dog | 160 | 12 | 1 | 28 | 6 |
| Evil Scarecrow | 220 | 9 | 3 | 32 | 7 |

### ⛏️ Hang Động — Lv 6–12 (×1.3)

| Tên | HP | ATK | DEF | EXP | Gold |
|---|---|---|---|---|---|
| Giant Bat | 300 | 14 | 3 | 50 | 10 |
| Skeleton | 280 | 15 | 3 | 55 | 11 |
| Cave Spider | 260 | 16 | 2 | 52 | 9 |
| Stone Golem | 380 | 12 | 6 | 60 | 13 |

### ⛰️ Núi Tuyết — Lv 10–18 (×1.5)

| Tên | HP | ATK | DEF | EXP | Gold |
|---|---|---|---|---|---|
| Snow Wolf | 450 | 19 | 4 | 75 | 16 |
| Yeti | 550 | 20 | 5 | 90 | 20 |
| Mountain Troll | 620 | 18 | 7 | 85 | 18 |
| Stone Eagle | 400 | 22 | 3 | 80 | 15 |

### 🏜️ Sa Mạc — Lv 15–25 (×1.8)

| Tên | HP | ATK | DEF | EXP | Gold |
|---|---|---|---|---|---|
| Giant Scorpion | 700 | 24 | 6 | 110 | 25 |
| Sand Worm | 800 | 22 | 7 | 120 | 22 |
| Mummy | 650 | 26 | 5 | 115 | 28 |
| Sand Wraith | 580 | 28 | 4 | 105 | 24 |

### 🌋 Núi Lửa — Lv 22–32 (×2.2)

| Tên | HP | ATK | DEF | EXP | Gold |
|---|---|---|---|---|---|
| Fire Salamander | 950 | 32 | 8 | 160 | 38 |
| Lava Golem | 1100 | 28 | 12 | 170 | 40 |
| Fire Drake | 900 | 36 | 7 | 180 | 45 |
| Inferno Fiend | 850 | 34 | 6 | 155 | 35 |

### 🌑 Vực Tối — Lv 30–42 (×2.8)

| Tên | HP | ATK | DEF | RES | EXP | Gold |
|---|---|---|---|---|---|---|
| Dark Phantom | 1300 | 42 | 9 | 10% | 230 | 55 |
| Cursed Knight | 1500 | 38 | 12 | — | 240 | 58 |
| Shadow Demon | 1200 | 45 | 8 | 15% | 220 | 52 |
| Void Crawler | 1100 | 40 | 10 | — | 210 | 50 |

### 🏛️ Thánh Địa — Lv 40–55 (×3.2)

| Tên | HP | ATK | DEF | RES | EXP | Gold |
|---|---|---|---|---|---|---|
| Holy Guardian | 2000 | 50 | 16 | — | 320 | 80 |
| Fallen Angel | 1800 | 55 | 13 | 10% | 340 | 85 |
| Sacred Beast | 2200 | 48 | 17 | — | 330 | 78 |
| Divine Sentinel | 1900 | 52 | 15 | — | 310 | 75 |

### 🌀 Hư Không — Lv 52–65 (×3.8)

| Tên | HP | ATK | DEF | RES | EXP | Gold |
|---|---|---|---|---|---|---|
| Void Phantom | 2500 | 62 | 18 | 15% | 430 | 110 |
| Dimension Stalker | 2300 | 65 | 16 | — | 450 | 115 |
| Chaos Fragment | 2100 | 68 | 14 | 20% | 420 | 105 |
| Reality Shredder | 2700 | 60 | 20 | — | 440 | 108 |

### 💠 Cõi Hỗn Nguồn — Lv 62–75 (×4.4)

| Tên | HP | ATK | DEF | RES | EXP | Gold |
|---|---|---|---|---|---|---|
| Chaos Titan | 3200 | 76 | 22 | — | 560 | 145 |
| Entropy Beast | 2900 | 80 | 19 | 15% | 580 | 150 |
| Doom Servant | 2800 | 78 | 20 | — | 550 | 140 |
| Chaos Spawn | 3100 | 74 | 23 | — | 570 | 148 |

### 🌤️ Thiên Đường — Lv 72–80 (×5.0)

| Tên | HP | ATK | DEF | RES | EXP | Gold |
|---|---|---|---|---|---|---|
| Dark Seraph | 3800 | 88 | 26 | — | 680 | 175 |
| Heaven Guard | 4200 | 84 | 30 | — | 700 | 180 |
| Divine Construct | 4000 | 86 | 28 | — | 690 | 178 |
| Fallen God | 3600 | 92 | 24 | 20% | 720 | 190 |

---

## Mini Boss (Dungeon lượt 10)

Mini Boss xuất hiện ở lượt 10 trong Dungeon, kèm 1 quái thường.

| Tên | HP | ATK | DEF | Skill | CD/Chance | ×DMG | Ghi chú |
|---|---|---|---|---|---|---|---|
| Elite Goblin | 960 | 20 | 5 | Đột Kích | 35% | ×1.6 | |
| Alpha Wolf | 1080 | 23 | 6 | Cắn Xé | 30% | ×1.3 | Bleed 2 lượt |
| Orc Champion | 1320 | 26 | 8 | Bổ Búa | 30% | ×1.8 | |
| Dark Sorcerer | 900 | 31 | 4 | Ma Thuật Tối | 35% | ×1.4 | Phép, xuyên giáp, RES 20% |
| Bone Colossus | 1680 | 24 | 9 | Nghiền Nát | 25% | ×2.0 | |

---

## Boss (Dungeon lượt 20)

Boss xuất hiện ở lượt 20, kèm 2 quái thường. Skill dùng cooldown (CD), không phải % chance.

| Tên | HP | ATK | DEF | Skill | CD | ×DMG | Ghi chú |
|---|---|---|---|---|---|---|---|
| Dragon Lord | 3000 | 44 | 14 | Thở Lửa | 3 | ×2.0 | Xuyên giáp |
| Demon King | 2700 | 50 | 12 | Hút Máu | 3 | ×1.7 | Lifesteal 50%, RES 15% |
| Ancient Golem | 3600 | 38 | 18 | Đập Đất | 4 | ×2.0 | Stun |
| Shadow Titan | 2880 | 48 | 15 | Bóng Tối | 3 | ×1.5 | Xuyên giáp, Bleed 2 lượt |

> **Lưu ý:** Tất cả Boss và Mini Boss cũng được scale theo `tier_scaleMult` của Dungeon tier đang chơi.

# Lịch Sử Cập Nhật

---

## v0.9.9 — 2026-04-16 · Targeted Accessory Craft Recipes

- **88 công thức trang sức mới** — chọn main stat cụ thể khi craft thay vì random
- 8 main stat có thể chọn: `ATK, CRIT%, CDMG%, EVA%, PEN%, RES%, HP, MP/TRN`
- ID pattern: `{rarity}_c{level}_{stat}` — ví dụ: `epic_c20_crit`, `ancient_c40_pen`
- Chi phí bằng với công thức generic cùng tier/rarity; công thức generic vẫn giữ nguyên

---

## v0.9.8 — 2026-04-16 · Gear Stat Rework + Reroll System

### Hệ Thống Stat Mới
- Mỗi trang bị có **1 main stat cố định** (★) + **sub stats ngẫu nhiên** (·)
- Main stat theo slot: Vũ Khí → **ATK** | Giáp/Mũ → **DEF** | Trang Sức → **random**
- **10 stats** có thể xuất hiện: `HP, DEF, ATK, CRIT%, CDMG%, EVA%, PEN%, RES%, CRIT-RES%, MP/TRN`
- Số sub stats theo rarity: Common 0 | Magic 1 | Rare 2 | Epic 3 | Ancient 3

### Lệnh Mới
- `/reroll <id>` — Reroll từng dòng sub stat bằng nút bấm (main stat cố định, tốn vàng + nguyên liệu)

### Cơ Chế
- Stat `MP/TRN` từ trang bị cộng vào MP regen cuối mỗi lượt chiến đấu
- Chi phí reroll tăng theo levelReq của đồ

---

## v0.9.7 — 2026-04-16 · Class Rework

- 🗡️ **Thích Khách**: Crit Rate DEX×0.25% hard cap 60% | CDMG hard cap 300% | EVA DEX×0.3% cap 65%
- 🔮 **Pháp Sư**: Crit hard cap 40% | MAG Penetration giảm Resist kẻ địch (`min(50%, MAG×0.5%)`) | Mana Shield 40% absorb
- ⚔️ **Chiến Binh**: Passive "Trụ Cột" — ATK +0.5% maxHP | DEF stack khi bị đánh (+5% giảm ST × tối đa 3 stack) | Giáp Nặng +10% Resist

---

## v0.9.6 — 2026-04-16 · Core Stats Rework

- DEF Thích Khách / Pháp Sư bỏ STR×0.25 scaling (Chiến Binh vẫn giữ STR×0.40)
- Crit Rate công thức mới: `baseDEX×0.18% + equipDEX×0.08% + gear CRIT%`

---

## v0.9.5 — 2026-04-16 · Explore Heal + Thích Khách Passive

- Explore hồi đầy HP/MP ngay khi bắt đầu session
- Thích Khách passive: **Phản Công** → **Sát Thương Chí Mạng** (+50% Crit DMG flat, không tính DR)

---

## v0.9.1 — 2026-04-14 · Lệnh /dummy

- Thêm `/dummy [target] [turns]` — tấn công nộm tập để đo DPS thực tế
- 5 loại nộm mục tiêu:
  - 🎯 **Thường** — DEF 0, Resist 0%
  - 🛡️ **Giáp Dày** — DEF 500, Resist 0%
  - 🔮 **Kháng Phép** — DEF 0, Resist 75% (cap)
  - 💠 **Boss T7** — DEF 215, Resist 15%
  - 🌤️ **Boss T8** — DEF 270, Resist 20%
- Ephemeral — chỉ người dùng thấy, không ảnh hưởng nhân vật (HP/MP khôi phục sau test)

---

## v0.9 — 2026-04-14 · Rebalance Tổng Thể + Đồ Lv35

### Nội Dung Mới
- Thêm tier trang bị mới: 🟠 **Epic Lv35**
  - Tên: **Kiếm Hư Vô / Giáp Hư Vô / Mũ Hư Vô / Bùa Hư Vô**
  - Drop từ Dungeon T7 (💠 Cõi Bóng Tối)
  - Craft được với: `3x 🌀 Tinh Chất Hư Vô + 5x 🐉 Xương Rồng + 8x 👑 Tinh Linh Cổ`
  - Trang sức Lv35 tốn ít hơn: `2x + 4x + 6x`

### Cân Bằng Quái Vật
- Tăng ATK base tất cả quái **~25%**, HP **~20%**
- Thêm `scaleMult` cho từng vùng Explore (Rừng Xanh 1.0 → Thiên Đường 5.0)
  - Trước đây quái Explore không có hệ số nhân → gần như không gây sát thương
  - Giờ quái từ zone Mountain trở lên có thể gây nguy hiểm thực sự

### Cân Bằng Dungeon
| Tier | scaleMult cũ | scaleMult mới | Ghi chú |
|---|---|---|---|
| T7 💠 | 3.0 | **3.8** | Endgame Lv40 (PR 7000) ~32% win rate |
| T8 🌤️ | 2.8 | **4.0** | Lv55/PR10000 ~46% win rate |
| T1–T6 | không đổi | — | Scalemult giữ nguyên |

> T1–T4 đã giảm scaleMult từ v0.8 để bù phần ATK base tăng — net khó hơn ~7-10%.

### Cơ Chế
- Crit rate >100% không còn bị cap (crit mọi đòn)
- Chết trong dungeon mất **5% vàng** hiện có

---

## v0.8 — 2026-03-20 · Crit & Resist System

### Nội Dung Mới
- Thêm chỉ số trang bị: **Crit Rate, Crit DMG, Magic Resist**
- Hiển thị Crit/EVA/Resist trên `/status` và `/stats`

### Cân Bằng
- Một số mini-boss và boss có Resist (Dark Sorcerer, Demon King...)
- Enemy evasion tăng nhẹ theo gap level với player

---

## v0.7 — 2026-03-10 · Armor Types & Crafting Overhaul

### Nội Dung Mới
- **3 loại giáp**: 🗡️ Giáp Nặng (Heavy), 🌬️ Giáp Nhẹ (Light), 🔮 Áo Phép (Robe)
  - Mỗi loại yêu cầu stat khác nhau để mặc
  - EVA cap: Heavy 5% / Light 80% / Robe 40%
- **Trang sức** chỉ craft được, không drop
- `/craft break` — rã 1 nguyên liệu cấp cao → 3 cấp thấp
- `/craft combine` — ghép 3 nguyên liệu cấp thấp → 1 cấp cao

---

## v0.6 — 2026-02-28 · Explore Zones & Multi-Slot

- Thêm 11 vùng Explore từ Rừng Xanh (Lv1) đến Thiên Đường (Lv72+)
- 3 slot nhân vật — mỗi tài khoản có thể có 3 nhân vật
- Dungeon 8 tier
- Hệ thống Rương (chest) dùng chung giữa các slot

---

## v0.5 — 2026-02-10 · Khởi Đầu

- 3 class: ⚔️ Chiến Binh, 🗡️ Thích Khách, 🔮 Pháp Sư
- Auto-battle turn-based
- Hệ thống EXP/Gold/Level
- Trang bị 4 slot: Vũ Khí, Giáp, Mũ, Trang Sức
- 5 độ hiếm: Common → Magic → Rare → Epic → Ancient
- Phong Ấn (Enchant) trang bị lên tới +5

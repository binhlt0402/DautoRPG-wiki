# Phong Ấn (Enchant)

Tăng chỉ số ngẫu nhiên cho trang bị, tối đa **+5 lần**.

## Cách Dùng

```
/enchant <id>    ← ID từ /inventory list hoặc /chest list
```

Cũng có thể phong ấn trực tiếp trên **Dashboard web** (mục Phong Ấn).

## Tỷ Lệ Thành Công

| Lần phong ấn | Tỷ lệ |
|---|---|
| +0 → +1 | 100% |
| +1 → +2 | 100% |
| +2 → +3 | 100% |
| +3 → +4 | 80% |
| +4 → +5 | 60% |

> ⚠️ Thất bại ở lần +4 hoặc +5 sẽ **mất nguyên liệu** nhưng đồ giữ nguyên mức hiện tại.

## Stat Được Tăng

Mỗi lần phong ấn tăng ngẫu nhiên **1 stat** đang có trên đồ (ưu tiên stat hiện có, không tạo stat mới).

| Loại đồ | Stat có thể tăng |
|---|---|
| ⚔️ Vũ Khí | STR, DEX, MAG, ATK, **Crit**, **CritDMG** |
| 🛡️ Giáp | DEF, HP, VIT, EVA, **Resist** |
| 🪖 Mũ | DEF, HP, VIT, EVA, **Resist** |
| 💍 Trang Sức | STR, DEX, VIT, MAG |

> **Lưu ý:** `ACC` đã được loại bỏ khỏi pool phong ấn vũ khí. Thay vào đó vũ khí có thể nhận **Crit Rate** và **Crit DMG**.

## Lượng Tăng Mỗi Lần

| Rarity | Tăng mỗi lần |
|---|---|
| ⚪ Common | +1 |
| 🔵 Magic | +1–2 |
| 🟡 Rare | +2–3 |
| 🟠 Epic | +3–5 |
| 🔴 Ancient | +4–7 |

## Chi Phí Nguyên Liệu

### Epic (ví dụ)

| Lần | Nguyên liệu |
|---|---|
| 0→1 | ❤️×1 💠×1 |
| 1→2 | ❤️×2 |
| 2→3 | ❤️×2 ⚡×1 |
| 3→4 | ⚡×2 |
| 4→5 | ⚡×2 👑×1 |

### Ancient

| Lần | Nguyên liệu |
|---|---|
| 0→1 | ❤️×2 👑×1 |
| 1→2 | ❤️×3 ⚡×1 |
| 2→3 | ⚡×2 👑×2 |
| 3→4 | 👑×3 ⚡×2 |
| 4→5 | 👑×5 🌑×1 |

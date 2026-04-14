# Chỉ Số & Power Rating

## 4 Chỉ Số Cơ Bản

| Stat | Ảnh hưởng |
|---|---|
| **STR** — Sức Mạnh | ATK (Chiến Binh), maxHP, DEF; yêu cầu Giáp Nặng |
| **DEX** — Nhanh Nhẹn | ATK (Thích Khách), EVA, Crit Rate; yêu cầu Giáp Nhẹ |
| **VIT** — Sinh Lực | maxHP (+10 HP/điểm) |
| **MAG** — Phép Thuật | ATK (Pháp Sư), maxMP (+5 MP/điểm); yêu cầu Áo Phép |

## Công Thức Chỉ Số

```
maxHP   = 100 + VIT×10 + STR×3 + bonus_equip.hp
maxMP   = 20  + MAG×5
ATK     = 5   + MainStat_hiệu_quả×3 + bonus_equip.atk
DEF     = 3   + Level + floor(STR×0.40) + bonus_equip.def   ← Chiến Binh
DEF     = 3   + Level + bonus_equip.def                     ← các class khác
```

## Tránh Né (Evasion)

EVA cap phụ thuộc vào **loại giáp đang mặc**, không còn phụ thuộc class:

| Loại Giáp | EVA Cap |
|---|---|
| 🗡️ Giáp Nặng (Heavy) | 5% |
| 🌬️ Giáp Nhẹ (Light) | 80% |
| 🔮 Áo Phép (Robe) | 40% |
| *(không mặc giáp)* | Cap theo class |

```
EVA = min(EVA_cap, BaseEVA_class + max(0, Lv_nhân_vật - Lv_quái)×2% + DEX×0.5% + bonus_equip.eva%)
```

## Crit Rate & Crit DMG

```
Crit Rate = min(50%, DEX×0.3% + bonus_equip.crit%)
Crit DMG  = 150% + bonus_equip.critDmg%
```

Crit chỉ áp dụng cho đòn thường và skill vật lý. Khi crit, sát thương nhân với hệ số Crit DMG.

## Kháng Phép (Resist)

```
Sát thương phép thực nhận = Sát_thương × (1 - resist%)
```

- `resist` đến từ trang bị (stat bonus)
- Cap tối đa: **75%**
- Chỉ giảm sát thương từ skill phép (magical), không giảm đòn thường vật lý

## Power Rating (PR)

Chỉ số đánh giá sức mạnh tổng hợp của nhân vật:

```
PR = Level×20 + ATK×3 + DEF×2 + maxHP÷5
```

Xem PR trong `/status` hoặc trên Dashboard.

## Phân Bổ Điểm

Mỗi lần lên cấp nhận **5 điểm chỉ số**.

```
/alloc auto              ← Tự động vào main stat
/alloc manual            ← Chuyển sang thủ công
/alloc stat <stat> [n]   ← Bỏ n điểm vào stat
/respec                  ← Hoàn trả tất cả (Lv×200g)
```

Cả hai chức năng này đều có thể thực hiện trực tiếp trên **Dashboard web**.

# Chỉ Số & Power Rating

## 4 Chỉ Số Cơ Bản

| Stat | Ảnh hưởng |
|---|---|
| **STR** — Sức Mạnh | ATK (Chiến Binh), maxHP, DEF |
| **DEX** — Nhanh Nhẹn | ATK (Thích Khách), EVA, ACC |
| **VIT** — Sinh Lực | maxHP (+10 HP/điểm) |
| **MAG** — Phép Thuật | ATK (Pháp Sư), maxMP (+5 MP/điểm) |

## Công Thức Chỉ Số

```
maxHP   = 100 + VIT×10 + STR×3 + bonus_equip.hp
maxMP   = 20  + MAG×5
ATK     = 5   + MainStat_hiệu_quả×3 + bonus_equip.atk
DEF     = 3   + Level + floor(STR×0.25) + bonus_equip.def
```

## Tránh Né (Evasion)

```
EVA = BaseEVA_class + max(0, Lv_nhân_vật - Lv_quái)×2% + DEX_hiệu_quả×0.5% + bonus_equip.eva%
```

| Class | Base EVA | Cap EVA |
|---|---|---|
| Chiến Binh | 5% | 49% |
| Thích Khách | 20% | 59% |
| Pháp Sư | 10% | 49% |

## Độ Chính Xác (Accuracy)

Accuracy làm giảm EVA hiệu quả của đối thủ:

```
ACC = DEX_hiệu_quả×1% + bonus_equip.acc%
```

## Power Rating (PR)

Chỉ số đánh giá sức mạnh tổng hợp của nhân vật, dùng làm tham khảo cho Dungeon:

```
PR = Level×20 + ATK×3 + DEF×2 + maxHP÷5
```

Xem PR trong `/status`.

## Phân Bổ Điểm

Mỗi lần lên cấp nhận **5 điểm chỉ số**.

```
/alloc auto              ← Tự động vào main stat
/alloc manual            ← Chuyển sang thủ công
/alloc stat <stat> [n]   ← Bỏ n điểm vào stat
/respec                  ← Hoàn trả tất cả (Lv×200g)
```

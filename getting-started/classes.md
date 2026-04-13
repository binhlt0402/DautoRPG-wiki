# Chọn Class

Có 3 class, mỗi class có **main stat** khác nhau ảnh hưởng đến sát thương tấn công.

## So Sánh

| Class | Main Stat | Ưu điểm | Phong cách |
|---|---|---|---|
| ⚔️ **Chiến Binh** | STR | HP cao, DEF tốt | Tank, bền bỉ |
| 🗡️ **Thích Khách** | DEX | Tránh né cao nhất (EVA tới 59%) | Dodge, burst |
| 🔮 **Pháp Sư** | MAG | Sát thương phép cao | Nuker |

## Chi Tiết Từng Class

### ⚔️ Chiến Binh

* **Main stat:** STR
* **Base EVA:** 5%
* **Điểm mạnh:** maxHP cao nhất (STR cộng cả vào HP lẫn ATK), DEF scale tốt theo STR
* **Phù hợp:** Người mới, muốn chơi an toàn

**Công thức ATK:** `5 + STR_hiệu_quả × 3 + bonus_equip`

---

### 🗡️ Thích Khách

* **Main stat:** DEX
* **Base EVA:** 20% — cao nhất trong 3 class, cap 59%
* **Điểm mạnh:** Tránh né cực cao, DEX tăng cả EVA lẫn ACC
* **Phù hợp:** Người thích dodge build, PvP

**Công thức ATK:** `5 + DEX_hiệu_quả × 3 + bonus_equip`

---

### 🔮 Pháp Sư

* **Main stat:** MAG
* **Base EVA:** 10%
* **Điểm mạnh:** MP cao (MAG × 5), sát thương ổn định
* **Phù hợp:** Người muốn dùng skill phép

**Công thức ATK:** `5 + MAG_hiệu_quả × 3 + bonus_equip`

---

## Phân Bổ Điểm

Mỗi lần lên cấp nhận **5 điểm chỉ số**. Có 2 chế độ:

```
/alloc auto    ← Tự động vào main stat
/alloc manual  ← Phân bổ thủ công
/alloc stat str 5  ← Bỏ 5 điểm vào STR
```

Muốn reset lại dùng `/respec` (tốn vàng = cấp × 200g).

## Skills

Mỗi class có skill Active, AOE (Lv10), và Passive. Pháp Sư còn có Extra skill ở Lv10. Xem đầy đủ trong [trang Skills](../systems/skills.md).

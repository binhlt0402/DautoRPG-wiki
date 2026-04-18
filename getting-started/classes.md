# Chọn Class

Có 3 class, mỗi class có **main stat** khác nhau ảnh hưởng đến sát thương tấn công.

## So Sánh

| Class | Main Stat | Ưu điểm | Phong cách |
|---|---|---|---|
| ⚔️ **Chiến Binh** | STR | HP cao, DEF mạnh nhất, giảm sát thương vật lý | Tank, bền bỉ |
| 🗡️ **Thích Khách** | DEX | Crit rate cao, EVA cực cao qua Giáp Nhẹ | Dodge, crit burst |
| 🔮 **Pháp Sư** | MAG | Sát thương phép cao, Mana Shield | Nuker, shield |

## Chi Tiết Từng Class

### ⚔️ Chiến Binh

* **Main stat:** STR
* **DEF bonus:** `floor(STR × 0.40)` — cao nhất trong 3 class
* **Passive:** Giảm 20% sát thương vật lý nhận vào
* **Giáp phù hợp:** 🗡️ Giáp Nặng (Heavy) — yêu cầu STR, EVA cap 5%
* **Phù hợp:** Người mới, muốn chơi an toàn, tank dungeon

**Công thức ATK:** `5 + STR_hiệu_quả × 3 + bonus_equip`

---

### 🗡️ Thích Khách

* **Main stat:** DEX
* **Crit Rate:** `DEX × 0.3%` (cộng thêm từ equip, cap 50%)
* **Giáp phù hợp:** 🌬️ Giáp Nhẹ (Light) — yêu cầu DEX, EVA cap **80%**
* **Phù hợp:** Người thích dodge build, crit burst, PvP

**Công thức ATK:** `5 + DEX_hiệu_quả × 3 + bonus_equip`

---

### 🔮 Pháp Sư

* **Main stat:** MAG
* **Base EVA:** 10%
* **Passive — Mana Shield:** Hấp thụ **30% sát thương** phép nhận vào thành chi phí MP (thay vì mất HP). Hồi 5 MP/lượt.
* **Giáp phù hợp:** 🔮 Áo Phép (Robe) — yêu cầu MAG, EVA cap 40%
* **Phù hợp:** Sát thương cao, có lớp giáp MP bổ sung

**Công thức ATK:** `5 + MAG_hiệu_quả × 3 + bonus_equip`

---

## Loại Giáp & Yêu Cầu Chỉ Số

Giáp và mũ chia 3 loại, mỗi loại yêu cầu stat khác nhau để mặc:

| Loại | Yêu cầu | EVA Cap | Stat pool chính |
|---|---|---|---|
| 🗡️ **Giáp Nặng** | STR ≥ ngưỡng | 5% | DEF, HP cao |
| 🌬️ **Giáp Nhẹ** | DEX ≥ ngưỡng | 80% | EVA, DEX |
| 🔮 **Áo Phép** | MAG ≥ ngưỡng | 40% | Resist, MAG |

Ngưỡng stat theo cấp đồ: Lv5=5, Lv10=8, Lv15=12, Lv20=18, Lv25=25, Lv30=32, Lv40=45.

## Phân Bổ Điểm

Mỗi lần lên cấp nhận **5 điểm chỉ số**. Có 2 chế độ:

```
/alloc auto    ← Tự động vào main stat
/alloc manual  ← Phân bổ thủ công
/alloc stat str 5  ← Bỏ 5 điểm vào STR
```

Muốn reset lại dùng `/respec` (tốn vàng = cấp × 200g). Cũng có thể làm trên **Dashboard web**.

## Skills

Mỗi class có skill Active, AOE (Lv10), và Passive. Pháp Sư còn có Extra skill ở Lv10. Xem đầy đủ trong [trang Skills](../systems/skills.md).

---

## Advanced Classes (Lv20+)

Đạt Lv20, **Chiến Binh** có thể nâng cấp lên 1 trong 3 nhánh — quyết định vĩnh viễn:

| Class | Passive | Cơ chế |
|---|---|---|
| ⚔️ **Berserker** | +15% ATK / −30% DEF | Rage: càng ít HP → ATK càng mạnh (tối đa +40%) |
| 🛡️ **Paladin** | −30% ATK / +30% DEF | Thorn: phản DEF×20% mỗi đòn nhận |
| 👑 **Royal Knight** | +7% ATK / +7% DEF | Bỏ qua stat req + bonus per item đeo |

Dùng `/advance <class>` để chọn. Xem đầy đủ trong [Advanced Classes](../systems/advanced-classes.md).

**Skill Slot System:** Sau khi advance, nhân vật có pool 7 skill (3 cũ + 4 mới). Chọn bất kỳ 4 để dùng trong battle — có thể swap tự do qua `/skill equip/unequip`.

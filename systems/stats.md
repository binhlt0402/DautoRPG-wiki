# Chỉ Số & Công Thức Tính Toán

## 4 Chỉ Số Cơ Bản

| Stat | Tên | Ảnh hưởng chính |
|---|---|---|
| **STR** | Sức Mạnh | ATK (Chiến Binh & nhánh), maxHP, DEF (Warrior family); req Giáp Nặng |
| **DEX** | Nhanh Nhẹn | ATK (Thích Khách & nhánh), EVA, Crit Rate, ACC; req Giáp Nhẹ |
| **VIT** | Sinh Lực | maxHP (+10 HP/điểm) |
| **MAG** | Phép Thuật | ATK (Pháp Sư & nhánh), maxMP (+5 MP/điểm), Pen; req Áo Phép |

**Main stat theo class:**

| Class | Main Stat |
|---|---|
| Chiến Binh / Berserker / Paladin / Royal Knight | STR |
| Thích Khách / Shadow / Samurai / Archer | DEX |
| Pháp Sư / Archmage / Ice Mage / Fire Mage | MAG |

---

## Công Thức Chỉ Số

### HP & MP

```
maxHP = 100 + (VIT + eq.vit)×10 + (STR + eq.str)×3 + eq.hp
maxMP = 20  + (MAG + eq.mag)×5
```

### Tấn Công (ATK)

```
ATK = 5 + MainStat_tổng×3 + eq.atk
```

**Warrior family bonus** (Chiến Binh, Berserker, Paladin, Royal Knight):
```
ATK += floor(maxHP × 0.005)      ← +0.5% maxHP vào ATK
```

### Phòng Thủ (DEF)

```
DEF = 3 + Level + eq.def
```

**Warrior family bonus:**
```
DEF += floor((STR + eq.str) × 0.40)   ← +40% STR tổng vào DEF
```

**Passive class modifier** (áp dụng sau khi tính base):
```
ATK  = round(ATK  × (1 + atkPct_class))
DEF  = round(DEF  × (1 + defPct_class))
```

| Advanced Class | ATK Modifier | DEF Modifier |
|---|---|---|
| Berserker | +15% | −30% |
| Paladin | −30% | +30% |
| Royal Knight | +7% | +7% |
| Archmage | +7% | — |
| Ice Mage | −10% | — |
| Fire Mage | +15% | −10% |
| Shadow | — | — |
| Samurai | — | — |
| Archer | +7% | — |

**Royal Knight thêm:** +2% ATK & DEF cho mỗi slot trang bị đang mặc (tối đa 5 slot = +10%).

### Kháng Phép (Resist)

```
Resist = eq.resist%
```
- Warrior family mặc **Giáp Nặng (Heavy)**: thêm +10% Resist
- **Cap tối đa: 75%**
- Chỉ giảm sát thương phép (magical skill), không giảm đòn thường

---

## Tránh Né (Evasion)

**Base EVA theo class:**

| Class | Base EVA |
|---|---|
| Chiến Binh / Berserker / Paladin | 5% |
| Royal Knight | 8% |
| Thích Khách / Archer | 20% |
| Samurai | 15% |
| Shadow | 25% |
| Pháp Sư / Archmage / Ice Mage / Fire Mage | 10% |

**Công thức:**

Rogue classes (Thích Khách, Shadow, Samurai, Archer):
```
EVA = min(65%, BaseEVA + max(0, myLv - enemyLv)×2% + DEX_tổng×0.3% + eq.eva%)
```

Các class khác:
```
EVA = min(ArmorCap, BaseEVA + max(0, myLv - enemyLv)×2% + DEX_tổng×0.5% + eq.eva%)
```

Mage classes (Pháp Sư, Archmage, Ice Mage, Fire Mage): cap thêm tối đa **40%** dù mặc giáp gì.

**Cap theo loại giáp (non-rogue):**

| Loại Giáp | EVA Cap |
|---|---|
| 🪖 Giáp Nặng (Heavy) | 5% |
| 🥷 Giáp Nhẹ (Light) | 80% |
| 🔮 Áo Phép (Robe) | 40% |
| *(không mặc)* | 49% |

**Shadow riêng:** EVA cao nhất trong rogue, +10% EVA bonus thêm từ passive.  
**Samurai riêng:** EVA hard-capped tại **40%**, EVA dư chuyển thành cơ chế **Parry** (20% chance, gây 150% dmg phản đòn).

---

## Độ Chính Xác (Accuracy)

```
ACC = (DEX + eq.dex) × 1%
```

ACC giảm EVA hiệu dụng của kẻ địch khi bị tấn công. Không có cap.

---

## Crit Rate & Crit DMG

### Crit Rate

Rogue classes:
```
Crit Rate = min(80%, (DEX + eq.dex) × 0.25% + eq.crit%)
```

Các class khác:
```
Crit Rate = min(40%, baseDEX × 0.18% + eq.dex × 0.08% + eq.crit%)
```

> `baseDEX` = DEX thuần từ stat points (không tính eq). `eq.dex` hiệu quả thấp hơn ~55%.

### Crit DMG Multiplier

```
Crit DMG = 150% + bonus%
bonus     = eq.critDmg% / 100
```

**Soft cap:** Phần bonus vượt quá **+100%** (tức tổng vượt 250%) chỉ tính 50% hiệu quả.

```
Nếu bonus ≤ 100%: effectiveBonus = bonus
Nếu bonus > 100%: effectiveBonus = 100% + (bonus - 100%) × 50%
```

**Samurai:** +150% Crit DMG thêm từ passive (cộng vào bonus trước soft cap).  
**Archer:** +50% Crit DMG từ passive.

### Crit trong PvP

Để giảm one-shot, Crit DMG trong PvP bị giảm:
```
pvpCritMult = 1 + (critDmgMult - 1) × 0.7
```

Ví dụ: critDmgMult = 3.0 → pvpCritMult = 1 + 2.0×0.7 = 2.4 (thay vì 3.0).

---

## Xuyên Giáp Phép (Magic Penetration)

```
Pen = min(50%, (MAG + eq.mag) × 0.5% + eq.pen%)
```

Khi tấn công phép, Pen giảm resist của kẻ địch:
```
effectiveResist = max(0%, resist - Pen)
```

---

## Công Thức Sát Thương (PvE)

Sát thương vật lý nhận vào được tính theo công thức **ATK-relative**:

```
reduction = min(90%, DEF / (DEF + incomingDMG × 0.3))
actualDMG = max(1, floor(incomingDMG × (1 - reduction)))
```

Bảng ví dụ (ATK = 200):

| DEF | Reduction | Thực nhận |
|---|---|---|
| 0 | 0% | 200 |
| 60 | 50% | 100 |
| 120 | 67% | 66 |
| 240 | 80% | 40 |
| 600 | 90% *(cap)* | 20 |

> DEF càng cao, cần DEF nhiều hơn để giảm thêm mỗi %. Cap 90% khi DEF ≈ ATK × 3.

---

## Công Thức Sát Thương (PvP)

PvP áp thêm hệ số scale ×0.2 lên raw ATK trước khi crit:

```
rawDMG  = ATK_hiệu_dụng × 0.2       (trước crit)
critDMG = rawDMG × pvpCritMult       (nếu crit)
```

**Kháng giáp PvP** dùng cùng công thức ATK-relative như PvE (với `incomingDMG` là rawDMG đã scale).

**Thorn (Paladin):** phản sát khi nhận đòn:
```
thornDMG = floor(DEF_Paladin × reflectPct × 0.2)
reflectPct = 0.60   (phản 60% DEF)
```

---

## EXP Lên Cấp

```
EXP cần = floor(50 × Level ^ 2.5)
```

| Level | EXP cần |
|---|---|
| 1 | 50 |
| 5 | 2.795 |
| 10 | 15.811 |
| 20 | 89.442 |
| 50 | 883.883 |

Mỗi lần lên cấp nhận **5 điểm chỉ số**.

---

## Power Rating (PR)

```
PR = Level×20 + ATK×3 + DEF×2 + maxHP÷5
```

Dùng để đánh giá sức mạnh tổng hợp, hiển thị trong `/status` và Dashboard.

---

## Phân Bổ Điểm

```
/alloc auto              ← Tự động vào main stat mỗi cấp
/alloc manual            ← Chuyển sang thủ công
/alloc stat <stat> [n]   ← Bỏ n điểm vào stat
/respec                  ← Hoàn trả tất cả (Lv×200g)
```

Cũng có thể phân bổ trực tiếp trên **Dashboard web**.

---

## Debuff Tháp Thử Thách

Sau mỗi 10 tầng vượt qua trong `/tower`, nhân vật nhận 1 debuff ngẫu nhiên:

| Debuff | Hiệu ứng |
|---|---|
| ⚔️ ATK | −22% ATK |
| 🛡️ DEF | −22% DEF |
| 👟 EVA | −25% EVA |
| 🎯 CRIT | −25% Crit Rate |
| 💥 CRIT DMG | −20% Crit DMG |

Debuff tích lũy — mỗi 10 tầng thêm 1 debuff mới. Hồi HP/MP đầy mỗi 5 tầng.

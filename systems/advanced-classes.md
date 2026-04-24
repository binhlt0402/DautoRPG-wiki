# Advanced Classes

Advanced class là bước nâng cấp từ base class ở **Lv20+**, mở khoá cơ chế và skill mới. Việc advance **không thể hoàn tác** (có thể đổi sang class cùng dòng bằng `/reclass`).

## Cách Advance

```
/advance <class>
```

Yêu cầu: Lv20+, đang là base class tương ứng.

Sau khi advance:
- Class đổi vĩnh viễn, passive stat modifier áp dụng ngay
- Skill pool nhận thêm 4 skill mới (giữ lại skill cũ của base class)
- 4 skill mới tự động lắp vào slot — có thể swap bất cứ lúc nào

---

## Hệ Thống Skill Slot

| Lệnh | Tác dụng |
|---|---|
| `/skill list` | Xem toàn bộ pool + 4 skill đang lắp (✅) |
| `/skill equip <id>` | Lắp skill (tối đa 4 slot) |
| `/skill unequip <id>` | Tháo skill |

Base class có 3–4 skill trong pool. Sau advance thêm 4 skill → chọn 4 trong pool để dùng.

---

## Tổng Quan 9 Advanced Classes

| Class | Base | ATK | DEF | Phong cách |
|---|---|---|---|---|
| ⚔️ Berserker | Chiến Binh | +15% | −30% | Burst, rage scale |
| 🛡️ Paladin | Chiến Binh | −30% | +30% | Tank, phản đòn |
| 👑 Royal Knight | Chiến Binh | +7% | +7% | Linh hoạt, full-item |
| 🌑 Shadow | Thích Khách | — | — | Poison, EVA, Giả Chết |
| ⚔️ Samurai | Thích Khách | — | — | Crit DMG, Parry |
| 🏹 Archer | Thích Khách | +7% | — | Mark, Crit DMG |
| 🌟 Archmage | Pháp Sư | +7% | — | MP synergy, Echo |
| ❄️ Ice Mage | Pháp Sư | −10% | — | CC, Freeze combo |
| 🔥 Fire Mage | Pháp Sư | +15% | −10% | Burn, phản lửa |

---

## ⚔️ Berserker

> *"Càng gần chết càng nguy hiểm."*

**Yêu cầu:** Chiến Binh Lv20+

### Passive Vĩnh Viễn

| | |
|---|---|
| ATK tổng | **+15%** |
| DEF tổng | **−30%** |
| **Rage Scale** | HP dưới 100% → ATK tăng dần, tối đa **+40% khi HP ≤ 40%** |

**Công thức Rage:**
```
t        = clamp((1.0 − hp/maxHp) / (1.0 − 0.40), 0, 1)
rageBonus = t × 0.40
```
> Ví dụ: HP 40% → rageBonus = +40% ATK thêm trên nền ATK sau passive.

### Skill Pool

| ID | Tên | Role | Mô tả | CD | MP |
|---|---|---|---|---|---|
| `berserker_lifesteal` | Hút Máu | ⚔️ active | 150% ATK, hồi HP = 30% dmg gây ra | 3 | 18 |
| `berserker_rampage` | Cơn Điên | 🌀 aoe | 110% ATK tất cả địch, xuyên 20% DEF | 4 | 25 |
| `berserker_rage` | Rage | ✨ buff | Immune hiệu ứng + **+50% ATK** 2 lượt; sau đó −20% ATK/−20% DEF 2 lượt | 7 | 30 |
| `berserker_sacrifice` | Chém Tuyệt Vọng | ⚔️ active | Tốn 15% HP hiện tại, **260% ATK xuyên giáp hoàn toàn** | 5 | 10 |
| `berserker_war_cry` | War Cry | 👥 party | **ATK toàn party +20%** trong 2 lượt | 5 | 30 |

**Pool đầy đủ (8 skill):** `warrior_slash`, `warrior_cleave`, `warrior_pillar` + 4 Berserker + 1 Group

### Mẹo Chơi

- Giữ HP thấp → Rage Scale cộng thêm ATK đáng kể
- **Rage** buff + Rage Scale → burst cực mạnh 2 lượt, cẩn thận debuff sau đó
- **Chém Tuyệt Vọng** mạnh nhất khi HP thấp (tốn HP nhưng không tự giết)
- **Hút Máu** giúp tự hồi để duy trì Rage Scale mà không chết

---

## 🛡️ Paladin

> *"Phòng thủ là vũ khí tốt nhất."*

**Yêu cầu:** Chiến Binh Lv20+

### Passive Vĩnh Viễn

| | |
|---|---|
| ATK tổng | **−30%** |
| DEF tổng | **+30%** |
| **Thorn** | Mỗi đòn nhận → phản `floor(DEF × 60%)` cho kẻ tấn công |
| **Thánh Kích bonus** | Khi dùng Thánh Kích: cộng thêm `floor(DEF × 15%)` vào sát thương |

**Công thức Thorn:**
```
reflect = floor(effectiveDEF × 0.60)
```
> `effectiveDEF` bao gồm buff từ Thánh Thuẫn nếu đang active.

### Skill Pool

| ID | Tên | Role | Mô tả | CD | MP |
|---|---|---|---|---|---|
| `paladin_strike` | Thánh Kích | ⚔️ active | 140% ATK phép xuyên giáp + **+15% DEF** vào dmg, hồi 25% dmg | 3 | 20 |
| `paladin_judgment` | Phán Quyết | 🌀 aoe | 100% ATK phép tất cả, địch trúng nhận **+30% dmg** lượt tiếp | 4 | 30 |
| `paladin_heal` | Thánh Hộ | 💚 heal | Hồi **30% maxHP**, xóa toàn bộ debuff | 5 | 25 |
| `paladin_shield` | Thánh Thuẫn | ✨ buff | Block **2 đòn** tiếp theo, **+25% DEF** thêm 3 lượt | 6 | 20 |
| `paladin_holy_banner` | Holy Banner | 👥 party | Hồi **20% maxHP cho toàn party** | 4 | 40 |

**Pool đầy đủ (8 skill):** `warrior_slash`, `warrior_cleave`, `warrior_pillar` + 4 Paladin + 1 Group

### Mẹo Chơi

- **DEF càng cao → Thorn càng mạnh** — đầu tư DEF trang bị cao nhất
- **Thánh Thuẫn** tăng DEF buff → Thorn reflect tăng theo trong 3 lượt
- **Phán Quyết** đánh dấu tất cả địch → lượt sau chúng nhận +30% dmg (kể cả Thorn)
- **Thánh Kích** xuyên giáp + thêm DEF vào dmg → Paladin có ATK thật cao từ DEF

---

## 👑 Royal Knight

> *"Không giới hạn, không ràng buộc."*

**Yêu cầu:** Chiến Binh Lv20+

### Passive Vĩnh Viễn

| | |
|---|---|
| ATK tổng | **+7%** |
| DEF tổng | **+7%** |
| **Bypass Stat Req** | Bỏ qua toàn bộ yêu cầu STR/DEX/MAG khi mặc armor, helmet, offhand |
| **Item Bonus** | Mỗi slot đang đeo item → **+2% ATK+DEF** (tối đa +14% khi 7/7 slot đầy) |

**Công thức Item Bonus:**
```
bonus   = số_slot_đang_đeo × 0.02
ATK/DEF = round(ATK/DEF × (1 + bonus))
```

### Skill Pool

| ID | Tên | Role | Mô tả | CD | MP |
|---|---|---|---|---|---|
| `royalknight_slash` | Kiếm Hiệp Sĩ | ⚔️ active | 170% ATK, xuyên **25% DEF** địch | 3 | 18 |
| `royalknight_charge` | Đột Kích | 🌀 aoe | 90% ATK tất cả, **35% stun** mỗi mục tiêu 1 lượt | 4 | 25 |
| `royalknight_aura` | Hào Quang | ✨ buff | Giảm **25% dmg nhận** + **+10% ATK** trong 3 lượt | 5 | 20 |
| `royalknight_prestige` | Phong Hầu | 🌙 passive | Mỗi crit → **+1% ATK/+1% DEF** trong battle (tối đa 10 stack) | — | — |
| `royalknight_royal_shield` | Royal Shield | 👥 party | Taunt kéo toàn bộ địch + **DEF party +30%** trong 1 lượt | 6 | 20 |

**Pool đầy đủ (8 skill):** `warrior_slash`, `warrior_cleave`, `warrior_pillar` + 4 Royal Knight + 1 Group

### Mẹo Chơi

- **Bypass stat req** cho phép mặc Giáp Nhẹ (EVA cao) dù thiếu DEX
- Đeo đủ 7 slot → +14% ATK+DEF thêm — ưu tiên lấp đầy các slot
- **Phong Hầu** + crit rate cao → snowball mạnh cuối dungeon/tháp

---

## 🌑 Shadow

> *"Không nhìn thấy, không né được."*

**Yêu cầu:** Thích Khách Lv20+

### Passive Vĩnh Viễn

| | |
|---|---|
| ATK / DEF | Không thay đổi |
| **EVA bonus** | **+10% EVA** thêm vào tổng |
| **On-hit Poison** | Mỗi đòn thường → gây độc: **15% ATK/lượt × 2 lượt** |
| **Crit DMG** | Cố định **150%** (không scale từ trang bị — nhưng EVA cao + Ẩn Thân guaranteed crit bù lại) |

### Skill Pool

| ID | Tên | Role | Mô tả | CD | MP |
|---|---|---|---|---|---|
| `shadow_venom_strike` | Đòn Độc | ⚔️ active | 120% ATK + độc **15% ATK/lượt × 2 lượt** | 3 | 18 |
| `shadow_vanish` | Ẩn Thân | ✨ buff | **Né toàn bộ 1 lượt** + đòn kế tiếp guaranteed crit | 5 | 20 |
| `shadow_nightfall` | Màn Đêm | 🌀 aoe | 85% ATK tất cả, **40% cơ hội** gây độc mỗi mục tiêu | 4 | 25 |
| `shadow_feign_death` | Giả Chết | 🌙 passive | **1 lần/trận:** khi nhận đòn chí tử → sống sót với **10% HP** | — | — |
| `shadow_smoke_screen` | Smoke Screen | 👥 party | **EVA toàn party +25%** trong 2 lượt | 5 | 25 |

**Pool đầy đủ (8 skill):** `rogue_stab`, `rogue_storm`, `rogue_crit` + 4 Shadow + 1 Group

### Mẹo Chơi

- Đòn thường luôn kèm poison → đánh nhanh chóng tích lũy DoT
- **Ẩn Thân** tránh 1 lượt + guaranteed crit lượt sau → combo với **Đòn Độc**
- **Giả Chết** là phao cứu sinh — đặc biệt hữu ích trong tháp hoặc dungeon boss
- EVA cao + on-hit poison → bắt địch hao mòn qua từng lượt

---

## ⚔️ Samurai

> *"Lưỡi kiếm không cần né — nó chặn."*

**Yêu cầu:** Thích Khách Lv20+

### Passive Vĩnh Viễn

| | |
|---|---|
| ATK / DEF | Không thay đổi |
| **EVA Cap** | Hard cap tại **40%** (EVA dư → Parry) |
| **Crit DMG bonus** | **+150%** thêm vào Crit DMG multiplier |
| **Parry** | 20% chance né → phản **150% ATK** ngay lập tức |

**Công thức Crit DMG Samurai:**
```
critDmgMult = 1.5 (base) + eq.critDmg/100 (soft-capped) + 1.5 (Samurai bonus)
```
> Ví dụ không có eq: 1.5 + 1.5 = 3.0 → crit gây 300% ATK.

### Skill Pool

| ID | Tên | Role | Mô tả | CD | MP |
|---|---|---|---|---|---|
| `samurai_iaijutsu` | Iaijutsu | ⚔️ active | **220% ATK**, xuyên 30% DEF địch | 4 | 20 |
| `samurai_blade_dance` | Vũ Điệu Đao | 🌀 aoe | **100% ATK** tất cả địch | 4 | 25 |
| `samurai_serenity` | Bình Tâm | 💚 heal | Hồi **20% maxHP** | 5 | 20 |
| `samurai_divine_blade` | Kiếm Thần | ⚔️ active | **190% ATK xuyên giáp hoàn toàn** | 3 | 20 |
| `samurai_hao_khi` | Hào Khí | 👥 party | **300% ATK xuyên giáp**; ×2 nếu đồng đội HP ≤30% hoặc đã ngã | 5 | 0 |

**Pool đầy đủ (8 skill):** `rogue_stab`, `rogue_storm`, `rogue_crit` + 4 Samurai + 1 Group

### Mẹo Chơi

- Crit DMG cực cao → đầu tư trang bị Crit Rate để crit thường xuyên hơn
- **Parry** 20% chance phản 150% ATK → synergy tốt với dungeon/tháp multi-turn
- **Kiếm Thần** xuyên giáp hoàn toàn → dùng vào boss có DEF cao
- **Bình Tâm** giúp tự hồi HP giữa trận dài

---

## 🏹 Archer

> *"Một mũi tên, một đời người."*

**Yêu cầu:** Thích Khách Lv20+

### Passive Vĩnh Viễn

| | |
|---|---|
| ATK tổng | **+7%** |
| **Crit DMG bonus** | **+50%** thêm vào Crit DMG multiplier |
| **Mark Streak** | Đánh dấu mục tiêu ≥2 lượt liên tiếp → **+30% dmg** |

**Cơ chế Mark:** Dùng `archer_mark_shot` để bắt đầu/duy trì chuỗi. Sau 2+ lượt liên tiếp đánh cùng mục tiêu → `archer_aimed_shot` và mũi tên đánh dấu gây +30% dmg.

### Skill Pool

| ID | Tên | Role | Mô tả | CD | MP |
|---|---|---|---|---|---|
| `archer_mark_shot` | Mũi Tên Đánh Dấu | ⚔️ active | 140% ATK + bắt đầu/duy trì **chuỗi đánh dấu** mục tiêu | 3 | 15 |
| `archer_multishot` | Mưa Tên | 🌀 aoe | 90% ATK tất cả địch | 4 | 20 |
| `archer_eagle_eye` | Mắt Đại Bàng | ✨ buff | **+25% Crit Rate** + xuyên **20% DEF** trong 3 lượt | 5 | 20 |
| `archer_aimed_shot` | Nhắm Bắn | ⚔️ active | 190% ATK, **+30% dmg** nếu mục tiêu bị đánh ≥2 lượt liên tiếp | 5 | 25 |
| `archer_volley` | Volley | 👥 party | **150% AoE** tất cả địch + đánh dấu toàn bộ (hit kế +30%) | 4 | 30 |

**Pool đầy đủ (8 skill):** `rogue_stab`, `rogue_storm`, `rogue_crit` + 4 Archer + 1 Group

### Mẹo Chơi

- **Mark Shot** → **Aimed Shot** → repeat: combo cốt lõi, giữ chuỗi để +30% dmg
- **Mắt Đại Bàng** +25% Crit Rate → bùng nổ dmg 3 lượt, kết hợp ngay lúc mark đã setup
- DEX cao → Crit Rate cao + EVA cao → tránh đòn trong khi duy trì mark

---

## 🌟 Archmage

> *"Mana là sức mạnh."*

**Yêu cầu:** Pháp Sư Lv20+

### Passive Vĩnh Viễn

| | |
|---|---|
| ATK tổng | **+7%** |
| **maxMP bonus** | **+15% maxMP** thêm |
| **MP Regen** | Tự hồi **2% maxMP/lượt** |
| **Arcane Infusion** | Khi MP > 80% maxMP → đòn thường kích hoạt thêm **+30% ATK phép xuyên giáp** |

### Skill Pool

| ID | Tên | Role | Mô tả | CD | MP |
|---|---|---|---|---|---|
| `archmage_arcane_blast` | Arcane Blast | ⚔️ active | 190% ATK phép xuyên giáp; **+30% dmg** nếu MP > 60% | 3 | 25 |
| `archmage_arcane_storm` | Arcane Storm | 🌀 aoe | **130% ATK phép xuyên giáp** tất cả | 4 | 30 |
| `archmage_mana_surge` | Mana Surge | ✨ buff | **+25% ATK** + hồi **8 MP/lượt** trong 3 lượt | 5 | 15 |
| `archmage_spell_echo` | Spell Echo | 🌙 passive | **30% chance** sau mỗi skill → bắn thêm **70% ATK phép xuyên giáp** | — | — |
| `archmage_mana_transfer` | Mana Transfer | 👥 party | Hồi **40% maxMP cho toàn party** | 5 | 50 |

**Pool đầy đủ (9 skill):** `mage_fireball`, `mage_firestorm`, `mage_chain`, `mage_shield` + 4 Archmage + 1 Group

### Mẹo Chơi

- Giữ MP cao → **Arcane Infusion** + **Arcane Blast** bonus dmg liên tục
- **Mana Surge** +8 MP/lượt → giúp duy trì MP ngưỡng 60–80% cho cả 2 bonus
- **Spell Echo** 30% chance → mỗi skill có thể gây thêm 70% ATK phép miễn phí

---

## ❄️ Ice Mage

> *"Đông cứng, rồi vỡ vụn."*

**Yêu cầu:** Pháp Sư Lv20+

### Passive Vĩnh Viễn

| | |
|---|---|
| ATK tổng | **−10%** |
| **CC Dmg Bonus** | **+30% dmg** lên địch đang bị CC (đóng băng, stun) |

### Skill Pool

| ID | Tên | Role | Mô tả | CD | MP |
|---|---|---|---|---|---|
| `icemage_frost_bolt` | Frost Bolt | ⚔️ active | 160% ATK phép xuyên giáp, **40% đóng băng** địch 1 lượt | 3 | 20 |
| `icemage_blizzard` | Blizzard | 🌀 aoe | 95% ATK phép xuyên giáp tất cả, **30% đóng băng** mỗi mục tiêu | 4 | 30 |
| `icemage_ice_shield` | Ice Shield | ✨ buff | Block **3 đòn** + **+20% Resist** trong 3 lượt | 6 | 20 |
| `icemage_shatter` | Shatter | ⚔️ active | **230% ATK phép** xuyên giáp; **+40% dmg** nếu địch đang bị đóng băng | 5 | 30 |
| `icemage_ice_prison` | Ice Prison | 👥 party | **Đóng băng toàn bộ địch** 1 lượt + DEF party +15% trong 2 lượt | 6 | 45 |

**Pool đầy đủ (9 skill):** `mage_fireball`, `mage_firestorm`, `mage_chain`, `mage_shield` + 4 Ice Mage + 1 Group

### Mẹo Chơi

- **Frost Bolt** đóng băng → **Shatter** 230% × 1.40 = **322% ATK phép** thực tế
- **CC Dmg Bonus** +30% áp lên cả đòn thường khi địch bị frozen
- **Ice Shield** block 3 đòn → rất hữu ích trong dungeon boss hoặc tháp cao tầng
- ATK thấp hơn → bù bằng combo freeze + Shatter burst

---

## 🔥 Fire Mage

> *"Không có gì cản được lửa."*

**Yêu cầu:** Pháp Sư Lv20+

### Passive Vĩnh Viễn

| | |
|---|---|
| ATK tổng | **+15%** |
| DEF tổng | **−10%** |
| **On-hit Burn** | Mỗi đòn thường → gây burn: **10% ATK/lượt × 2 lượt** |

### Skill Pool

| ID | Tên | Role | Mô tả | CD | MP |
|---|---|---|---|---|---|
| `firemage_meteor` | Meteor | 🌀 aoe | 140% ATK phép xuyên giáp tất cả + **burn 10% ATK/lượt × 2t** | 4 | 30 |
| `firemage_inferno` | Inferno | ⚔️ active | **260% ATK phép**, bỏ qua hoàn toàn Resist | 5 | 35 |
| `firemage_fire_armor` | Fire Armor | ✨ buff | **+15% ATK** 3 lượt; đòn nhận → phản **floor(ATK địch × 15%)** burn | 5 | 20 |
| `firemage_combustion` | Combustion | 🌙 passive | Burn tick gây thêm **+50% dmg** | — | — |
| `firemage_hellfire` | Hellfire | 👥 party | **150% AoE phép xuyên giáp** + burn 15% ATK/lượt × 2t toàn bộ địch | 5 | 40 |

**Pool đầy đủ (9 skill):** `mage_fireball`, `mage_firestorm`, `mage_chain`, `mage_shield` + 4 Fire Mage + 1 Group

### Mẹo Chơi

- **Combustion** passive → mọi burn tick (on-hit + skill) đều gây +50% thêm
- **Fire Armor** phản burn ATK địch → địch tự burn chính mình khi tấn công
- **Inferno** bỏ qua Resist hoàn toàn → dùng vào boss có Resist cao
- **Meteor** AoE + burn → clear multi-enemy nhanh trong dungeon

---

## So Sánh Theo Dòng Class

### Chiến Binh

| | ⚔️ Berserker | 🛡️ Paladin | 👑 Royal Knight |
|---|---|---|---|
| **ATK** | +15% + rage | −30% | +7% + item |
| **DEF** | −30% | +30% + thorn | +7% + item |
| **Phong cách** | Burst liều lĩnh | Tank phản đòn | Linh hoạt đa dạng |
| **Build đề xuất** | STR + VIT, giữ HP thấp | STR, DEF trang bị tối đa | Bất kỳ, đeo đủ 7 slot |

### Thích Khách

| | 🌑 Shadow | ⚔️ Samurai | 🏹 Archer |
|---|---|---|---|
| **ATK** | — | — | +7% |
| **EVA** | +10% bonus | Hard cap 40% → Parry | Bình thường |
| **Crit DMG** | Cố định 150% | +150% bonus | +50% bonus |
| **Đặc trưng** | Poison + Giả Chết | Parry + Crit burst | Mark streak |
| **Build đề xuất** | DEX, EVA tối đa | DEX, Crit Rate cao | DEX, duy trì mark |

### Pháp Sư

| | 🌟 Archmage | ❄️ Ice Mage | 🔥 Fire Mage |
|---|---|---|---|
| **ATK** | +7% | −10% | +15% |
| **Đặc trưng** | MP synergy, Echo | Freeze + Shatter burst | Burn DoT + phản lửa |
| **Điểm mạnh** | Sustained dmg cao | Single-target burst | AoE + DEF bypass |
| **Build đề xuất** | MAG, giữ MP cao | MAG, kết hợp CC | MAG, ATK cao |

# Party & Group Content

## Tổng Quan

Party cho phép tối đa **4 người chơi** cùng Explore hoặc Dungeon. Khi có party, `/explore` và `/dungeon` tự động chuyển sang chế độ co-op.

---

## Tạo Party

```
/party create
```

- Bạn trở thành **leader**
- Party trống, chờ mời thành viên

---

## Mời Thành Viên

```
/party invite @user
```

- Gửi lời mời, người được mời có **5 phút** để chấp nhận
- Nếu đối phương bật **AutoAdd** → thêm ngay không cần xác nhận

```
/party accept        ← chấp nhận lời mời gần nhất
/party decline       ← từ chối lời mời gần nhất
```

---

## AutoAdd

```
/party autoadd toggle    ← bật/tắt
/party autoadd list      ← xem danh sách người bật
```

AutoAdd cho phép bất kỳ ai thêm bạn vào party mà không cần bạn chấp nhận. Hữu ích khi đội quen cần ghép nhanh.

---

## Quản Lý Party

| Lệnh | Ai dùng được | Mô tả |
|---|---|---|
| `/party status` | Mọi thành viên | Xem thông tin party |
| `/party kick @user` | Leader | Đuổi thành viên |
| `/party leave` | Mọi thành viên | Rời party |
| `/party disband` | Leader | Giải tán party |

Khi leader rời party → quyền leader tự động chuyển sang thành viên tham gia lâu nhất.

---

## Co-op Explore & Dungeon

Dùng `/explore` hoặc `/dungeon` khi đang trong party (≥ 2 người) để tự động bắt đầu co-op session.

- Tất cả thành viên phải **không đang trong session khác** và **không bất tỉnh**
- Mọi thành viên bị **khoá lệnh** trong suốt session

---

## Scaling Co-op

| Cơ chế | Mô tả |
|---|---|
| **Số địch** | Base + (số thành viên − 1), tối đa **6 địch/lượt** |
| **Boss HP** | × (1 + 0.3 × số địch thêm) |
| **EXP / Vàng** | Mỗi thành viên nhận **full** như solo |
| **Loot** | Mỗi thành viên roll **cá nhân** |
| **Bất tỉnh** | **5 phút** (solo: 10 phút) |
| **Fatigue (Explore)** | HP trừ dần mỗi lượt; thành viên ngã vẫn tiếp tục nếu còn người sống |

---

## Group Skills

Mỗi **advanced class** có 1 skill nhóm dành riêng cho co-op. Cần unlock và trang bị thủ công.

| Class | Skill | Hiệu ứng | CD / MP |
|---|---|---|---|
| ⚔️ Berserker | War Cry | ATK toàn party +20% trong 2 lượt | CD:5 MP:30 |
| 🛡️ Paladin | Holy Banner | Hồi 20% maxHP cho tất cả đồng đội | CD:4 MP:40 |
| 👑 Royal Knight | Royal Shield | Taunt kéo toàn bộ địch + DEF party +30% trong 1 lượt | CD:6 MP:20 |
| 🌑 Shadow | Smoke Screen | EVA toàn party +25% trong 2 lượt | CD:5 MP:25 |
| ⚔️ Samurai | Hào Khí | 300% ATK xuyên giáp; ×2 nếu đồng đội HP ≤30% hoặc đã ngã | CD:5 MP:0 |
| 🏹 Archer | Volley | 150% AoE + đánh dấu toàn bộ địch (hit kế +30%) | CD:4 MP:30 |
| 🌟 Archmage | Mana Transfer | Hồi 40% maxMP cho toàn party | CD:5 MP:50 |
| ❄️ Ice Mage | Ice Prison | Đóng băng toàn bộ địch 1 lượt + DEF party +15% trong 2 lượt | CD:6 MP:45 |
| 🔥 Fire Mage | Hellfire | 150% AoE phép xuyên giáp + burn 15% ATK/lượt × 2t toàn bộ địch | CD:5 MP:40 |

> Group skill được kích hoạt **đầu tiên** trong lượt của người chơi (trước Heal, AoE, và đòn thường).

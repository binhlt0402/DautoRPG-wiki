# Web Dashboard

DautoRPG có trang web dashboard cho phép quản lý nhân vật mà không cần gõ lệnh Discord.

## Truy Cập

1. Vào URL bot (ví dụ `http://localhost:3000`)
2. Đăng nhập bằng tài khoản Discord (OAuth2)
3. Dashboard hiển thị nhân vật đang active của bạn

## Các Chức Năng

### 📊 Chỉ Số Nhân Vật
- Xem toàn bộ stats: STR, DEX, VIT, MAG, ATK, DEF, MaxHP, MaxMP
- **Crit Rate, Crit DMG, EVA, Resist** — các chỉ số mới từ trang bị
- Thanh tiến trình EXP
- Power Rating, vàng, kills, thắng/thua PvP

### 🎯 Phân Bổ Điểm Chỉ Số
- Chọn stat và số điểm muốn bỏ vào (nếu còn điểm chưa dùng)
- Bật/tắt **chế độ tự động** (auto-alloc vào main stat)
- Nút **Respec** — hoàn trả tất cả điểm, tốn `Lv × 200g`

### 🎽 Trang Bị
- Xem 4 slot đang mặc (Vũ Khí, Giáp, Mũ, Trang Sức)
- Nút **Tháo** từng slot trực tiếp

### 🎒 Túi Đồ
- Bán hàng loạt theo độ hiếm (≤ Common / Magic / Rare / Epic)
- Mỗi item có nút: **Mặc** / **Cất vào Rương** / **Bán**

### 📦 Rương
- Xem đồ đang cất trong rương (dùng chung mọi slot nhân vật)
- Nút **Lấy ra** để chuyển vào túi nhân vật active

### 🧪 Nguyên Liệu
- Xem kho nguyên liệu của nhân vật active

### 📋 Nhiệm Vụ Hàng Ngày
- Xem tiến độ từng quest với thanh progress bar
- Hiển thị phần thưởng: EXP, vàng, nguyên liệu
- Reset lúc 00:00 UTC mỗi ngày

### 👹 Raid Boss
- Xem boss đang hoạt động: tên, HP, thời gian còn lại
- Danh sách người tham chiến và sát thương đóng góp
- Nút **Tấn Công** (cooldown 5 phút/lần)
- Nếu chưa có boss, tấn công sẽ tự triệu hồi boss mới

### 📜 Chiến Đấu Gần Nhất
- Xem kết quả trận đấu cuối: địch, thắng/thua, số lượt
- Mở rộng để xem log chi tiết từng lượt

### 🛒 Cửa Hàng
- Mua đồ Common từ shop (hiển thị rõ yêu cầu cấp / đủ vàng không)

### ⚒️ Chế Tạo
- Danh sách toàn bộ recipe
- Hiển thị nguyên liệu có / cần (đỏ = thiếu)
- Nút chế tạo bị khoá nếu không đủ điều kiện

### ✨ Phong Ấn
- Danh sách các vật phẩm trong túi chưa đạt phong ấn tối đa
- Bấm phong ấn trực tiếp

## Chức Năng Chưa Có Trên Web

Các tính năng cần real-time (WebSocket) chỉ dùng được qua lệnh Discord:

- `/explore` — khám phá vùng đất
- `/dungeon` — vào dungeon boss


# Danh Sách Lệnh

## Nhân Vật

| Lệnh | Mô tả |
|---|---|
| `/start <class> [tên]` | Tạo nhân vật (warrior / rogue / mage) — tối đa 3 slot |
| `/status` | Xem chỉ số, trang bị, EXP, vàng |
| `/stats @user` | Xem chỉ số nhân vật của người khác |
| `/alloc auto` | Tự động phân bổ điểm vào main stat |
| `/alloc manual` | Chuyển sang phân bổ thủ công |
| `/alloc stat <stat> [n]` | Bỏ n điểm vào STR/DEX/VIT/MAG |
| `/respec` | Hoàn trả toàn bộ điểm (Lv × 200g) |
| `/ranking` | Bảng xếp hạng top 10 |

## Advanced Class & Skill Slots

| Lệnh | Mô tả |
|---|---|
| `/advance <class>` | Nâng cấp class (Lv20+, không hoàn tác). Chiến Binh → Berserker / Paladin / Royal Knight |
| `/skill list` | Xem toàn bộ skill pool + skill đang lắp (✅ = active) |
| `/skill equip <id>` | Lắp skill vào slot chiến đấu (tối đa 4 cùng lúc) |
| `/skill unequip <id>` | Tháo skill ra khỏi slot |

## Character Slots

| Lệnh | Mô tả |
|---|---|
| `/slot list` | Xem 3 slot nhân vật (tên, class, lv, slot đang dùng) |
| `/slot switch <1–3>` | Chuyển sang nhân vật ở slot chỉ định (miễn phí) |
| `/slot delete <1–3>` | Xóa nhân vật ở slot không active (đồ trong rương giữ lại) |

## Party (Nhóm)

| Lệnh | Mô tả |
|---|---|
| `/party create` | Tạo party mới, bạn là leader (tối đa 4 người) |
| `/party invite @user` | Mời người chơi (hết hạn sau 5 phút; nếu họ bật AutoAdd thì thêm ngay) |
| `/party accept` | Chấp nhận lời mời gần nhất |
| `/party decline` | Từ chối lời mời gần nhất |
| `/party kick @user` | Đuổi thành viên khỏi party (chỉ leader) |
| `/party leave` | Rời party (quyền leader tự động chuyển sang người cũ nhất) |
| `/party disband` | Giải tán toàn bộ party (chỉ leader) |
| `/party status` | Xem thông tin party hiện tại |
| `/party autoadd toggle` | Bật/tắt chế độ tự động chấp nhận lời mời |
| `/party autoadd list` | Xem danh sách người đang bật AutoAdd |

## Chiến Đấu

| Lệnh | Mô tả |
|---|---|
| `/explore <zone> [turns]` | Phiêu lưu tự động (tối đa 100 lượt); tự động co-op nếu có party |
| `/dungeon [tier]` | Vào Dungeon tier 1–8 (20 lượt); tự động co-op nếu có party |
| `/log` | Xem chi tiết trận đấu cuối |
| `/pvp @user` | Thách đấu 1v1 |
| `/raid status` | Xem Raid Boss cộng đồng |
| `/raid attack` | Tấn công Raid Boss (cooldown 5 phút) |
| `/quest` | Xem nhiệm vụ hàng ngày |

## Trang Bị

| Lệnh | Mô tả |
|---|---|
| `/inventory list [page]` | Xem túi đồ |
| `/inventory sell <id\|all>` | Bán vật phẩm |
| `/equip <id>` | Mặc đồ (hiển thị thay đổi chỉ số) |
| `/unequip <slot>` | Tháo đồ — slot: weapon, offhand, armor, helmet, accessory |
| `/autoequip` | Tự động mặc đồ có PR cao nhất |
| `/enchant <id>` | Phong ấn trang bị (+stat ngẫu nhiên) |
| `/reroll <id>` | Reroll sub stat (main stat cố định, tốn vàng + nguyên liệu) |

## Shop & Craft

| Lệnh | Mô tả |
|---|---|
| `/shop list` | Xem đồ Common đang bán |
| `/shop buy <đồ>` | Mua trang bị Common |
| `/shop sell <rarity>` | Bán hàng loạt theo rarity |
| `/craft materials` | Xem kho nguyên liệu |
| `/craft list` | Xem công thức craft |
| `/craft make <id>` | Tổng hợp vật phẩm |
| `/craft break <mat> [qty]` | Rã 1 nguyên liệu cao → 3 thấp (200g/lần) |
| `/craft combine <mat> [qty]` | Ghép 3 nguyên liệu thấp → 1 cao (300g/lần) |

## Lưu Trữ & Giao Dịch

| Lệnh | Mô tả |
|---|---|
| `/chest list` | Xem rương đồ |
| `/chest deposit <id>` | Cất đồ vào rương |
| `/chest withdraw <id>` | Lấy đồ ra túi |
| `/gift @user <id>` | Tặng đồ cho người chơi khác |
| `/market browse [page]` | Xem chợ người chơi |
| `/market sell <id> <giá>` | Rao bán lên chợ |
| `/market buy <listing>` | Mua từ chợ |
| `/market cancel <listing>` | Hủy tin rao bán |

## Khác

| Lệnh | Mô tả |
|---|---|
| `/revive` | Tỉnh dậy ngay lập tức bằng vàng (bỏ qua thời gian bất tỉnh) |
| `/dummy [target] [turns]` | Tấn công nộm tập để đo DPS thực tế (không ảnh hưởng nhân vật) |
| `/help` | Xem tóm tắt lệnh trong Discord |

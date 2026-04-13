# Character Slots

Mỗi tài khoản Discord có tối đa **3 slot nhân vật**. Mỗi slot là một nhân vật độc lập với stats, inventory, và equipment riêng. **Rương (chest) dùng chung** giữa tất cả các slot.

## Lệnh

```
/slot list              ← Xem tất cả slot (tên, class, lv, slot đang active)
/slot switch <1–3>      ← Chuyển sang nhân vật khác (miễn phí, tức thì)
/slot delete <1–3>      ← Xóa nhân vật ở slot không active
```

## Tạo Nhân Vật Mới

```
/start <class> [tên]
```

Nếu đã có nhân vật, `/start` tạo thêm vào **slot trống tiếp theo**. Nhân vật mới **không tự kích hoạt** — dùng `/slot switch` để chuyển sang.

## Shared Chest (Rương Dùng Chung)

Đồ trong rương (`/chest deposit`) có thể truy cập từ **bất kỳ slot nào**. Khi `/chest withdraw`, đồ sẽ vào túi của nhân vật đang active.

| Riêng từng slot | Dùng chung |
|---|---|
| Inventory (túi đồ) | 📦 Rương (chest) |
| Equipment đang mặc | — |
| Vàng | — |
| Stats / EXP / Level | — |
| Nguyên liệu craft | — |

## Xóa Nhân Vật

- Chỉ xóa được slot **không phải active** — dùng `/slot switch` trước
- Đồ trong **túi** của nhân vật bị xóa mất theo
- Đồ trong **rương** được giữ lại (vì rương dùng chung)
- Vàng và nguyên liệu của slot đó mất theo nhân vật

> **Tip:** Cất đồ quý vào `/chest deposit` trước khi xóa nhân vật.

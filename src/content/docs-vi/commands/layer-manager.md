---
title: LayerManager — Quản Lý Tất Cả Lớp trong Một Bảng
description: Lệnh LayerManager mở một bảng liệt kê tất cả lớp trong bản vẽ, cho phép bạn thêm lớp và chỉnh sửa trực tiếp cho từng lớp trạng thái đóng băng, khóa, in, màu sắc, độ dày đường và kiểu đường.
group: layer
order: 1
---

# LayerManager

Lệnh `LayerManager` mở một bảng liệt kê tất cả lớp trong bản vẽ, với các cài đặt **Freeze** (đóng băng), **Lock** (khóa), **Plot** (in), **Màu sắc**, **Độ dày đường** và **Kiểu đường** có thể chỉnh sửa trực tiếp trong hàng. Đây là nơi trung tâm để thêm lớp mới và điều chỉnh cách các lớp hiện có hoạt động — các lệnh lớp khác ([LayerMakeCurrent](../layer-make-current/), [LayerMatch](../layer-match/), [LayerIsolate](../layer-isolate/), [LayerUnfreezeAll](../layer-unfreeze-all/)) mỗi lệnh thực hiện một việc cụ thể mà không cần mở bảng này.

## Mở Layer Manager

- Gõ `LayerManager` trong terminal, **hoặc**
- Nhấp nút **Layer Manager** trên bảng lớp.

Hộp thoại mở dưới dạng bảng nổi; không cần chọn gì trước.

## Bảng lớp

| Cột | Điều khiển gì |
|-----|------------------|
| Name | Tên lớp, hiển thị chỉ đọc trong bảng (đặt một lần, khi tạo) |
| Freeze | Ẩn các thực thể của lớp và loại chúng khỏi lựa chọn cho đến khi bỏ đóng băng |
| Lock | Ngăn chỉnh sửa các thực thể trên lớp, mà không ẩn chúng |
| Plot | Liệu các thực thể của lớp có được đưa vào khi in hoặc xuất PDF hay không |
| Color | Màu ACI của lớp — nhấp vào mẫu màu để mở bộ chọn màu |
| Lineweight | Độ dày đường của lớp — nhấp vào chip để mở bộ chọn độ dày |
| Linetype | Kiểu nét đứt của lớp — nhấp vào chip để mở bộ chọn kiểu đường |

Bật/tắt Freeze, Lock hoặc Plot có hiệu lực ngay lập tức — không có bước lưu riêng. Các thực thể được đặt thành **ByLayer** cho màu sắc, độ dày đường hoặc kiểu đường (giá trị mặc định) sẽ theo những gì bạn đặt ở đây; các thực thể có ghi đè riêng của chúng không bị ảnh hưởng.

## Thêm một lớp

1. Nhấp **+ Add Layer** ở cuối bảng.
2. Gõ tên và nhấn **Enter** để xác nhận, hoặc **Escape** để hủy.

Tên lớp có thể chứa chữ cái, số, khoảng trắng và `_`, `-`, `$`. Tên trống, đã được sử dụng, hoặc chứa ký tự khác sẽ bị từ chối với lỗi hiển thị ngay tại chỗ, và hàng vẫn mở để thử lại.

Lớp mới bắt đầu ở trạng thái **không đóng băng, không khóa, có thể in**, với màu 7 (trắng/đen), độ dày đường Default và kiểu đường Continuous — cùng các giá trị mặc định mà [Import](../import/) gán cho lớp `0` trong một bản vẽ trống.

## Những gì bạn không thể làm ở đây

Không có nút xóa — lớp không bao giờ bị xóa sau khi tạo, chỉ có thể đóng băng hoặc để không dùng. Bảng cũng không cho biết lớp nào là lớp *hiện tại*; điều đó được đặt qua menu thả xuống trên bảng lớp hoặc bằng [LayerMakeCurrent](../layer-make-current/), không phải từ hộp thoại này.

## Tham khảo phím tắt

| Phím | Hành động |
|------|-----------|
| `Enter` | Xác nhận tên của lớp mới (trong khi thêm) |
| `Escape` | Hủy việc thêm lớp, hoặc đóng hộp thoại |

## Các lệnh liên quan

| Lệnh | Chức năng |
|------|-----------|
| [LayerMakeCurrent](../layer-make-current/) | Đặt lớp hiện tại theo lớp của đối tượng được bấm |
| [LayerMatch](../layer-match/) | Gán lại các đối tượng được chọn về lớp của đối tượng nguồn |
| [LayerIsolate](../layer-isolate/) | Đóng băng tất cả các lớp trừ những lớp của đối tượng được chọn |
| [LayerUnfreezeAll](../layer-unfreeze-all/) | Bỏ đóng băng tất cả các lớp trong một bước |

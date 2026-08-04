---
title: New File — Bắt Đầu Bản Vẽ Trắng trong KulmanLab CAD
description: Lệnh New File xóa canvas và mở một bản vẽ trắng mới. Tên tệp đơn giản được tạo tự động và lưu vào bộ nhớ trình duyệt.
group: file
order: 2
---

# New File

Lệnh **New File** xóa canvas và bắt đầu một bản vẽ trắng mới. Tên tệp duy nhất được tạo tự động.

## Cách tạo tệp mới

Nhấp nút **New File** trên thanh công cụ (biểu tượng trang mới) trong bảng File. Canvas xóa ngay lập tức — không có lời nhắc hoặc hộp thoại xác nhận.

## Nội dung tệp mới

Tệp mới được tạo bắt đầu với:

- **Không có thực thể** nào trên canvas.
- **Một lớp mặc định** có tên `0` với màu trắng và kiểu đường `Continuous`.
- **Tên tệp được tạo**, `kulman.dxf` — hoặc `kulman (2).dxf`, `kulman (3).dxf`, … nếu tên đó đã được dùng.

Tệp được lưu vào bộ nhớ trình duyệt tự động, xuất hiện trong [File Manager](../file-manager/), và có thể được [đổi tên](../file-manager/#doi-ten-mot-tep) bất cứ lúc nào.

## Cảnh báo — công việc chưa lưu bị xóa

Nhấp **New File** xóa tất cả thực thể trên canvas hiện tại mà không có cảnh báo. Nếu bạn muốn giữ bản vẽ hiện tại, hãy [Export](../export/) nó trước.

## Khi nào dùng New File vs Import

| Tình huống | Hành động được đề xuất |
|-----------|----------------------|
| Bắt đầu bản vẽ từ đầu | **New File** |
| Mở tệp DXF hoặc JSON hiện có | [Import](../import/) |
| Sao chép bản vẽ để làm biến thể | [Export](../export/) tệp hiện tại, sau đó [Import](../import/) bản sao |

## Các lệnh liên quan

- [Import](../import/) — mở bản vẽ DXF hoặc JSON hiện có
- [Export](../export/) — tải bản vẽ trước khi bắt đầu mới
- [File Manager](../file-manager/) — khôi phục bản vẽ trước đó từ bộ nhớ trình duyệt

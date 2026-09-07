# Lịch sử cập nhật tài liệu

Chỉ ghi thay đổi có ý nghĩa. Ngày theo `YYYY-MM-DD`; thời gian chi tiết và tác giả kỹ thuật truy vết bằng lịch sử commit. Changelog không thay thế nhật ký quyết định hoặc bằng chứng thực nghiệm.

## 2026-09-07 — Khởi tạo kho tài liệu chính thức

**Nguồn thay đổi:** người dùng chỉ định `QuocKhanhLuong/ultrasound-dataset` và yêu cầu chủ động đẩy cập nhật source of truth/knowledge base.

**Nội dung trong đợt khởi tạo:**

- Tổng hợp bối cảnh, phạm vi đã xác nhận và 12 nhóm quyết định/điều kiện còn mở.
- Lưu bốn nhóm hướng theo nhu cầu–task–dạng dữ liệu để trao đổi phía Y, với hai nhánh thay thế ở nhóm siêu âm động.
- Lập bảng đối chiếu dataset và sổ nguồn; phân biệt nguồn đã kiểm tra mô tả, nguồn chỉ đọc được kết quả tìm kiếm và nguồn chờ xác minh. Không coi đây là systematic review hay audit các gói dữ liệu.
- Ghi mâu thuẫn thống kê giữa paper ThyroidXL và dataset card; ghi rõ Open Kidney được trang tác giả dẫn bằng preprint. Chưa dùng số liệu nguồn mâu thuẫn làm một giá trị đã được chuẩn hóa.
- Thêm phiếu trao đổi HMU, khung pilot/chất lượng/quản trị và vai trò ba tài liệu mẫu.
- Thêm hướng dẫn duy trì docs và `.gitignore` phòng commit nhầm tệp riêng tư.

**Không thay đổi:** chưa chọn cơ quan/task/format; chưa thu nhận dữ liệu, phê duyệt protocol, chạy benchmark hoặc viết code nghiên cứu. Không upload PDF/DOCX gốc, dữ liệu lâm sàng hoặc thông tin liên hệ trong mẫu thuyết minh.

**Bước tiếp theo:** lấy phản hồi thực tế từ phía Y qua `planning/HMU_ALIGNMENT.md`, rồi cập nhật source of truth và thu hẹp phương án khi có đủ căn cứ.

## Mẫu cập nhật sau

Ngày; nguồn thay đổi; nội dung mới/sửa; quyết định liên quan; giới hạn của bằng chứng; tài liệu bị ảnh hưởng; hành động tiếp theo. Chỉ ghi “đã đồng bộ” sau khi xác nhận được trạng thái Git từ công cụ.

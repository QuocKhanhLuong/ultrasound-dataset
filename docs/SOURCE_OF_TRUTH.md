# Source of truth — Trạng thái dự án

Cập nhật: **2026-09-07**. Nguồn xác nhận: các phát biểu trực tiếp của người dùng trong phiên khởi tạo dự án và chỉ định repo. Lịch sử: [DECISIONS](DECISIONS.md).

## 1. Đã xác nhận

| Nội dung | Trạng thái chính thức hiện tại |
|---|---|
| Dự án | Một paper dataset siêu âm y tế riêng |
| Nền tảng của người dùng | AI/Computer Vision |
| Cộng tác | Đang hợp tác với một số bạn bên Đại học Y Hà Nội; chưa xác nhận đối tác thu nhận lâm sàng cụ thể |
| Modality | Siêu âm |
| Mục tiêu | Tìm nhu cầu dữ liệu có ý nghĩa và khả thi; không chỉ tăng số ảnh |
| Nhu cầu trước mắt | Đề xuất các lựa chọn cơ quan–task–dạng dữ liệu để đối chiếu với khả năng hợp tác phía Y |
| Tài liệu mẫu | CariXray và DATE để tham khảo cách viết; `Thuyet minh De tai co so_ver2.docx` là mẫu thuyết minh dùng để nộp bên Đại học Y Hà Nội theo xác nhận của người dùng |
| Repo chính thức | `https://github.com/QuocKhanhLuong/ultrasound-dataset` |
| Quy tắc cập nhật | Chủ động đẩy thay đổi có ý nghĩa về source of truth và knowledge base thành docs vào repo trong các phiên làm việc |

**Không diễn giải hàng “cộng tác” thành một quan hệ hợp tác cấp trường hoặc cam kết cung cấp dữ liệu.**

## 2. Chưa xác nhận / chưa chốt

| Mã | Quyết định hoặc điều kiện | Trạng thái |
|---|---|---|
| U01 | Cơ quan, quy trình khám, bệnh lý, quần thể mục tiêu | Chưa chốt |
| U02 | Task chính và mục tiêu đánh giá | Chưa chốt |
| U03 | Ảnh tĩnh, nhiều mặt cắt, cine/video, 3D | Chưa chốt |
| U04 | Chế độ thu nhận: B-mode, Doppler, đàn hồi… | Chưa chốt |
| U05 | Dạng tệp có thể xuất và metadata/hiệu chuẩn còn giữ được | Chưa kiểm tra |
| U06 | Quyền tiếp cận dữ liệu hồi cứu hoặc thu tiền cứu | Chưa xác nhận |
| U07 | Cơ sở, máy, đầu dò, người quét | Chưa xác nhận |
| U08 | Nhãn sẵn có, chuyên gia đọc độc lập và chuẩn tham chiếu | Chưa xác nhận |
| U09 | Liên kết bệnh nhân–lần khám–tổn thương–ảnh/video–kết quả | Chưa xác nhận |
| U10 | Phê duyệt, đồng ý/miễn đồng ý phù hợp và điều kiện chia sẻ | Chưa xác nhận |
| U11 | Cỡ mẫu pilot và nghiên cứu chính thức, kinh phí, lịch thu | Chưa chốt; không lấy số frame làm cỡ mẫu bệnh nhân |
| U12 | Nơi nộp và hạn nộp paper dataset này | Chưa chốt trong phạm vi dự án này |

Chưa có cơ sở để ghi “đã có dataset”, “đa trung tâm”, “public dataset được phép phát hành”, “đã chạy benchmark” hoặc một cỡ mẫu thu nhận chính thức.

## 3. Phạm vi và giới hạn công việc

Khảo sát có dẫn nguồn; phân biệt ảnh/video, cơ quan, loại nhãn, metadata, nguồn thu nhận và truy cập. Phân tích độ rộng theo các trục độc lập. Chuẩn bị một số cấu hình để gặp phía Y; giữ điều kiện khả thi và gap ứng viên rõ ràng. Đề xuất pilot kiểm tra quy trình trước khi thu lớn.

Chưa thiết kế model mới, chưa viết code cho pipeline/huấn luyện. Không ép ghép với world model, VLA hoặc forensic. Không đặt mục tiêu chia một dataset thành nhiều paper. Không lấy nội dung khoa học, cỡ mẫu, ngân sách hoặc nhân sự của mẫu Word làm thông tin của nghiên cứu mới.

## 4. Các hướng đang được đề xuất, chưa được người dùng chọn

| Mã | Nhóm hướng | Lưu ý |
|---|---|---|
| O1 | Tổn thương khu trú: tuyến giáp **hoặc** vú | Chọn một phạm vi; không mặc định classification/segmentation cơ bản là tính mới |
| O2 | Đo hình thái thận | Cần một phép đo có nhu cầu và dữ liệu hiệu chuẩn phù hợp |
| O3 | Mặt cắt đủ điều kiện và đo lường sản khoa | Có nhánh ảnh tĩnh và nhánh video; chưa yêu cầu phải có video |
| O4A | Thông số chức năng tim từ video | Cần video và phương pháp đo tham chiếu |
| O4B | Dấu hiệu phổi theo clip/vùng quét | Là lựa chọn thay thế O4A, không phải dataset tim–phổi hỗn hợp |

Chi tiết: [DATA_AND_TASK_OPTIONS](research/DATA_AND_TASK_OPTIONS.md). Bất đồng chuyên gia, nhiều thiết bị/cơ sở và đánh giá ngoài là trục có thể bổ sung, không tự động trở thành những paper riêng.

Nhận định ưu tiên khảo sát O2/O3 từng được trợ lý đề xuất chỉ là **khuyến nghị có điều kiện**, không phải quyết định chọn cơ quan hay kết luận chúng khả thi hơn khi chưa biết nguồn.

## 5. Bước tiếp theo

Dùng [phiếu trao đổi HMU](planning/HMU_ALIGNMENT.md) để xác nhận nhu cầu, nguồn thực tế, chuyên gia và quyền sử dụng. Có thể thu hẹp còn hai hướng để kiểm tra sâu nếu buổi trao đổi cung cấp đủ thông tin; đây là mục tiêu làm việc đề xuất, chưa phải cam kết của phía Y.

Sau xác nhận, cập nhật U01–U12 bằng người xác nhận, ngày và bằng chứng được phép chia sẻ. Chỉ triển khai [pilot](planning/PILOT_QUALITY_GOVERNANCE.md) khi điều kiện tiếp cận và phê duyệt tương ứng đã rõ.

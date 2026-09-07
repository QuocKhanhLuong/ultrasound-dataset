# Vai trò tài liệu cách viết và mẫu thuyết minh

Cập nhật: 2026-09-07. **Vai trò đã được người dùng làm rõ:** hai PDF tham khảo cách viết paper; bản Word là mẫu thuyết minh để nộp bên Đại học Y Hà Nội. Chúng không lựa chọn cơ quan, task hay dạng dữ liệu cho dự án siêu âm.

Bản này chỉ lưu ghi chú và liên kết thư mục; không đưa toàn văn, hình chụp trang, thông tin liên hệ hoặc bản DOCX đã điền của một đề tài khác lên repo công khai.

## R01 — CariXray

Dang và cộng sự, *Carixray: a periapical X-ray dataset for machine vision-based dental caries recognition*, Machine Vision and Applications (2026). DOI [10.1007/s00138-025-01776-8](https://doi.org/10.1007/s00138-025-01776-8).

**Nguồn đã đọc:** PDF do người dùng cung cấp trong hội thoại. Vị trí tham khảo: mục 3, trang 4–7 về thu nhận/gán nhãn/rà soát; mục 4 về benchmark; mục 5 về đánh giá. Đây là ảnh X-quang nha khoa, không phải siêu âm.

**Cách dùng đề xuất:** tham khảo cách trình bày quy trình dữ liệu, thống kê, chất lượng nhãn, benchmark và phân tích lỗi. Không sao chép các tuyên bố gap, chiến lược lọc, cỡ mẫu, model hoặc quyết định đạo đức của paper sang dự án mới. Điều hợp lý với dataset chỉ giữ tổn thương nhìn rõ có thể không phù hợp nhiệm vụ nghiên cứu ảnh chưa đủ điều kiện.

## R02 — DATE

Dang và cộng sự, *DATE: a video dataset and benchmark for dynamic hand gesture recognition*, Neural Computing and Applications (2024). DOI [10.1007/s00521-024-09990-7](https://doi.org/10.1007/s00521-024-09990-7).

**Nguồn đã đọc:** PDF do người dùng cung cấp. Vị trí: mục 3, trang 3–4 về thu nhận/đặc điểm; mục 5.1, trang 8 và mục 5.1.7, trang 9 về chia theo người. Đây là video cử chỉ tay, không phải dữ liệu y khoa.

**Cách dùng đề xuất:** tham khảo cách thiết kế điều kiện thu nhận, mô tả đơn vị video và quản lý nhóm người khi chia tập. Không chuyển sang video siêu âm chỉ vì DATE dùng video; không buộc đề tài mới phải thiết kế model tùy biến giống paper.

## R03 — Mẫu thuyết minh HMU

**Tên nguồn:** `Thuyet minh De tai co so_ver2.docx`, người dùng cung cấp; không phát hành lại ở repo. Người dùng xác nhận đây là mẫu để nộp phía Đại học Y Hà Nội. Chưa dùng nó làm bằng chứng độc lập rằng mọi quy định hành chính hiện hành đã được kiểm tra.

**Vị trí tham khảo:** phần mở đầu và các mục 7–14. Bản mẫu đã điền thuộc đề tài thang đo, không thuộc dataset siêu âm. Các tên người, liên hệ, thời gian, ngân sách và cỡ mẫu trong đó không phải thông tin dự án mới.

### Bản đồ 14 mục để dùng khi đủ thông tin

| Mục của mẫu | Việc cần điền cho đề tài siêu âm sau này |
|---|---|
| 1. Tên đề tài | Nhu cầu/nhiệm vụ và phạm vi được hai bên xác nhận |
| 2. Thời gian thực hiện | Lịch thực tế, chưa sao chép từ mẫu |
| 3. Cấp quản lý | Xác nhận theo nơi tiếp nhận |
| 4. Chủ nhiệm | Nhân sự thực tế được thống nhất |
| 5. Người hướng dẫn | Người phụ trách chuyên môn được xác nhận |
| 6. Sinh viên tham gia | Thành viên thực tế và vai trò |
| 7. Mục tiêu | Sản phẩm dữ liệu và câu hỏi đánh giá chất lượng/khả năng sử dụng |
| 8. Tổng quan trong/ngoài nước | Nhu cầu, dataset gần nhất, giới hạn có nguồn, gap ứng viên |
| 9. Đối tượng/phương pháp | Nguồn, đơn vị, chọn ca, cỡ mẫu có căn cứ, nhãn/chuẩn tham chiếu, chia tập và quản trị |
| 10. Kết quả dự kiến | Loại sản phẩm dự kiến, không viết kết quả đo lường chắc chắn |
| 11. Tài liệu tham khảo | Nguồn gốc đã kiểm tra; cách trích dẫn theo yêu cầu nơi nộp |
| 12. Phụ lục | Biểu mẫu trống, từ điển dữ liệu, hướng dẫn nhãn và kiểm tra chất lượng |
| 13. Tiến độ | Mốc xác nhận nguồn/quyền, pilot, thu chính, đánh giá và viết |
| 14. Kinh phí | Ước tính theo công việc thực tế, không sao chép ngân sách mẫu |

Đây là bản đồ chuyển đổi để chuẩn bị, chưa phải đề cương hoàn chỉnh. Câu hỏi cần xử lý trước ở [HMU_ALIGNMENT](../planning/HMU_ALIGNMENT.md).

# Nhật ký quyết định và xác nhận

Ngày ghi nhận ban đầu: 2026-09-07. Nguồn: hội thoại dự án; người xác nhận: Alvin/người dùng. Bản ghi này được tổng hợp khi khởi tạo repo, không giả lập biên bản họp với phía Y.

Các quyết định được bổ sung theo lịch sử. Khi thay đổi, tạo bản ghi mới chỉ rõ bản nào bị thay thế; không xóa dấu vết. Ý tưởng của trợ lý không được đánh dấu đã chấp thuận.

## D001 — Paper dataset siêu âm độc lập

**Trạng thái:** đã xác nhận bởi người dùng.

Chọn modality siêu âm. Mục tiêu tìm nhu cầu dữ liệu có ý nghĩa, khả thi. Cơ quan, bệnh lý, task, ảnh/video và quy mô chưa được lựa chọn. Không ép kết hợp với world model/VLA/forensic và không đặt mục tiêu tách nhiều paper.

**Hệ quả:** giữ các lựa chọn mở; source of truth phải tách điều đã biết khỏi điều chưa có bằng chứng tiếp cận.

## D002 — Vai trò của các tài liệu gửi kèm

**Trạng thái:** đã được người dùng làm rõ.

CariXray và DATE là ví dụ cách viết paper. Bản `Thuyet minh De tai co so_ver2.docx` là mẫu thuyết minh để nộp bên Đại học Y Hà Nội.

**Hệ quả:** không dùng đề tài thang đo trong bản Word làm chủ đề mới; không lấy thông tin nhân sự, cỡ mẫu, thời gian, kinh phí hoặc phê duyệt trong mẫu làm dữ kiện dự án. Không dùng hai PDF ngoài siêu âm làm bằng chứng khoảng trống của lĩnh vực siêu âm.

## D003 — Menu hướng nghiên cứu trước đề cương hoàn chỉnh

**Trạng thái:** đã xác nhận bởi người dùng.

Ưu tiên đề xuất các hướng cụ thể theo cơ quan–task–dạng dữ liệu để đi khớp với phía Y. Không yêu cầu người dùng chốt bệnh lý trước khi hỗ trợ khảo sát.

**Hệ quả:** O1–O4 là các phương án trao đổi, không phải thiết kế đã được thông qua. Chưa điền một đề cương hoàn chỉnh với thông tin giả định.

## D004 — Repo chính thức và cập nhật docs

**Trạng thái:** đã xác nhận bởi người dùng trong yêu cầu chỉ định GitHub.

Repo: `QuocKhanhLuong/ultrasound-dataset`. Mỗi thay đổi có ý nghĩa về source of truth hoặc knowledge base phải được chủ động chuyển thành tài liệu và đẩy vào repo trong phiên làm việc có quyền truy cập, không cần yêu cầu push riêng.

**Hệ quả triển khai:** dùng README để điều hướng; SOURCE_OF_TRUTH cho trạng thái dự án; research cho bằng chứng/đề xuất; DECISIONS và CHANGELOG để truy vết. Không suy ra yêu cầu chạy nền hay tự động theo lịch.

## D005 — Khảo sát song song một CT longitudinal oncology ontology

**Trạng thái:** đã xác nhận yêu cầu nghiên cứu bởi người dùng ngày 2026-09-08.

Người dùng muốn khảo sát thêm một hướng **CT ontology theo hồ sơ bệnh theo thời gian**, trong đó imaging states được nối với lesion-level labels/measurements, treatment/intervention giữa các state và clinical outcome/assessment. Người dùng yêu cầu tiếp tục survey để chọn scale và scope.

**Không được diễn giải thành:** đã bỏ ultrasound; đã chọn HCC/NSCLC/HNSCC; đã chọn RECIST/mRECIST/iRECIST; đã có CT/EHR linkage; đã có quyền public; hoặc đã quyết định world-model paper.

**Hệ quả:** giữ nhánh CT như một candidate chiến lược chính thức để đánh giá song song. Tài liệu làm việc: `research/CT_ONTOLOGY_SCOPE_SCALE_2026-09-08.md`. Khuyến nghị của trợ lý hiện là ontology kiểu `core + disease-specific profile` và ưu tiên single-disease/single-treatment trước pan-cancer, nhưng đây vẫn là đề xuất chưa được HMU xác nhận.

## Chưa có quyết định lựa chọn

Chưa có bản ghi chấp thuận O1, O2, O3, O4A/O4B hoặc một CT disease/treatment profile cụ thể; chưa chọn tĩnh/video, máy, cơ sở, cỡ mẫu, protocol hay benchmark cuối cùng. Các nhận định ưu tiên trong tài liệu nghiên cứu vẫn là đề xuất của trợ lý.

## Mẫu bản ghi tiếp theo

- Mã, ngày, trạng thái: đề xuất / xác nhận / thay thế / rút lại.
- Vấn đề và các phương án thực sự đã xem xét.
- Quyết định, người xác nhận và nguồn/bằng chứng được phép lưu.
- Điều kiện, giới hạn, hệ quả, câu hỏi còn mở.
- Tài liệu cần cập nhật và bản ghi bị thay thế nếu có.

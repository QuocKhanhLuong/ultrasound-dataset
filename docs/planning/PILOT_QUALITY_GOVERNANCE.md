# Pilot, chất lượng và quản trị dữ liệu

Cập nhật: 2026-09-07. **Trạng thái: khung đề xuất để thảo luận; chưa được phê duyệt, chưa triển khai.** Không phải hướng dẫn chẩn đoán hay kết luận pháp lý về quyền dùng dữ liệu.

## 1. Mục đích và phạm vi pilot

Kiểm tra khả năng xuất, khử định danh, liên kết, gán nhãn và kiểm soát chất lượng trước khi thu lớn. Đề xuất chọn một quy trình và một nhiệm vụ nhãn chính sau phản hồi HMU; không thu nhiều cơ quan chỉ để tăng độ rộng.

Chưa ấn định số bệnh nhân, ảnh, clip hoặc phần trăm nhãn kép. Cần xác định tình huống cần thử, thời gian chuyên gia, sản lượng và tỷ lệ thiếu dữ liệu trước khi xây kế hoạch thu chính thức. CLAIM yêu cầu giải thích cách xác định cỡ tập kiểm tra và mục tiêu nghiên cứu; đây là hướng dẫn báo cáo, không cung cấp một cỡ mẫu chung cho dự án [S010](../research/SOURCES.md#s010).

## 2. Các mốc kiểm tra đề xuất

| Mốc | Nội dung kiểm tra | Sản phẩm | Điều kiện mới được đi tiếp |
|---|---|---|---|
| P0 — Nguồn và quyền | Đơn vị quản lý, mục đích, dữ liệu được phép xem/xuất, nơi lưu và người nhận | Bản đồ nguồn và điều kiện còn thiếu | Có xác nhận/phê duyệt phù hợp trước khi xử lý dữ liệu thật |
| P1 — Xuất và liên kết | Định dạng, đơn vị bệnh nhân/lần khám, ảnh/clip, metadata | Manifest thử và danh sách lỗi | Truy vết được cấu trúc; không cần đưa manifest ca thật lên repo công khai |
| P2 — Khử định danh và toàn vẹn | Header/private tags, chữ trong pixel, tên tệp, tài liệu đi kèm; hiệu chuẩn và thời gian sau xử lý | Báo cáo kiểm tra trong môi trường được phép | Không phát hiện thông tin định danh còn sót trong phần được chia sẻ; cần quy trình rà soát, không hứa bảo đảm tuyệt đối |
| P3 — Nhãn | Hiệu chỉnh hướng dẫn trên một phần; đọc độc lập trên phần khác; ghi bất đồng và thời gian | Sổ tay nhãn v0.1, loại lỗi và chi phí | Có rubric/chuẩn tham chiếu đủ để thử nhiệm vụ đã chọn |
| P4 — Thiết kế đánh giá | Đơn vị dự đoán, tiêu chí chọn ca, chia tập, metric chính, nhóm cần báo cáo | Bản benchmark protocol dự thảo | Đánh giá đúng câu hỏi, tránh leakage và đủ căn cứ tính cỡ mẫu |
| P5 — Quyết định mở rộng | Tốc độ ca đủ điều kiện, nhãn, metadata, quyền sử dụng, nguồn lực | Tiếp tục / thu hẹp / đổi hướng / dừng | Quyết định thực sự được ghi lại; không coi pilot thành công chỉ vì xuất được nhiều frame |

Có thể cố ý chọn tình huống khó để thử quy trình nhưng không dùng lô đó ước tính tỷ lệ bệnh trong thực tế. Muốn kiểm tra sản lượng ca cần một kiểm kê theo thời gian/khung tuyển chọn rõ ràng, tách khỏi lô thử lỗi.

## 3. Nhãn và chuẩn tham chiếu

Đề xuất tách nhãn quan sát trên ảnh, nhận định của người đọc và kết quả xác minh lâm sàng. Dùng thuật ngữ chuẩn tham chiếu, không ngụ ý nhãn luôn đúng tuyệt đối; cách diễn đạt này phù hợp CLAIM [S010](../research/SOURCES.md#s010).

Lưu phiên bản rubric; nhãn độc lập trước phân xử; trạng thái không xác định/không đủ điều kiện; lý do sửa. Chưa đặt ngưỡng đồng thuận hoặc cỡ phần đọc kép khi chưa biết task. Không gộp ca khó về nhãn âm tính để bảng nhãn trông sạch hơn. Phân biệt tệp hỏng, ảnh khó thuộc phạm vi và thiếu chuẩn tham chiếu; chúng không nhất thiết có cùng cách xử lý.

## 4. Chia tập và leakage — yêu cầu thiết kế của dự án

Giữ dữ liệu cùng bệnh nhân trong cùng tập, bao gồm nhiều lần khám, tổn thương, clip, frame và crop. Kiểm tra trùng/gần trùng và khả năng một người xuất hiện ở nhiều nguồn. Nếu chưa có định danh liên kết phù hợp thì chưa được khẳng định tập kiểm tra độc lập theo bệnh nhân.

Tách dữ liệu dùng hiệu chỉnh rubric, chọn phép tiền xử lý hoặc chỉnh mô hình khỏi tập kiểm tra cuối. Kiểm tra chữ chẩn đoán, caliper, cách crop, tên tệp, nhãn do GT tạo và thông tin chỉ có sau thời điểm dự đoán. Không dùng nhãn bệnh nhân làm nhãn mặc định cho mọi frame.

Giữ riêng một máy/cơ sở chỉ có ý nghĩa nếu nguồn xác minh được; phải xem thành phần ca bệnh và máy/cơ sở có bị trùng khớp hoàn toàn hay không. Đây là kiểm tra cần thực hiện, chưa phải kết quả dự án đã vượt qua.

## 5. Khử định danh không được phá thông tin cần đánh giá

DICOM nêu riêng xử lý chữ định danh ghi trong pixel và lưu ý siêu âm thường có trường hợp đó; overlay che chữ không tương đương thay đổi pixel gốc [S009](../research/SOURCES.md#s009). Quy trình cần xem toàn clip và các vùng chứa thông tin, không chỉ frame đầu.

Đối với nhiệm vụ đo, kiểm tra hiệu chuẩn theo vùng trước và sau chuyển tệp/crop/resize [S008](../research/SOURCES.md#s008). Đối với video, kiểm tra thứ tự frame, tốc độ/nhãn thời gian và các thao tác cắt/đổi tốc độ. Không tuyên bố khôi phục được thông tin gốc không còn lưu.

Bảng nối định danh phải thuộc nơi lưu được đơn vị quản lý chấp thuận, tách khỏi tài liệu công khai. Repo này không phải nơi lưu dữ liệu ca thật, kể cả khi đã thay tên.

## 6. Quyền sử dụng và công bố

Cần đầu mối phù hợp xác định yêu cầu phê duyệt, đồng ý/miễn đồng ý nếu áp dụng, trích xuất, lưu trữ, chuyển giao, sử dụng thứ cấp và chia sẻ. Không kết luận rằng dữ liệu khử định danh tự động được public hoặc miễn phê duyệt.

Các phương án để thảo luận là tải mở, truy cập có xét duyệt hoặc đánh giá trong môi trường kiểm soát. Chưa lựa chọn phương án nào; quyền nghiên cứu không mặc nhiên là quyền tái phân phối. Giấy phép tương lai phải tương thích với thẩm quyền và thỏa thuận thực tế.

## 7. Phiên bản và tính toán quy mô sau pilot

Khi có dữ liệu, đề xuất quản lý phiên bản ảnh, nhãn, phép đo, split và manifest riêng; lưu lịch sử sửa lỗi. Số bệnh nhân/lần khám/clip/frame phải báo cáo tách biệt. Cỡ mẫu chính thức phụ thuộc mục tiêu, độ chính xác mong muốn, tỷ lệ nhóm và cấu trúc phụ thuộc; cần người phụ trách thống kê cùng chuyên gia xác định. Chưa viết trước số ca hoặc điểm metric thành kết quả chắc chắn.

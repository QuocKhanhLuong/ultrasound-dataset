# Hướng dẫn duy trì tài liệu dự án

Áp dụng cho toàn bộ repo `QuocKhanhLuong/ultrasound-dataset`.

## Bắt đầu một phiên làm việc

Đọc `docs/SOURCE_OF_TRUTH.md`, `docs/DECISIONS.md`, `docs/CHANGELOG.md` và các tài liệu liên quan trước khi cập nhật. Đọc trạng thái hiện tại trên GitHub, không chỉ dựa vào trí nhớ hoặc bản chat cũ. Khi người dùng xác nhận thay đổi, ghi lại nguồn xác nhận; nếu thông tin mâu thuẫn chưa giải quyết, giữ trạng thái chưa xác minh.

## Những điều không được tự giả định

- Chỉ modality siêu âm và định hướng paper dataset đã được xác nhận. Cơ quan, bệnh lý, task, ảnh/video, quy mô, thiết bị, số cơ sở và khả năng lấy nhãn vẫn mở cho đến khi có xác nhận mới.
- Cộng tác với một số bạn Đại học Y Hà Nội không đồng nghĩa đã có thỏa thuận cấp trường, bệnh viện cung cấp dữ liệu hoặc phê duyệt đạo đức.
- CariXray và DATE chỉ tham khảo cách viết/tổ chức paper. Bản Word là mẫu thuyết minh nộp phía Y, không phải nghiên cứu siêu âm hiện tại.
- Không ép kết hợp world model, VLA hoặc forensic. Không thêm model mới, code huấn luyện hay mục tiêu tách nhiều paper khi chưa được yêu cầu.
- Không chuyển lời khuyên của trợ lý thành quyết định của người dùng. Không tự đặt cỡ mẫu chính thức hoặc kết quả kỳ vọng có số.

## Cập nhật docs trong mỗi phiên có thay đổi có ý nghĩa

Người dùng đã yêu cầu chủ động đẩy các cập nhật source of truth/knowledge base vào repo này, không cần nhắc riêng.

1. Phân loại cập nhật: xác nhận dự án, bằng chứng nghiên cứu, đề xuất, câu hỏi mở, kết quả thực nghiệm hoặc sửa sai.
2. Sửa đúng tài liệu; bổ sung nguồn có DOI/URL và ngày kiểm tra khi có khẳng định bên ngoài.
3. Cập nhật `docs/DECISIONS.md` chỉ khi có quyết định/xác nhận thực sự; cập nhật `docs/CHANGELOG.md` cho thay đổi đáng kể. Không ghi chuyện phiếm hoặc bản sao không có thay đổi.
4. Kiểm tra nội dung nhạy cảm, liên kết, tính nhất quán và diff trước khi ghi. Không commit toàn bộ thư mục tải về.
5. Commit/push thay đổi tài liệu được ủy quyền lên nhánh mặc định sau khi đọc HEAD. Không force-push, không xóa lịch sử hoặc ghi đè thay đổi đồng thời. Nếu nhánh được bảo vệ, dùng nhánh docs và PR theo quy tắc repo.
6. Đọc lại ref/commit và tệp liên quan để xác nhận. Trả lại SHA/PR và trạng thái thực tế. Nếu không ghi được, báo rõ phần chưa đồng bộ; không nói đã push.

Không tự tạo lịch theo dõi nền. Quy tắc này áp dụng khi agent đang thực hiện một phiên làm việc có quyền truy cập.

## Chất lượng nguồn

Ưu tiên paper gốc, trang tác giả/dataset và tài liệu chính thức. Tra cứu lại các thông tin có thể thay đổi. Ghi rõ nguồn chỉ là preprint. Dữ liệu mô tả trong paper khác với tệp thực tế đã tải và kiểm toán; cấp truy cập khác với quyền tái phân phối. Khi có mâu thuẫn số liệu, giữ cả hai phát biểu có nguồn và một mục cần kiểm tra, không tự sửa thành một con số chắc chắn.

Trong Markdown dùng mã nguồn bền vững từ `docs/research/SOURCES.md`, không để citation token chỉ tồn tại trong một phiên chat. Với nguồn đính kèm riêng tư, lưu vai trò và vị trí tham khảo tối thiểu; không sao chép toàn bộ tài liệu vào repo công khai.

## Dữ liệu và quyền riêng tư

Không upload dữ liệu lâm sàng, DICOM, video, ảnh bệnh nhân, hồ sơ, bảng ánh xạ định danh, chữ ký, thông tin liên hệ cá nhân, tài liệu phê duyệt chứa thông tin riêng tư, secrets hay bản PDF/DOCX nguồn khi chưa được phép. Cả GitHub API lẫn `git add -f` đều có thể vượt qua `.gitignore`; phải kiểm tra payload/diff thực tế.

Chỉ lưu biểu mẫu trống và quy trình dự kiến. Không tự khẳng định khử định danh đồng nghĩa được public hoặc được miễn phê duyệt. Viết tài liệu làm việc bằng tiếng Việt, giữ thuật ngữ chuyên môn cần thiết và tên nguồn gốc.

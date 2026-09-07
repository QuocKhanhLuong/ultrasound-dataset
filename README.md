# Ultrasound Dataset — Kho tài liệu nghiên cứu

Repo chính thức của dự án paper **dataset siêu âm y tế**, được phát triển qua trao đổi giữa Alvin và nhóm cộng tác Đại học Y Hà Nội.

**Trạng thái ngày 07/09/2026:** đang khảo sát hướng nghiên cứu để đối chiếu với khả năng hợp tác phía Y. Chưa chốt cơ quan, bệnh lý, task, ảnh tĩnh/video, cỡ mẫu hoặc nguồn thu nhận. Chưa xác nhận quyền tiếp cận hay quyền công bố dữ liệu. Đây **không phải** bản phát hành dataset và chưa có kết quả thực nghiệm.

## Đọc từ đâu?

| Tài liệu | Mục đích |
|---|---|
| [Source of truth](docs/SOURCE_OF_TRUTH.md) | Bối cảnh, điều đã được người dùng xác nhận và các quyết định còn mở |
| [Bản đồ dạng dữ liệu và task](docs/research/DATA_AND_TASK_OPTIONS.md) | Bốn nhóm hướng cụ thể để trao đổi với phía Y; tất cả vẫn là đề xuất |
| [Bảng đối chiếu dataset](docs/research/DATASET_MAP.md) | Những nguồn tiêu biểu và giới hạn của bằng chứng đã kiểm tra |
| [Sổ nguồn và hàng đợi xác minh](docs/research/SOURCES.md) | Paper/trang chính thức, tình trạng công bố, ngày kiểm tra, mâu thuẫn chưa giải quyết |
| [Phiếu trao đổi với Đại học Y Hà Nội](docs/planning/HMU_ALIGNMENT.md) | Nhu cầu lâm sàng, dữ liệu thực tế, chuyên gia và quyền sử dụng cần xác nhận |
| [Pilot, chất lượng và quản trị dữ liệu](docs/planning/PILOT_QUALITY_GOVERNANCE.md) | Khung thử quy trình; chưa phải protocol được phê duyệt |
| [Vai trò tài liệu tham khảo và mẫu đề cương](docs/references/WRITING_AND_TEMPLATE.md) | CariXray/DATE là mẫu cách viết; bản Word là mẫu thuyết minh nộp phía Y |
| [Nhật ký quyết định](docs/DECISIONS.md) | Ai xác nhận điều gì; không chuyển đề xuất của trợ lý thành quyết định |
| [Lịch sử cập nhật](docs/CHANGELOG.md) | Các thay đổi có ý nghĩa trong kho tài liệu |
| [Hướng dẫn cho người/agent đóng góp](AGENTS.md) | Quy tắc đọc, cập nhật, kiểm chứng và đẩy docs |

## Nguyên tắc sử dụng

**Git là nguồn tài liệu chuẩn của dự án**, không phải bằng chứng rằng mọi nội dung trong repo đã được xác minh khoa học. Mỗi nội dung được phân biệt thành: đã xác nhận về dự án, có nguồn nghiên cứu hỗ trợ, đề xuất, hoặc chưa xác minh.

Khi có cập nhật có ý nghĩa trong các phiên làm việc, cập nhật tài liệu liên quan và changelog, bổ sung quyết định hoặc nguồn khi cần, rồi commit/push vào repo. Đây là quy trình cập nhật trong phiên làm việc, không phải dịch vụ theo dõi nền hoặc lịch đồng bộ tự động.

## Phạm vi an toàn của repo

Repo hiện công khai. Chỉ đưa lên tài liệu nghiên cứu đã lược bỏ thông tin riêng tư, biểu mẫu trống và liên kết nguồn. Không đưa dữ liệu bệnh nhân, ảnh/video lâm sàng, bảng nối định danh, thông tin liên hệ trong mẫu Word, tài khoản/mật khẩu hoặc toàn văn paper chưa được phép tái phân phối lên Git.

`.gitignore` chỉ giúp tránh commit nhầm một số loại tệp; nó không thay thế việc rà soát nội dung và không chặn các thao tác ghi trực tiếp qua API. Chưa lựa chọn giấy phép cho dataset tương lai; quyền truy cập repo không tạo ra quyền sử dụng dữ liệu y tế.

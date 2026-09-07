# Bảng đối chiếu dataset siêu âm — Bản khởi tạo

Ngày kiểm tra nguồn: 2026-09-07. Đây là khảo sát chọn lọc phục vụ lựa chọn, **không phải tổng quan hệ thống**. Chỉ ghi những thuộc tính được nguồn đã đọc hỗ trợ. `Chưa xác minh` không có nghĩa thuộc tính không tồn tại.

Mã nguồn dẫn tới [SOURCES](SOURCES.md). Chưa tải/kiểm toán các gói dataset, chưa xác minh đủ quyền tái sử dụng từng bản phát hành. Các số dưới đây là **báo cáo của nguồn**, không phải số ca của dự án mới.

| Dataset / tình trạng nguồn | Dạng và đơn vị báo cáo | Nhãn, thông tin và task được mô tả | Thu nhận | Truy cập đã quan sát |
|---|---|---|---|---|
| ThyroidXL — MICCAI 2025 [S001](SOURCES.md#s001) | Ảnh B-mode; paper: 11.635 ảnh / 4.093 bệnh nhân; có mâu thuẫn với card | Nhãn từ tế bào học/bệnh học, vùng nốt; classification, detection, segmentation | Bệnh viện Nội tiết Trung ương, Việt Nam; paper nêu hệ máy Hitachi Aloka | Hugging Face có gate; chưa chấp nhận điều khoản hoặc kiểm toán tệp |
| Open Kidney — trang tác giả, dẫn preprint 2022 [S002](SOURCES.md#s002) | Hơn 500 ảnh B-mode 2D; tối đa một ảnh/bệnh nhân | Hai bộ polygon của chuyên gia, mặt cắt, loại thận, chất lượng; metadata máy/hiệu chuẩn nơi có; segmentation | Nhiều hãng; số cơ sở chưa xác minh | PNG; đăng ký được duyệt thủ công; nguồn ghi CC BY-NC-SA |
| BrEaST — Scientific Data 2024 [S003](SOURCES.md#s003) | 256 ảnh / 256 bệnh nhân | Mask, dấu hiệu/BI-RADS, thông tin người bệnh và phương pháp xác minh; phân đoạn/phân loại/phát hiện | Hai đơn vị ở Ba Lan, năm dòng máy nêu trong paper | Nguồn ghi CC BY 4.0; chưa audit gói phát hành |
| ACOUSLIC-AI — Zenodo v1.1, mô tả truy được qua tìm kiếm [S004](SOURCES.md#s004) | Frame trong các lượt blind-sweep; chưa đưa số lượng vào bản này | Vùng/chu vi bụng trên frame đo được và số đo tham chiếu theo sweep; chọn frame/đo | Người mới quét theo quy trình; số cơ sở/máy chưa xác minh | Có record phiên bản; chưa đọc đủ điều khoản hoặc tải gói |
| EchoNet-Dynamic — Nature 2020 và trang tác giả [S005](SOURCES.md#s005) | 10.030 video bốn buồng | EF, thể tích cuối tâm thu/tâm trương, đường biên ở hai thời điểm; định lượng chức năng | Stanford University Hospital; số máy chưa xác minh | Đăng ký và thỏa thuận phi thương mại; không mặc định quyền tái phân phối |
| CAMUS — IEEE TMI 2019 và trang dự án [S006](SOURCES.md#s006) | 500 bệnh nhân; chuỗi hai/bốn buồng | Nhãn cấu trúc ở ED/ES, chất lượng, đo chức năng | Một bệnh viện St Etienne; GE Vivid E95 | Trang chính thức dẫn nơi tải; raw/mhd; chưa rà soát đầy đủ giấy phép |
| OpenPOCUS — POCUS Journal 2026 [S007](SOURCES.md#s007) | 226 người lớn; abstract: 1.871 clip; có bất nhất thống kê trong bài | Dấu hiệu cấp clip, vùng quét, nhân khẩu/lâm sàng và không xác định; đọc độc lập/phân xử | Nghiên cứu đa trung tâm, năm dòng thiết bị được nêu; số cơ sở chưa xác minh | Paper dẫn repo tác giả; bản này chưa kiểm tra nội dung tệp hoặc giấy phép repo |

## Giới hạn có nguồn và gap ứng viên là hai việc khác nhau

**Ví dụ giới hạn cục bộ:** Open Kidney mô tả tối đa một ảnh/bệnh nhân [S002](SOURCES.md#s002). Điều đó giới hạn việc dùng riêng bộ này để đánh giá nhiều mặt cắt hoặc quét lặp cùng ca; không chứng minh chưa có bộ thận nào khác làm được.

**Ví dụ chống tuyên bố tính mới quá rộng:** ThyroidXL đã là dữ liệu Việt Nam với các task cơ bản [S001](SOURCES.md#s001). Video tim và nhãn phép đo đã có nguồn đối chiếu [S005](SOURCES.md#s005), [S006](SOURCES.md#s006). Vì vậy “Việt Nam”, “có video”, “có nhiều task” không tự tạo luận điểm đóng góp.

**Các gap ứng viên cần khảo sát:** bằng chứng chưa đủ trong một quy trình cụ thể; liên kết nhiều mặt cắt/lần khám; tách biến thiên người đọc và lần quét; dữ liệu cho một điều kiện đánh giá ngoài chưa được bao phủ. Cần kiểm tra cả tài liệu gần nhất lẫn nhu cầu bác sĩ trước khi gọi là gap đã xác lập.

## Những điều chưa thể so sánh công bằng

Chưa xếp hạng dataset bằng một cột số ảnh: các nguồn có đơn vị, tiêu chí chọn và nhãn khác nhau. Không so Dice/mAP/AUC giữa những tập và protocol khác nhau như một bảng SOTA thống nhất. Chưa kết luận nguồn nào “dễ”, có leakage hoặc được phép tái phát hành chỉ từ việc đọc mô tả.

Các nguồn được nhắc ở vòng trao đổi trước nhưng chưa kiểm chứng lại nằm riêng trong [hàng đợi nguồn](SOURCES.md#pending), không lấp khoảng trống của bảng này bằng suy đoán.

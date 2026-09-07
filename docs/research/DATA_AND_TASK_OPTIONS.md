# Bản đồ dạng dữ liệu và task để trao đổi với phía Y

Cập nhật: 2026-09-07. **Trạng thái: đề xuất, chưa lựa chọn.** Nguồn bối cảnh: [SOURCE_OF_TRUTH](../SOURCE_OF_TRUTH.md). Dataset đối chiếu: [DATASET_MAP](DATASET_MAP.md); mã Sxxx: [SOURCES](SOURCES.md).

Mục tiêu là tìm điểm khớp giữa nhu cầu lâm sàng và dữ liệu có thể tiếp cận. Không chấm cơ quan nào “dễ ra paper hơn” khi chưa biết nguồn, và không lấy số task làm giá trị nghiên cứu.

## 1. Phân biệt những quyết định về dữ liệu

Khung dưới đây là cách tổ chức lựa chọn của dự án, không phải một protocol đã được phía Y phê duyệt.

| Trục | Những lựa chọn cần tách |
|---|---|
| Phạm vi giải phẫu/bệnh lý | Một cấu trúc, một phép đo, một nhóm tổn thương hoặc một quy trình khám; nhiều cơ quan chỉ khi cùng nhu cầu được chứng minh |
| Nguồn thu nhận | Cơ sở, máy/dòng máy, đầu dò, người quét, kinh nghiệm và bối cảnh khám; số kho tải không thay số bệnh viện |
| Cấu trúc và thời gian | Một ảnh, nhiều mặt cắt, video quét, video một mặt cắt, nhiều lần khám; video không đồng nghĩa theo dõi dọc |
| Độ sâu nhãn | Mặt cắt, chất lượng, hộp, mask, landmark, phép đo, dấu hiệu, kết quả xác minh, nhãn độc lập của chuyên gia |
| Mục tiêu đánh giá | Phân đoạn, đo lường, tính đầy đủ, nhận diện dấu hiệu, nguy cơ/chẩn đoán hoặc chuyển điều kiện thu nhận |

Tách thêm **chế độ tạo ảnh** (B-mode, Doppler, đàn hồi…) khỏi **dạng mẫu** (ảnh/clip/khối 3D) và **dạng tệp** (DICOM, PNG/JPG, video…). DICOM có mô-đun hiệu chuẩn vùng siêu âm; không suy ra đơn vị vật lý chỉ từ số pixel [S008](SOURCES.md#s008).

| Dạng mẫu ứng viên | Có thể cân nhắc task nào? | Điều cần kiểm tra tại nguồn |
|---|---|---|
| Ảnh B-mode tĩnh | Vùng tổn thương, landmark, dấu hiệu, phép đo | Trường nhìn, caliper/chữ ghi sẵn, nhãn và hiệu chuẩn |
| Nhiều mặt cắt cùng ca | Kết hợp bằng chứng, đánh giá cấp tổn thương, nhất quán đo | Có liên kết đúng ca/tổn thương và định danh mặt cắt không |
| Video quét qua mặt cắt | Chọn frame, tìm đoạn đủ điều kiện, đánh giá phần còn thiếu | Có cả lượt thử không đạt hay chỉ clip được chọn; thứ tự và thời gian |
| Video duy trì một mặt cắt | Chức năng hoặc dấu hiệu động | Độ dài/tốc độ khung hình đủ cho nhiệm vụ và nhãn tham chiếu phù hợp |
| Khối 3D | Định vị, phân đoạn hoặc đo thể tích | Thực sự xuất được dữ liệu thể tích và thông tin không gian; hiện chưa ưu tiên |

Doppler, đàn hồi, 3D là lựa chọn mở rộng nếu nguồn và nhu cầu được xác nhận, không phải yêu cầu khởi đầu. Những task nêu trong bảng là phương án thiết kế, không khẳng định mọi bộ tệp ở dạng đó đều hỗ trợ được.

## 2. O1 — Tổn thương khu trú: tuyến giáp hoặc vú

**Câu hỏi để phía Y đánh giá:** có nhu cầu thống nhất khoanh vùng, mô tả dấu hiệu, phép đo hoặc tổng hợp nhiều mặt cắt của cùng tổn thương không?

**Cấu hình đề xuất:** ảnh B-mode nhiều mặt cắt → vùng tổn thương và/hoặc một bộ dấu hiệu do chuyên gia xác định. Chọn một cơ quan và một mục tiêu chính. Đơn vị quản lý: bệnh nhân → lần khám → tổn thương → mặt cắt.

**Thiết yếu:** liên kết các cấp; loại mặt cắt; vùng/điểm cần gán; định nghĩa từng dấu hiệu; người đọc và mức không chắc chắn. Nếu đo kích thước cần hiệu chuẩn. Phân biệt nhãn quan sát, nhận định nguy cơ và kết quả xác minh lâm sàng.

**Bổ sung sau:** mask chi tiết toàn bộ, Doppler, video hoặc theo dõi dọc nếu chưa cần cho mục tiêu chính. Ngược lại, chuẩn tham chiếu lành/ác không thể để “bổ sung sau” mà vẫn tuyên bố benchmark chẩn đoán lành/ác ngay.

**Đối chiếu bắt buộc:** ThyroidXL [S001](SOURCES.md#s001) và BrEaST [S003](SOURCES.md#s003); các nguồn tuyến giáp/vú khác ở hàng đợi xác minh. Không dùng “dữ liệu Việt Nam + classification/detection/segmentation” làm luận điểm tính mới duy nhất.

**Khác biệt ứng viên, chưa chứng minh:** liên kết lần khám/tổn thương tốt hơn cho nhiệm vụ cụ thể; nhãn bất đồng hoặc không xác định; giữ các tình huống khó; đánh giá ở một điều kiện thu nhận chưa được nguồn gần nhất hỗ trợ.

**Benchmark đề xuất:** độ đúng theo dấu hiệu; chất lượng định vị/đường biên; một ảnh so với nhiều mặt cắt ở cấp tổn thương. Phân loại nguy cơ/chẩn đoán chỉ khi nhãn đáp ứng. Nếu chỉ có ảnh đã crop quanh nốt, phải giới hạn tuyên bố về phát hiện trên toàn lần khám.

**Gánh nặng và rủi ro:** thời gian chuyên gia, ghép hồ sơ và chuẩn tham chiếu. Không xem “không sinh thiết” là “lành”. Nếu chỉ thu ca được sinh thiết, không tự mở rộng kết luận sang sàng lọc quần thể.

**Điều kiện để đi tiếp:** một đối tác chuyên môn; ảnh truy vết được; có người xác định rubric; cơ chế xác minh phù hợp task.

## 3. O2 — Một phép đo hình thái thận

**Câu hỏi để phía Y đánh giá:** một phép đo nào đang cần kiểm tra tính nhất quán hoặc giảm sai khác giữa người đọc/lần thu nhận?

**Cấu hình đề xuất:** ảnh mặt cắt phù hợp → landmark/đường biên cần thiết → một phép đo. Chiều dài trên mặt cắt dọc chỉ là ví dụ cần chuyên gia chọn, không phải quyết định đã chốt.

**Đơn vị:** bệnh nhân → lần khám → thận trái/phải hoặc loại thận phù hợp → mặt cắt → phép đo/người đọc. Không coi hai thận hoặc nhiều ảnh cùng bệnh nhân là các ca độc lập để chia tập.

**Thiết yếu:** hiệu chuẩn theo đơn vị vật lý, bên và mặt cắt, điểm đặt thước/đường biên, giá trị và phương pháp đo tham chiếu, nhãn đo được/chưa đủ điều kiện. Kiểm tra ảnh sạch và caliper để tránh lộ đáp án.

**Bổ sung sau:** nhiều mặt cắt, đọc lại, quét lại hoặc dữ liệu lâm sàng theo mục tiêu. Quét lặp là bắt buộc nếu tuyên bố đo biến thiên do thu nhận, nhưng không bắt buộc cho một pilot chỉ đánh giá người đọc.

**Dataset gần nhất:** Open Kidney [S002](SOURCES.md#s002). Trang nguồn đã có nhãn chi tiết của hai chuyên gia; không coi “thận + mask + nhiều người đọc” là gap mới.

**Khác biệt ứng viên:** tách sai khác do chọn mặt cắt và đặt điểm đo; nhiều mặt cắt có liên kết trong cùng lần khám; định nghĩa phép đo và dữ liệu lặp lại. Chưa xác lập khoảng trống toàn lĩnh vực.

**Benchmark đề xuất:** sai số đo theo đơn vị vật lý, sai lệch có hệ thống và mức phù hợp với chuyên gia; điểm mask chỉ là hỗ trợ nếu mục tiêu cuối là đo. Chưa đặt ngưỡng sai số chấp nhận khi chưa hỏi bác sĩ.

**Gánh nặng/rủi ro:** giữ hiệu chuẩn và thời gian đọc độc lập; mask nhiều cấu trúc có thể làm khối lượng nhãn tăng. Không đổi task thành dự đoán bệnh thận chỉ vì đã có ảnh thận.

**Điều kiện để đi tiếp:** phép đo có nhu cầu được phía Y xác nhận, dữ liệu đủ thông tin đo và nhân lực nhãn phù hợp.

## 4. O3 — Mặt cắt đủ điều kiện và đo lường sản khoa

**Câu hỏi để phía Y đánh giá:** ảnh/đoạn quét nào đủ điều kiện cho một phép đo; không đạt vì thiếu cấu trúc hoặc tiêu chí gì?

**Hai mức đề xuất:** ảnh tĩnh → tiêu chí đủ điều kiện + điểm đo; hoặc video quét → chọn frame/đoạn đủ điều kiện → đo. Không bắt buộc video ngay.

**Đơn vị:** bệnh nhân → lần khám → lượt quét → frame/đoạn thời gian → nhãn và phép đo.

**Thiết yếu:** phép đo mục tiêu, rubric mặt cắt/cấu trúc phải thấy, đạt/chưa đạt/không xác định, nhãn frame hoặc đoạn dùng được, hiệu chuẩn, tuổi thai và nguồn xác định khi cần, thông tin thời gian cho video.

**Bổ sung sau:** nhiều phép đo, nhiều nhóm kinh nghiệm, đọc/quét lặp lại. Không mở ngay sang phát hiện mọi dị tật; đó là yêu cầu dữ liệu/chuẩn tham chiếu khác.

**Đối chiếu:** ACOUSLIC-AI [S004](SOURCES.md#s004), FETAL_PLANES_DB và các bộ sinh trắc/video sản khoa trong hàng đợi. Không giả định quy trình chọn mặt cắt rồi đo là chưa từng có.

**Khác biệt ứng viên:** lý do thiếu bằng chứng, quá trình thử quét, một quy trình chưa được bao phủ hoặc sai khác giữa frame được lưu và frame chọn từ toàn lượt quét.

**Benchmark đề xuất:** tỷ lệ báo đủ điều kiện khi thực tế chưa đủ; khả năng chọn frame; sai số phép đo sau lựa chọn. Đánh giá riêng nhiệm vụ mặt cắt và đo, không dùng accuracy mặt cắt thay cho chất lượng đo.

**Gánh nặng/rủi ro:** xây rubric và xem video. Có thể gán nhãn đoạn + frame chủ chốt thay vì mask mọi frame. Kho chỉ lưu ảnh đẹp không đủ để khẳng định đại diện toàn bộ quá trình quét.

**Điều kiện để đi tiếp:** nhóm sản khoa xác nhận một nhu cầu cụ thể, loại dữ liệu có thể xuất và chuyên gia kiểm tra nhãn.

## 5. O4 — Siêu âm động: chọn tim hoặc phổi

### O4A — Một thông số chức năng tim từ video

Đề xuất video → thông số chức năng đã thống nhất, với thời điểm/đường biên chủ chốt khi cần. Phân suất tống máu là ví dụ để thảo luận, chưa được chọn.

**Đơn vị và thiết yếu:** bệnh nhân → lần khám → mặt cắt/clip; thông tin thời gian; giá trị, phương pháp và người tạo phép đo tham chiếu. Bổ sung sau: nhiều mặt cắt, đọc lặp và nhãn dày hơn.

**Đối chiếu:** EchoNet-Dynamic [S005](SOURCES.md#s005), CAMUS [S006](SOURCES.md#s006). Khác biệt ứng viên cần nằm ở bối cảnh, thiết kế kiểm định hoặc quần thể có lý do; không chỉ ở việc có video tim.

**Benchmark đề xuất:** sai số thông số và mức phù hợp với người đọc, theo chất lượng hình ảnh; không chỉ hệ số tương quan. **Gánh nặng:** chuyên gia tim mạch, thống nhất cách đo. **Điều kiện:** video và chuẩn đo thực sự liên kết được.

### O4B — Dấu hiệu phổi theo clip và vùng quét

Đề xuất clip → dấu hiệu, chất lượng và trạng thái không xác định. B-lines/đông đặc là ví dụ theo phạm vi nguồn đối chiếu, không phải bộ nhãn đã được nhóm Y thông qua.

**Đơn vị và thiết yếu:** bệnh nhân → lần khám → vùng quét → clip; thiết bị/cài đặt có thể truy xuất, rubric dấu hiệu, người đọc và chất lượng. Bổ sung sau: nhãn theo thời gian; kết quả bệnh hoặc đáp ứng chỉ khi có chuẩn tham chiếu và mốc khám tương ứng.

**Đối chiếu:** OpenPOCUS [S007](SOURCES.md#s007). Khác biệt ứng viên: cấu trúc thời gian/nhãn hoặc điều kiện thu nhận cụ thể chưa được nguồn gần nhất hỗ trợ; cần kiểm tra trước khi tuyên bố gap.

**Benchmark đề xuất:** nhận diện dấu hiệu cấp clip, theo vùng và chất lượng; khả năng không kết luận khi thiếu bằng chứng. **Rủi ro:** không gán nhãn bệnh của bệnh nhân thành nhãn đúng cho mọi frame. **Điều kiện:** người đọc có chuyên môn và clip có liên kết vùng quét.

O4A và O4B là hai lựa chọn thay thế, không đề xuất gom thành một dataset hỗn hợp.

## 6. Cách thu hẹp, không tự chốt

Hỏi phía Y về nguồn ảnh tổn thương cho O1, dữ liệu đo thận cho O2, quy trình sản khoa cho O3 và video/chuyên gia động tương ứng O4. Một hướng chỉ đi tiếp khi có cả nhu cầu, dữ liệu phù hợp, nhãn/chuẩn tham chiếu, nhân lực và đường tiếp cận hợp lệ.

Ưu tiên khảo sát O2/O3 từng được trợ lý gợi ý vì có thể định nghĩa một phép đo/tiêu chí cụ thể mà chưa gắn ngay với bệnh học. Đây chỉ là nhận định có điều kiện, không phải lựa chọn chính thức hoặc kết luận về tính mới.

Bất đồng chuyên gia và chuyển máy/cơ sở là trục bổ sung cho bất kỳ hướng nào. Chỉ tổ chức test ngoài khi xác minh được nguồn và tránh sự trùng khớp hoàn toàn giữa bệnh, máy và cơ sở. Không mở rộng chỉ để thêm nhãn “đa trung tâm”.

# Source of truth — Trạng thái dự án

Cập nhật: **2026-09-08**. Nguồn xác nhận: các phát biểu trực tiếp của người dùng trong phiên khởi tạo dự án và chỉ định repo. Lịch sử: [DECISIONS](DECISIONS.md). Bản survey ultrasound mới nhất: [SURVEY_2026-09-08](research/SURVEY_2026-09-08.md). Khảo sát chiến lược ngoài ultrasound: [CROSS_MODALITY_WORLD_MODEL_VLA_2026-09-08](research/CROSS_MODALITY_WORLD_MODEL_VLA_2026-09-08.md).

## 1. Đã xác nhận

| Nội dung | Trạng thái chính thức hiện tại |
|---|---|
| Dự án | Một paper dataset siêu âm y tế riêng |
| Nền tảng của người dùng | AI/Computer Vision |
| Cộng tác | Đang hợp tác với một số bạn bên Đại học Y Hà Nội; chưa xác nhận đối tác thu nhận lâm sàng cụ thể |
| Modality hiện tại | Siêu âm |
| Mục tiêu | Tìm nhu cầu dữ liệu có ý nghĩa và khả thi; không chỉ tăng số ảnh |
| Nhu cầu trước mắt | Đề xuất các lựa chọn cơ quan–task–dạng dữ liệu để đối chiếu với khả năng hợp tác phía Y; đồng thời người dùng đang **khảo sát chiến lược** xem longitudinal CT/MRI, retinal imaging hoặc procedural/surgical video có tiềm năng hơn cho VLA/world model/disease-state hay không. Đây chưa phải quyết định đổi modality. |
| Tài liệu mẫu | CariXray và DATE để tham khảo cách viết; `Thuyet minh De tai co so_ver2.docx` là mẫu thuyết minh dùng để nộp bên Đại học Y Hà Nội theo xác nhận của người dùng |
| Repo chính thức | `https://github.com/QuocKhanhLuong/ultrasound-dataset` |
| Quy tắc cập nhật | Chủ động đẩy thay đổi có ý nghĩa về source of truth và knowledge base thành docs vào repo trong các phiên làm việc |

**Không diễn giải hàng “cộng tác” thành một quan hệ hợp tác cấp trường hoặc cam kết cung cấp dữ liệu. Không coi việc khảo sát modality khác là đã rút quyết định siêu âm.**

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
| U13 | Có đổi modality khỏi ultrasound để theo longitudinal CT/MRI/retina/procedural video hay không | **Chưa quyết định; mới là strategic survey** |

Chưa có cơ sở để ghi “đã có dataset”, “đa trung tâm”, “public dataset được phép phát hành”, “đã chạy benchmark” hoặc một cỡ mẫu thu nhận chính thức.

## 3. Phạm vi và giới hạn công việc

Khảo sát có dẫn nguồn; phân biệt ảnh/video, cơ quan, loại nhãn, metadata, nguồn thu nhận và truy cập. Phân tích độ rộng theo các trục độc lập. Chuẩn bị một số cấu hình để gặp phía Y; giữ điều kiện khả thi và gap ứng viên rõ ràng. Đề xuất pilot kiểm tra quy trình trước khi thu lớn.

Chưa thiết kế model mới, chưa viết code cho pipeline/huấn luyện. Không ép ghép dataset ultrasound với world model, VLA hoặc forensic. Tuy nhiên, theo yêu cầu mới của người dùng, được phép **so sánh chiến lược** ultrasound với modality khác dựa trên mức phù hợp với longitudinal disease-state, VLA và medical world models; phải phân biệt rõ khảo sát với quyết định. Không đặt mục tiêu chia một dataset thành nhiều paper. Không lấy nội dung khoa học, cỡ mẫu, ngân sách hoặc nhân sự của mẫu Word làm thông tin của nghiên cứu mới.

## 4. Các hướng ultrasound đang được đề xuất — chưa được người dùng/HMU chọn

Menu ban đầu O1–O4 vẫn được lưu tại [DATA_AND_TASK_OPTIONS](research/DATA_AND_TASK_OPTIONS.md). Sau survey cập nhật 08/09/2026, trợ lý đề xuất shortlist mới dưới đây để **khảo sát tính khớp nguồn dữ liệu**, không phải quyết định dự án:

| Mã | Shortlist khảo sát mới | Điều kiện chính |
|---|---|---|
| A | Full-exam / acquisition-quality / completeness cho một protocol abdominal ultrasound hoặc POCUS cụ thể | Cần full/near-full cine, sweep hoặc sequence đủ đại diện quá trình thu nhận; selected stills đơn thuần không đủ cho claim acquisition |
| B | Kidney multi-view biometry + repeatability / label reliability | Phù hợp hơn nếu chủ yếu có ảnh tĩnh/DICOM nhưng giữ multiple views, patient–exam linkage và calibration |
| C | Adnexal mass exam-level: multi-view + feature/O-RADS + independent readers + pathology/reference | Cần đối tác phụ khoa/chẩn đoán hình ảnh và khả năng liên kết reference standard phù hợp |
| D | Procedural cine cho ultrasound-guided regional anesthesia | Cần video thủ thuật và đối tác gây mê; đã có public brachial-plexus video nên novelty phải sâu hơn “có video” |

**Nhận định của trợ lý, không phải quyết định:** A có novelty upside tốt nếu quá trình quét thực sự được lưu; B có feasibility tốt nếu nguồn thực tế chủ yếu là ảnh tĩnh. C/D phụ thuộc mạnh vào đúng đối tác lâm sàng.

Các hướng basic thyroid classification/detection/segmentation, breast lesion/multimodal, fetal standard-plane/biometry, liver classification, DVT compression video, DDH Graf và diaphragm thickness/excursion đã có comparator mạnh hơn trong 2025–2026. Điều này chỉ làm giảm ưu tiên của cấu hình cơ bản; không chứng minh các cơ quan đó không thể tạo một dataset tốt nếu HMU có cấu trúc dữ liệu hoặc nhu cầu khác biệt.

Chi tiết bằng chứng/gap: [SURVEY_2026-09-08](research/SURVEY_2026-09-08.md) và [SOURCES](research/SOURCES.md).

## 5. Khảo sát chiến lược ngoài ultrasound — chưa phải quyết định đổi modality

Tài liệu [CROSS_MODALITY_WORLD_MODEL_VLA_2026-09-08](research/CROSS_MODALITY_WORLD_MODEL_VLA_2026-09-08.md) tách ba hướng đang hot:

- **VLA/embodied:** tự nhiên nhất với robotic/endoscopic surgical video + action/kinematics và ultrasound scanning trajectories.
- **Physical/procedural world model:** cần state + action + next-state của thủ thuật; surgical video/robotics và probe trajectories phù hợp hơn static imaging.
- **Disease-state/clinical world model:** longitudinal oncology CT, multi-sequence MRI, PET/CT hoặc retinal imaging qua nhiều visit phù hợp hơn; giá trị tăng mạnh nếu có treatment/intervention semantics, lesion correspondence và outcomes.

Các candidate ngoài ultrasound đáng kiểm tra với HMU gồm: X1 longitudinal oncology CT dưới treatment; X2 longitudinal multi-sequence brain MRI; X3 longitudinal fundus/OCT; X4 surgical/endoscopic video + action/kinematics. Chưa candidate nào được chọn.

## 6. Bước tiếp theo

Dùng [phiếu trao đổi HMU](planning/HMU_ALIGNMENT.md) và shortlist A–D để xác nhận: dạng dữ liệu thực tế (selected stills / multiple views / cine / full sweep), patient–exam linkage, calibration/metadata, clinical owner, reader time, reference standard và điều kiện trích xuất nghiên cứu.

Đồng thời hỏi thêm xem ngoài ultrasound phía HMU có nguồn **longitudinal CT/MRI/retinal imaging có patient-time-treatment linkage** hoặc **procedural/surgical video có action/kinematics** hay không. Chỉ khi có nguồn khả thi mới cân nhắc thay đổi U13 và tạo decision record mới.

Sau khi có phản hồi, cập nhật U01–U13 bằng người xác nhận, ngày và bằng chứng được phép chia sẻ. Chỉ khi biết 1–2 nguồn khả thi mới thực hiện systematic novelty check sâu cho đúng anatomy/task và thiết kế [pilot](planning/PILOT_QUALITY_GOVERNANCE.md). Chưa đặt cỡ mẫu nghiên cứu chính thức trước khi primary evaluation target được chốt.

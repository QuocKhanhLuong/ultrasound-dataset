# Source of truth — Trạng thái dự án

Cập nhật: **2026-09-08**. Nguồn xác nhận: các phát biểu trực tiếp của người dùng trong phiên khởi tạo dự án và chỉ định repo. Lịch sử: [DECISIONS](DECISIONS.md). Bản survey ultrasound mới nhất: [SURVEY_2026-09-08](research/SURVEY_2026-09-08.md). Khảo sát chiến lược ngoài ultrasound: [CROSS_MODALITY_WORLD_MODEL_VLA_2026-09-08](research/CROSS_MODALITY_WORLD_MODEL_VLA_2026-09-08.md). Nhánh CT ontology: [CT_ONTOLOGY_SCOPE_SCALE_2026-09-08](research/CT_ONTOLOGY_SCOPE_SCALE_2026-09-08.md).

## 1. Đã xác nhận

| Nội dung | Trạng thái chính thức hiện tại |
|---|---|
| Dự án gốc | Một paper dataset siêu âm y tế riêng |
| Nền tảng của người dùng | AI/Computer Vision |
| Cộng tác | Đang hợp tác với một số bạn bên Đại học Y Hà Nội; chưa xác nhận đối tác thu nhận lâm sàng cụ thể |
| Modality hiện tại của đề tài gốc | Siêu âm |
| Mục tiêu | Tìm nhu cầu dữ liệu có ý nghĩa và khả thi; không chỉ tăng số ảnh |
| Nhu cầu trước mắt | Đề xuất các lựa chọn cơ quan–task–dạng dữ liệu để đối chiếu với khả năng hợp tác phía Y; đồng thời khảo sát longitudinal CT/MRI, retinal imaging hoặc procedural/surgical video cho VLA/world-model/disease-state. |
| Nhánh CT mới | Người dùng muốn **khảo sát song song một longitudinal oncology CT ontology**, theo kiểu hồ sơ bệnh theo thời gian: imaging state + lesion labels/measurements + treatment/intervention + follow-up state + outcome/clinical assessment. Chưa chọn cancer/treatment/response profile/scale. |
| Tài liệu mẫu | CariXray và DATE để tham khảo cách viết; `Thuyet minh De tai co so_ver2.docx` là mẫu thuyết minh dùng để nộp bên Đại học Y Hà Nội theo xác nhận của người dùng |
| Repo chính thức | `https://github.com/QuocKhanhLuong/ultrasound-dataset` |
| Quy tắc cập nhật | Chủ động đẩy thay đổi có ý nghĩa về source of truth và knowledge base thành docs vào repo trong các phiên làm việc |

**Không diễn giải hàng “cộng tác” thành một quan hệ hợp tác cấp trường hoặc cam kết cung cấp dữ liệu. Không coi nhánh CT mới là đã rút quyết định ultrasound hoặc đã xác nhận nguồn CT.**

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
| U14 | CT ontology sẽ chọn cancer nào, treatment family nào, RECIST/mRECIST/iRECIST profile nào, temporal depth và annotation depth nào | **Chưa chốt; đang survey scope/scale** |

Chưa có cơ sở để ghi “đã có dataset”, “đa trung tâm”, “public dataset được phép phát hành”, “đã chạy benchmark” hoặc một cỡ mẫu thu nhận chính thức.

## 3. Phạm vi và giới hạn công việc

Khảo sát có dẫn nguồn; phân biệt ảnh/video, cơ quan, loại nhãn, metadata, nguồn thu nhận và truy cập. Phân tích độ rộng theo các trục độc lập. Chuẩn bị một số cấu hình để gặp phía Y; giữ điều kiện khả thi và gap ứng viên rõ ràng. Đề xuất pilot kiểm tra quy trình trước khi thu lớn.

Chưa thiết kế model mới, chưa viết code cho pipeline/huấn luyện. Không ép dataset ultrasound với world model, VLA hoặc forensic. Theo yêu cầu mới của người dùng, được phép **so sánh chiến lược** ultrasound với modality khác và khảo sát một CT longitudinal oncology ontology dựa trên patient state, lesion state, treatment action, time và outcome; phải phân biệt rõ khảo sát với quyết định modality/paper. Không đặt mục tiêu chia một dataset thành nhiều paper. Không lấy nội dung khoa học, cỡ mẫu, ngân sách hoặc nhân sự của mẫu Word làm thông tin của nghiên cứu mới.

## 4. Các hướng ultrasound đang được đề xuất — chưa được người dùng/HMU chọn

Menu ban đầu O1–O4 vẫn được lưu tại [DATA_AND_TASK_OPTIONS](research/DATA_AND_TASK_OPTIONS.md). Sau survey cập nhật 08/09/2026, trợ lý đề xuất shortlist mới dưới đây để **khảo sát tính khớp nguồn dữ liệu**, không phải quyết định dự án:

| Mã | Shortlist khảo sát mới | Điều kiện chính |
|---|---|---|
| A | Full-exam / acquisition-quality / completeness cho một protocol abdominal ultrasound hoặc POCUS cụ thể | Cần full/near-full cine, sweep hoặc sequence đủ đại diện quá trình thu nhận; selected stills đơn thuần không đủ cho claim acquisition |
| B | Kidney multi-view biometry + repeatability / label reliability | Phù hợp hơn nếu chủ yếu có ảnh tĩnh/DICOM nhưng giữ multiple views, patient–exam linkage và calibration |
| C | Adnexal mass exam-level: multi-view + feature/O-RADS + independent readers + pathology/reference | Cần đối tác phụ khoa/chẩn đoán hình ảnh và khả năng liên kết reference standard phù hợp |
| D | Procedural cine cho ultrasound-guided regional anesthesia | Cần video thủ thuật và đối tác gây mê; đã có public brachial-plexus video nên novelty phải sâu hơn “có video” |

**Nhận định của trợ lý, không phải quyết định:** A có novelty upside tốt nếu quá trình quét thực sự được lưu; B có feasibility tốt nếu nguồn thực tế chủ yếu là ảnh tĩnh. C/D phụ thuộc mạnh vào đúng đối tác lâm sàng.

Chi tiết bằng chứng/gap: [SURVEY_2026-09-08](research/SURVEY_2026-09-08.md) và [SOURCES](research/SOURCES.md).

## 5. Nhánh CT ontology — đang khảo sát scope/scale

Tài liệu chính: [CT_ONTOLOGY_SCOPE_SCALE_2026-09-08](research/CT_ONTOLOGY_SCOPE_SCALE_2026-09-08.md); sổ nguồn riêng: [CT_ONTOLOGY_SOURCES_2026-09-08](research/CT_ONTOLOGY_SOURCES_2026-09-08.md).

Khung hiện tại được đề xuất theo **core + disease-specific profile**:

`Patient -> CancerEpisode -> Timepoint -> CT Study/Series -> Lesion/Measurement/Assessment`

và transition:

`State_t -- treatment/intervention, Δt --> State_t+1`.

Core tham khảo mCODE/FHIR + DICOM/FHIR ImagingStudy + RadLex + DICOM SR TID1500; disease profile có thể là RECIST 1.1, mRECIST cho HCC/TACE hoặc iRECIST cho immunotherapy.

**Khuyến nghị của trợ lý, chưa phải quyết định:** ưu tiên `single disease + single treatment family + longitudinal lesion graph + standardized response + outcome` trước pan-cancer. Candidate ưu tiên khảo sát: HCC/TACE, NSCLC/immunotherapy, HNSCC/radiotherapy. HCC/TACE có alignment world-model rất rõ nhưng đã có HCC-TACE-Seg và Medical World Model comparator; novelty phải sâu hơn pre/post CT.

Không đặt cỡ mẫu chính thức. Với CT longitudinal phải theo dõi scale dạng `(N_patient, N_study, N_timepoint, N_transition, N_lesion, N_action_type, N_reader, N_site)`, không chỉ số ảnh.

## 6. Khảo sát chiến lược ngoài ultrasound — chưa phải quyết định đổi modality

Tài liệu [CROSS_MODALITY_WORLD_MODEL_VLA_2026-09-08](research/CROSS_MODALITY_WORLD_MODEL_VLA_2026-09-08.md) tách ba hướng:

- **VLA/embodied:** tự nhiên nhất với robotic/endoscopic surgical video + action/kinematics và ultrasound scanning trajectories.
- **Physical/procedural world model:** cần state + action + next-state của thủ thuật; surgical video/robotics và probe trajectories phù hợp hơn static imaging.
- **Disease-state/clinical world model:** longitudinal oncology CT, multi-sequence MRI, PET/CT hoặc retinal imaging qua nhiều visit phù hợp hơn; giá trị tăng mạnh nếu có treatment/intervention semantics, lesion correspondence và outcomes.

## 7. Bước tiếp theo

Dùng [phiếu trao đổi HMU](planning/HMU_ALIGNMENT.md) để xác nhận nguồn ultrasound và hỏi thêm về CT: cancer cohort nào giữ được **baseline + response-assessment CT + treatment dates/regimens/procedures + outcome** dưới cùng patient linkage; DICOM/contrast phase/report còn giữ được đến đâu; và clinical owner nào có thể định nghĩa response framework/annotation.

Chỉ khi có nguồn khả thi mới cân nhắc thay đổi U13 và chốt U14. Sau đó mới tính sample size theo primary evaluation target và thiết kế pilot; không chọn N chỉ từ số ảnh/lesion của các public comparator.

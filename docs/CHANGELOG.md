# Lịch sử cập nhật tài liệu

Chỉ ghi thay đổi có ý nghĩa. Ngày theo `YYYY-MM-DD`; thời gian chi tiết và tác giả kỹ thuật truy vết bằng lịch sử commit. Changelog không thay thế nhật ký quyết định hoặc bằng chứng thực nghiệm.

## 2026-09-08 — Thêm nhánh CT longitudinal oncology ontology và survey scope/scale

**Nguồn thay đổi:** người dùng xác nhận muốn khảo sát thêm một bộ CT ontology theo hồ sơ bệnh theo thời gian và hỏi cách chọn scale/scope.

**Nội dung mới/sửa:**

- Thêm `docs/research/CT_ONTOLOGY_SCOPE_SCALE_2026-09-08.md` để tách rõ scope (disease/treatment/temporal/anatomy/annotation/clinical breadth) khỏi scale `(N_patient, N_study, N_timepoint, N_transition, N_lesion, N_action_type, N_reader, N_site)`.
- Đề xuất ontology kiểu `core + disease-specific profile`: mCODE/FHIR + DICOM/FHIR ImagingStudy + RadLex + DICOM SR TID1500 ở core; RECIST 1.1/mRECIST/iRECIST làm response profile theo bệnh/treatment.
- Survey comparator CT longitudinal: Longitudinal-CT 2026, HCC-TACE-Seg, RECIST CT dataset 2026, Anti-PD-1 Lung, HNSCC-3DCT-RT và Medical World Model ICCV 2025.
- Đề xuất ưu tiên khảo sát single disease + single treatment family trước pan-solid. Candidate có điều kiện: HCC/TACE, NSCLC/immunotherapy, HNSCC/radiotherapy. Đây chưa phải lựa chọn của HMU/người dùng.
- Thêm `docs/research/CT_ONTOLOGY_SOURCES_2026-09-08.md` làm source register riêng cho nhánh CT trước khi quyết định hợp nhất vào sổ nguồn ultrasound.
- Cập nhật `DECISIONS.md` với D005: khảo sát song song CT longitudinal oncology ontology; không ghi là đã bỏ ultrasound.
- Cập nhật `SOURCE_OF_TRUTH.md` thêm U14 theo dõi cancer/treatment/response profile/temporal depth/annotation depth của CT ontology.

**Không thay đổi:** chưa chọn HCC/NSCLC/HNSCC; chưa xác nhận nguồn CT/PACS/EHR ở HMU; chưa chọn RECIST profile chính; chưa đặt sample size; chưa biến paper thành world-model paper hoặc claim causal treatment effect.

**Bước tiếp theo:** hỏi HMU cohort nào giữ được baseline + response-assessment CT + treatment timeline + outcome dưới cùng patient linkage, rồi mới chốt disease/treatment scope và tính scale dựa trên primary evaluation target.

## 2026-09-08 — Khảo sát cross-modality cho VLA, world model và disease-state

**Nguồn thay đổi:** người dùng hỏi liệu ngoài ultrasound có modality nào tiềm năng hơn trong bối cảnh VLA, medical world models và mô hình hóa state/progression của bệnh.

**Nội dung mới/sửa:**

- Thêm `docs/research/CROSS_MODALITY_WORLD_MODEL_VLA_2026-09-08.md` để phân biệt VLA, physical/procedural world model và clinical/disease-state world model.
- Tổng hợp bằng chứng cập nhật 2025–2026: Medical World Model (ICCV 2025), X-WIN (CVPR 2026), MICCAI 2026 Medical World Model Workshop, SurgLaVi/Action Planning, US-VLA, Longitudinal-CT 2026, RETFound Plus 2026 và Time-Aware Multi-View MRI benchmark (preprint 2026).
- Đề xuất shortlist ngoài ultrasound để kiểm tra với HMU: X1 longitudinal oncology CT + treatment; X2 longitudinal multi-sequence brain MRI; X3 longitudinal fundus/OCT; X4 surgical/endoscopic video + action/kinematics.
- Ghi chiến lược: longitudinal CT/MRI có độ khớp cao hơn static ultrasound nếu mục tiêu là disease-state/world-model; surgical robotic video và ultrasound trajectories có độ khớp cao nhất với VLA/physical world model.
- Cập nhật `SOURCE_OF_TRUTH.md` thêm U13 để theo dõi việc có đổi modality khỏi ultrasound hay không. **U13 chưa quyết định.** Việc khảo sát modality khác không rút quyết định ultrasound hiện tại.

**Không thay đổi:** chưa chọn CT/MRI/retina/surgical video; chưa xác nhận HMU có các nguồn này; chưa thay đổi paper thành VLA/world-model paper; chưa thiết kế model hoặc cỡ mẫu.

**Bước tiếp theo:** hỏi HMU về longitudinal patient-time-treatment linkage ngoài ultrasound và procedural video/action state; chỉ đổi modality nếu có một nguồn cụ thể vừa có feasibility vừa trả lời research question tốt hơn.

## 2026-09-08 — Mở rộng survey và thu hẹp shortlist khảo sát

**Nguồn thay đổi:** khảo sát web cập nhật đến 08/09/2026 theo yêu cầu tiếp tục survey/gợi ý dataset nên làm; ưu tiên paper gốc, trang dataset và directory NIDUS.

**Nội dung mới/sửa:**

- Thêm `docs/research/SURVEY_2026-09-08.md` với bản đồ landscape mới, các hướng đã cạnh tranh mạnh và shortlist bốn cấu hình A–D để mang sang HMU.
- Đổi tiêu chí khuyến nghị từ “tìm cơ quan chưa có dataset” sang tìm **cấu trúc dữ liệu/nhãn/protocol đánh giá còn thiếu cho một nhu cầu lâm sàng cụ thể**.
- Shortlist đề xuất của trợ lý: (A) full-exam/acquisition-quality/completeness cho một protocol abdominal/POCUS; (B) kidney multi-view biometry + repeatability; (C) adnexal mass exam-level O-RADS + reader + pathology; (D) procedural cine cho ultrasound-guided regional anesthesia. Đây **không phải quyết định** của Alvin/HMU.
- Ghi nhận các vùng đã có comparator mạnh hơn trong 2025–2026: ThyroidXL, BUS-CoT, fetal biometry/video/quality, SMC-LUD/NAFLD, ThrombUS+, DDH và diaphragm resources. “De-prioritize” chỉ là đánh giá tương đối, không kết luận các cơ quan đó hết giá trị nghiên cứu.
- Mở rộng `docs/research/SOURCES.md` từ S001–S010 lên S001–S030; sửa S002: Open Kidney đã có chapter peer-reviewed tại ASMUS 2023/MICCAI Workshops, không còn ghi như nguồn chỉ có preprint.
- Giữ tách biệt gap có bằng chứng cục bộ với gap ứng viên cần systematic verification. Không có claim “first” mới được chốt.

**Không thay đổi source of truth:** cơ quan, bệnh lý, task, tĩnh/video, nguồn dữ liệu, chuyên gia, phê duyệt và khả năng public vẫn chưa được xác nhận. Không thêm quyết định vào `DECISIONS.md`; chưa đặt cỡ mẫu hoặc thiết kế model.

**Bước tiếp theo:** dùng shortlist như menu cho buổi alignment HMU; ưu tiên xác nhận dạng dữ liệu thực tế (selected still / multiple views / cine / full sweep), patient–exam linkage, calibration/metadata, clinical owner và reference standard. Sau đó mới chọn 1–2 hướng để systematic novelty check sâu hơn và pilot.

## 2026-09-07 — Khởi tạo kho tài liệu chính thức

**Nguồn thay đổi:** người dùng chỉ định `QuocKhanhLuong/ultrasound-dataset` và yêu cầu chủ động đẩy cập nhật source of truth/knowledge base.

**Nội dung trong đợt khởi tạo:**

- Tổng hợp bối cảnh, phạm vi đã xác nhận và 12 nhóm quyết định/điều kiện còn mở.
- Lưu bốn nhóm hướng theo nhu cầu–task–dạng dữ liệu để trao đổi phía Y, với hai nhánh thay thế ở nhóm siêu âm động.
- Lập bảng đối chiếu dataset và sổ nguồn; phân biệt nguồn đã kiểm tra mô tả, nguồn chỉ đọc được kết quả tìm kiếm và nguồn chờ xác minh. Không coi đây là systematic review hay audit các gói dữ liệu.
- Ghi mâu thuẫn thống kê giữa paper ThyroidXL và dataset card; ghi rõ Open Kidney được trang tác giả dẫn bằng preprint. Chưa dùng số liệu nguồn mâu thuẫn làm một giá trị đã được chuẩn hóa.
- Thêm phiếu trao đổi HMU, khung pilot/chất lượng/quản trị và vai trò ba tài liệu mẫu.
- Thêm hướng dẫn duy trì docs và `.gitignore` phòng commit nhầm tệp riêng tư.

**Không thay đổi:** chưa chọn cơ quan/task/format; chưa thu nhận dữ liệu, phê duyệt protocol, chạy benchmark hoặc viết code nghiên cứu. Không upload PDF/DOCX gốc, dữ liệu lâm sàng hoặc thông tin liên hệ trong mẫu thuyết minh.

**Bước tiếp theo:** lấy phản hồi thực tế từ phía Y qua `planning/HMU_ALIGNMENT.md`, rồi cập nhật source of truth và thu hẹp phương án khi có đủ căn cứ.

## Mẫu cập nhật sau

Ngày; nguồn thay đổi; nội dung mới/sửa; quyết định liên quan; giới hạn của bằng chứng; tài liệu bị ảnh hưởng; hành động tiếp theo. Chỉ ghi “đã đồng bộ” sau khi xác nhận được trạng thái Git từ công cụ.

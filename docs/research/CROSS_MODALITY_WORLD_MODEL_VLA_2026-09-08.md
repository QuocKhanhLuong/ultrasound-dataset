# Cross-modality opportunities — VLA, medical world models và disease-state datasets

Cập nhật: 2026-09-08. **Trạng thái: khảo sát chiến lược, chưa thay đổi quyết định modality siêu âm của dự án.** Người dùng đang kiểm tra liệu ngoài ultrasound có modality nào phù hợp hơn với các xu hướng VLA, world model và longitudinal disease-state modelling. Tài liệu này so sánh hướng nghiên cứu; không khẳng định HMU có quyền truy cập các dữ liệu nêu dưới đây.

## 1. Không đồng nhất VLA, world model và disease-state modelling

- **VLA (vision-language-action):** nhận observation thị giác + mục tiêu/ngôn ngữ và sinh action. Trong y tế, action tự nhiên nhất ở robotic surgery, endoscopy/interventional procedures và robotic/automated ultrasound scanning.
- **Physical/procedural world model:** học dynamics của môi trường/thủ thuật, ví dụ trạng thái mô và dụng cụ thay đổi dưới tác động của một action.
- **Clinical/disease world model:** biểu diễn trạng thái bệnh nhân và học chuyển trạng thái theo thời gian, lý tưởng là có conditioning bởi điều trị/intervention. Longitudinal imaging chỉ là progression modelling nếu không có action/intervention semantics rõ.

Dataset gần với world-model tuple nên cố gắng bảo tồn: `state_t`, `action/intervention_t`, `delta_t`, `state_t+1`, clinical context và outcome/reference. Nếu không có action thì vẫn là longitudinal state modelling có giá trị, nhưng không nên tự gọi là action-conditioned world model.

## 2. Bằng chứng xu hướng 2025–2026

### Medical world model đã chuyển từ ý tưởng sang venue lớn

- **Medical World Model (ICCV 2025)** mô phỏng tiến triển/regression khối u dưới clinical treatment actions cho TACE. Paper dùng longitudinal pre/post-treatment CT, tumor masks, treatment records và survival. Đây là ví dụ rất sát cấu trúc `state -> treatment action -> future state`: https://openaccess.thecvf.com/content/ICCV2025/html/Yang_Medical_World_Model_ICCV_2025_paper.html
- **X-WIN (CVPR 2026)** gọi một chest-radiograph predictive-sensing model là CXR world model, học structural/volumetric knowledge từ CT để dự đoán projections. Điều này cho thấy thuật ngữ “world model” hiện được dùng rộng hơn disease progression; cần định nghĩa state/action/dynamics cụ thể trong từng paper: https://openaccess.thecvf.com/content/CVPR2026/html/Yang_X-WIN_Building_Chest_Radiograph_World_Model_via_Predictive_Sensing_CVPR_2026_paper.html
- **MICCAI 2026 Medical World Model Workshop** tập trung multimodal integration, digital twins, patient-specific trajectory/causal learning và simulation-based decision support: https://mwm2026.github.io/
- Hai review medical-world-model 2026 trên arXiv nhấn mạnh ba/four capability chính quanh patient state, temporal dynamics, intervention-conditioned simulation và planning; đây là review/preprint, không dùng để chứng minh clinical maturity: https://arxiv.org/abs/2606.16721 và https://arxiv.org/abs/2607.25242

### VLA trong medicine hiện mạnh nhất ở embodied/procedural domains

- **Surgical Action Planning, MICCAI 2025** dự đoán future surgical action plans từ visual inputs, cho thấy predictive planning đã trở thành benchmark direction: https://papers.miccai.org/miccai-2025/0882-Paper0426.html
- **SurgLaVi, Medical Image Analysis 2026** có 240k hierarchical surgical clip-caption pairs trên hơn 200 procedures; open derivative 113k pairs. Đây là bằng chứng mạnh cho video-language data engine trong surgery: https://www.sciencedirect.com/science/article/pii/S1361841526000514
- **npj Digital Surgery 2026** nêu bottleneck của surgical VLA là thiếu synchronized visual observations, robot kinematics và control commands; physical AI world models được xem là hướng để mô hình hóa/sinh dynamics: https://doi.org/10.1038/s44484-026-00008-4
- **US-VLA (ACM MM 2026; arXiv 2608.16074)** cho thấy ultrasound không đứng ngoài VLA: dataset của paper có 320 expert abdominal scanning trajectories và khoảng 80k synchronized timesteps cho liver/kidney standard planes. Vì vậy static ultrasound có thể crowded, nhưng acquisition trajectories lại là một VLA-compatible data type: https://arxiv.org/abs/2608.16074

### Longitudinal disease state đang tăng rất nhanh

- **Longitudinal-CT, Scientific Data 2026:** 300 bệnh nhân metastatic melanoma, baseline + follow-up trong systemic therapy, 7,182 manually segmented lesions với lesion correspondence và evolution labels (persistence, regression, merging, new appearance). Đây là blueprint rất mạnh cho dataset state transition: https://www.nature.com/articles/s41597-026-07466-y
- **RETFound Plus, npj Digital Medicine 2026:** temporal modelling trên 1,304,292 fundus photographs từ 304,345 participants qua nhiều visits cải thiện progression/risk prediction. Retina rất phù hợp longitudinal state modelling ở scale lớn: https://www.nature.com/articles/s41746-026-02524-6
- **Time-Aware Multi-View MRI benchmark, arXiv Aug 2026 — preprint:** 890 patients, >3,200 longitudinal MRI timepoints và 3,920 expert-verified QA pairs; 16 VLMs vẫn gặp lỗi direction-of-change và volumetric reasoning. Đây là bằng chứng mới về gap temporal reasoning, nhưng hiện là preprint: https://arxiv.org/abs/2608.13309

## 3. Ranking modality theo loại research question

| Modality/data type | VLA/embodied | Physical world model | Disease-state world model | Dataset-paper upside | Main bottleneck |
|---|---:|---:|---:|---:|---|
| Robotic/endoscopic surgical video + kinematics/actions | 5/5 | 5/5 | 2/5 | Rất cao | Khó lấy synchronized action/robot state; governance nặng |
| Ultrasound cine + probe trajectory/robot state | 5/5 | 5/5 | 2–3/5 | Cao nếu có trajectories thật | Cần probe pose/action và standardized acquisition; US-VLA đã xuất hiện |
| Longitudinal oncology CT + treatment | 1/5 | 2/5 | 5/5 | Rất cao | Cần pre/post linkage, treatment semantics, lesion correspondence/outcomes |
| Longitudinal multi-sequence MRI | 1/5 | 2/5 | 5/5 | Rất cao | Follow-up dài, registration/multi-sequence complexity, cohort heterogeneity |
| Fundus/OCT longitudinal | 0–1/5 | 1/5 | 4–5/5 | Cao nhưng cạnh tranh mạnh | Large FMs/datasets đã mạnh; cần trajectory/outcome question rõ |
| Serial CXR + reports | 0/5 | 2–3/5 | 3/5 | Trung bình | Rất crowded, 2D projection; novelty khó nếu chỉ temporal labels |
| Digital pathology | 0/5 | 1/5 | 2–3/5 | Cao cho multimodal, thấp hơn cho dynamics | Thường cross-sectional; serial biopsies hiếm |
| PET/CT longitudinal | 0/5 | 1–2/5 | 5/5 | Cao | Scarcity, harmonization, therapy-specific cohorts |

Điểm trên là đánh giá chiến lược của trợ lý dựa trên độ tự nhiên của state/action/transition và mức cạnh tranh hiện tại; không phải benchmark định lượng hoặc quyết định dự án.

## 4. Shortlist ngoài ultrasound đáng khảo sát với HMU

### X1 — Longitudinal oncology CT: lesion state transition under therapy

**Schema:** patient -> baseline CT -> lesions -> treatment/intervention -> follow-up CT -> lesion correspondence -> outcome.

**Primary research questions:** lesion nào persist/regress/new; tổng burden thay đổi ra sao; treatment-conditioned future state; uncertainty khi correspondence mơ hồ.

**Điểm mạnh:** gần trực tiếp với Medical World Model và Longitudinal-CT; có thể tạo dataset rất có giá trị nếu HMU có treatment-linked longitudinal scans.

**Điều kiện tối thiểu:** patient/time linkage, treatment dates/types, follow-up imaging, lesion annotations/correspondence trên subset, clinical owner. Không tự gọi causal treatment-response dataset nếu treatment selection confounded và thiết kế chỉ retrospective.

### X2 — Longitudinal multi-sequence brain MRI

**Targets ứng viên:** glioma/brain metastasis progression, post-treatment change, neurodegeneration hoặc một bệnh có serial MRI rõ.

**Schema:** patient -> timepoint -> multi-sequence/multi-view -> lesion/anatomical state -> interval change labels -> treatment/context.

**Benchmark:** temporal ordering, change localization, progression/stable/regression, volumetric delta, multi-view temporal reasoning.

**Điểm mạnh:** rất tự nhiên cho “state of disease”; preprint Time-Aware MRI 2026 cho thấy current foundation models còn yếu ở direction-of-change và volumetric reasoning.

**Bottleneck:** acquisition protocol khác nhau theo time; pseudoprogression/post-treatment effects; registration; expert time.

### X3 — Longitudinal retinal CFP/OCT

**Schema:** eye/patient -> visit_t -> CFP/OCT volume -> disease grade/biomarkers -> treatment -> visit_t+1.

**Targets:** progression risk, biomarker trajectory, response to anti-VEGF hoặc glaucoma/DR progression tùy nguồn thật.

**Điểm mạnh:** repeated visits rất tự nhiên, imaging standardized hơn CT/MRI ở nhiều settings, scale tiềm năng lớn.

**Bottleneck:** field đã có foundation models/large datasets mạnh; novelty phải nằm ở richer longitudinal intervention/outcome structure hoặc population/domain gap có ý nghĩa, không chỉ số ảnh.

### X4 — Surgical/endoscopic video + action/kinematics

**Schema lý tưởng:** procedure -> video frames/clips + phase/step/tool-tissue state + robot/tool kinematics/control + event/outcome.

**Targets:** next-action prediction, action planning, state transition, counterfactual/safety event prediction.

**Điểm mạnh:** aligned nhất với VLA + physical world models và hiện rất hot.

**Bottleneck:** khó nhất về data access; nếu chỉ có public teaching video + text mà không có action/kinematics thì phù hợp VLM/video-language hơn true VLA.

## 5. Kết luận chiến lược cho dự án hiện tại

- Nếu mục tiêu là **dataset paper gắn disease-state/world-model trend**, ưu tiên khảo sát **longitudinal CT/MRI** hơn static ultrasound.
- Nếu mục tiêu là **VLA/embodied medical AI**, **surgical robotic video** và **ultrasound scanning trajectories** là hai dạng tự nhiên nhất. Ultrasound không hề yếu ở đây; ngược lại probe action trực tiếp thay đổi observation nên có structure VLA rất rõ.
- Nếu mục tiêu là **feasibility + temporal state at scale**, retina (fundus/OCT) rất hấp dẫn nhưng cạnh tranh mạnh.
- Một dataset chỉ có ảnh tại một timepoint + class/mask không trở thành world-model dataset chỉ vì benchmark sau này dùng model tên “world model”. Giá trị cần nằm ở state, transition và nếu có thể action/intervention.

### Câu hỏi alignment mới cho HMU

1. Ngoài ultrasound, nhóm có quyền tiếp cận longitudinal CT/MRI/retinal imaging có patient-level time linkage và treatment/follow-up hay không?
2. Có khoa/thủ thuật nào lưu video cùng action/kinematics/robot state hoặc ít nhất thao tác/procedure phase theo thời gian không?
3. Trong nguồn longitudinal nào, clinical team có thể định nghĩa state transition/reference đáng tin cậy (lesion correspondence, progression, response, event) thay vì chỉ final diagnosis?

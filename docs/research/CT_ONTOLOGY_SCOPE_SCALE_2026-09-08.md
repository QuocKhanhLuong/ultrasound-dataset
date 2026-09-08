# CT oncology ontology — khảo sát scope và scale

Cập nhật: **2026-09-08**. **Trạng thái: hướng nghiên cứu được người dùng yêu cầu khảo sát thêm; chưa thay thế quyết định ultrasound hiện tại và chưa chọn bệnh/treatment cụ thể.** Nguồn CT riêng: [CT_ONTOLOGY_SOURCES_2026-09-08](CT_ONTOLOGY_SOURCES_2026-09-08.md).

## 1. Ý tưởng cốt lõi

Không xây một “ontology CT” theo nghĩa liệt kê mọi bệnh có thể thấy trên CT. Với mục tiêu longitudinal disease-state/world-model, cấu trúc nên là:

`Patient -> CancerEpisode -> Timepoint -> ImagingStudy/Series -> LesionObservation -> Measurement/Assessment`

và giữa hai timepoint:

`State_t --Treatment/Intervention_t, Δt--> State_t+1`

Các lesion phải có identity/correspondence theo thời gian. Radiology report là một lớp evidence/assessment, không đồng nhất với ground truth duy nhất.

Khuyến nghị thiết kế ontology theo **core + disease-specific profile**:

- Core: patient, diagnosis, timepoint, study/series, lesion, anatomy, measurement, treatment, outcome, provenance.
- Generic solid-tumor profile: RECIST 1.1.
- HCC/TACE profile: mRECIST + arterial enhancement + TACE protocol.
- Immunotherapy profile: iRECIST + confirmed/unconfirmed progression.
- Các bệnh khác chỉ thêm profile khi nguồn thực tế yêu cầu.

Core có thể map tới mCODE/FHIR; imaging identifiers theo DICOM/FHIR ImagingStudy; imaging terminology theo RadLex; quantitative lesion tracking có thể tham khảo DICOM SR TID 1500.

## 2. Phải tách `scope` và `scale`

### Scope = dataset nói về cái gì

| Trục | Hẹp | Rộng | Rủi ro khi mở rộng quá sớm |
|---|---|---|---|
| Disease | 1 cancer | pan-solid cancers | biology/response criteria/treatment khác nhau |
| Treatment | 1 treatment family | mọi treatment | action semantics quá hỗn tạp |
| Temporal | baseline + 1 follow-up | full treatment course | missing visits/protocol drift/annotation cost |
| Anatomy | một vùng CT chính | whole-body | nhiều lesion types + reporting complexity |
| Lesion depth | target lesions | exhaustive all lesions | annotation cost tăng rất mạnh |
| Clinical depth | treatment + response/outcome | full EHR/labs/genomics | missingness và governance tăng mạnh |
| Acquisition | 1 site/protocol | multi-site/multi-scanner | harmonization, domain shift, governance |

### Scale = dataset lớn đến đâu trên nhiều trục

Không dùng `N images` làm scale chính. Với longitudinal CT, nên theo dõi vector:

`(N_patient, N_study, N_timepoint, N_transition, N_lesion, N_action_type, N_reader, N_site)`

- **N_patient:** đơn vị độc lập cho split/evaluation.
- **N_transition:** số cặp state→state có treatment/time ở giữa; trực tiếp hơn cho progression/world-model tasks.
- **N_lesion:** khối lượng annotation/training signal nhưng không phải ca độc lập.
- **N_timepoint:** độ sâu temporal trên mỗi bệnh nhân.
- **N_action_type:** độ đa dạng treatment; quá ít action thì không đủ để nghiên cứu treatment selection, nhưng vẫn có thể nghiên cứu dynamics dưới một treatment family.
- **N_reader/N_site:** quyết định có benchmark reliability/generalization hay không.

## 3. Landscape cho thấy scale rất đa dạng

| Resource | Patient scale | Temporal depth | Annotation/clinical depth | Bài học |
|---|---:|---:|---|---|
| RECIST CT dataset 2026 [CT10] | 22 | 1–4 studies/patient | 1.246 segmented lesions + 82 target RECIST measurements | patient N nhỏ vẫn có dataset paper nếu annotation rất sâu |
| HNSCC-3DCT-RT [CT12] | 31 | 3 CT states | RTSTRUCT/RTDOSE + anatomy + outcomes | action/dose structure có thể quan trọng hơn patient count |
| Anti-PD-1 Lung [CT11] | 46 | pre + mostly 1 follow-up | treatment-specific longitudinal imaging | two-state immunotherapy đã có precedent |
| HCC-TACE-Seg [CT09] | 105 | pre/post treatment studies | segmentations + treatment/follow-up + TTP/OS | HCC/TACE pre-post đơn thuần không còn novel |
| Longitudinal-CT 2026 [CT08] | 300 | exactly 2 timepoints | 7.182 lesions + exhaustive correspondence | lesion graph quy mô lớn đã có benchmark mạnh |

Không có “magic N” từ bảng này. Cỡ mẫu chính thức phải dựa trên primary evaluation target, cohort availability và precision/power. Các số trên chỉ là comparator để đặt tham vọng và chi phí annotation.

## 4. Ba scope khả thi nhất

### S1 — Single disease + single treatment family + 2-state CT ontology

**Cấu trúc:** baseline CT -> lesions/measurements -> one treatment episode -> first response CT -> response/outcome.

**Ưu:** khả thi nhất; ontology sạch; ít ambiguity về action.

**Nhược:** dễ bị reviewer xem là “pre/post dataset” nếu không có lesion correspondence, standardized response criteria, provenance và clinical outcome.

**Dùng khi:** HMU chỉ có baseline + first follow-up đáng tin cậy.

### S2 — Single disease + full treatment trajectory

**Cấu trúc:** T0 -> treatment/cycle 1 -> T1 -> treatment/cycle 2 -> T2 -> … -> terminal/last follow-up outcome.

**Ưu:** phù hợp disease-state/world-model nhất; học được trajectory thay vì một delta.

**Nhược:** missing visits, treatment changes, censoring, registration và lesion correspondence khó hơn rất nhiều.

**Dùng khi:** bệnh viện giữ longitudinal linkage qua nhiều đợt điều trị và có timeline treatment rõ.

### S3 — Pan-solid RECIST ontology

**Cấu trúc:** nhiều cancer types nhưng dùng common RECIST core; treatment/outcome được chuẩn hóa qua mCODE-like fields.

**Ưu:** reusable, broad, phù hợp foundation/RECIST automation.

**Nhược:** treatment semantics và biology quá heterogenous; khó làm world-model action-conditioned nghiêm túc. RECIST CT dataset 2026 [CT10] đã chứng minh pan-cancer + comprehensive segmentation là một comparator trực tiếp.

**Dùng khi:** nguồn dữ liệu mỗi bệnh riêng lẻ quá ít nhưng hospital có kho RECIST longitudinal lớn và structured.

**Khuyến nghị hiện tại:** ưu tiên **S1 hoặc S2**, không bắt đầu bằng S3.

## 5. Ranking disease/treatment để khảo sát với HMU

### #1 — HCC + TACE, nếu có multi-phase CT và treatment records

**Response profile:** mRECIST [CT07].

**State đặc thù:** total lesion, arterially enhancing viable tumor, necrotic/non-enhancing component, lesion location, target/non-target status, liver disease context nếu cần.

**Action:** TACE episode/protocol; nếu record đủ, có thể giữ drug/embolization material, procedure date và repeat TACE.

**Why strong:** `state -> explicit intervention -> future state` rất tự nhiên; Medical World Model ICCV 2025 dùng đúng HCC/TACE [CT13].

**Novelty pressure:** HCC-TACE-Seg đã có 105 subjects + pre/post CT + treatment/follow-up/outcomes [CT09]. Vì vậy dataset mới không được dừng ở “pre/post HCC CT”. Khác biệt đáng khảo sát: nhiều TACE cycles, lesion correspondence qua toàn course, mRECIST + volumetric/viable-tumor labels, treatment protocol detail, multi-reader uncertainty, richer outcomes.

**Main risk:** multiphase CT phải đủ/đúng phase; viable enhancement khó label; retrospective treatment choice không cho phép causal claim.

### #2 — NSCLC + immune checkpoint therapy

**Response profile:** RECIST 1.1 + iRECIST [CT05–CT06].

**State:** primary/metastatic target lesions, nodes, new lesions, tumor burden, iRECIST disease state.

**Action:** anti-PD-1/PD-L1 regimen/cycle timeline.

**Why strong:** CT là modality routine; immunotherapy có response dynamics đặc thù, iRECIST phân biệt progression cần xác nhận.

**Comparator:** Anti-PD-1 Lung có 46 cases, pre-treatment và most one follow-up [CT11]. Candidate gap đáng kiểm tra là multi-timepoint + lesion graph + iRECIST confirmation + treatment/outcome, không phải “lung CT before/after immunotherapy” nói chung.

**Main risk:** regimen combinations, pseudoprogression hiếm, PET/other modalities có thể xen vào; cần oncologist/radiologist đồng thuận protocol.

### #3 — HNSCC + radiotherapy

**Response/action profile:** RT treatment course; anatomy/tumor state + RTPLAN/RTDOSE nếu có.

**Why strong:** radiotherapy là action có dose/spatial structure rất rõ; thích hợp cả disease-state lẫn dose-conditioned anatomical dynamics.

**Comparator:** HNSCC-3DCT-RT có 31 patients và 3 timepoints với RT structures/dose/outcomes [CT12].

**Opportunity:** larger longitudinal course, adaptive RT/replanning, richer lesion/anatomy correspondence hoặc outcomes.

**Main risk:** scope dễ trượt sang radiotherapy physics/deformable anatomy thay vì cancer-state ontology; cần quyết định primary question.

### #4 — Metastatic melanoma systemic therapy

Longitudinal-CT 2026 [CT08] là comparator rất mạnh: 300 patients, 7.182 lesions, exhaustive lesion correspondence ở hai timepoints. Chỉ nên chọn nếu HMU có thứ mà resource này thiếu rõ rệt, ví dụ nhiều timepoints, detailed treatment, iRECIST/outcome hoặc population/protocol riêng có ý nghĩa.

### #5 — Lymphoma

Lugano [CT14] dùng PET-CT cho FDG-avid lymphomas; CT-only scope dễ không phản ánh chuẩn response chính. Không ưu tiên nếu mục tiêu là một CT ontology sạch, trừ khi nhóm lâm sàng có use case cụ thể với histology low/variable FDG avidity hoặc setting không có PET.

## 6. Minimal Viable Ontology (MVO) đề xuất

### Bắt buộc ở v1

1. **Patient/Cancer episode:** pseudonymous patient ID; primary cancer; histology khi có; stage/status source.
2. **Timepoint:** study date/time relative; baseline/follow-up role; interval from previous state.
3. **ImagingStudy/Series:** DICOM Study/Series UIDs, anatomy, contrast phase, scanner/protocol fields cần thiết.
4. **Lesion:** stable lesion ID; anatomy/site; target/non-target/new; primary/metastasis/node; lesion correspondence edges.
5. **Measurement:** diameter theo response framework; volume nếu mask có; measurement source/reader.
6. **Assessment:** RECIST/mRECIST/iRECIST state phù hợp; radiologist conclusion giữ riêng.
7. **Treatment episode:** type, date interval, regimen/protocol level đủ để phân biệt actions.
8. **Outcome:** response/progression event; PFS/TTP/OS hoặc other endpoint chỉ khi có định nghĩa và censoring rõ.
9. **Provenance:** annotator/reader role, manual/derived, version, adjudication status.

### Extension, không bắt buộc v1

ECOG/Karnofsky, labs, tumor markers, genomics, pathology slides, toxicity, dose-level detail, PET/MRI, full free-text EHR.

Lý do: mCODE [CT01] đã cho thấy oncology information rất rộng; dataset đầu tiên không nên cố thu đủ mọi profile.

## 7. Scope/scale recommendation hiện tại

Nếu chưa biết nguồn HMU, đề xuất working target:

**Core:** `single cancer + single treatment family + CT longitudinal + lesion graph + standardized response + outcome + provenance`.

**Temporal:** ưu tiên toàn bộ các response-assessment CT trong một treatment course nếu truy xuất được; nếu không, baseline + first response CT vẫn có thể là v1 nhưng phải ghi giới hạn.

**Lesion annotation:** không mặc định exhaustive masks cho mọi lesion ở mọi timepoint. Có thể tách:

- Tier A: target lesions + measurements + correspondence cho toàn cohort.
- Tier B: full 3D masks cho target lesions hoặc representative subset.
- Tier C: exhaustive all-lesion masks chỉ nếu annotation capacity đủ và đó là đóng góp chính.

**Clinical fields:** treatment/action + primary response/outcome là core; labs/genomics là extension.

**Site:** một site vẫn có thể publish được nếu ontology/annotation sâu. Multi-site chỉ thêm khi có nguồn thật; không biến multi-site thành điều kiện khiến dự án không khởi động.

## 8. Cách quyết định scale mà không bịa sample size

Trước khi chốt N, pilot phải ước lượng được:

- tỷ lệ bệnh nhân có >=2 CT hợp lệ trong cùng treatment episode;
- tỷ lệ còn đủ contrast phase/protocol cần thiết;
- tỷ lệ treatment timeline nối được với scan;
- lesion count/patient và thời gian annotate/track mỗi lesion;
- tỷ lệ mất follow-up/outcome;
- inter-reader disagreement cho response/lesion correspondence;
- distribution của treatment actions và response classes.

Sau đó mới chọn cỡ test set theo metric chính và uncertainty mong muốn. Với world-model/forecasting, `N_transition` và coverage của action/state quan trọng hơn chỉ tăng `N_image`.

## 9. Ba câu hỏi HMU cần trả lời để chọn scope

1. Có cancer cohort nào giữ được **CT baseline + các response-assessment CT sau đó + treatment dates/regimen/procedure + outcome** ở cùng patient ID không?
2. Trong các cohort đó, HCC/TACE, NSCLC/immunotherapy hoặc HNSCC/radiotherapy hướng nào có clinical owner sẵn sàng định nghĩa response framework và hỗ trợ annotation/verification?
3. PACS/EHR hiện giữ được original DICOM, contrast phase/protocol, report và linkage sang treatment/outcome ở mức nào; có bao nhiêu timepoints thực tế trên một bệnh nhân trước khi mất follow-up?
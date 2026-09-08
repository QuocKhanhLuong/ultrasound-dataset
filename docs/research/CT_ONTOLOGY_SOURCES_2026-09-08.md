# Sổ nguồn riêng — CT ontology / longitudinal oncology

Cập nhật: **2026-09-08**. Tài liệu này là sổ nguồn riêng cho nhánh khảo sát CT longitudinal oncology để tránh trộn bằng chứng mới vào sổ ultrasound trước khi dự án quyết định đổi modality. Các nguồn dưới đây đã được kiểm tra ở mức paper/trang tiêu chuẩn/trang dataset; **chưa có dataset nào được dự án tải và audit toàn bộ**.

## CT01 — mCODE 4.0.0

- **Nguồn:** HL7 FHIR minimal Common Oncology Data Elements (mCODE) Implementation Guide v4.0.0, active 2025-02-16.
- **URL:** https://hl7.org/fhir/us/mcode/
- **Vai trò:** khung dữ liệu oncology có cấu trúc cho Patient Information, Disease Characterization, Health Assessment, Genomics, Cancer Treatments và Outcomes. Profiles gồm CancerDiseaseStatus, CancerStage, Tumor, TumorSize, CancerRelatedMedicationAdministration, CancerRelatedSurgicalProcedure, RadiotherapyCourseSummary…
- **Giới hạn:** mCODE là implementation guide; không tự quyết định trường nào bắt buộc phải thu ở dataset này và không thay response criteria cho từng bệnh.

## CT02 — HL7 FHIR ImagingStudy

- **Nguồn:** HL7 FHIR R5 ImagingStudy.
- **URL:** https://hl7.org/fhir/imagingstudy.html
- **Vai trò:** chuẩn hóa quan hệ study → series → imaging objects và mapping tới DICOM. Hữu ích để thiết kế lớp metadata/identifier của CT ontology.

## CT03 — RSNA RadLex

- **Nguồn:** RSNA RadLex Radiology Lexicon.
- **URL:** https://www.rsna.org/practice-tools/data-tools-and-standards/radlex-radiology-lexicon
- **Vai trò:** terminology chuẩn cho anatomy, radiology findings/procedures và structured reporting; RSNA định nghĩa ontology là tập khái niệm chuẩn cùng quan hệ giữa chúng.

## CT04 — DICOM SR TID 1500 Measurement Report

- **Nguồn:** DICOM PS3.16, TID 1500 Measurement Report; mapping AIM↔TID1500 hiện có trong DICOM Part 21.
- **URL:** https://dicom.nema.org/medical/dicom/current/output/chtml/part16/chapter_A.html
- **Vai trò:** nhóm measurement có Tracking ID/UID, image references và quantitative measurements; phù hợp để giữ lesion identity + measurements một cách machine-readable.

## CT05 — RECIST 1.1

- **Nguồn chính thức:** RECIST Working Group / EORTC.
- **URL:** https://recist.eortc.org/recist-1-1/
- **Paper gốc:** Eisenhauer et al., *New response evaluation criteria in solid tumours: revised RECIST guideline (version 1.1)*, Eur J Cancer 2009, DOI 10.1016/j.ejca.2008.10.026.
- **Vai trò:** generic solid-tumor response profile. Chọn tối đa 5 target lesions tổng cộng, tối đa 2 mỗi cơ quan; longest diameter cho phần lớn target lesions, short-axis cho nodes; response CR/PR/SD/PD.

## CT06 — iRECIST

- **Nguồn:** RECIST Working Group; Seymour et al., Lancet Oncology 2017, DOI 10.1016/S1470-2045(17)30074-8.
- **URL:** https://recist.eortc.org/irecist/
- **Vai trò:** extension cho immunotherapy, xử lý response patterns đặc thù như progression cần xác nhận. Candidate phù hợp nếu chọn NSCLC/melanoma dưới immune checkpoint therapy.

## CT07 — mRECIST cho HCC

- **Nguồn:** Lencioni & Llovet, *Modified RECIST (mRECIST) assessment for hepatocellular carcinoma*, Semin Liver Dis 2010, DOI 10.1055/s-0030-1247132.
- **PubMed:** https://pubmed.ncbi.nlm.nih.gov/20175033/
- **Vai trò:** HCC-specific response profile dựa trên viable enhancing tumor; đặc biệt tự nhiên với TACE/locoregional therapy. Viable part được đánh giá dựa trên arterial enhancement, khác với chỉ đo toàn bộ đường kính khối.

## CT08 — Longitudinal-CT 2026

- **Nguồn:** *A longitudinal whole-body CT dataset with manually annotated tumor lesions*, Scientific Data (2026).
- **URL:** https://www.nature.com/articles/s41597-026-07466-y
- **Kiểm tra 2026-09-08:** 300 bệnh nhân metastatic melanoma, 600 CT studies tại baseline/follow-up trong systemic therapy; 7.182 manually segmented lesions; anatomy, volume và longitudinal correspondence với persistence/regression/merging/new appearance.
- **Hệ quả:** hai timepoints + exhaustive lesion graph đã có comparator mạnh; một dataset mới phải sâu hơn ở treatment semantics, số timepoint, response framework, outcomes hoặc population/protocol.

## CT09 — HCC-TACE-Seg

- **Nguồn:** The Cancer Imaging Archive / Imaging Data Commons.
- **TCIA:** https://www.cancerimagingarchive.net/collection/hcc-tace-seg/
- **IDC:** https://portal.imaging.datacommons.cancer.gov/collections/hcc_tace_seg/
- **Kiểm tra 2026-09-08:** 105 HCC subjects; TCIA version hiện nêu 211 studies, 51.968 images, pre/post TACE CT + segmentations; clinical data gồm treatment/measurement/classification/follow-up. IDC mô tả outcome gồm time-to-progression và overall survival.
- **Hệ quả:** “HCC + pre/post TACE CT + outcome” không còn là novelty tự thân.

## CT10 — RECIST CT dataset 2026

- **Nguồn:** *A CT Dataset with RECIST Measurements and Comprehensive Segmentation Masks for Tumors and Lymph Nodes*, Scientific Data 13:270 (2026).
- **URL:** https://www.nature.com/articles/s41597-026-06597-6
- **Kiểm tra 2026-09-08:** 22 patients, 48 distinct studies / 58 CT series, 1–4 studies mỗi patient; 1.246 lesion segmentations và 82 RECIST target-lesion measurements. Target lesions có identifier để theo dõi qua follow-up.
- **Hệ quả:** dataset rất nhỏ theo patient count nhưng annotation rất sâu; minh họa rằng scale không thể đánh giá chỉ bằng số bệnh nhân.

## CT11 — Anti-PD-1 Lung

- **Nguồn:** TCIA Anti-PD-1_LUNG.
- **URL:** https://www.cancerimagingarchive.net/collection/anti-pd-1_lung/
- **Kiểm tra 2026-09-08:** 46 lung cancer cases treated with anti-PD1 immunotherapy; pre-treatment imaging và phần lớn có một follow-up; CT/PET cùng một số supporting objects.
- **Hệ quả:** pre/post immunotherapy lung CT đã có precedent; richer multi-timepoint lesion graph + iRECIST + treatment/outcome có thể là hướng khác biệt ứng viên, chưa chứng minh gap toàn lĩnh vực.

## CT12 — HNSCC-3DCT-RT

- **Nguồn:** Bejarano et al., *Longitudinal fan-beam computed tomography dataset for head-and-neck squamous cell carcinoma patients*, Medical Physics 2019, DOI 10.1002/mp.13460; TCIA collection HNSCC-3DCT-RT.
- **URL:** https://www.cancerimagingarchive.net/collection/hnscc-3dct-rt/
- **Kiểm tra 2026-09-08:** 31 HNSCC patients, ba CT timepoints (pre-, mid-, post-radiotherapy), RTSTRUCT/RTDOSE, anatomical contours, demographics/outcomes.
- **Hệ quả:** small-N nhưng nhiều state + structured treatment/dose là một blueprint tốt cho action-conditioned longitudinal data.

## CT13 — Medical World Model, ICCV 2025

- **Nguồn:** Yang et al., *Medical World Model*, ICCV 2025.
- **URL:** https://openaccess.thecvf.com/content/ICCV2025/html/Yang_Medical_World_Model_ICCV_2025_paper.html
- **Kiểm tra 2026-09-08:** framework dùng pre-treatment CT + language goal/treatment protocol để simulate post-treatment tumor state trong HCC/TACE; policy model, dynamics model và survival-based evaluation.
- **Vai trò:** bằng chứng research direction; không coi paper này là dataset release tương đương CT09.

## CT14 — Lugano Classification

- **Nguồn:** Cheson et al., JCO 2014, DOI 10.1200/JCO.2013.54.8800.
- **URL:** https://ascopubs.org/doi/10.1200/JCO.2013.54.8800
- **Vai trò:** lymphoma response/staging. PET-CT được tích hợp cho FDG-avid lymphomas; vì vậy nếu mục tiêu là CT-only ontology, lymphoma thường không phải candidate sạch bằng generic solid tumor hoặc HCC.

## Quy tắc sử dụng nguồn

- Không coi số patient/scan/lesion là trực tiếp tương đương giữa các dataset.
- Không gọi dataset retrospective là causal treatment-response chỉ vì có treatment nằm giữa hai scan.
- Không suy quyền public/re-distribution của dữ liệu HMU từ việc các comparator trên public.
- Khi dự án quyết định CT trở thành modality chính, chuyển các nguồn đã dùng vào `docs/research/SOURCES.md` hoặc hợp nhất sổ nguồn theo cấu trúc repo.
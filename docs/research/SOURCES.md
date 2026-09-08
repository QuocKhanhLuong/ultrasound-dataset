# Sổ nguồn nghiên cứu

Cập nhật: 2026-09-08. DOI/URL là điểm truy vết bền vững; không lưu token trích dẫn phụ thuộc một phiên chat.

## Cách đọc mức kiểm chứng

- **Đã đọc mô tả nguồn gốc:** kiểm tra paper/trang tác giả hoặc tài liệu chính thức cho những phát biểu được ghi. Không tương đương tải và kiểm toán dataset.
- **Xác minh một phần:** chỉ đọc được một phần hoặc mô tả qua kết quả tìm kiếm. Ghi rõ giới hạn, không suy giấy phép/số lượng còn thiếu.
- **Chờ xác minh:** đầu mối từ trao đổi trước, chưa dùng như bằng chứng đã kiểm tra trong đợt hiện tại.

Không có nguồn dataset nào dưới đây đã được dự án tải về và kiểm toán toàn bộ ở thời điểm này. Các tình trạng truy cập có thể đổi; phải kiểm tra lại trước khi tái sử dụng. Tình trạng công bố và mức kiểm chứng truy cập là hai cột riêng về ý nghĩa.

<a id="s001"></a>
## S001 — ThyroidXL

- **Nguồn:** *ThyroidXL: Advancing Thyroid Nodule Diagnosis with an Expert-Labeled, Pathology-Validated Dataset*.
- **Công bố:** MICCAI 2025; DOI [10.1007/978-3-032-05182-0_60](https://doi.org/10.1007/978-3-032-05182-0_60). Không phải nguồn chỉ có preprint.
- **Paper:** [MICCAI Open Access](https://papers.miccai.org/miccai-2025/0928-Paper2024.html).
- **Phát hành:** [dataset card tác giả](https://huggingface.co/datasets/hunglc007/ThyroidXL).
- **Kiểm tra 2026-09-08:** MICCAI mô tả >11.000 ảnh/>4.000 bệnh nhân, thu tại Vietnam National Hospital of Endocrinology, classification/detection/segmentation và xác minh tế bào học/bệnh học. Chưa qua gate/tải dữ liệu.
- **Bất nhất chưa giải quyết:** paper/conclusion và card/review hiển thị các tổng ảnh/bệnh nhân khác nhau ở một số vị trí. Giữ số theo từng nguồn khi trích, không tự chuẩn hóa thành một manifest chưa kiểm toán.

<a id="s002"></a>
## S002 — Open Kidney

- **Nguồn dataset:** [trang Open Kidney của tác giả](https://rsingla.ca/kidneyUS/), các mục Data Description, Repository/Data Structure, License and Usage, Citation.
- **Công bố:** Singla et al., *The Open Kidney Ultrasound Data Set*, trong **ASMUS 2023 / MICCAI 2023 Workshops**, LNCS 14337, tr. 155–164. Proceedings [Springer](https://link.springer.com/book/10.1007/978-3-031-44521-7); chapter DOI [10.1007/978-3-031-44521-7_15](https://doi.org/10.1007/978-3-031-44521-7_15). Trang tác giả vẫn dẫn bản arXiv 2022; do đó không còn ghi “chỉ preprint”.
- **Kiểm tra 2026-09-08:** >500 ảnh B-mode 2D; trang dataset mô tả tối đa một ảnh được chọn ngẫu nhiên trên mỗi bệnh nhân, hai bộ polygon annotation chuyên gia, nhãn view/type/quality và thông tin hiệu chuẩn/máy khi có. Chưa đăng ký/tải gói.
- **Hệ quả đối chiếu:** bộ này không tự cung cấp cấu trúc nhiều view/lần khám hoặc cine để đánh giá repeatability theo cùng ca.

<a id="s003"></a>
## S003 — BrEaST

- **Nguồn:** Pawłowska et al., *Curated benchmark dataset for ultrasound based breast lesion analysis*, Scientific Data 11, 148 (2024).
- **Paper/DOI:** [10.1038/s41597-024-02984-z](https://doi.org/10.1038/s41597-024-02984-z).
- **Kiểm tra 2026-09-07:** đã đọc abstract, Methods và Data acquisition; nguồn đã qua tạp chí. Chưa tải collection. Phân biệt trường hợp xác minh bằng sinh thiết với theo dõi; không ghi tất cả đều có bệnh học.

<a id="s004"></a>
## S004 — ACOUSLIC-AI

- **Nguồn phát hành:** [Zenodo record 12697994, v1.1](https://zenodo.org/records/12697994), công bố 09/07/2024.
- **Kiểm tra 2026-09-07:** **xác minh một phần**. Mô tả truy được: frame prenatal từ người mới quét theo blind-sweep; nhãn chu vi bụng trên frame có thể đo và số đo mm theo sweep. Ghi chú v1.1 sửa phép tính chu vi của v1.0 bị lớn gấp hai.
- **Cần tiếp tục:** đọc record/paper tương ứng, điều khoản và cấu trúc gói đầy đủ trước khi dùng làm đối chiếu cuối cùng.

<a id="s005"></a>
## S005 — EchoNet-Dynamic

- **Nguồn gốc:** [trang EchoNet-Dynamic](https://echonet.github.io/dynamic/).
- **Công bố:** Ouyang et al., *Video-based AI for beat-to-beat assessment of cardiac function*, Nature (2020).
- **Kiểm tra 2026-09-07:** đã đọc mô tả và Research Use Agreement trên trang. Chưa đăng ký/tải. Quyền nghiên cứu phi thương mại không phải quyền chia sẻ lại clip hoặc đường tải.

<a id="s006"></a>
## S006 — CAMUS

- **Nguồn gốc:** [trang dataset CAMUS](https://www.creatis.insa-lyon.fr/Challenge/camus/databases.html).
- **Công bố:** Leclerc et al., *Deep Learning for Segmentation using an Open Large-Scale Dataset in 2D Echocardiography*, IEEE TMI 38(9), 2198–2210 (2019), DOI [10.1109/TMI.2019.2900516](https://doi.org/10.1109/TMI.2019.2900516).
- **Kiểm tra 2026-09-07:** đã đọc mô tả chính thức; chưa tải. Trang mô tả xử lý riêng nhóm chất lượng kém trong metric; phải đọc protocol khi tái lập.

<a id="s007"></a>
## S007 — OpenPOCUS

- **Nguồn:** Kumar et al., *Creation of an Open-Access Lung POCUS Image Database for Deep Learning and Neural Network Applications*, POCUS Journal 11(1), 62–67 (2026).
- **Paper/DOI:** [10.24908/pocusj.v11i01.19439](https://doi.org/10.24908/pocusj.v11i01.19439).
- **Kiểm tra 2026-09-07:** đã đọc abstract và Methods; chưa mở/tải repo dữ liệu.
- **Bất nhất cần giữ:** các phần bài báo có tổng frame/clip không hoàn toàn nhất quán; cần khóa version/manifest nếu sử dụng thực nghiệm.

<a id="s008"></a>
## S008 — DICOM: hiệu chuẩn vùng siêu âm

- **Nguồn:** [PS3.3, C.8.5.5 US Region Calibration Module](https://dicom.nema.org/medical/dicom/current/output/chtml/part03/sect_C.8.5.5.html).
- **Loại:** tiêu chuẩn kỹ thuật chính thức.
- **Kiểm tra 2026-09-07:** dùng để yêu cầu kiểm tra đơn vị/hiệu chuẩn theo vùng; không mặc định mọi PNG hoặc DICOM đều còn metadata đầy đủ.

<a id="s009"></a>
## S009 — DICOM: thông tin định danh trong pixel

- **Nguồn:** [PS3.15, E.3 Clean Pixel Data Option](https://dicom.nema.org/medical/dicom/current/output/chtml/part15/sect_E.3.html).
- **Loại:** tài liệu chính thức; phiên bản hiển thị PS3.15 2026c khi kiểm tra 2026-09-07.
- **Phát biểu hỗ trợ:** siêu âm có thể có thông tin định danh ghi trực tiếp trong pixel; thay metadata không đủ để kết luận đã khử định danh.

<a id="s010"></a>
## S010 — CLAIM 2024

- **Nguồn:** Tejani et al., *Checklist for Artificial Intelligence in Medical Imaging (CLAIM): 2024 Update*, Radiology: Artificial Intelligence (2024).
- **DOI:** [10.1148/ryai.240300](https://doi.org/10.1148/ryai.240300).
- **Vai trò:** hướng dẫn báo cáo về reference standard, thu nhận, split và xác định test size; không phải thang điểm đảm bảo chất lượng/phê duyệt dataset.

<a id="s011"></a>
## S011 — Survey public ultrasound resources 2025

- **Nguồn:** Alsharid et al., *On the public dissemination and open sourcing of ultrasound resources, datasets and deep learning models*, npj Digital Medicine (2025).
- **DOI:** [10.1038/s41746-025-02162-4](https://doi.org/10.1038/s41746-025-02162-4).
- **Kiểm tra 2026-09-08:** paper xác định 72 public ultrasound datasets và 56 open-source models ở thời điểm khảo sát; dùng như bản đồ lĩnh vực, không coi số 72 là tổng hiện tại.

<a id="s012"></a>
## S012 — NIDUS Ultrasound Open Access Datasets

- **Nguồn:** [NIDUS directory](https://ultrasound-open-access.nidusai.ca/).
- **Loại:** directory sống, không phải paper peer-reviewed.
- **Kiểm tra 2026-09-08:** trang hiển thị 96 datasets, cập nhật 07/09/2026. Vì là directory thay đổi theo thời gian, phải ghi ngày truy cập và xác minh lại paper/dataset page của từng mục trước khi dùng như bằng chứng chi tiết.

<a id="s013"></a>
## S013 — AbVLM-Q abdominal ultrasound quality

- **Nguồn:** *AbVLM-Q: intelligent quality assessment for abdominal ultrasound standard planes via vision-language modeling*, BMC Medical Imaging (2025).
- **DOI:** [10.1186/s12880-025-01885-w](https://doi.org/10.1186/s12880-025-01885-w).
- **Kiểm tra 2026-09-08:** 7.766 ảnh từ hai trung tâm; 11 standard planes, key-structure/quality scoring. Inclusion yêu cầu predefined standard planes và complete scans không artifact/noise; exclusion loại anatomical abnormalities hoặc quality issues làm giảm interpretation. Điều này hỗ trợ đối chiếu cho hướng quality, nhưng không phải full-acquisition failure-aware dataset.

<a id="s014"></a>
## S014 — SpaceTime-SonoNet abdominal video

- **Nguồn:** Interlando et al., *SpaceTime-SonoNet: efficient classification of ultra-sound video sequences*, Medical & Biological Engineering & Computing (2026).
- **DOI:** [10.1007/s11517-025-03504-w](https://doi.org/10.1007/s11517-025-03504-w).
- **Kiểm tra 2026-09-08:** paper dùng private anonymised abdominal dataset gồm 2.086 videos/413 patients/388.787 frames; đa số bệnh nhân có complete exam gồm 5 scan videos; có 6 standard scan-plane classes + Other. Không xem đây là public resource.

<a id="s015"></a>
## S015 — SHM POCUS minimum image quality criteria

- **Nguồn:** Anstey et al., *Defining minimum image quality criteria for common diagnostic point-of-care ultrasound images: A position statement of the Society of Hospital Medicine*, Journal of Hospital Medicine 21(2), 183–196 (2026; epub 2025).
- **DOI:** [10.1002/jhm.70156](https://doi.org/10.1002/jhm.70156).
- **Kiểm tra 2026-09-08:** 32 POCUS experts, modified Delphi, 215 criteria across heart, lung, abdomen, lower-extremity veins và skin/soft tissue. Dùng làm nguồn xây rubric tham khảo; không thay consensus của chuyên gia tại dự án cho protocol cụ thể.

<a id="s016"></a>
## S016 — Maternal-Fetal intrapartum ultrasound video 2026

- **Nguồn:** *Maternal-Fetal Ultrasound Video Dataset for End-to-end Intrapartum Biometry and Multi-task Learning*, Scientific Data (2026).
- **DOI:** [10.1038/s41597-026-06900-5](https://doi.org/10.1038/s41597-026-06900-5).
- **Kiểm tra 2026-09-08:** public multi-center/multi-device video dataset cho intrapartum biometry; nguồn mô tả 774 videos/68.106 frames. Đây là đối chiếu trực tiếp chống claim “video sản khoa + biometry” như novelty tự thân.

<a id="s017"></a>
## S017 — Multicentre fetal biometry benchmark 2026

- **Nguồn:** Di Vece et al., *A multicentre benchmark dataset for comprehensive landmark-based fetal ultrasound biometry*, Scientific Reports 16, 17405 (2026).
- **DOI:** [10.1038/s41598-026-47854-3](https://doi.org/10.1038/s41598-026-47854-3).
- **Kiểm tra 2026-09-08:** 4.513 images/1.904 subjects, bốn sites, bảy devices, expert landmarks, subject-disjoint splits. Ảnh là pre-selected clinically appropriate standard planes; không phải raw acquisition process.

<a id="s018"></a>
## S018 — Fetal exam quality/completeness 2026

- **Nguồn:** Zhang et al., *Artificial intelligence-assisted quality assessment of mid-trimester ultrasound examinations using large vision-language models*, BMC Pregnancy and Childbirth 26, 614 (2026).
- **DOI:** [10.1186/s12884-026-09073-6](https://doi.org/10.1186/s12884-026-09073-6).
- **Kiểm tra 2026-09-08:** 22.544 planes từ 273 internal + 29 external examinations và public FETAL_PLANES_DB; mỗi exam nội bộ có 20 required standard planes cùng 10–20 non-standard planes; nhãn plane/structure visibility/quality; exam-level completeness. Clinical datasets không được mô tả là tải mở toàn bộ.

<a id="s019"></a>
## S019 — TRUSTED kidney 3DUS + CT

- **Nguồn:** Ndzimbong et al., *TRUSTED: The Paired 3D Transabdominal Ultrasound and CT Human Data for Kidney Segmentation and Registration Research*, Scientific Data 12, 615 (2025).
- **DOI:** [10.1038/s41597-025-04467-1](https://doi.org/10.1038/s41597-025-04467-1).
- **Kiểm tra 2026-09-08:** 48 patients/96 kidneys, paired 3DUS+CT, segmentation và seven landmarks từ two experienced radiographers. Đây không thay thế một 2D multi-view/repeatability dataset nhưng làm hẹp novelty cho kidney segmentation/landmark nói chung.

<a id="s020"></a>
## S020 — BUS-CoT breast ultrasound 2026

- **Nguồn:** *A Chain-of-thought Reasoning Breast Ultrasound Dataset Covering All Histopathology Categories*, Scientific Data (2026).
- **DOI:** [10.1038/s41597-026-06702-9](https://doi.org/10.1038/s41597-026-06702-9).
- **Kiểm tra 2026-09-08:** 11.439 ultrasound images/11.850 lesions/4.838 patients; B-mode, Doppler, elastography; labels gồm lesion characteristics, reports, BI-RADS và histopathology categories; public Figshare. Là bằng chứng rằng “breast + multimodal + histopathology” không tự tạo novelty.

<a id="s021"></a>
## S021 — SMC-LUD liver ultrasound 2026

- **Nguồn:** *SMC-LUD: Large-Scale B-Mode Liver Ultrasound Dataset for Hepatocellular Carcinoma and Hemangioma Classification*, Scientific Data (2026).
- **DOI:** [10.1038/s41597-026-07023-7](https://doi.org/10.1038/s41597-026-07023-7).
- **Kiểm tra 2026-09-08:** 5.385 anonymized B-mode images/1.021 patients; HCC histopathology-confirmed, hemangioma radiologically diagnosed. Basic liver lesion classification đã có public comparator quy mô đáng kể.

<a id="s022"></a>
## S022 — NAFLD ultrasound + biopsy 2025

- **Nguồn:** *Large annotated ultrasound dataset of non-alcoholic fatty liver from Saudi hospitals for analysis and applications*, Data in Brief 58, 111266 (2025).
- **DOI:** [10.1016/j.dib.2024.111266](https://doi.org/10.1016/j.dib.2024.111266).
- **Kiểm tra 2026-09-08:** 10.352 images/384 patients từ hai hospitals; image-level labels gắn với biopsy-based NAS fibrosis staging/steatosis grading. Không dùng “liver ultrasound + fibrosis/steatosis classification” làm gap mặc định.

<a id="s023"></a>
## S023 — ThrombUS+ compression ultrasound videos

- **Nguồn dataset:** [Zenodo 17664207](https://zenodo.org/records/17664207), DOI [10.5281/zenodo.17664207](https://doi.org/10.5281/zenodo.17664207).
- **Nguồn mô tả:** record dẫn paper BIOSTEC 2026 về dataset cho autonomous DVT detection từ compression ultrasound videos.
- **Kiểm tra 2026-09-08:** testing archive công khai trên Zenodo; description nêu vein compressibility/segmentation trong ultrasound video. Do đó “DVT + compression video” không phải novelty tự thân.

<a id="s024"></a>
## S024 — Regional-US brachial plexus procedural ultrasound

- **Nguồn:** [Regional-US/brachial_plexus](https://github.com/Regional-US/brachial_plexus).
- **Tình trạng:** public GitHub resource; README liên kết nghiên cứu submitted to IROS 2024. Cần đọc proceedings paper riêng nếu dùng claim về method.
- **Kiểm tra 2026-09-08:** 227 deidentified brachial-plexus ultrasound videos từ 3 ultrasound machines; nerve-plexus annotations/masks, needle annotations ở một phần; non-commercial data use agreement. Không claim “first UGRA video dataset”.

<a id="s025"></a>
## S025 — UGRA annotation/evaluation clinical perspective 2026

- **Nguồn:** Delvaux et al., *Data annotation and its evaluation in artificial intelligence-based anatomy recognition for ultrasound-guided regional anesthesia: a clinical perspective*, Frontiers in Medicine 13:1823745 (2026).
- **DOI:** [10.3389/fmed.2026.1823745](https://doi.org/10.3389/fmed.2026.1823745).
- **Kiểm tra 2026-09-08:** opinion/clinical perspective, không phải dataset descriptor. Tác giả nhấn mạnh thiếu chuẩn hóa annotation/evaluation, uncertainty, multi-rater strategy và clinical operating points; chính bài cũng nêu nhiều khái niệm là hypothesis-generating. Dùng làm căn cứ thiết kế câu hỏi, không dùng để tuyên bố gap dataset tuyệt đối.

<a id="s026"></a>
## S026 — MMOTU ovarian tumor ultrasound

- **Nguồn:** Zhao et al., *MMOTU: A Multi-Modality Ovarian Tumor Ultrasound Image Dataset for Unsupervised Cross-Domain Semantic Segmentation*, arXiv:2207.06799 (2022) — **preprint**.
- **Repo:** [cv516Buaa/MMOTU_DS2Net](https://github.com/cv516Buaa/MMOTU_DS2Net).
- **Kiểm tra 2026-09-08:** repo/preprint mô tả 1.469 2D images + 170 CEUS images với pixel-wise và category annotations. Không coi nguồn này là peer-reviewed dataset paper nếu chưa xác minh phiên bản xuất bản khác.

<a id="s027"></a>
## S027 — Adnexal masses, 23-hospital study 2026

- **Nguồn:** Wu et al., *Development and validation of an artificial intelligence-based model for diagnosing benign, borderline, and malignant adnexal masses*, npj Precision Oncology 10, 106 (2026).
- **Article:** [Nature](https://www.nature.com/articles/s41698-026-01320-5).
- **Kiểm tra 2026-09-08:** retrospective data từ 23 hospitals/2.381 patients, 9.636 images và external video test subset; 38 commercial systems/9 vendors. Đây là study dataset, không được coi là public dataset chỉ vì paper open access.

<a id="s028"></a>
## S028 — Ovarian tumor multimodal US + clinical data 2026

- **Nguồn:** Lai et al., *Investigation of multimodal deep learning models for predicting ovarian tumor malignancy based on ultrasound images and clinical information – a comprehensive comparative study against readers and O-RADS*, BMC Medical Imaging 26, 257 (2026).
- **DOI:** [10.1186/s12880-026-02312-4](https://doi.org/10.1186/s12880-026-02312-4).
- **Kiểm tra 2026-09-08:** 508 patients từ 3 institutions; grayscale US + CDFI + clinical markers, pathology reference và comparison với radiologists/O-RADS. Paper nêu study dataset không public do privacy, nhưng có thể request corresponding author.

<a id="s029"></a>
## S029 — DDH: standard-plane/Graf resources 2025–2026

- **Nguồn đối chiếu 1:** *Automated Neonatal Hip Ultrasound System for Diagnosing Developmental Dysplasia of Hips Using Assistive AI*; accessible via PMC. Dataset description nêu 39.349 standard/non-standard frames, 4.411 standard/Graf-region images và Graf grades; patient split.
- **Nguồn đối chiếu 2:** Zhang et al., *Artificial Intelligence-Assisted Wireless Handheld Ultrasound for Screening Developmental Dysplasia of the Hip in Infants*, Journal of Ultrasound in Medicine (2026), DOI [10.1002/jum.70318](https://doi.org/10.1002/jum.70318); abstract nêu 1.192 images + 498 dynamic videos.
- **Open resource:** [radoss-org/open-hip-dysplasia](https://github.com/radoss-org/open-hip-dysplasia) và Retuve DOI [10.1016/j.simpa.2025.100791](https://doi.org/10.1016/j.simpa.2025.100791).
- **Hệ quả:** basic standard-plane + Graf angle/grade/segmentation không phải low-hanging novelty; cần kiểm tra public availability của từng cohort riêng.

<a id="s030"></a>
## S030 — Open diaphragm ultrasound dataset 2025

- **Nguồn:** Li et al., *Open-access ultrasonic diaphragm dataset and an automatic diaphragm measurement using deep learning network*, Respiratory Research 26, 251 (2025).
- **DOI:** [10.1186/s12931-025-03325-3](https://doi.org/10.1186/s12931-025-03325-3).
- **Kiểm tra 2026-09-08:** nguồn mô tả B-mode images/videos cho thickness và M-mode images/videos cho excursion/movement measurement. Basic diaphragm thickness/excursion dataset đã có comparator công khai.

<a id="pending"></a>
## Hàng đợi xác minh / mở rộng

Các mục sau được giữ để không mất hướng tra cứu; không dùng làm bằng chứng chính nếu chưa đọc nguồn gốc ở vòng gần nhất.

| Đầu mối | Nguồn cần kiểm tra | Việc còn thiếu |
|---|---|---|
| BUSI | [bài nguồn](https://www.sciencedirect.com/science/article/pii/S2352340919312181) | Nhãn, liên kết bệnh nhân, bản phát hành/giấy phép |
| BUS-BRA | [PubMed](https://pubmed.ncbi.nlm.nih.gov/37937827/) | Paper gốc, máy/cơ sở, chuẩn xác minh, bản Zenodo |
| TN5000 | [Scientific Data](https://www.nature.com/articles/s41597-025-05757-4) | Đơn vị bệnh nhân/ảnh, chia tập và nhãn thực tế |
| Stanford Thyroid Cine-clip | [Stanford AIMI](https://aimi.stanford.edu/datasets/thyroid-ultrasound-cine-clip) | Video/tổn thương, nhãn và điều kiện cấp quyền |
| FETAL_PLANES_DB | [Zenodo](https://zenodo.org/records/3904280) | Phiên bản, patient ID, mặt cắt và giấy phép |
| FUSEP KDD 2026 | [repo tác giả](https://github.com/ahuteam/FUSEP) | Đọc paper KDD chính thức, số ca/site và release terms trước khi dùng |
| Prostate/TRUS | NIDUS entries + Prostate-MRI-US-Biopsy + ProCUSNet | Xác minh complete-sweep/core-level mapping và public status cho từng resource |
| Clinical Ultrasound Image Repository | NIDUS/AWS registry | Kiểm tra manifest, DICOM study structure và license trực tiếp |
| CMCNet/STN | Đầu mối tuyến giáp hai mặt cắt từ trao đổi cũ | Chưa xác nhận URL, ngày và tình trạng preprint |

## Khi thêm nguồn mới

Ghi mã ổn định, tiêu đề, DOI/URL chính thức, phiên bản/ngày, công bố tạp chí/hội nghị/preprint, phần đã đọc, phát biểu thực sự hỗ trợ, giới hạn và hành động kiểm chứng. Nếu nguồn nói về một dataset khác hoặc phiên bản khác, không dùng để thay số liệu đang thiếu.

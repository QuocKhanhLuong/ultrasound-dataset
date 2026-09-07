# Sổ nguồn nghiên cứu

Cập nhật: 2026-09-07. DOI/URL là điểm truy vết bền vững; không lưu token trích dẫn phụ thuộc một phiên chat.

## Cách đọc mức kiểm chứng

- **Đã đọc mô tả nguồn gốc:** kiểm tra paper/trang tác giả hoặc tài liệu chính thức cho những phát biểu được ghi. Không tương đương tải và kiểm toán dataset.
- **Xác minh một phần:** chỉ đọc được một phần hoặc mô tả qua kết quả tìm kiếm. Ghi rõ giới hạn, không suy giấy phép/số lượng còn thiếu.
- **Chờ xác minh:** đầu mối từ trao đổi trước, chưa dùng như bằng chứng đã kiểm tra trong đợt khởi tạo.

Không có nguồn dataset nào dưới đây đã được dự án tải về và kiểm toán toàn bộ ở thời điểm này. Các tình trạng truy cập có thể đổi; phải kiểm tra lại trước khi tái sử dụng. Tình trạng công bố và mức kiểm chứng truy cập là hai cột riêng về ý nghĩa.

<a id="s001"></a>
## S001 — ThyroidXL

- **Nguồn:** *ThyroidXL: Advancing Thyroid Nodule Diagnosis with an Expert-Labeled, Pathology-Validated Dataset*.
- **Công bố:** MICCAI 2025; DOI [10.1007/978-3-032-05182-0_60](https://doi.org/10.1007/978-3-032-05182-0_60), được card tác giả dẫn. Không phải nguồn chỉ có preprint.
- **Paper:** [bản trên trang MICCAI](https://papers.miccai.org/miccai-2025/paper/2024_paper.pdf), mục 3.1–3.2 và abstract.
- **Phát hành:** [dataset card tác giả](https://huggingface.co/datasets/hunglc007/ThyroidXL).
- **Kiểm tra 2026-09-07:** đã đọc paper và card công khai; chưa qua gate, chưa tải dữ liệu.
- **Bất nhất chưa giải quyết:** paper ghi 11.635 ảnh; card ghi tổng 11.545 nhưng hai phần ảnh ghi 9.541 và 2.094. Card còn có các tổng bệnh nhân không nhất quán. Giữ số paper với định danh nguồn, không tự sửa card hoặc kết luận số tệp thực tế. Gate yêu cầu đăng nhập/chấp nhận điều kiện; chưa xác minh giấy phép đầy đủ.

<a id="s002"></a>
## S002 — Open Kidney

- **Nguồn:** [trang Open Kidney của tác giả](https://rsingla.ca/kidneyUS/), các mục Data Description, Repository/Data Structure, License and Usage, Citation.
- **Công bố được trang dẫn:** *The open kidney ultrasound data set*, [arXiv:2206.06657](https://arxiv.org/abs/2206.06657), 2022 — **preprint**. Bản ghi này chưa xác minh một phiên bản tạp chí thay thế.
- **Kiểm tra 2026-09-07:** đã đọc mô tả nguồn gốc; chưa đăng ký/tải. Trang ghi bản phát hành 14/06/2022. Các thuộc tính được tổng hợp tại [DATASET_MAP](DATASET_MAP.md); không suy thêm số cơ sở từ tên đơn vị tác giả.

<a id="s003"></a>
## S003 — BrEaST

- **Nguồn:** Pawłowska và cộng sự, *Curated benchmark dataset for ultrasound based breast lesion analysis*, Scientific Data 11, 148 (2024).
- **Paper/DOI:** [10.1038/s41597-024-02984-z](https://www.nature.com/articles/s41597-024-02984-z).
- **Kiểm tra 2026-09-07:** đã đọc abstract, Methods và Data acquisition; nguồn đã qua tạp chí, không chỉ preprint. Chưa tải collection. Phân biệt trường hợp xác minh bằng sinh thiết với theo dõi; không ghi tất cả đều có bệnh học.

<a id="s004"></a>
## S004 — ACOUSLIC-AI

- **Nguồn phát hành:** [Zenodo record 12697994, v1.1](https://zenodo.org/records/12697994), công bố 09/07/2024.
- **Kiểm tra 2026-09-07:** **xác minh một phần** qua kết quả tìm kiếm của record; mở trực tiếp record bị lỗi trong phiên này. Không ghi đã đọc toàn bộ tệp/giấy phép hoặc đã đối chiếu paper benchmark.
- **Mô tả truy được:** frame prenatal từ người mới quét theo blind-sweep; nhãn chu vi bụng trên frame có thể đo và số đo mm theo sweep. Ghi chú v1.1 sửa phép tính chu vi của v1.0 bị lớn gấp hai. Đây là dữ kiện của record phiên bản, không phải benchmark do dự án thực hiện.
- **Cần tiếp tục:** đọc record đầy đủ, paper tương ứng, điều khoản và cấu trúc gói trước khi sử dụng làm đối chiếu cuối cùng.

<a id="s005"></a>
## S005 — EchoNet-Dynamic

- **Nguồn gốc:** [trang EchoNet-Dynamic](https://echonet.github.io/dynamic/), các mục Dataset, Accessing Dataset và Paper.
- **Công bố:** Ouyang và cộng sự, *Video-based AI for beat-to-beat assessment of cardiac function*, Nature (2020), theo nguồn tác giả; không chỉ preprint.
- **Kiểm tra 2026-09-07:** đã đọc mô tả và Research Use Agreement trên trang. Chưa đăng ký/tải. Quyền nghiên cứu phi thương mại không phải quyền chia sẻ lại clip hoặc đường tải.

<a id="s006"></a>
## S006 — CAMUS

- **Nguồn gốc:** [trang dataset CAMUS](https://www.creatis.insa-lyon.fr/Challenge/camus/databases.html).
- **Công bố:** Leclerc và cộng sự, *Deep Learning for Segmentation using an Open Large-Scale Dataset in 2D Echocardiography*, IEEE TMI 38(9), 2198–2210 (2019), DOI [10.1109/TMI.2019.2900516](https://doi.org/10.1109/TMI.2019.2900516).
- **Kiểm tra 2026-09-07:** đã đọc mô tả chính thức; chưa tải. Trang cũng mô tả xử lý khác nhau với nhóm chất lượng kém trong phép tính metric; phải kiểm tra protocol khi tái lập, không chỉ sao chép số bệnh nhân.

<a id="s007"></a>
## S007 — OpenPOCUS

- **Nguồn:** Kumar và cộng sự, *Creation of an Open-Access Lung POCUS Image Database for Deep Learning and Neural Network Applications*, POCUS Journal 11(1), 62–67 (2026).
- **Paper/DOI:** [bài chính thức](https://pocusjournal.com/article/19439/), [10.24908/pocusj.v11i01.19439](https://doi.org/10.24908/pocusj.v11i01.19439).
- **Kiểm tra 2026-09-07:** đã đọc abstract và Methods; bài tạp chí, không chỉ preprint. Chưa mở/tải repo dữ liệu được bài dẫn.
- **Bất nhất cần giữ:** abstract/tiền xử lý ghi 324.027 frame trong khi đoạn cuối Introduction ghi 303.977; bản trao đổi trước còn ghi nhận khác biệt tổng clip giữa các phần. Chưa chọn một tổng đã chuẩn hóa; cần manifest/version khi đối chiếu thực nghiệm.

<a id="s008"></a>
## S008 — DICOM: hiệu chuẩn vùng siêu âm

- **Nguồn:** [PS3.3, C.8.5.5 US Region Calibration Module](https://dicom.nema.org/medical/dicom/current/output/chtml/part03/sect_C.8.5.5.html).
- **Loại:** tiêu chuẩn kỹ thuật chính thức, không phải paper/preprint.
- **Kiểm tra 2026-09-07:** đã mở tài liệu; dùng cho việc yêu cầu kiểm tra đơn vị và hiệu chuẩn theo vùng. Không mặc định mọi ảnh PNG hay mọi tệp DICOM thu được đều có metadata đầy đủ. URL `current` có thể thay phiên bản; khi triển khai cần khóa bản tài liệu phù hợp.

<a id="s009"></a>
## S009 — DICOM: thông tin định danh trong pixel

- **Nguồn:** [PS3.15, E.3 và E.3.1 Clean Pixel Data Option](https://dicom.nema.org/medical/dicom/current/output/chtml/part15/sect_E.3.html).
- **Loại/phiên bản hiển thị:** tài liệu chính thức, PS3.15 2026c khi kiểm tra ngày 2026-09-07.
- **Phát biểu hỗ trợ:** siêu âm có thể có chữ ghi trực tiếp trong pixel; không thể chỉ thay metadata hoặc phủ một overlay rồi coi là đã xóa thông tin gốc. Đây là yêu cầu kỹ thuật tham khảo, không thay quyết định pháp lý/phê duyệt của đơn vị quản lý.

<a id="s010"></a>
## S010 — CLAIM 2024

- **Nguồn:** Tejani và cộng sự, *Checklist for Artificial Intelligence in Medical Imaging (CLAIM): 2024 Update*, Radiology: Artificial Intelligence (2024).
- **Paper/DOI:** [10.1148/ryai.240300](https://pubs.rsna.org/doi/10.1148/ryai.240300).
- **Kiểm tra 2026-09-07:** đọc nội dung nguồn tạp chí qua kết quả tìm kiếm; nguồn không chỉ preprint. Dùng như hướng dẫn báo cáo về chuẩn tham chiếu, thu nhận, chia tập và cách xác định cỡ tập kiểm tra; không dùng như một thang điểm bảo đảm chất lượng hay phê duyệt dataset.

<a id="pending"></a>
## Hàng đợi xác minh từ các trao đổi trước

Những mục này được giữ để không mất hướng tra cứu, nhưng **chưa được kiểm chứng lại trong đợt khởi tạo repo**. Tên/URL không tự chứng minh thuộc tính, giấy phép hay tình trạng công bố. Không sao chép các con số của chat trước vào bảng xác nhận chỉ vì đã từng được trợ lý nói.

| Đầu mối | Nguồn cần kiểm tra | Việc còn thiếu |
|---|---|---|
| BUSI | [bài nguồn](https://www.sciencedirect.com/science/article/pii/S2352340919312181) | Nhãn, liên kết bệnh nhân, bản phát hành/giấy phép |
| BUS-BRA | [bản ghi công bố](https://pubmed.ncbi.nlm.nih.gov/37937827/) | Paper gốc, máy/cơ sở, chuẩn xác minh, bản Zenodo |
| TN5000 | [bài nguồn](https://www.nature.com/articles/s41597-025-05757-4) | Đơn vị bệnh nhân/ảnh, chia tập và nhãn thực tế |
| Stanford Thyroid Cine-clip | [trang AIMI](https://aimi.stanford.edu/datasets/thyroid-ultrasound-cine-clip) | Video/tổn thương, nhãn và điều kiện cấp quyền |
| FETAL_PLANES_DB | [record Zenodo](https://zenodo.org/records/3904280) | Phiên bản, patient ID, mặt cắt và giấy phép |
| Bộ video sản khoa trong chuyển dạ 2026 | Tìm lại paper/record gốc; trao đổi trước chưa giữ URL đầy đủ trong bản này | Chưa đưa số ca/frame/nguồn thu vào bảng xác nhận |
| Bộ landmark sinh trắc thai 2026 | [đầu mối bài](https://www.nature.com/articles/s41598-026-47854-3) | Xác nhận bài và dataset đúng, nhãn/phép đo, quyền truy cập |
| TRUSTED | Tìm paper và trang phát hành chính thức | Khối siêu âm 3D, quan hệ CT–US và điều kiện sử dụng |
| Regensburg Pediatric Appendicitis | [trang UCI](https://archive.ics.uci.edu/dataset/938/regensburg+pediatric+appendicitis) | Phân biệt số hồ sơ với nhánh ảnh và bản phát hành |
| CMCNet/STN | Đầu mối được trợ lý nêu trước về tuyến giáp hai mặt cắt | Chưa xác nhận URL, ngày và tình trạng preprint; không dùng làm bằng chứng mới |

## Khi thêm nguồn mới

Ghi mã ổn định, tiêu đề, DOI/URL chính thức, phiên bản/ngày, công bố tạp chí/hội nghị/preprint, phần đã đọc, phát biểu thực sự hỗ trợ, giới hạn và hành động kiểm chứng. Nếu nguồn nói về một dataset khác hoặc phiên bản khác, không dùng để thay số liệu đang thiếu.

# Clinical longitudinal imaging schema — cách hiểu đơn giản

Cập nhật: 2026-09-08. **Trạng thái: knowledge note, chưa phải thiết kế dataset đã được chốt.**

## 1. Cách hiểu bằng ngôn ngữ lâm sàng

Một dataset phù hợp với disease-state / medical-world-model có thể được hiểu gần như **một hồ sơ bệnh án theo thời gian đã được cấu trúc hóa cho nghiên cứu**.

Đơn vị cốt lõi không còn là `một ảnh -> một nhãn`, mà là:

`bệnh nhân -> mốc khám/điều trị -> hình ảnh + trạng thái bệnh -> can thiệp -> mốc tiếp theo -> outcome`.

Ví dụ oncology CT:

`Patient`
→ `CT trước điều trị (T0)`
→ `tổn thương/lesion + vị trí + kích thước/volume + nhận định bác sĩ`
→ `điều trị A0`
→ `CT theo dõi T1`
→ `lesion tương ứng: nhỏ đi / lớn lên / mất / xuất hiện mới`
→ `điều trị tiếp theo A1`
→ `CT T2`
→ `outcome lâm sàng`.

## 2. Các thành phần nên phân biệt

### Imaging state
- CT/MRI/PET-CT tại từng timepoint.
- Lesion/organ annotations khi phù hợp: mask, box, landmark, volume, measurement.
- Không mặc định mọi timepoint phải có dense segmentation toàn bộ.

### Clinical state
- Chẩn đoán/stage được ghi nhận tại thời điểm đó.
- Tumor burden, biomarker/lab hoặc triệu chứng nếu có và nếu phục vụ câu hỏi nghiên cứu.
- Báo cáo/kết luận radiologist hoặc bác sĩ điều trị cần giữ nguyên nguồn và thời điểm.

### Action / intervention
- Loại điều trị hoặc thủ thuật thực tế diễn ra giữa hai timepoint.
- Ngày bắt đầu/kết thúc, regimen/dose/procedure details chỉ giữ ở mức cần thiết cho task và được phép sử dụng.
- Không đồng nhất treatment với causal effect: cohort hồi cứu thường có confounding do bác sĩ chọn điều trị dựa trên trạng thái bệnh.

### Transition labels
- Lesion correspondence giữa T0 và T1.
- `new / persistent / regressed / progressed / resolved / merged / uncertain` hoặc taxonomy do chuyên gia xác định.
- Change in size/volume và vị trí của thay đổi nếu có.

### Outcome
- Response assessment, progression, recurrence, event, survival hoặc kết luận lâm sàng tùy bài toán.
- Outcome không phải lúc nào cũng là một nhãn cuối duy nhất; có thể có nhiều horizon và nhiều loại outcome.

## 3. Vì sao "kết luận bác sĩ" chưa đủ

Báo cáo/kết luận của bác sĩ rất giá trị nhưng nên được xem là **một lớp annotation/reference**, không phải toàn bộ ground truth. Dataset tốt nên, khi khả thi, bảo tồn riêng:

1. hình ảnh gốc tại từng timepoint;
2. annotation cấu trúc/tổn thương;
3. báo cáo radiology hoặc nhận định chuyên gia;
4. treatment/intervention thực tế;
5. follow-up imaging;
6. outcome/reference sau đó.

Nhờ vậy có thể benchmark nhiều mức: state recognition, temporal change, lesion correspondence, outcome prediction và action-conditioned forecasting mà không ép tất cả thành một nhãn chẩn đoán.

## 4. Schema tối thiểu và schema lý tưởng

### Tối thiểu cho longitudinal disease-state dataset
`patient_id (pseudonymized)` + `timepoint` + `image` + `state label/report` + `next timepoint`.

### Tốt hơn cho world-model direction
`state_t` + `intervention_t` + `delta_t` + `state_t+1` + `outcome/reference`.

### Lý tưởng cho oncology CT
`patient -> scan_t -> lesions_t -> treatment_t -> scan_t+1 -> lesion correspondence/change -> outcome`.

## 5. Điểm cần hỏi phía lâm sàng

- Hệ thống có giữ được patient-level linkage giữa các lần CT/MRI không?
- Có biết treatment nào diễn ra giữa hai lần chụp và thời gian tương đối không?
- Có thể nối lesion giữa các lần chụp bằng chuyên gia/RECIST hoặc một protocol tương tự không?
- Báo cáo radiology, stage, pathology, labs và outcome nào thực sự truy cập hợp lệ?
- Có đủ ca follow-up liên tiếp để mô hình hóa transition thay vì chỉ baseline/final scan?

Không giả định HMU hiện có các thành phần này. Đây là checklist để đánh giá độ giàu của nguồn dữ liệu nếu nhóm cân nhắc chuyển khỏi ultrasound sang longitudinal CT/MRI.

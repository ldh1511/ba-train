# BA Learning Progress

> Domain: Banking | Background: Frontend Developer
> Cập nhật lần cuối: 2026-06-17

---

## Tổng quan lộ trình

| Module | Nội dung | Trạng thái |
|---|---|---|
| Module 1 | Tư duy BA | ✅ Hoàn thành |
| Module 2 | Thu thập yêu cầu / Elicitation | ✅ Hoàn thành |
| Module 3 | Phân tích yêu cầu | ✅ Hoàn thành |
| Module 4 | Tài liệu hóa / Documentation | 🔄 Đang học |
| Module 5 | Agile/Scrum thực chiến | ⬜ Chưa học |
| Module 6 | Kỹ năng mềm & thực chiến | ⬜ Chưa học |

---

## ✅ Module 1 — Tư duy BA

### Bài 1.1 — BA là gì, không phải là gì
- BA = người phát hiện vấn đề thật đằng sau yêu cầu được nói ra
- Không phải người ghi chép yêu cầu rồi chuyển cho dev
- Luôn hỏi "tại sao" trước khi ghi yêu cầu

**Điểm mạnh:** Tư duy đặt câu hỏi đa chiều, nhớ compliance/SBV  
**Cần luyện:** Đào sâu root business goal hơn

---

### Bài 1.2 — Các loại yêu cầu
| Loại | Câu hỏi cốt lõi | Ví dụ banking |
|---|---|---|
| BR | Tổ chức muốn đạt gì? | Tăng khách hàng SME 30% |
| StR | Người dùng cần gì? | Khách tự mở tài khoản online |
| FR | Hệ thống làm gì? | Tích hợp eKYC xác thực CCCD |
| NFR | Hệ thống tốt đến đâu? | Uptime 99.9%, lưu log 10 năm |

**Công thức phân loại nhanh:**
```
"[Tổ chức] muốn đạt..."        → BR
"[Người dùng] cần có thể..."   → StR
"Hệ thống phải [làm gì]..."    → FR
"Hệ thống phải [có số đo]..."  → NFR
```

**Điểm mạnh:** Nắm FR và NFR chắc  
**Cần luyện:** Ranh giới BR vs StR — BR không bao giờ nhắc đến người dùng cụ thể

---

### Bài 1.3 — Vòng đời dự án & vai trò BA

```
Initiation → Planning → Analysis → Design → Dev → Testing → Deploy → Maintenance
```

- BA làm nhiều nhất ở Analysis
- BA có bức tranh toàn cảnh duy nhất trong team
- Bug = sai so với spec | Spec gap = spec chưa cover case này
- Change Request: điều tra trước → kết luận sau, không kết luận vội

**Điểm mạnh:** Map đúng tình huống vào giai đoạn  
**Cần luyện:** Điều tra trước khi gọi là bug hay CR

---

## ✅ Module 2 — Thu thập yêu cầu / Elicitation

### Bài 2.1 — 5 kỹ thuật Elicitation

| Kỹ thuật | Dùng khi |
|---|---|
| Interview | Đào sâu 1 người |
| Workshop | Align nhiều người / giải quyết conflict |
| Observation | Hiểu As-Is thực tế |
| Survey | Scale số lượng lớn |
| Document Analysis | Chuẩn bị nền tảng trước khi gặp stakeholder |

> ⚠️ Document Analysis là bước **prep**, không phải kỹ thuật chính với technical stakeholder

**Điểm mạnh:** Chọn đúng kỹ thuật cho từng stakeholder  
**Cần luyện:** Document Analysis → phải Interview IT Architect sau

---

### Bài 2.2 — Nghệ thuật đặt câu hỏi

**5W1H:** Who / What / When / Where / Why / How

**5 Whys — hỏi chuỗi, không hỏi song song:**
```
Hỏi Why → Nhận câu trả lời → Hỏi Why về CÂU TRẢ LỜI ĐÓ → ...
```

**Câu hỏi mở vs đóng:**
- Tránh Yes/No → dùng "Anh mô tả... / Điều gì... / Như thế nào..."
- Câu đóng chỉ dùng để **confirm** thông tin đã biết

**Điểm mạnh:** Domain knowledge tốt (T24, portal, feature flag)  
**Cần luyện:** 5 Whys theo chiều dọc, chuyển câu đóng thành câu mở

---

### Bài 2.3 — Stakeholder Analysis

**Ma trận Power/Interest:**
```
Power cao + Interest cao  → Manage Closely
Power cao + Interest thấp → Keep Satisfied
Power thấp + Interest cao → Keep Informed
Power thấp + Interest thấp→ Monitor
```

**Xử lý conflict:**
1. Xác nhận conflict có thật không
2. Phân tích trade-off
3. Trình bày cho decision maker
4. Document quyết định

**Xử lý scope creep:** Không nói "không" — nói "có, nhưng + impact"

> ⚠️ Luôn nhớ: Compliance officer là stakeholder bắt buộc trong mọi dự án banking

**Điểm mạnh:** Phát hiện KPI quầy bị ảnh hưởng khi làm digital  
**Cần luyện:** Vẽ ma trận đầy đủ, đề xuất phased release khi conflict

---

## ✅ Module 3 — Phân tích yêu cầu

### Bài 3.1 — As-Is / To-Be Process

```
As-Is → Tìm pain point → Gap Analysis → To-Be
```

**Gap Analysis checklist:**
- Process nào thay đổi?
- Data nào thiếu/cần migrate?
- Hệ thống nào cần tích hợp mới?
- Ai bị ảnh hưởng về role/KPI?
- Luật/quy định nào cần đáp ứng?
- Kỹ năng nào cần train?

**Điểm mạnh:** Gap Analysis xuất sắc, nhận ra KPI quầy và Legal rule  
**Cần luyện:** Flowchart cần thêm swim lane, nhớ bước ký số điện tử trong To-Be banking

---

### Bài 3.2 — Mô hình hóa

**Use Case Diagram:**
- Actor, Use Case, System Boundary
- Include = bắt buộc có | Extend = tuỳ điều kiện
- Mũi tên <<include>> đi từ UC con → UC cha

**DFD:**
- Process = biến đổi data (input ≠ output)
- Data Store = lưu trữ, không biến đổi
- Level 0 = Context Diagram (1 process trung tâm)
- Level 1 = chi tiết sub-process

> ⚠️ Rectangle trong flowchart = Process trong DFD. Diamond KHÔNG xuất hiện trong DFD.

**Điểm mạnh:** AML + SWIFT trong DFD, domain knowledge banking rõ  
**Cần luyện:** Phân biệt Level 0 vs Level 1, không duplicate data store

---

### Bài 3.3 — Conflict, Gap & Scope Creep

**3 loại conflict:**
- Giữa stakeholder
- Giữa FR và NFR
- Conflict ngầm (không ai nói ra)

**Async FD check** — pattern phổ biến banking:
> Cho giao dịch chạy trước, FD check song song, nếu phát hiện gian lận → freeze/reverse sau

**Xử lý scope creep — 4 bước:**
1. Ghi nhận (không reject ngay)
2. Estimate impact
3. Trình bày trade-off
4. Document nếu approve — CC PM/PO

> ⚠️ Luôn loop in PM/PO khi có yêu cầu mới từ stakeholder  
> ⚠️ Đề xuất lightweight option trước khi estimate full feature

**Điểm mạnh:** Quy trình xử lý scope creep chuẩn  
**Cần luyện:** Nhớ async FD check, flag compliance risk trước khi làm

---

## 🔄 Module 4 — Tài liệu hóa (Đang học)

### Bài 4.1 — User Story & Acceptance Criteria ✅

**Format User Story:**
```
As a [role cụ thể],
I want to [action],
So that [benefit thật sự — không phải action tránh được].
```

**INVEST:** Independent / Negotiable / Valuable / Estimable / Small / Testable

**AC format Given/When/Then:**
```
Given [pre-condition đầy đủ],
When [hành động],
Then [kết quả cụ thể, đo được].
```

**AC checklist:**
- Happy path
- Validation errors
- Business rule violations
- System errors (timeout, T24 down)
- Edge cases
- Security (OTP sai, session hết hạn)

> ⚠️ Rule vàng: Không bao giờ trừ tiền khi không có confirmation từ core banking  
> ⚠️ Tính năng auto-run: luôn hỏi "nếu thất bại lúc 2 giờ sáng — khách biết không? Retry không?"

**Điểm mạnh:** Nghĩ đến system-triggered scenario  
**Cần luyện:** Role cụ thể hơn, So that là benefit thật, AC cho scheduled job cần retry logic

---

### Bài 4.2 — Use Case Description 🔄 Đang học

**Cấu trúc:**
- Use Case ID / Name / Actor / Description
- Precondition / Postcondition
- Main Flow → Alternative Flow → Exception Flow

| Loại Flow | Khi nào | Kết quả |
|---|---|---|
| Main | Con đường lý tưởng | Thành công |
| Alternative | Biến thể, vẫn thành công | Thành công |
| Exception | Lỗi, không thỏa điều kiện | Thất bại |

---

### ⬜ Bài 4.3 — BRD
### ⬜ Bài 4.4 — FRD
### ⬜ Bài 4.5 — Wireframe & Prototype review

---

## ⬜ Module 5 — Agile/Scrum thực chiến
- 5.1 Scrum cơ bản
- 5.2 Vai trò BA trong Scrum (3 amigos)
- 5.3 Quản lý backlog (MoSCoW)

---

## ⬜ Module 6 — Kỹ năng mềm & thực chiến
- 6.1 Giao tiếp business vs dev
- 6.2 Facilitation
- 6.3 Các bẫy thường gặp của BA mới

---

## Điểm mạnh tổng thể
- Tư duy kỹ thuật (T24, AML, SWIFT, feature flag, portal)
- Phân tích đa chiều, không accept yêu cầu mù quáng
- Gap Analysis và downstream thinking tốt
- Xử lý conflict có cấu trúc

## Pattern cần cải thiện
- Nhớ **Compliance/SBV** là stakeholder bắt buộc mọi dự án banking
- **Document quyết định** sau mọi cuộc họp
- **Loop in PM/PO** khi có yêu cầu mới
- **So that** trong User Story phải là benefit thật, không phải action tránh được
- **Không kết luận** bug/CR trước khi điều tra

# Thin SPEC

## 1. Track, product/app và user

Track:
AI Agent

Product/app thật:
AI Travel Planner Agent

User cụ thể:
Người muốn du lịch tự túc và chưa có lịch trình.

Nhóm có phải user thật không?

Có.

---

## 2. Evidence summary

| Evidence                                            | Nguồn      | User/pain nói lên điều gì? | SPEC phải đổi gì?      |
| --------------------------------------------------- | ----------- | ------------------------------- | -------------------------- |
| Người dùng mất nhiều giờ để lên kế hoạch | Self-use    | Planning quá tốn thời gian   | Tập trung vào itinerary  |
| Thiếu thông tin đầu vào                        | Observation | AI dễ trả lời sai            | Thêm clarification        |
| Review từ cộng đồng travel                      | Social      | Khó chọn khách sạn          | Thêm hotel recommendation |

---

## 3. Pain statement

User muốn đi du lịch tự túc đang gặp khó ở bước lập kế hoạch.

Vì phải tìm kiếm và tổng hợp thông tin từ nhiều nguồn.

Dẫn tới mất nhiều giờ chuẩn bị và khó đưa ra quyết định.

Bằng chứng chính là observation từ self-use và review cộng đồng du lịch.

---

## 4. Build slice

Cho người đang lên kế hoạch du lịch.

Prototype sẽ dùng AI để:

* Thu thập intent còn thiếu.
* Tạo itinerary 3 ngày.
* Đề xuất khách sạn phù hợp.

Output:

* Itinerary theo ngày.
* Danh sách địa điểm.
* Khách sạn đề xuất.

Failure mode:

Thông tin đầu vào không đủ.

Mitigation:

AI hỏi lại trước khi lập kế hoạch.

---

## 5. Auto/Aug decision

[X] Conditional Automation

Lý do chọn:

AI có thể tự động lập kế hoạch khi đủ dữ liệu.

Nếu thiếu dữ liệu hoặc mơ hồ thì phải hỏi lại người dùng.

Human role:

Decider

---

## 6. Four paths

| Path           | Prototype phải thể hiện gì?                     |
| -------------- | --------------------------------------------------- |
| Happy          | User cung cấp đủ thông tin → AI tạo itinerary |
| Low-confidence | Thiếu ngân sách hoặc số ngày → AI hỏi lại  |
| Failure        | User nhập yêu cầu quá mơ hồ → kế hoạch sai |
| Correction     | User bổ sung thông tin → AI tạo lại kế hoạch |

---

## 7. Failure mode nguy hiểm nhất

Nếu user chỉ nhập:

"Tôi muốn đi Nhật"

AI có thể tạo lịch trình sai hoàn toàn so với nhu cầu thực tế.

Hậu quả:

Mất niềm tin vào hệ thống.

Prototype sẽ xử lý bằng:

Ask Again.

Owner kiểm thử path này là:

[Tên thành viên]

---

## 8. Owner plan cho sáng Day 06

| Thành viên | Việc phụ trách | Bằng chứng cần có trong repo |
| ------------ | ----------------- | -------------------------------- |
| Member 1     | Research          | Evidence                         |
| Member 2     | SPEC              | Thin SPEC                        |
| Member 3     | Agent Workflow    | Diagram                          |
| Member 4     | Prototype         | Demo                             |
| Member 5     | Testing           | Failure Cases                    |
|              |                   |                                  |

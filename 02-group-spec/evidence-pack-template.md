
# Evidence Pack

## 1. Nhóm và track

Tên nhóm: [Tên nhóm]

Track: AI Agent

Product/app đã chọn:
AI Travel Planner Agent

Build slice đang nghĩ:
AI Travel Planner Agent là một hệ thống AI Agent hỗ trợ lập kế hoạch du lịch đầu-cuối (end-to-end). Người dùng chỉ cần mô tả nhu cầu bằng ngôn ngữ tự nhiên, agent sẽ tự động thu thập và làm rõ các intent còn thiếu, sau đó sử dụng nhiều công cụ để tìm kiếm địa điểm, tối ưu lịch trình, hiển thị trên bản đồ và gợi ý khách sạn hoặc dịch vụ phù hợp. Thay vì chỉ trả lời câu hỏi, agent có khả năng chủ động lập kế hoạch và hỗ trợ ra quyết định, giúp người dùng xây dựng một chuyến đi hoàn chỉnh trong vài phút.

---

## 2. Self-use evidence

| Observation    | Screenshot/link                                                           | Path liên quan   | Điều học được                                                |
| -------------- | ------------------------------------------------------------------------- | ----------------- | ------------------------------------------------------------------ |
| Happy          | User nhập: "Tôi muốn đi Đà Nẵng 3 ngày với ngân sách 8 triệu" | Planning          | AI có thể tạo itinerary khá nhanh                              |
| Low-confidence | User chỉ nhập: "Tôi muốn đi Nhật"                                   | Intent Collection | Thiếu ngân sách, thời gian, sở thích nên AI phải hỏi lại |
| Failure        | User yêu cầu "lịch trình tối ưu nhất"                              | Optimization      | Không có một đáp án tối ưu tuyệt đối                    |
| Correction     | AI hỏi lại số ngày và ngân sách trước khi lập kế hoạch        | Clarification     | Hỏi lại giúp giảm kế hoạch sai                               |

---

## 3. User / review / social evidence

| Quote / review / observation                                | Nguồn                | User là ai?          | Pain/failure mode        |
| ----------------------------------------------------------- | --------------------- | --------------------- | ------------------------ |
| "Mất cả buổi tối để lên lịch trình đi Phú Quốc" | Phỏng vấn nhanh     | Sinh viên            | Planning tốn thời gian |
| "Không biết nên ở khu vực nào để tiện đi lại"    | Travel Facebook Group | Du khách tự túc    | Decision support         |
| "Đọc quá nhiều blog nhưng mỗi nơi nói một kiểu"   | Reddit Travel         | Người mới du lịch | Information overload     |

---

## 4. Competitor / analog evidence

| App / mô hình tham khảo | Họ xử lý task này thế nào?   | Pattern học được       | Có áp dụng trong 1 ngày không? |
| -------------------------- | ---------------------------------- | -------------------------- | ----------------------------------- |
| Google Maps                | Gợi ý địa điểm theo khu vực | Hiển thị trên bản đồ | Có                                 |
| TripAdvisor                | Review và ranking                 | Social proof               | Có                                 |
| Wonderplan AI              | Sinh lịch trình tự động       | AI itinerary generation    | Có                                 |
| ChatGPT                    | Hỏi đáp và planning            | Clarification loop         | Có                                 |

---

## 5. Evidence -> Insight

Evidence nổi bật nhất:

Người dùng mất nhiều thời gian tổng hợp thông tin từ blog, bản đồ, review và khách sạn trước khi ra quyết định.

Insight:

User không chỉ gặp khó trong việc tìm địa điểm.

Thật ra họ cần hỗ trợ ra quyết định và tổng hợp thông tin đáng tin cậy thành một kế hoạch hoàn chỉnh.

Opportunity:

AI có thể giúp bằng cách tự động thu thập intent còn thiếu và tạo itinerary sơ bộ để người dùng chỉnh sửa thay vì tự lập kế hoạch từ đầu.

---

## 6. Evidence đổi SPEC như thế nào?

[X] Đổi build slice.

Trước evidence, nhóm định build travel agent end-to-end.

Sau evidence, nhóm đổi thành:

"AI hỏi lại intent còn thiếu và tạo itinerary 3 ngày."

Lý do:

Có thể demo trong vài phút và kiểm thử được failure path.

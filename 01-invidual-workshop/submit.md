# Workshop — Mổ App AI Thật

**Họ và tên:** Hồ Thành Tiến

**Sản phẩm được chọn:** Vietnam Airlines — NEO

**Thời gian:** 35-45 phút

**Output:** Finding Note + As-Is / To-Be Sketch

---

# 1. Chọn một sản phẩm để dùng thử

| Sản phẩm              | AI Feature                                                                  | Cách truy cập          |
| ----------------------- | --------------------------------------------------------------------------- | ------------------------ |
| Vietnam Airlines — NEO | Chatbot hỗ trợ vé máy bay, hành lý, đổi vé, hoàn vé, khiếu nại | Website Vietnam Airlines |

Lý do chọn:

* Có lượng người dùng lớn.
* Workflow hỗ trợ khách hàng rõ ràng.
* Nhiều tình huống thực tế cần AI hỗ trợ.
* Dễ quan sát khoảng cách giữa "Product Promise" và "Reality".

---

# 2. Dùng thử: Promise vs Reality

## Product Promise

NEO được giới thiệu là trợ lý hỗ trợ khách hàng của Vietnam Airlines.

Các nhiệm vụ chính:

* Tra cứu hành lý.
* Hỗ trợ đổi vé.
* Hỗ trợ hoàn vé.
* Hỗ trợ chuyến bay.
* Hỗ trợ khiếu nại.
* Giảm tải cho tổng đài chăm sóc khách hàng.

---

## User được hứa sẽ được giúp

* Hành khách Vietnam Airlines.
* Người cần thông tin nhanh.
* Người không muốn gọi tổng đài.
* Người gặp sự cố trong quá trình bay.

---

## Kỳ vọng của tôi

Tôi kỳ vọng NEO có thể:

1. Trả lời nhanh các câu hỏi FAQ.
2. Hướng dẫn từng bước khi gặp sự cố.
3. Hỏi lại khi thiếu thông tin.
4. Đưa ra phương án xử lý thay vì chỉ cung cấp chính sách.

---

# Evidence Collected

## Test 1 — Hành lý xách tay

### Prompt

```text
Tôi được mang bao nhiêu kg hành lý xách tay?
```

### Observation

NEO trả lời chính xác và đầy đủ theo từng hạng vé và từng hành trình.

### Kết quả

Thành công

### Nhận xét

Đây là trường hợp FAQ rõ ràng.

NEO hoạt động tốt khi câu hỏi khớp với dữ liệu chính sách đã có.

---

## Test 2 — Đổi vé

### Prompt

```text
Tôi muốn đổi vé.
```

### Observation

NEO trả về toàn bộ chính sách đổi vé.

Bot không hỏi:

* Vé mua ở đâu?
* Vé hạng nào?
* Muốn đổi ngày hay đổi chuyến?

### Kết quả

Chưa tối ưu

### Nhận xét

Bot hiểu chủ đề nhưng không làm rõ nhu cầu thực sự của người dùng.

---

## Test 3 — Lỡ chuyến bay

### Prompt

```text
Tôi bị lỡ chuyến bay rồi.
```

### Observation

NEO yêu cầu người dùng liên hệ hotline hoặc email hỗ trợ.

### Kết quả

Trải nghiệm chưa tốt

### Nhận xét

Người dùng đang gặp tình huống khẩn cấp nhưng bot không hướng dẫn các bước xử lý trước mắt.

---

## Test 4 — Trễ chuyến nối chuyến quốc tế

### Prompt

```text
Tôi bị trễ chuyến nối chuyến quốc tế thì phải làm gì?
```

### Observation

NEO tiếp tục yêu cầu liên hệ hotline hoặc đại lý.

Không có hướng dẫn hành động.

### Kết quả

Thất bại

### Nhận xét

Bot biết đây là tình huống nối chuyến nhưng không giúp người dùng hoàn thành nhiệm vụ.

---

## Test 5 — Pin dự phòng 30000mAh

### Prompt

```text
Tôi được mang pin dự phòng 30000mAh lên máy bay không?
```

### Observation

NEO giải thích quy định theo Wh nhưng không giúp người dùng quy đổi từ mAh sang Wh.

### Kết quả

Chưa hoàn thành nhiệm vụ

### Nhận xét

Bot cung cấp kiến thức nhưng chưa đưa ra kết luận cho câu hỏi của người dùng.

---

# Tổng hợp Observation

| Test                   | Kỳ vọng               | Kết quả |
| ---------------------- | ----------------------- | --------- |
| Hành lý xách tay    | Trả lời FAQ           | ✅        |
| Đổi vé              | Hỏi lại để làm rõ | ⚠️      |
| Lỡ chuyến bay        | Hướng dẫn xử lý    | ❌        |
| Nối chuyến quốc tế | Action plan             | ❌        |
| Pin dự phòng         | Trả lời Yes/No        | ⚠️      |

---

# 3. Vẽ 4 Paths

## Happy Path

```text
User
  ↓
Hỏi thông tin hành lý
  ↓
NEO hiểu chính xác
  ↓
Tra cứu policy
  ↓
Trả lời đúng
  ↓
User hoàn thành task
```

### Đánh giá

Happy Path hoạt động tốt đối với FAQ đơn giản.

---

## Low Confidence Path

### Quan sát

Không thấy cơ chế Low Confidence.

Ví dụ:

```text
Tôi muốn đổi vé
```

Bot không hỏi thêm thông tin.

Bot giả định intent và trả về toàn bộ chính sách.

### Đánh giá

Chưa có Low Confidence Flow rõ ràng.

---

## Failure Path

```text
User
  ↓
Tôi bị lỡ chuyến bay
  ↓
NEO trả hotline
  ↓
User vẫn không biết phải làm gì
  ↓
Thoát chatbot
```

### Đánh giá

Failure xảy ra ở các tình huống cần hướng dẫn hành động.

---

## Correction Path

### Quan sát

Không thấy:

* Nút feedback.
* Cơ chế correction.
* Cơ chế học từ phản hồi.

### Đánh giá

Correction Path chưa được thể hiện.

---

# 4. Finding thành Product Decision

## Finding #1 — Actionability Gap

### Trigger

Người dùng gặp sự cố:

* Lỡ chuyến bay.
* Trễ nối chuyến.
* Đổi vé.

### Failure

NEO chủ yếu cung cấp:

* Hotline.
* Email.
* Chính sách.

### Impact

Người dùng không biết:

```text
Tôi cần làm gì ngay bây giờ?
```

### Layer

Promise + UX Recovery

### Product Decision

NEO nên cung cấp:

* Action Plan.
* Step-by-step guidance.
* Sau đó mới chuyển sang hotline.

Ví dụ:

```text
Bước 1:
Đến quầy Transfer.

Bước 2:
Xuất trình Boarding Pass.

Bước 3:
Yêu cầu hỗ trợ đổi chuyến.
```

---

## Finding #2 — Thiếu Clarification Flow

### Trigger

```text
Tôi muốn đổi vé.
```

### Failure

NEO không hỏi thêm thông tin.

### Impact

Câu trả lời dài nhưng không cá nhân hóa.

### Layer

Intent Clarification

### Product Decision

Thêm Clarification Flow:

```text
Anh/chị mua vé ở đâu?

( ) Website
( ) App
( ) Đại lý
```

Sau đó mới trả lời.

---

## Finding #3 — Trả lời kiến thức thay vì kết luận

### Trigger

```text
Tôi được mang pin dự phòng 30000mAh không?
```

### Failure

Bot đưa quy định nhưng không đưa kết luận.

### Impact

Người dùng phải tự tính toán.

### Layer

Reasoning + UX

### Product Decision

Bot nên:

* Quy đổi tự động.
* Trả lời Yes/No trước.
* Giải thích sau.

---

# 5. Sketch As-Is / To-Be

## As-Is

```text
USER
  │
  ▼
Nhập câu hỏi
  │
  ▼
NEO
  │
  ├── FAQ đơn giản
  │       │
  │       ▼
  │   Trả lời đúng
  │
  └── Tình huống phức tạp
          │
          ▼
     Trả policy
          │
          ▼
     Hotline
          │
          ▼
      User tự xử
```

### Điểm gãy

* Không có Clarification Flow.
* Không có Action Guidance.
* Không có Recovery Flow.
* Không có Correction Path.

---

## To-Be

```text
USER
  │
  ▼
Nhập câu hỏi
  │
  ▼
Intent Detection
  │
  ├── FAQ
  │       │
  │       ▼
  │   Trả lời trực tiếp
  │
  └── Tình huống xử lý
          │
          ▼
     Clarification Flow
          │
          ▼
       Action Plan
          │
          ▼
       Escalation
          │
          ▼
         Hotline
```

---

# 6. Kết luận

Qua quá trình sử dụng thực tế, tôi nhận thấy NEO không gặp vấn đề lớn về độ chính xác dữ liệu. Các câu hỏi FAQ như hành lý hoặc quy định pin đều được trả lời tương đối đúng.

Tuy nhiên, điểm yếu lớn nhất nằm ở khả năng hỗ trợ hành động. Khi người dùng gặp các tình huống thực tế như lỡ chuyến bay, trễ nối chuyến hoặc đổi vé, chatbot chủ yếu đóng vai trò công cụ tra cứu thông tin thay vì trợ lý hỗ trợ giải quyết vấn đề.

Finding này dẫn tới quyết định product rằng NEO nên được phát triển theo hướng  **Action-Oriented Assistant** , có khả năng:

* Clarify intent.
* Hướng dẫn từng bước.
* Hỗ trợ recovery.
* Chỉ chuyển sang con người khi thật sự cần thiết.

Điều này sẽ giúp chatbot hoàn thành đúng lời hứa ban đầu là hỗ trợ hành khách, thay vì chỉ cung cấp chính sách và thông tin liên hệ.

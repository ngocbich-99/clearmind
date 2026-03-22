# Story: 1.2 - Mood History Chart

**Epic:** 1 - Mood Tracking

**As a** người dùng
**I want** xem biểu đồ mood theo tuần và tháng
**So that** tôi có thể nhận ra xu hướng cảm xúc

## 1.  Business Context
*   **Value:** Giúp người dùng nhận biết xu hướng cảm xúc của mình theo thời gian, từ đó có thể điều chỉnh hành vi và tìm kiếm sự hỗ trợ khi cần thiết.
*   **Impact:** Cải thiện nhận thức về sức khỏe tinh thần, thúc đẩy hành vi tích cực.
*   **Priority:** High (Quan trọng để hoàn thiện tính năng theo dõi cảm xúc)

## 2.  Requirements

### 2.1. Functional Requirements

*   **FR1:** Hiển thị line chart thể hiện mood trong 7 ngày gần nhất khi vào tab Mood History.
*   **FR2:** Cho phép người dùng chuyển đổi giữa biểu đồ tuần (7 ngày) và biểu đồ tháng (30 ngày).
*   **FR3:** Hiển thị empty state với prompt "Hãy bắt đầu ghi nhận cảm xúc" nếu không có dữ liệu mood.
*   **FR4:** Dữ liệu mood hiển thị trên chart phải được lấy từ Supabase table `mood_logs`.

### 2.2. Non-Functional Requirements

*   **NFR1:** Biểu đồ phải load nhanh (dưới 2 giây).
*   **NFR2:** Giao diện biểu đồ phải responsive, hiển thị tốt trên các kích thước màn hình khác nhau.
*   **NFR3:** Sử dụng thư viện chart nhẹ (recharts hoặc chart.js) để tối ưu hiệu năng.

## 3.  Mockups / Wireframes
*(Cần đính kèm ảnh mockups/wireframes minh họa giao diện biểu đồ tuần, tháng và empty state)*

## 4.  Acceptance Criteria

*   **AC1:** Given người dùng vào tab Mood History, When data có sẵn, Then hiển thị line chart 7 ngày gần nhất.
*   **AC2:** Given biểu đồ tuần hiển thị, When người dùng chuyển sang Monthly, Then hiển thị chart 30 ngày.
*   **AC3:** Given không có data, When mở Mood History, Then hiển thị empty state với prompt "Hãy bắt đầu ghi nhận cảm xúc".
*   **AC4:** Given có data mood trong tháng này, When xem biểu đồ tháng, Then dữ liệu hiển thị chính xác theo mood đã ghi.
*   **AC5:** Given không có data trong tuần này, When xem biểu đồ tuần, Then hiển thị empty state phù hợp.

## 5.  Technical Design

*   **Component:** `src/features/mood/components/MoodHistory.tsx`
*   **Data Fetching:** Sử dụng Supabase client để query dữ liệu từ table `mood_logs`.
*   **Chart Library:** recharts hoặc chart.js (chọn một).
*   **Data Transformation:** Xử lý dữ liệu lấy được từ Supabase để phù hợp với định dạng của thư viện chart.
*   **Date Range Handling:** Implement logic để chuyển đổi giữa biểu đồ tuần và tháng.
*   **Error Handling:** Hiển thị thông báo lỗi nếu không lấy được dữ liệu từ Supabase.

## 6.  Open Issues / Risks

*   **Issue 1:** Lựa chọn thư viện chart phù hợp (cần cân nhắc kích thước bundle, hiệu năng và dễ sử dụng).
*   **Risk 1:** Khả năng gặp vấn đề về hiệu năng nếu query dữ liệu lớn từ Supabase (cần tối ưu query).
*   **Risk 2:** Khó khăn trong việc tùy chỉnh giao diện biểu đồ theo design mong muốn.

## 7.  Out of Scope

*   Hiển thị dữ liệu mood chi tiết cho từng ngày (chỉ hiển thị tổng quan trên chart).
*   Cho phép người dùng tùy chỉnh khoảng thời gian hiển thị trên chart (chỉ hỗ trợ tuần và tháng).
*   Phân tích chuyên sâu về xu hướng cảm xúc (ví dụ: so sánh với các yếu tố bên ngoài).

## 8.  Future Considerations

*   Thêm tính năng dự đoán mood dựa trên lịch sử dữ liệu.
*   Tích hợp với các tính năng khác (ví dụ: gợi ý hoạt động dựa trên xu hướng mood).
*   Cho phép người dùng chia sẻ biểu đồ mood với bạn bè/người thân.

## Mockup
![Mockup 1-2-mood-history-chart](https://image.pollinations.ai/prompt/Mobile%20app%20UI%20mockup%2C%20iOS%20style%2C%20clean%20minimal%20design%2C%20ClearMind%20mental%20health%20app%2C%20feature%3A%20mood%20history%20chart%2C%20soft%20pastel%20colors%2C%20rounded%20corners%2C%20modern%20mobile%20interface?width=390&height=844&model=flux&seed=1774201304842)
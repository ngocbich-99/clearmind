# 1-2-mood-history-chart (Epic 1, Story 2: Mood History Chart)

## Epic: Mood Tracking

**Objective**: Cho phép người dùng theo dõi cảm xúc hàng ngày và xem xu hướng theo thời gian.

### Story: Mood History Chart
- **As a** người dùng
- **I want** xem biểu đồ mood theo tuần và tháng
- **So that** tôi có thể nhận ra xu hướng cảm xúc

**Acceptance Criteria:**
- Given người dùng vào tab Mood History, When data có sẵn, Then hiển thị line chart 7 ngày gần nhất
- Given biểu đồ tuần hiển thị, When người dùng chuyển sang Monthly, Then hiển thị chart 30 ngày
- Given không có data, When mở Mood History, Then hiển thị empty state với prompt "Hãy bắt đầu ghi nhận cảm xúc"

**Technical Notes:**
- Sử dụng thư viện chart nhẹ (recharts hoặc chart.js)
- Component: `src/features/mood/components/MoodHistory.tsx`
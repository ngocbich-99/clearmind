# Story 1.1: Mood Selector UI
Status: ready-for-dev

## Story
As a người dùng, I want chọn mood hàng ngày từ 5 levels, so that tôi có thể ghi nhận cảm xúc một cách nhanh chóng.

## Acceptance Criteria (BDD)
1. Given trang chủ hiển thị, When người dùng chưa chọn mood hôm nay, Then hiển thị Mood Selector.
2. Given Mood Selector hiển thị, When người dùng tap vào 1 emoji, Then lưu mood và hiển thị xác nhận.
3. Given đã chọn mood hôm nay, When quay lại trang chủ, Then hiển thị mood đã chọn (không cho chọn lại).

## Tasks / Subtasks
- [ ] Tạo component `src/features/mood/components/MoodSelector.tsx`
- [ ] Tạo hook `src/features/mood/hooks/useMood.ts` để quản lý state và tương tác Supabase
- [ ] Kết nối với Supabase table `mood_logs` để lưu trữ mood
- [ ] Xử lý logic hiển thị dựa trên trạng thái đã chọn mood hay chưa

## Dev Notes
- Sử dụng React Context hoặc Redux Toolkit nếu cần chia sẻ state mood rộng hơn.
- Component nên hiển thị 5 emojis đại diện cho các mức mood khác nhau.
- Hook `useMood` nên có các hàm `selectMood(level: number)` và `getTodayMood()`
- Sử dụng Row Level Security (RLS) trên Supabase để đảm bảo người dùng chỉ có thể truy cập mood của mình.

### References
- PRD: Mood Tracking (F1)
- Architecture: Database Schema (mood_logs)

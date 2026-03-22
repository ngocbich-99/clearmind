# Story 1.1: Mood Selector UI
Status: ready-for-dev

## Story
As a người dùng, I want chọn mood hàng ngày từ 5 levels, so that tôi có thể ghi nhận cảm xúc một cách nhanh chóng.

## Acceptance Criteria (BDD)
1. Given trang chủ hiển thị, When người dùng chưa chọn mood hôm nay, Then hiển thị Mood Selector
2. Given Mood Selector hiển thị, When người dùng tap vào 1 emoji, Then lưu mood và hiển thị xác nhận
3. Given đã chọn mood hôm nay, When quay lại trang chủ, Then hiển thị mood đã chọn (không cho chọn lại)

## Tasks / Subtasks
- [ ] Tạo component `MoodSelector.tsx` với 5 emoji đại diện cho mức độ cảm xúc.
- [ ] Tạo hook `useMood.ts` để quản lý trạng thái mood hiện tại và tương tác với Supabase.
- [ ] Thiết lập Supabase table `mood_logs` với các cột `id`, `user_id`, `mood_level`, `created_at`.
- [ ] Implement logic để lưu mood vào Supabase khi người dùng chọn một emoji.
- [ ] Implement logic để hiển thị mood đã chọn nếu người dùng đã chọn mood trong ngày.
- [ ] Kiểm tra và đảm bảo tính responsive của Mood Selector trên các thiết bị khác nhau.
- [ ] Viết unit tests cho component và hook.

## Dev Notes
- Component: `src/features/mood/components/MoodSelector.tsx`
- Hook: `src/features/mood/hooks/useMood.ts`
- Supabase table: `mood_logs`
- Sử dụng React Context hoặc Redux Toolkit để quản lý state (tuỳ chọn).
- Sử dụng Supabase client SDK để tương tác với database.
- Chú ý đến Row Level Security (RLS) trên table `mood_logs`.
- Áp dụng coding conventions của dự án.

### References
- PRD: Mood Tracking (F1)
- Architecture Document: Database Schema (mood_logs), API Patterns

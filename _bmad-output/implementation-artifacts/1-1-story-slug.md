# 1-1-story-slug (Epic 1, Story 1: Mood Selector UI)

## Overview

Người dùng có thể chọn mood hàng ngày từ 5 levels (rất tệ -> rất tốt) để ghi nhận cảm xúc một cách nhanh chóng.

## Story Details

- **As a** người dùng
- **I want** chọn mood hàng ngày từ 5 levels
- **So that** tôi có thể ghi nhận cảm xúc một cách nhanh chóng

## Acceptance Criteria

- Given trang chủ hiển thị, When người dùng chưa chọn mood hôm nay, Then hiển thị Mood Selector
- Given Mood Selector hiển thị, When người dùng tap vào 1 emoji, Then lưu mood và hiển thị xác nhận
- Given đã chọn mood hôm nay, When quay lại trang chủ, Then hiển thị mood đã chọn (không cho chọn lại)

## Technical Notes

- Component: `src/features/mood/components/MoodSelector.tsx`
- Hook: `src/features/mood/hooks/useMood.ts`
- Supabase table: `mood_logs`

## Dependencies

- Cần có Supabase project và bảng `mood_logs` được setup.
- Cần component trang chủ để hiển thị Mood Selector.

## Out of Scope

- Tính năng gợi ý hoạt động dựa trên mood.
- Thiết kế UX chi tiết cho Mood Selector (sẽ có trong file thiết kế).

## Future Considerations

- Thêm tùy chọn ghi chú ngắn gọn cho mood.
- Tích hợp với tính năng nhắc nhở chọn mood hàng ngày.
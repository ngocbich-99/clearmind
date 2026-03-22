# 2-1-story-slug (Epic 2, Story 1: Garden Layout & Display)

**Story Point:** 3

## Mô tả

- **As a** người dùng
- **I want** xem khu vườn của mình với các cây cối
- **So that** tôi cảm thấy motivated để duy trì thói quen

## Acceptance Criteria

- Given người dùng vào tab Vườn, When load xong, Then hiển thị grid layout khu vườn
- Given khu vườn hiển thị, When có cây, Then cây hiển thị đúng growth stage (1-5)
- Given người dùng mới, When chưa có cây, Then hiển thị vườn trống với prompt "Trồng cây đầu tiên"

## Tasks

- [ ] Tạo component `GardenView.tsx` tại `src/features/garden/components/GardenView.tsx`
- [ ] Implement grid layout cho khu vườn (responsive cho mobile).
- [ ] Lấy danh sách cây từ Supabase table `garden_items` (sử dụng `useSupabaseClient`).
- [ ] Hiển thị cây cối với growth stage tương ứng (1-5).
- [ ] Implement logic hiển thị vườn trống với prompt "Trồng cây đầu tiên" nếu user chưa có cây nào.
- [ ] Thêm CSS animations đơn giản cho cây (ví dụ: hiệu ứng rung nhẹ).
- [ ] Viết unit tests cho component `GardenView.tsx`.

## Technical Notes

- Component: `src/features/garden/components/GardenView.tsx`
- CSS animations cho cây phát triển
- Grid layout responsive cho mobile
- Sử dụng `useSupabaseClient` hook để tương tác với Supabase.
- Fetch data `garden_items` cho user hiện tại.

## Dependencies

- Epic 2: Vườn Tâm Trí (Mental Garden)
- Supabase client

## Blockers

- Cần có schema database `garden_items` đã được định nghĩa (đã có trong Architecture Document).
- Cần có Supabase client đã được cấu hình.

## Out of Scope

- Tương tác với cây (ví dụ: tưới cây).
- Hiển thị thông tin chi tiết về cây.
- Tuỳ chỉnh layout vườn.
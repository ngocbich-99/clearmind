# 2-2-story-slug (Epic 2, Story 2: story slug)

## Story Summary

Người dùng có thể trồng cây mới trong Vườn Tâm Trí, liên kết cây đó với một thói quen cụ thể. Khi người dùng hoàn thành thói quen, cây sẽ phát triển.

## As a

người dùng

## I want

trồng cây mới gắn với một thói quen

## So that

tôi có động lực duy trì thói quen đó

## Acceptance Criteria

- Given người dùng tap "Trồng cây", When chọn loại cây và thói quen, Then tạo cây mới ở stage 1
- Given cây vừa trồng, When hoàn thành thói quen liên quan, Then cây tăng growth stage
- Given tối đa 6 cây trong vườn, When đã có 6 cây, Then disable nút "Trồng cây"

## Technical Notes

- Component: `src/features/garden/components/PlantTree.tsx`
- Supabase table: `garden_items`
- Max 6 cây per user

## UI/UX Considerations

- Giao diện chọn loại cây phải trực quan và hấp dẫn.
- Danh sách thói quen có thể lấy từ gợi ý hoặc cho phép người dùng tự tạo.
- Hiển thị thông báo hoặc animation khi cây tăng trưởng stage.
- Cân nhắc hiệu ứng âm thanh nhẹ khi trồng cây hoặc cây phát triển.

## Backend Considerations

- Cần có API endpoint để tạo mới `garden_items` trong Supabase.
- Cần có logic để theo dõi và cập nhật `growth_stage` dựa trên việc hoàn thành thói quen.
- Sử dụng Row Level Security để đảm bảo người dùng chỉ có thể thao tác với cây của mình.

## Potential Risks

- Khó khăn trong việc liên kết cây với thói quen một cách tự động (cần cân nhắc cơ chế thủ công hoặc tích hợp với hệ thống theo dõi thói quen nếu có).
- Performance có thể bị ảnh hưởng nếu số lượng cây trong vườn quá lớn (cần tối ưu hóa query và render).

## Open Questions

- Làm thế nào để xác định khi nào người dùng đã hoàn thành một thói quen liên kết với cây? (Cần thiết kế cơ chế theo dõi và trigger cập nhật `growth_stage`).
- Cần những loại cây nào và liên kết với những thói quen nào? (Cần nghiên cứu và lựa chọn các loại cây và thói quen phù hợp với người dùng mục tiêu).
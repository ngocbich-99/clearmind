# Story: 2-2-plant-a-new-tree (Epic 2, Story 2: plant a new tree)

**As a** người dùng
**I want** trồng cây mới gắn với một thói quen
**So that** tôi có động lực duy trì thói quen đó

## Acceptance Criteria

- Given người dùng tap "Trồng cây", When chọn loại cây và thói quen, Then tạo cây mới ở stage 1
- Given cây vừa trồng, When hoàn thành thói quen liên quan, Then cây tăng growth stage
- Given tối đa 6 cây trong vườn, When đã có 6 cây, Then disable nút "Trồng cây"

## Technical Notes

- Component: `src/features/garden/components/PlantTree.tsx`
- Supabase table: `garden_items`
- Max 6 cây per user
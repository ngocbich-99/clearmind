# Story: 2-1-garden-layout-display (Epic 2, Story 1: garden layout display)

**Epic:** Vườn Tâm Trí (Mental Garden)

**Objective**: Tạo khu vườn ảo phản ánh sức khỏe tinh thần, gamify thói quen tốt.

**As a** người dùng
**I want** xem khu vườn của mình với các cây cối
**So that** tôi cảm thấy motivated để duy trì thói quen

## Acceptance Criteria:

- Given người dùng vào tab Vườn, When load xong, Then hiển thị grid layout khu vườn
- Given khu vườn hiển thị, When có cây, Then cây hiển thị đúng growth stage (1-5)
- Given người dùng mới, When chưa có cây, Then hiển thị vườn trống với prompt "Trồng cây đầu tiên"

## Technical Notes:

- Component: `src/features/garden/components/GardenView.tsx`
- CSS animations cho cây phát triển
- Grid layout responsive cho mobile

## Tasks:

- [ ] Tạo component `GardenView.tsx` để hiển thị layout khu vườn.
- [ ] Implement grid layout (CSS Grid hoặc Flexbox) để sắp xếp cây.
- [ ] Kết nối với Supabase để lấy danh sách cây (`garden_items`) của người dùng.
- [ ] Hiển thị cây với growth stage tương ứng (1-5).
- [ ] Xử lý trường hợp người dùng mới (chưa có cây) và hiển thị prompt.
- [ ] Đảm bảo responsive trên các kích thước màn hình khác nhau (mobile first).
- [ ] Thêm CSS animation đơn giản cho cây (ví dụ: rung nhẹ).
- [ ] Viết unit test cho component.

## Development Considerations:

- Sử dụng React Context để quản lý state của khu vườn (nếu cần thiết).
- Cân nhắc sử dụng thư viện UI component nếu cần thiết (ví dụ: React Grid Layout).
- Tối ưu hóa hiệu năng khi hiển thị nhiều cây trong vườn.
- Chú ý đến khả năng mở rộng, dễ dàng thêm các loại cây mới trong tương lai.

## QA Notes:

- Kiểm tra hiển thị trên các thiết bị và trình duyệt khác nhau.
- Kiểm tra hiệu năng khi có nhiều cây trong vườn.
- Kiểm tra trường hợp edge case (ví dụ: lỗi kết nối mạng).
- Kiểm tra tính responsive của layout.

## Dependencies:

- Supabase client
- Dữ liệu cây trong bảng `garden_items`

## Definition of Done:

- [ ] Component `GardenView.tsx` hiển thị đúng layout khu vườn.
- [ ] Cây hiển thị đúng growth stage.
- [ ] Xử lý trường hợp người dùng mới.
- [ ] Layout responsive.
- [ ] Unit tests pass.
- [ ] Code review approved.

## Mockup
![Mockup 2-1-garden-layout-display](https://image.pollinations.ai/prompt/ClearMind%20mobile%20app%20garden%20layout%20display%20iOS%20UI%20mockup%20pastel?width=390&height=844&model=flux&seed=1774201519021)
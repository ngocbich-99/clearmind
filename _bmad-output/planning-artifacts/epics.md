# ClearMind - Epics and Stories

## Epic 1: Mood Tracking

**Objective**: Cho phép người dùng theo dõi cảm xúc hàng ngày và xem xu hướng theo thời gian.

### Story 1.1: Mood Selector UI
- **As a** người dùng
- **I want** chọn mood hàng ngày từ 5 levels
- **So that** tôi có thể ghi nhận cảm xúc một cách nhanh chóng

**Acceptance Criteria:**
- Given trang chủ hiển thị, When người dùng chưa chọn mood hôm nay, Then hiển thị Mood Selector
- Given Mood Selector hiển thị, When người dùng tap vào 1 emoji, Then lưu mood và hiển thị xác nhận
- Given đã chọn mood hôm nay, When quay lại trang chủ, Then hiển thị mood đã chọn (không cho chọn lại)

**Technical Notes:**
- Component: `src/features/mood/components/MoodSelector.tsx`
- Hook: `src/features/mood/hooks/useMood.ts`
- Supabase table: `mood_logs`

### Story 1.2: Mood History Chart
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

---

## Epic 2: Vườn Tâm Trí (Mental Garden)

**Objective**: Tạo khu vườn ảo phản ánh sức khỏe tinh thần, gamify thói quen tốt.

### Story 2.1: Garden Layout & Display
- **As a** người dùng
- **I want** xem khu vườn của mình với các cây cối
- **So that** tôi cảm thấy motivated để duy trì thói quen

**Acceptance Criteria:**
- Given người dùng vào tab Vườn, When load xong, Then hiển thị grid layout khu vườn
- Given khu vườn hiển thị, When có cây, Then cây hiển thị đúng growth stage (1-5)
- Given người dùng mới, When chưa có cây, Then hiển thị vườn trống với prompt "Trồng cây đầu tiên"

**Technical Notes:**
- Component: `src/features/garden/components/GardenView.tsx`
- CSS animations cho cây phát triển
- Grid layout responsive cho mobile

### Story 2.2: Plant a New Tree
- **As a** người dùng
- **I want** trồng cây mới gắn với một thói quen
- **So that** tôi có động lực duy trì thói quen đó

**Acceptance Criteria:**
- Given người dùng tap "Trồng cây", When chọn loại cây và thói quen, Then tạo cây mới ở stage 1
- Given cây vừa trồng, When hoàn thành thói quen liên quan, Then cây tăng growth stage
- Given tối đa 6 cây trong vườn, When đã có 6 cây, Then disable nút "Trồng cây"

**Technical Notes:**
- Component: `src/features/garden/components/PlantTree.tsx`
- Supabase table: `garden_items`
- Max 6 cây per user

---

## Epic 3: Breathing Exercises

**Objective**: Cung cấp bài tập thở guided với animation trực quan.

### Story 3.1: Breathing Exercise UI
- **As a** người dùng
- **I want** làm bài tập thở 4-7-8 với animation hướng dẫn
- **So that** tôi có thể thư giãn ngay lập tức

**Acceptance Criteria:**
- Given người dùng chọn "Thở 4-7-8", When bắt đầu, Then hiển thị animation vòng tròn expand/contract
- Given bài tập đang chạy, When hít vào 4s, Then vòng tròn mở rộng + text "Hít vào"
- Given bài tập đang chạy, When giữ 7s, Then vòng tròn giữ nguyên + text "Giữ"
- Given bài tập đang chạy, When thở ra 8s, Then vòng tròn thu nhỏ + text "Thở ra"
- Given hoàn thành 1 set (3 lần), When xong, Then hiển thị summary + option tiếp tục

**Technical Notes:**
- CSS animation keyframes cho circle
- Component: `src/features/breathing/components/BreathingExercise.tsx`
- No external animation library needed

# Story: 3-1-breathing-exercise-ui (Epic 3, Story 1: breathing exercise ui)

## Mô tả

**As a** người dùng
**I want** làm bài tập thở 4-7-8 với animation hướng dẫn
**So that** tôi có thể thư giãn ngay lập tức

## Tiêu chí chấp nhận

- Given người dùng chọn "Thở 4-7-8", When bắt đầu, Then hiển thị animation vòng tròn expand/contract
- Given bài tập đang chạy, When hít vào 4s, Then vòng tròn mở rộng + text "Hít vào"
- Given bài tập đang chạy, When giữ 7s, Then vòng tròn giữ nguyên + text "Giữ"
- Given bài tập đang chạy, When thở ra 8s, Then vòng tròn thu nhỏ + text "Thở ra"
- Given hoàn thành 1 set (3 lần), When xong, Then hiển thị summary + option tiếp tục

## Ghi chú kỹ thuật

- CSS animation keyframes cho circle
- Component: `src/features/breathing/components/BreathingExercise.tsx`
- No external animation library needed
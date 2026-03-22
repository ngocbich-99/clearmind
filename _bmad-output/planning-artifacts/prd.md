# ClearMind - Product Requirements Document

## Executive Summary

ClearMind là ứng dụng chăm sóc sức khỏe tinh thần, giúp người dùng theo dõi cảm xúc, thực hành mindfulness, và xây dựng thói quen tích cực thông qua giao diện "Vườn Tâm Trí" — nơi sức khỏe tinh thần được thể hiện bằng hình ảnh khu vườn phát triển.

## Vision

Biến việc chăm sóc sức khỏe tinh thần trở nên trực quan, thú vị và dễ duy trì thông qua gamification.

## Target Users

- Người trưởng thành 20-40 tuổi
- Quan tâm đến sức khỏe tinh thần nhưng chưa có thói quen
- Thích giao diện đẹp, trực quan

## Core Features

### F1: Mood Tracking (Theo dõi cảm xúc)
- Chọn mood hàng ngày (5 levels: rất tệ → rất tốt)
- Xem lịch sử mood theo tuần/tháng
- Gợi ý hoạt động dựa trên mood

### F2: Vườn Tâm Trí (Mental Garden)
- Khu vườn ảo phản ánh sức khỏe tinh thần
- Cây cối phát triển khi duy trì thói quen tốt
- Các loại cây khác nhau cho các thói quen khác nhau

### F3: Breathing Exercises (Bài tập thở)
- Hướng dẫn thở 4-7-8
- Box breathing
- Animation trực quan theo nhịp thở

### F4: Daily Journal (Nhật ký hàng ngày)
- Viết nhật ký tự do
- Gợi ý prompt hàng ngày
- Phân tích sentiment đơn giản

## Non-Functional Requirements

- **Performance**: Load time < 2s
- **Platform**: Mobile-first (React Native hoặc PWA)
- **Security**: Dữ liệu cảm xúc mã hóa end-to-end
- **Language**: Tiếng Việt là ngôn ngữ chính

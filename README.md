# AI Travel Planner – User Website

Repository dành riêng cho khách du lịch, gồm giao diện User và API phục vụ người dùng. Repository kết nối PostgreSQL và có thể tích hợp API AI, bản đồ cùng dịch vụ du lịch bên ngoài khi nhóm thống nhất nhà cung cấp.

Đây là bộ khung ban đầu: chưa triển khai nghiệp vụ đăng ký/đăng nhập, tìm kiếm, lịch trình, chuyến đi, yêu thích hay hồ sơ; chưa tạo schema nghiệp vụ và không chứa giao diện quản trị.

## Công nghệ

- Backend: Java 17, Spring Boot, Spring Web, Spring Data JPA, Spring Security, Validation, Lombok, PostgreSQL Driver.
- Frontend: React, TypeScript, Vite, React Router DOM, Axios.
- Version control: Git và GitHub.

## Cấu trúc

```text
backend/          Spring Boot API cho người dùng
frontend-user/    Website React dành cho khách du lịch
docs/             Tổng quan, kiến trúc, database và API
.env.example      Mẫu biến môi trường cho backend
```

Backend dùng package gốc `com.travelplanner.user`. Các package `integration/ai`, `integration/maps` và `integration/travel` để dành cho tích hợp bên ngoài. Schema database sẽ được thống nhất trước khi tạo entity.

## Yêu cầu môi trường

- JDK 17 trở lên và Maven 3.9 trở lên.
- Node.js 20 trở lên và npm.
- PostgreSQL 14 trở lên.

## Clone repository

```bash
git clone <URL-repository>
cd AI-TRAVEL-PLANNER-USER
```

## Cấu hình PostgreSQL và môi trường

Tạo database PostgreSQL rỗng, ví dụ `travel_planner_user`. Sao chép `.env.example` thành `.env` và thay giá trị theo máy. Spring Boot không tự đọc file `.env`; hãy export các biến trong terminal hoặc cấu hình chúng trong IDE. Không commit `.env`, mật khẩu hay API key.

PowerShell:

```powershell
$env:DB_URL="jdbc:postgresql://localhost:5432/travel_planner_user"
$env:DB_USERNAME="postgres"
$env:DB_PASSWORD="your-local-password"
```

## Chạy Backend

```bash
cd backend
mvn spring-boot:run
```

API mặc định chạy tại `http://localhost:8080`. Health check: `GET http://localhost:8080/api/health`. Cần PostgreSQL đang chạy và các biến môi trường đã được thiết lập. JPA không tự tạo schema (`ddl-auto=none`).

## Chạy Frontend User

```bash
cd frontend-user
npm install
npm run dev
```

Để đổi backend URL, sao chép `frontend-user/.env.example` thành `.env.local` và đặt `VITE_API_BASE_URL` (mặc định `http://localhost:8080`).

Build production:

```bash
npm run build
```

## Làm việc nhóm với Git

```bash
git switch -c feat/ten-cong-viec
git add <cac-file-can-commit>
git commit -m "feat: mo ta thay doi"
git push -u origin feat/ten-cong-viec
```

Tạo Pull Request để thành viên còn lại review trước khi merge. Thống nhất phân chia backend/frontend và quy ước nhánh trong nhóm. Không commit file môi trường, mật khẩu, token hoặc API key.

## Tài liệu

Các tài liệu khởi đầu ở [docs/](docs/): tổng quan dự án, kiến trúc, thiết kế database và API. Nhóm bổ sung nội dung sau khi yêu cầu được thống nhất.

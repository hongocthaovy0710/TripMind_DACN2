# AI Travel Planner

Website hỗ trợ lập kế hoạch du lịch bằng AI. Đây là bộ khung ban đầu cho đồ án tốt nghiệp của nhóm hai thành viên; các chức năng nghiệp vụ và tích hợp AI sẽ được thống nhất, triển khai sau.

## Mục tiêu

- Tạo nền tảng web để người dùng khám phá địa điểm và lập kế hoạch chuyến đi.
- Tổ chức backend theo MVC và layered architecture, tách frontend người dùng và quản trị.
- Tích hợp API AI có sẵn sau khi nhóm chọn nhà cung cấp; dự án không huấn luyện mô hình AI.

## Công nghệ

- Backend: Java 17, Spring Boot, Spring Web, Spring Data JPA, Spring Security, Validation, Lombok, PostgreSQL.
- Frontend User/Admin: React, TypeScript, Vite, React Router DOM, Axios.
- Quản lý mã nguồn: Git và GitHub.

## Cấu trúc

```text
backend/          Spring Boot REST API
frontend-user/    Ứng dụng React cho người dùng
frontend-admin/   Ứng dụng React quản trị độc lập
docs/             Tài liệu dự án và thiết kế
.env.example      Mẫu biến môi trường dùng chung cho backend
```

## Yêu cầu môi trường

- JDK 17 trở lên, Maven 3.9 trở lên.
- Node.js 20 trở lên và npm.
- PostgreSQL 14 trở lên (hoặc phiên bản tương thích).

## Clone và cấu hình

```bash
git clone <URL-repository>
cd TripMind_DACN2
```

Tạo database rỗng trong PostgreSQL (ví dụ `travel_planner`). Sao chép `.env.example` thành `.env`, rồi đặt `DB_URL`, `DB_USERNAME`, `DB_PASSWORD` theo máy của bạn. Không commit `.env` hay API key lên GitHub. Spring Boot không tự nạp file `.env`; hãy export các biến môi trường trong terminal hoặc cấu hình chúng trong IDE trước khi chạy backend.

PowerShell:

```powershell
$env:DB_URL="jdbc:postgresql://localhost:5432/travel_planner"
$env:DB_USERNAME="postgres"
$env:DB_PASSWORD="your-local-password"
```

## Chạy Backend

Từ thư mục `backend`:

```bash
mvn spring-boot:run
```

Backend mặc định chạy tại `http://localhost:8080`; kiểm tra `GET http://localhost:8080/api/health`. Nếu chưa cấu hình PostgreSQL, ứng dụng không thể khởi động do JPA cần kết nối cơ sở dữ liệu.

## Chạy Frontend User

```bash
cd frontend-user
npm install
```

Sao chép `.env.example` thành `.env.local` nếu cần thay URL backend (mặc định `http://localhost:8080`), sau đó:

```bash
npm run dev
```

## Chạy Frontend Admin

```bash
cd frontend-admin
npm install
```

Sao chép `.env.example` thành `.env.local` nếu cần thay URL backend (mặc định `http://localhost:8080`), sau đó:

```bash
npm run dev
```

Frontend User và Admin là hai ứng dụng Vite độc lập. Mỗi ứng dụng có thể chạy ở cổng khác nhau; Vite sẽ thông báo URL nếu cổng mặc định đang bận.

## Làm việc nhóm với Git

```bash
git switch -c feat/ten-cong-viec
git add <cac-file-can-commit>
git commit -m "feat: mo ta thay doi"
git push -u origin feat/ten-cong-viec
```

Tạo Pull Request để thành viên còn lại review trước khi merge vào nhánh chính. Thống nhất quy ước nhánh và phân chia backend/frontend trong nhóm; không commit file môi trường, mật khẩu, token hoặc API key.

## Tài liệu

Xem [docs/](docs/) để bổ sung tổng quan, kiến trúc, thiết kế cơ sở dữ liệu và tài liệu API.

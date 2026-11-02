# Backend

Spring Boot REST API dùng Java 17 và Maven. Cấu hình PostgreSQL qua `DB_URL`, `DB_USERNAME`, `DB_PASSWORD`; xem `.env.example` ở thư mục gốc. Spring Security hiện chỉ dùng cấu hình mặc định của Spring Boot, chưa có đăng nhập/JWT/phân quyền nghiệp vụ.

Chạy từ thư mục này bằng `mvn spring-boot:run`. Health check: `GET /api/health`.

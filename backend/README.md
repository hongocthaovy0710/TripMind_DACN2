# Backend User

Spring Boot REST API cho website khách du lịch, dùng Java 17, Maven và package gốc `com.travelplanner.user`. Các dependency nền tảng gồm Spring Web, Data JPA, Security, Validation, PostgreSQL Driver và Lombok.

Cấu hình `DB_URL`, `DB_USERNAME`, `DB_PASSWORD` bằng biến môi trường trước khi chạy. Mẫu nằm tại `.env.example` ở thư mục gốc; Spring Boot không tự nạp `.env`. Schema chưa được khởi tạo và `spring.jpa.hibernate.ddl-auto=none`.

```bash
mvn spring-boot:run
```

Health check: `GET /api/health`. Chưa có nghiệp vụ đăng nhập, JWT, phân quyền, hay API du lịch/AI thực tế.

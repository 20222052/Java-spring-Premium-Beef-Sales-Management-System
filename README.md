# Premium Beef Sales Management System 🛒

Ứng dụng thương mại điện tử được xây dựng bằng **Java Spring Boot**, hỗ trợ đầy đủ tính năng mua sắm trực tuyến và quản lý hệ thống qua trang quản trị.

---

## 📋 Mục lục

- [Giới thiệu](#giới-thiệu)
- [Tính năng](#tính-năng)
- [Công nghệ sử dụng](#công-nghệ-sử-dụng)
- [Yêu cầu hệ thống](#yêu-cầu-hệ-thống)
- [Cài đặt & Chạy dự án](#cài-đặt--chạy-dự-án)
- [Cấu trúc dự án](#cấu-trúc-dự-án)

---

## Giới thiệu

**ShopSpring** là một website bán hàng trực tuyến hoàn chỉnh, gồm hai phần chính:

- **Trang khách hàng (Frontend):** Xem sản phẩm, tìm kiếm, thêm vào giỏ hàng, đặt hàng, quản lý tài khoản, yêu thích sản phẩm, đọc blog.
- **Trang quản trị (Admin):** Quản lý sản phẩm, danh mục, đơn hàng, khách hàng, người dùng, blog, banner, bình luận và liên hệ.

---

## Tính năng

### 🏠 Khách hàng
- Xem danh sách sản phẩm, lọc theo danh mục, sản phẩm nổi bật, khuyến mãi, sản phẩm mới
- Xem chi tiết sản phẩm và hình ảnh
- Thêm/xóa sản phẩm yêu thích
- Giỏ hàng: thêm, cập nhật số lượng, xóa
- Đặt hàng và theo dõi trạng thái đơn hàng
- Đăng ký, đăng nhập, quản lý thông tin tài khoản
- Đọc bài viết blog
- Gửi liên hệ

### 🔧 Quản trị (Admin)
- Quản lý sản phẩm (thêm, sửa, xóa, hình ảnh sản phẩm)
- Quản lý danh mục sản phẩm
- Quản lý đơn hàng (xem, cập nhật trạng thái, gửi email xác nhận)
- Quản lý khách hàng
- Quản lý người dùng (phân quyền)
- Quản lý blog & bình luận
- Quản lý banner trang chủ
- Xem và xử lý liên hệ

---

## Công nghệ sử dụng

| Thành phần      | Công nghệ                          |
|-----------------|------------------------------------|
| Ngôn ngữ        | Java 21                            |
| Framework       | Spring Boot 3.4.2                  |
| ORM             | Spring Data JPA / Hibernate        |
| Template Engine | Thymeleaf + Layout Dialect + Spring Security Extras |
| Bảo mật         | Spring Security (BCrypt, sessions) |
| Database        | MySQL / MariaDB                    |
| Email           | Spring Mail (Gmail SMTP)           |
| Build tool      | Gradle                             |
| Khác            | Lombok, Spring Validation, Spring DevTools |

---

## Yêu cầu hệ thống

- **Java:** 21+
- **MySQL:** 8.0+ hoặc **MariaDB:** 10.6+
- **Gradle:** 7+ (hoặc dùng `gradlew` wrapper đi kèm)

---

## Cài đặt & Chạy dự án

### 1. Clone repository

```bash
git clone https://github.com/20222052/Java_Project.git
cd Java_Project
```

### 2. Tạo database

```sql
CREATE DATABASE on_tap;
```

> Ứng dụng sẽ tự động tạo các bảng khi khởi động lần đầu (`spring.jpa.hibernate.ddl-auto=update`).

### 3. Cấu hình ứng dụng

Mở file `src/main/resources/application.properties` và cập nhật thông tin kết nối database:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/on_tap
spring.datasource.username=<your_username>
spring.datasource.password=<your_password>
```

Cấu hình email (nếu cần gửi email xác nhận đơn hàng):

```properties
spring.mail.username=<your_gmail>
spring.mail.password=<your_app_password>
```

### 4. Chạy ứng dụng

```bash
./gradlew bootRun
```

Ứng dụng sẽ chạy tại: [http://localhost:8080](http://localhost:8080)

Trang quản trị: [http://localhost:8080/admin](http://localhost:8080/admin)

---

## Cấu trúc dự án

```
src/main/java/com/example/demo/
├── controller/
│   ├── admin/          # Controllers trang quản trị
│   └── home/           # Controllers trang khách hàng
├── model/
│   └── entity/         # Các entity JPA (Product, Order, Customer, ...)
├── repository/         # Spring Data JPA Repositories
├── service/            # Business logic (interfaces + implementations)
├── security/           # Cấu hình Spring Security
└── validation/         # Custom validators

src/main/resources/
├── templates/          # Thymeleaf HTML templates
├── static/             # CSS, JS, hình ảnh tĩnh
└── application.properties
```

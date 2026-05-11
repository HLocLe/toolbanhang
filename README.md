# ChaoLongTool - Công Cụ Bán Hàng Trực Tuyến

## Mô Tả Dự Án

ChaoLongTool là một ứng dụng web được xây dựng bằng Java và Spring Boot, cung cấp giải pháp quản lý bán hàng trực tuyến toàn diện. Dự án sử dụng công nghệ hiện đại để tạo nên một nền tảng mạnh mẽ, có khả năng mở rộng và dễ bảo trì.

## Công Nghệ Sử Dụng

### Backend
- **Spring Boot 3.2.4**: Framework Java hiện đại cho phát triển ứng dụng web
- **Java 17**: Ngôn ngữ lập trình chính
- **MongoDB**: Cơ sở dữ liệu NoSQL để lưu trữ dữ liệu linh hoạt
- **Spring Data MongoDB**: Thư viện hỗ trợ tương tác với MongoDB
- **WebSocket**: Hỗ trợ giao tiếp real-time hai chiều
- **STOMP**: Giao thức truyền thông tin nhắn đơn giản
- **SockJS**: Thư viện JavaScript để hỗ trợ WebSocket khi trình duyệt không hỗ trợ

### API Documentation
- **SpringDoc OpenAPI**: Công cụ tạo tài liệu API tự động theo chuẩn OpenAPI

### Containerization
- **Docker**: Để đóng gói ứng dụng thành container
- **Docker Compose**: Để quản lý nhiều container

## Tính Năng Chính

### 1. Giao Tiếp Real-time
- Sử dụng WebSocket để truyền thông tin trực tiếp giữa server và client
- Hỗ trợ STOMP messaging protocol để quản lý các kênh truyền thông

### 2. Quản Lý Dữ Liệu
- Lưu trữ dữ liệu linh hoạt bằng MongoDB
- Hỗ trợ các thao tác CRUD cơ bản

### 3. Tài Liệu API
- Tự động tạo tài liệu API theo chuẩn OpenAPI/Swagger
- Dễ dàng khám phá và kiểm tra các endpoint

### 4. Triển Khai Container
- Hỗ trợ triển khai bằng Docker
- Cấu hình Docker Compose để chạy toàn bộ ứng dụng

## Cấu Trúc Thư Mục

```
toolbanhang/
├── src/                    # Mã nguồn chính của ứng dụng
├── Dockerfile             # Tệp cấu hình Docker
├── docker-compose.yml     # Tệp cấu hình Docker Compose
├── pom.xml               # Tệp cấu hình Maven và khai báo dependencies
├── .gitignore            # Tệp chỉ định các file/thư mục cần bỏ qua
└── .dockerignore         # Tệp chỉ định các file/thư mục không đưa vào Docker image
```

## Dependencies Chính

### Spring Boot Starters
- `spring-boot-starter-websocket`: Hỗ trợ WebSocket
- `spring-boot-starter`: Core Spring Boot starter
- `spring-boot-starter-data-mongodb`: Tích hợp MongoDB
- `spring-boot-starter-web`: Phát triển ứng dụng web
- `spring-boot-starter-test`: Testing framework

### Web Jar Dependencies
- `stomp-websocket` (v2.3.4): STOMP client cho JavaScript
- `sockjs-client` (v1.5.1): SockJS client cho fallback WebSocket

### API Documentation
- `springdoc-openapi-starter-webmvc-ui` (v2.3.0): Swagger UI cho API documentation

## Yêu Cầu Hệ Thống

- Java 17 hoặc cao hơn
- Maven 3.6+
- MongoDB (có thể chạy qua Docker Compose)
- Docker (tùy chọn, cho triển khai container)

## Cách Cài Đặt

### 1. Clone Repository
```bash
git clone https://github.com/HLocLe/toolbanhang.git
cd toolbanhang
```

### 2. Cấu Hình MongoDB
Đảm bảo MongoDB đang chạy. Bạn có thể sử dụng Docker Compose:

```bash
docker-compose up -d
```

### 3. Build Ứng Dụng
```bash
mvn clean package
```

### 4. Chạy Ứng Dụng
```bash
mvn spring-boot:run
```

Hoặc chạy file JAR được tạo:
```bash
java -jar target/ChaoLongTool-1.0-SNAPSHOT.jar
```

## Chạy Với Docker

### Build Docker Image
```bash
docker build -t toolbanhang:latest .
```

### Chạy Container
```bash
docker run -p 8080:8080 toolbanhang:latest
```

### Chạy Với Docker Compose
```bash
docker-compose up -d
```

## API Documentation

Sau khi ứng dụng chạy, bạn có thể truy cập Swagger UI tại:
```
http://localhost:8080/swagger-ui.html
```

## Cấu Hình

Ứng dụng sử dụng các cấu hình mặc định từ Spring Boot. Bạn có thể tùy chỉnh các thuộc tính trong file `application.properties` hoặc `application.yml`.

### MongoDB Connection
Mặc định kết nối tới MongoDB local. Cấu hình có thể được thay đổi qua biến môi trường hoặc tệp cấu hình.

## Phát Triển

### Build Maven
```bash
mvn clean install
```

### Chạy Tests
```bash
mvn test
```

### Kiểm Tra Linting
```bash
mvn verify
```

## Git Workflow

- **Default Branch**: main
- **Repository Owner**: HLocLe
- **Repository Name**: toolbanhang
- **Visibility**: Public




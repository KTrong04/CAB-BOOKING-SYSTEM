# ĐỒ ÁN: CAB BOOKING SYSTEM
## Cấu trúc thư mục dự án

````markdown
cab-booking-system/
├── apps/                        # Lớp giao diện người dùng (Client Layer)
│   ├── admin-dashboard/         # ReactJS + Vite: Quản lý hệ thống, điều phối tài xế & phân tích dữ liệu
│   ├── customer-app/            # ReactJS + Vite: Ứng dụng dành cho khách hàng đặt xe & theo dõi hành trình
│   └── driver-app/              # ReactJS + Vite: Ứng dụng dành cho tài xế nhận chuyến & định vị GPS
│
├── gateway/                     # API Gateway (NodeJS/Express)
│   └── index.js                 # Điểm tiếp nhận duy nhất, định tuyến yêu cầu & kiểm soát bảo mật (PEP)
│
├── services/                    # Lớp nghiệp vụ (Microservices Layer)
│   ├── auth-service/            # Quản lý định danh, cấp phát JWT & phân quyền theo mô hình Zero Trust
│   ├── user-service/            # Quản lý hồ sơ (Profile) khách hàng và tài xế
│   ├── driver-service/          # Quản lý danh sách tài xế và trạng thái hoạt động
│   ├── ride-service/            # Xử lý logic chuyến đi và cập nhật tọa độ GPS thời gian thực
│   ├── booking-service/         # Quản lý quy trình đặt xe và ghép nối (Matching)
│   ├── pricing-service/         # Tính toán giá cước động (Surge Pricing) sử dụng AI
│   ├── payment-service/         # Xử lý giao dịch qua Saga Pattern & đảm bảo tính nhất quán dữ liệu
│   └── notification-service/    # Gửi thông báo thông qua WebSocket và Event Broker (Kafka)
│
├── infrastructure/              # Lớp hạ tầng và dữ liệu (Data Layer)
│   ├── kafka/                   # Message Broker hỗ trợ kiến trúc hướng sự kiện (Event-driven)
│   ├── databases/               # Quản lý dữ liệu riêng biệt (Database per service)
│   │   ├── postgres/            # Lưu trữ dữ liệu quan hệ (Chuyến đi, Giao dịch)
│   │   ├── mongodb/             # Lưu trữ dữ liệu phi cấu trúc (Logs, Audit Trail)
│   │   └── redis/               # Cache tọa độ GPS & xử lý truy vấn không gian (Geo-spatial)
│   └── docker-compose.yml       # Cấu hình container hóa để triển khai toàn bộ hệ thống
│
├── scripts/                     # Các script tự động hóa khởi tạo môi trường và dữ liệu mẫu
└── README.md                    # Tài liệu hướng dẫn chi tiết dự án
````
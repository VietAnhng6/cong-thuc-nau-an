# Website Công Thức Nấu Ăn

## 1. Giới thiệu

Website Công Thức Nấu Ăn là hệ thống chia sẻ công thức nấu ăn, cho phép quản lý món ăn, nguyên liệu và danh mục món ăn.

Hệ thống được triển khai bằng Docker Compose, kết hợp website, cơ sở dữ liệu, reverse proxy, monitoring và logging.

## 2. Công nghệ sử dụng

- WordPress
- MySQL 8.0
- phpMyAdmin
- Nginx
- Docker & Docker Compose
- Prometheus
- Grafana
- cAdvisor
- Loki
- Promtail

## 3. Kiến trúc hệ thống

Hệ thống gồm hai network chính:

### Frontend network

- Nginx
- WordPress

Nginx đóng vai trò reverse proxy và là điểm truy cập chính của website.

### Backend network

- MySQL
- WordPress
- phpMyAdmin
- Prometheus
- Grafana
- cAdvisor
- MySQL Exporter
- Loki
- Promtail

WordPress kết nối với MySQL để lưu trữ dữ liệu website.

Prometheus thu thập metrics từ cAdvisor và MySQL Exporter.

Grafana sử dụng dữ liệu từ Prometheus để hiển thị monitoring.

Promtail thu thập log Nginx và gửi đến Loki.

Grafana sử dụng Loki để truy vấn và phân tích log bằng LogQL.

## 4. Khởi động hệ thống

Clone repository:

```bash
git clone https://github.com/VietAnhng6/cong-thuc-nau-an.git
cd cong-thuc-nau-an

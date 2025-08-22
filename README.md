```mermaid
sequenceDiagram
participant A as Người dùng
participant B as Hệ thống
participant C as Database
A->>B: Đăng nhập
B->>C: Kiểm tra user
C-->>B: Thông tin user
B-->>A: Đăng nhập thành công

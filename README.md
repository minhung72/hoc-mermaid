```mermaid
sequenceDiagram
User->>System: Login
alt Đăng nhập thành công
System-->>User: Welcome
else Sai mật khẩu
System-->>User: Error
end
loop Kiểm tra mỗi 5 phút
System->>Database: Health check
end
```

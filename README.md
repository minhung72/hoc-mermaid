```mermaid
stateDiagram-v2
[*] --> Chờ
Chờ --> Xử_lý : Bắt đầu
Xử_lý --> Hoàn_thành : Thành công
Xử_lý --> Lỗi : Thất bại
Hoàn_thành --> [*]
Lỗi --> Chờ : Thử lại
Lỗi --> [*] : Hủy

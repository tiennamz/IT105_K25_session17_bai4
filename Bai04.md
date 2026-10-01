## Phần 1: 

| Tiêu chí                              | Giải pháp 1 (Sync API):                                            | Giải pháp 2 (Async Webhook/Queue)                                                    |
| --------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| Độ tin cậy khi nghẽn mạng          | Độ tin cậy kém khi phải chờ trả về kết quả từ Ngân hàng | Độ tin cậy cao khi không cần phải chờ mà Ngân hàng sẽ trả kết quả nhanh |
| Độ phức tạp triển khai             | Thấp khi cần thiết kế API nhận và thiết kế response trả về | Cao khi phải phân các luồng khác nhau để có thể thực hiện                   |
| Rủi ro sai lệch dữ liệu tài chính | Rủi ro cao                                                          | Rủi ro thấp                                                                          |

## Phần 2:

![1790834293444](image/Bai04/1790834293444.png)

## Phần 3: 4 bảng dữ liệu cần thiết 

Shipment: Thông tin chi tiết về đơn vận chuyển

PaymentTransaction: Ghi nhận lịch sử giao dịch

CODSettlement: Quản lý quá trình đối soát và quyết tiền thu hộ

AuditLog: Lưu vết toàn bộ hoạt động về hệ thống

++ Cơ chế bảo mật hệ thống:

+ API Key: chuỗi ký tự định danh cho mỗi đối tác để xác thực dnah tính khi gọi API
+ HMAC Checksum: Mã băm được tạo ra từ nội dung kết hợp với một chuỗi bí mật, giúp xác thực tính toàn vẹn của dữ liệu, đảm bảo thông tin không bị chỉnh sửa hay bị người khác giả mạo trên đường truyền

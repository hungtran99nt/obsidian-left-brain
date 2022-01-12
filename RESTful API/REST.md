### REST (REpresentational State Transfer) 
là một kiểu **kiến trúc**

### API
là **quy tắc** mà 1 ứng dụng hay 1 thành phần sẽ tương tác với 1 ứng dụng hay thành phần khác

### RESTful API 
là một **tiêu chuẩn thiết kế API** theo chuẩn RESTful
- 200 OK – Trả về thành công cho những phương thức GET, PUT, PATCH hoặc DELETE.
- 400 Bad Request – Request không hợp lệ
- 401 Unauthorized – Request cần có authorize
.....

----
#### Mục đích sử dụng 
- Giúp các hệ thống riêng biệt có thể giao tiếp được với nhau.
- Đồng bộ dữ liệu giữa các nền tảng
#### HTTP methods
- GET: lấy thông tin từ server theo URI 
- POST: gửi thông tin tới server thông qua các biểu mẫu http
- HEAD: giống với GET nhưng response trả về **chỉ có header**
- PUT: ghi đè tất cả thông tin của đối tượng với thông tin được gửi lên
- PATCH: ghi đè các thông tin được thay đổi của đối tượng
- DELETE: xóa tài nguyên trên server
- CONNECT: thiết lập một kết nối tới server theo URI
- OPTIONS: mô tả các tùy chọn giao tiếp cho resource
- TRACE: thực hiện một test loop - back theo đường dẫn tới resource
#### Resource, endpoint convention
1. Sử dụng danh từ đặt tên cho resource
`http://api.example.com/users # Liệt kê tất cả user` 
`http://api.example.com/users/1 # Chi tiết user có ID là 1`
2. Sử dụng dấu xuộc (/) để thể hiện mối quan hệ phân cấp giữa các resource
`http://api.example.com/users/1/images # Liệt kê tất cả images của user có ID là 1`
3. Dùng dấu gạch ngang (-) để ngăn cách giữa các cụm từ
`http://api.example.com/banned-users`
4. Sử dụng query params để lọc kết quả
`http://api.example.com/users?country=vn # Sử dụng query params country để lọc những user ở VN`
`http://api.example.com/users?page=1`
`http://api.example.com/users?orderBy=latest`

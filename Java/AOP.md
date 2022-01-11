##### AOP (Aspects-Oriented Programming)
![[AOP.png]]
Với mỗi chức năng, ta phải làm nhiều những **công việc lặp lại** như logging, đóng/mở transaction, catch exception. Do đó, code **bị liên kết chặt vào nhau**, **dupplicate code**, **phân mảnh nhiều nơi, khó khăn khi sửa đổi hay thêm mới logic,....** 
=> AOP có thể giải quyết những vấn đề trên.

##### Mục tiêu
1. Phân tách chương trình thành các **module riêng rẽ, không phụ thuộc** vào nhau. Các module có thể kết hợp để thực hiện các chức năng nhưng chỉ cần sửa đổi trên 1 module cụ thể khi cần.
2. Những vấn đề tương tự nhau nên được giải quyết trong 1 **unit of code** (trong OOP, **unit of code = class**).

###### Ví dụ với chức năng REGISTRATION
1. **Core concerns**: hàm chính của chương trình (hàm cho phép đăng kí tài khoản).
2. **Cross-cutting concern**: các vấn đề xung quanh chức năng đăng kí (kiểm tra ràng buộc, quản lý transaction, xử lý ngoại lệ, logging, debug...). ^b34317
3. **Join point**: là những nơi có thể được chèn các Cross-cutting concern, Join point có thể là 1 phương thức được gọi, một ngoại lệ được throw ra, 1 field được thay đổi.
4. **Pointcut**: là **cách để xác định Joint Point**.
5. 
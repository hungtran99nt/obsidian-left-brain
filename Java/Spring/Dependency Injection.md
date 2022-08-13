### Dependency Injection
- Là 1 kỹ thuật, 1 design pattern
- Cho phép xoá bỏ sự phụ thuộc (hard code) và làm ứng dụng dễ mở rộng và maintain hơn.

`1. Các module không giao tiếp trực tiếp với nhau, mà thông qua interface. Module cấp thấp sẽ implement interface, module cấp cao sẽ gọi module cấp thấp thông qua interface.*
Ví dụ: Để giao tiếp với database, ta có interface IDatabase, các module cấp thấp là XMLDatabase, SQLDatabase.  Module cấp cao là CustomerBusiness sẽ chỉ sử dụng interface IDatabase.

2.Việc khởi tạo các module cấp thấp sẽ do DI Container thực hiện. 
Ví dụ: Trong module CustomerBusiness, ta sẽ không khởi tạo IDatabase db = new XMLDatabase(), việc này sẽ do DI Container thực hiện. Module CustomerBusiness sẽ không biết gì về module XMLDatabase hay SQLDatabase.
     
3.Việc Module nào gắn với interface nào sẽ được config trong code hoặc trong file XML.

4.DI được dùng để làm giảm sự phụ thuộc giữa các module, dễ dàng hơn trong việc thay đổi module, bảo trì code và testing.*`

#### Phương pháp thực hiện DI
1. **Constructor Injection**: Các dependency được truyền vào qua constructor của class đó.
2. **Setter Injection**: Các dependency được truyền vào 1 class thông qua các hàm Setter/Getter.
3. **Public fields**: Các dependency được truyền vào class trực tiếp từ các public fields
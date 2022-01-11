### Dependency Injection
- Là 1 kỹ thuật, 1 design pattern
- Cho phép xoá bỏ sự phụ thuộc (hard code) và làm ứng dụng dễ mở rộng và maintain hơn.
#### Phương pháp thực hiện DI
1. **Constructor Injection**: Các dependency được truyền vào qua constructor của class đó.
2. Setter Injection: Các dependency được truyền vào 1 class thông qua các hàm Setter/Getter.
3. Public fields: Các dependency được truyền vào class trực tiếp từ các public fields
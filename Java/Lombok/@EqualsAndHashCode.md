- Chỉ sử dụng các thuộc tính không phải là [[Static]] và [[Transient]] (non-static, non-transient) để generate *equals()* và *hashCode()*.
- Thêm method *canEqual()* để xác định nhanh object có phải là instance của class đó hay không.
---
##### Exclude Fields
- Các thuộc tính định danh **(id)**, thời gian khởi tạo object **(createdAt)** **không nên** tham gia vào *equals()* và *hashCode()*, vì mỗi khi object được tạo ra thì các giá trị này sẽ khác nhau => giá trị *hashCode()* của mỗi object sẽ khác nhau và *equals()* sẽ luôn trả về FALSE.
###### Exclude Field Level
Sử dụng _**@EqualsAndHashCode.Exclude**_ chú thích các thuộc tính không được sử dụng khi Lombok generate _equals()_ và _hashCode()_ method.

###### Exclude Class Level

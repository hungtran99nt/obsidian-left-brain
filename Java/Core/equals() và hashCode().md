- Được định nghĩa mặc định trong tất cả các class.
##### Equals
- **Mặc định**: **so sánh địa chỉ object** thay vì so sánh giá trị thuộc tính trong object.
###### Contract
-   **Phản xạ**: Một object phải bằng chính nó
-   **Đối xứng**: **_x.equals(y)_** trả về kết quả giống với **_y.equals(x)_**
-   **Bắc cầu**: Nếu **_x.equals(y)_**_,_ **_y.equals(z)_** thì **_x.equals(z)_**
-   **Nhất quán**: Giá trị của **_equals(_)** chỉ thay đổi khi 1 trong 2 object được so sánh bởi **_equals()_** thay đổi.
###### Tránh vi phạm _equals()_ bất đối xứng
Để tránh vi phạm _equals()_ bất đối xứng, chúng ta nên áp dụng mối [quan hệ HAS-A](https://shareprogramming.net//quan-he-has-a-trong-java/) thay cho thừa kế.

---
##### HashCode
- _hashCode()_ trả về một số nguyên đại diện cho 1 instance của class.
- Khi 2 object là bằng nhau thì _hashCode()_ method của chúng cũng phải trả về giá trị bằng nhau.
=> Đó là lý do nếu **đã override _equals()_ method thì cũng phải override _hashCode()_ method.**
###### Contract
-   **Thống nhất trong nội bộ:** Giá trị _hashCode()_ sẽ không thay đổi trong các lần gọi trên cùng 1 object. Các object bằng nhau thì _hashCode()_ cũng phải có giá trị bằng nhau.
-   **Sự va chạm:** Các đối tượng không bằng nhau có thể có giá trị hashCode() giống nhau.
###### HashMap Key và hashCode()
[[HashMap]] là cấu trúc dữ liệu dạng **<key, value>**.
- Khi truy xuất các phần tử theo **object key** thì HashMap sẽ kiểm tra xem có phần tử nào có **key** trùng giá trị với _hashCode()_ của **object key** thì tiến hành trả về.
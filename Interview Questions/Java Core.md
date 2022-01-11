###### 1. Sự khác nhau giữa bộ nhớ HEAP và STACK trong Java? 
- [[Bộ nhớ Heap]]: 1 **vùng nhớ** trong bộ nhớ được sử dụng để lưu trữ các đối tượng khi từ khoá **new, các biến static, biến toàn cục (biến instance)** được được gọi ra.
- [[Bộ nhớ Stack]]: 1 **vùng nhớ** trong bộ nhớ được sử dụng để lưu trữ **các tham số và các biến local của phương thức** được gọi.

---
###### 2. Constructor là gì? 
[[Constructor]] giống như một phương thức được sử dụng để khởi tạo trạng thái của một đối tượng. Nó được gọi ra vào thời điểm tạo ra đối tượng.

---
###### 3. Constructor trả về kiểu giá trị gì?
[[Constructor]] trả về thể hiện của lớp hiện tại.

---
###### 4. Constructor được kế thừa không?
**Không**, [[Constructor]] không được kế thừa. 
Lớp con có thể khởi tạo [[Constructor]] bằng phương thức `super()` 
`class Circle extends Shape {
	Circle(){
		super();
		r = 0;
	}
	Circle(square, r){
		super(square);
		this.r = r;
	}
}`

---
###### 5. Có thể tạo constructor final không?
**Không** , constructor không thể là final.
### Static reference
###### 6. Biến static là gì?
-   Biến static có thể được sử dụng để tham chiếu thuộc tính chung của tất cả đối tượng (mà không là duy nhất cho mỗi đối tượng), ví dụ như tên công ty của nhân viên, tên trường học của các sinh viên, …
-   Biến static lấy bộ nhớ chỉ một lần trong Class Area tại thời gian tải lớp đó.
[chi tiết...](https://viettuts.vn/java/tu-khoa-static-trong-java)
---
###### 7. Phương thức static là gì?
-   Một phương thức static thuộc lớp chứ không phải đối tượng của lớp.
-   Một phương thức static gọi mà không cần tạo một instance của một lớp.
-   Phương thức static có thể truy cập biến static và có thể thay đổi giá trị của nó.
[chi tiết...](https://viettuts.vn/java/tu-khoa-static-trong-java)
---
###### 8. Tại sao phương thức main là static?
Bởi vì không cần thiết phải tạo đối tượng để gọi phương thức static. Nếu nó là phương thức non-static, JVM đầu tiên tạo đối tượng và sau đó gọi phương thức main() mà có thể gây ra vấn đề về cấp phát bộ nhớ bộ nhớ phụ.
[chi tiết...](https://viettuts.vn/java/tu-khoa-static-trong-java) 
---
###### 9. Khối static là gì?
-   Được sử dụng để khởi tạo thành viên dữ liệu static.
-   Nó được thực thi trước phương thức main tại lúc tải lớp.
[chi tiết...](https://viettuts.vn/java/tu-khoa-static-trong-java)
---
###### 10. Sự khác nhau giữa phương thức static và phương thức instance?
| Phương thức static                                                                      | Phương thức instance                                                   |
|--------------------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| Phương thức được khai báo với từ khoá static                                            | Phương thức **không** được khai báo với từ khoá static                 |
| Không cần tạo đối tượng để gọi phương thức từ class                                     | Phải tạo đối tượng ở class để gọi phương thức instance                 |
| Biến non-static không được truy cập trực tiếp trong phương thức static hoặc khối static | Biến static và non-static được truy cập trực tiếp phương thức instance |

---
### Overloading vs Override

###### 11. Overloading (nạp chồng) phương thức là gì?

Nếu một lớp có nhiều phương thức có tên giống nhau nhưng các tham số khác nhau, được gọi là [[Overloading]] phương thức (nạp chồng phương thức). Nó giúp code rõ ràng, dễ hiểu hơn.

[chi tiết...](https://viettuts.vn/java/overloading-phuong-thuc-trong-java)

---

###### 12. Tại sao overloading phương thức không xảy ra khi thay đổi kiểu giá trị trả về?

Bởi vì đó là sự không rõ ràng, không biết gọi phương thức nào khi runtime.

[chi tiết...](https://viettuts.vn/java/overloading-phuong-thuc-trong-java)

---

###### 13. Có thể overload phương thúc main() không?

Có, có thể overload phương thức main().

[chi tiết...](https://viettuts.vn/java/overloading-phuong-thuc-trong-java)

---
###### 14. Ghi đè (overriding) phương thức là gì?

Nếu lớp con có phương thức giống lớp cha được gọi là ghi đè (overriding) phương thức trong java.

Nói cách khác, nếu lớp con cung cấp sự cài đặt cụ thể cho phương thức đã được cung cấp bởi một lớp cha của nó được gọi là ghi đè (overriding) phương thức trong java.

[chi tiết...](https://viettuts.vn/java/overriding-phuong-thuc-trong-java)

---

###### 15. Có thể ghi đè phương thức static không?

**Không thể ghi đè phương thức static** vì chúng thuộc về class chứ không thuộc về đối tượng.

---

###### 16. Tại sao không thể ghi đè phương thức static?

Bởi vì phương thức static là một phần của lớp và nó bị ràng buộc với lớp, trong khi phương thức instance là bị ràng buộc với đối tượng, static được lưu trong vùng nhớ, Class và instance được lưu trong bộ nhớ heap.

---

###### 17. Có thể ghi đè phương thức đã nạp chồng?

Có.

---

###### 18. Có thể ghi đè biến instance không?

Không.

---

###### 19. Sự khác nhau giữa nạp chồng và ghi đè là gì?

| [[Overloading]]                                                                                                     | [[Override]]                                                    |
| ------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------- |
| Sử dụng để code dễ đọc hơn                                                                                          | Cung cấp cài đặt cụ thể cho phương thức được khai báo ở lớp cha |
| Thực hiện bên trong 1 class                                                                                         | Xảy ra trong 2 class có quan hệ kế thừa                         |
| Tham số phải khác nhau                                                                                              | Tham số của phương thức ở lớp cha và con phải giống nhau        |
| Không thể Overloading khi chỉ thay đổi kiểu giá trị trả về của phương thức. Kiểu trả về có thể giống hoặc khác nhau | Kiểu giá trị trả về phải giống nhau                                                                |

---
###### 20. Kiểu trả về hiệp biến là gì?

Từ java 5 trở đi, có thể ghi đè bất kỳ phương thức nào bởi việc thay đổi kiểu giá trị trả về. Nếu kiểu trả về của phương thức ghi đè của lớp con là lớp con. Nó được gọi là kiểu trả về hiệp biến.

### Final reference
###### 21. Biến final là gì?

Nếu bạn tạo một biến với từ khóa final, bạn sẽ không thể thay đổi được giá trị của biến đó (hằng số).

[chi tiết...](https://viettuts.vn/java/tu-khoa-final-trong-java)

---

###### 22. Phương thức final là gì?

Phương thức final không thể được ghi đè.

[chi tiết...](https://viettuts.vn/java/tu-khoa-final-trong-java)

---

###### 23. Lớp final là gì?

Lớp final không thể được kế thừa.

[chi tiết...](https://viettuts.vn/java/tu-khoa-final-trong-java)

---

###### 24. Biến final blank là gì?

Một biến final không được khởi tạo giá trị lúc khai báo được gọi là biến final blank.

[chi tiết...](https://viettuts.vn/java/tu-khoa-final-trong-java)

---

###### 25. Có thể khởi tạo giá trị cho biến final blank không?

Có, nếu biến đó là non-static thì chỉ khởi tạo được trong constructor. Nếu biến đó là static thì chỉ khởi tạo được trong khối static.

[chi tiết...](https://viettuts.vn/java/tu-khoa-final-trong-java)

---

###### 26. Có thể khai báo phương thức main là final không?

Có, giống như: `public static final void main(String[] args){}`

###### 27. Đa hình tại runtime là gì? 

Đa hình tại runtime là quá trình gọi phương thức đã được ghi đè trong thời gian thực thi chương trình. Trong quá trình này, một phương thức được ghi đè được gọi thông qua biến tham chiếu của một lớp cha.

[chi tiết...](https://viettuts.vn/java/tinh-da-hinh-trong-java)

---
###### 28. Sự khác nhau giữa trừu tượng và đóng gói?

Trừu tượng là ẩn đi cài đặt chi tiết còn đóng gói là gói code và data vào một khối duy nhất.

---
###### 29. Lớp trừu tượng là gì? 
Một lớp được khai báo với từ khóa abstract là lớp trừu tượng trong Java. Cần có một lớp khác kế thừa nó và cài đặt phương thức của nó. Nó không thể là thể hiện (instance) cụ thể.

[chi tiết...](https://viettuts.vn/java/abstract-class-trong-java)

---
###### 30. Có thể sử dụng cả abstract và final cho một phương thức không?

**Không**, vì phuong thức trừu tượng (abstract) cần phải được ghi đè, trong khi đó không thể ghi đè được phương thức final.

---
###### 31. Có thể tạo thể hiện của lớp trừu tượng không?

**Không**, lớp trừu tượng không có thể hiện.

--- 
###### 32. Interface là gì?

Một [[Interface]] trong Java là một bản thiết kế của một lớp. Nó chỉ có các phương thức trừu tượng. Interface là một kỹ thuật để thu được tính trừu tượng hoàn toàn và đa kế thừa trong Java.

[chi tiết...](https://viettuts.vn/java/interface-trong-java)

--- 
###### 33. Có thể khai báo một phương thức của interface với từ khóa static không?

**Không**, vì mặc định các phương thức của một interface là trừu tượng, từ khóa static và abtract không thể được sử dụng chung với nhau.

---

###### 34. Sự khác nhau giữa lớp abstract và interface là gì?

| [[Lớp Abstract]]                                                                 | [[Interface]]                                          |
| -------------------------------------------------------------------------------- | -------------------------------------------------- |
| Một lớp abstract có thể có phương thức có nội dung (các phương thức tường minh). | Interface chỉ có các phương thức trừu tượng.       |
| Một lớp abstract có thể có các biến instance.                                    | Một interface không thể có các biến instance.      |
| Một lớp abstract có thể có constructor.                                          | Một interface không thể có constructor.            |
| Một lớp abstract có thể có các phương thức static.                               | Một interface không thể có các phương thức static. |
| Một lớp abstract chỉ có thể extends một lớp abstract.                            | Một lớp thể implement nhiều interface.                                                   |

---
###### 35. Có thể sử dụng cả abstract và final cho một phương thức không?

Không, vì phuong thức trừu tượng (abstract) cần phải được ghi đè, trong khi đó không thể ghi đè được phương thức final.

---
###### 36. Sự khác nhau giữa throw và throws là gì?
| Throw                                                                | Throws                                                                  |
| -------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| Sử dụng để ném ra một ngoại lệ rõ ràng.                              | Sử dụng để khai báo một ngoại lệ.                                       |
| Ngoại lệ checked không được truyền ra nếu chỉ sử dụng từ khóa throw. | Ngoại lệ checked được truyền ra ngay cả khi chỉ sử dụng từ khóa throws. |
| Sau throw là một instance.                                           | Sau throws là một hoặc nhiều class.                                     |
| Throw được sử dụng trong phương thức.                                | Throws được khai báo ngay sau dấu đóng ngoặc đơn của phương thức        |
| Không thể throw nhiều exceptions                                     | Có thể khai báo nhiều exceptions. Ví dụ: `void method() throws IOException, SQLException.`                                                                        |

### Collections
37. Sự khác nhau giữa ArrayList và Vector?
38. Sự khác nhau giữa ArrayList và LinkedList?
39. Sự khác nhau giữa Iterator và ListIterator?
40. Sự khác nhau giữa Iterator và Enumeration?
41. Sự khác nhau giữa List và Set?
42. Sự khác nhau giữa HashSet và TreeSet?
43. Sự khác nhau giữa Set và Map?
44. Sự khác nhau giữa HashSet và HashMap?
45. Sự khác nhau giữa HashMap và Hashtable?
46. Sự khác nhau giữa Collection và Collections?
47. Sự khác nhau giữa Comparable và Comparator?
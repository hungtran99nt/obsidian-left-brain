- Chỉ sử dụng các thuộc tính không phải là [[Static]] và [[Transient]] (non-static, non-transient) để generate *equals()* và *hashCode()*.
- Thêm method *canEqual()* để xác định nhanh object có phải là instance của class đó hay không.
---
##### Exclude Fields
- Các thuộc tính định danh **(id)**, thời gian khởi tạo object **(createdAt)** **không nên** tham gia vào *equals()* và *hashCode()*, vì mỗi khi object được tạo ra thì các giá trị này sẽ khác nhau => giá trị *hashCode()* của mỗi object sẽ khác nhau và *equals()* sẽ luôn trả về FALSE.

###### Exclude Field Level
Sử dụng _**@EqualsAndHashCode.Exclude**_ chú thích các thuộc tính không được sử dụng khi Lombok generate _equals()_ và _hashCode()_ method.
```java
@EqualsAndHashCode
public class Employee {
	private String name;
	private int salary;
	@EqualsAndHashCode.Exclude
	private LocalDate createdAt;
	private transient int transientVar = 10;
	private final int finalVar = 10;
}
```

###### Exclude Class Level
```java
@EqualsAndHashCode(exclude = {"createdAt", "none"} )
public class Employee {
	private String name;
	private int salary;
	private LocalDate createdAt;
	private transient int transientVar = 10;
	private final int finalVar = 10;
}
```
---
##### Include Fields

###### Include Field Level
Chỉ định các thuộc tính được _@EqualsAndHashCode_ generate, các ==thuộc tính không được chỉ định sẽ bị loại bỏ==.
```java
@EqualsAndHashCode(onlyExplicitlyIncluded = true )
public class Employee {
	@EqualsAndHashCode.Include
	private String name;
	@EqualsAndHashCode.Include
	private int salary;
	private LocalDate createdAt;
	private transient int transientVar = 10;
	private final int finalVar = 10;
}
```

###### Include Method Level
So sánh các Employee theo mức lương thay vì chính xác từng chữ số
```java
@EqualsAndHashCode(onlyExplicitlyIncluded = true )
public class Employee {
    @EqualsAndHashCode.Include
    private String name;
    private int salary;
    private LocalDate createdAt;
    private transient int transientVar = 10;
    private final int finalVar = 10;

    @EqualsAndHashCode.Include
    public int canGo() {
        if (salary < 10000000 && salary > 0) {
            return 1;
        } else if (salary >= 10000000 && salary < 15000000) {
            return 2;
        } else if (salary >= 15000000 && salary <=30000000) {
            return 3;
        } else {
            return 4;
        }
    }

    public Employee(String name, int salary, LocalDate createdAt) {
        this.name = name;
        this.salary = salary;
        this.createdAt = createdAt;
    }
}

class Main {
    public static void main(String[] agrs) {
        Employee employee1 = new Employee("Hai", 10000000, LocalDate.now());
        Employee employee2 = new Employee("Hai", 14000000, LocalDate.now());
        Employee employee3 = new Employee("Hai", 300000000, LocalDate.now());


        boolean b1 = employee1.equals(employee2); // TRUE
        boolean b2 = employee1.equals(employee3); // FALSE
    }
}
```

###### Include class level
```java
@EqualsAndHashCode(of = {"name", "salary"})
public class Employee {
    private String name;
    private int salary;
    private LocalDate createdAt;
    private transient int transientVar = 10;
    private final int finalVar = 10;
}
```
---
##### Thừa kế và Call supper class
==WARNING:== Sử dụng _@EqualsAndHashCode_ cho **subclass** có thể vi phạm equals() và hashCode() contract.

Default callSupper
Khi chú thích _@EqualsAndHashCode_ cho 1 class, **mặc định thuộc tính callSupper là FALSE**, hay class đó sẽ ==không gọi *equals()* và *hashCode()* ở supper class khi generate.==

###### Custom callSupper
1. Case 1: 
- Supper class **không override** equals() và hashCode().
- callSupper = **FALSE**
=> *equals()* và *hashCode()* sẽ ==chỉ sử dụng các thuộc tính trong subclass==
 
3. Case 2
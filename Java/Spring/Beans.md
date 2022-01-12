- Bean là những module chính của chương trình, được tạo và quản lý bởi Spring [[IoC]] Container.
- Các Bean mô tả sự phụ thuộc cho [[IoC]] bằng cơ chế [[Dependency Injection]].

###### Inject qua constructor hoặc setter
1. Constructor
`@Component 
public class Car { 
	private final Engine engine; 
	// Các bản Spring Boot mới thì không cần @Autowired trên constructor 
	public Car(Engine engine) { 
		this.engine = engine; 
	} 
}`
2. Setter/Getter
`@Component 
public class Car { 
	private final Engine engine; 
	// Thêm @Required để setter luôn được gọi để inject @Required 
	public void setEngine(Engine engine) { 
		this.engine = engine; 
	} 
}`
Inject bằng setter thường dùng trong trường hợp **phụ thuộc vòng**, module A phụ thuộc vào B và ngược lại.
Nếu 2 module phụ thuộc vòng sử dụng constructor injection thì [[Spring Boot]] sẽ không biết tạo Bean nào trước.



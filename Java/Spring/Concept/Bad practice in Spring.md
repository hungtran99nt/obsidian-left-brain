#### Tránh dùng try-catch-finally để logging
###### Vấn đề:
1. Code dài dòng.
2. Làm cho `@ExeptionHandler` không còn ý nghĩa.
###### Giải pháp
1. Dùng AOP để inject module logging.
---
#### Luôn dùng `Response Entity<T>`
###### Vấn đề 
1. Vi phạm nguyên tắc Single Responsibility (**S**OLID).
```java
@PostMapping("/users") 
public ResponseEntity<UserModel> createUser(@RequestBody UserDto dto) { // Thêm đoạn này còn tệ hơn nữa 
	if (dto == null) 
		return ResponseEntity.badRequest().body("Error"); 
	else 
		return ResponseEntity.ok(userService.createUser(dto)); 
}
```
###### Giải pháp
1. Trường hợp lỗi thì để @ExceptionHandler xử lý.
2. Nếu chỉ dùng method `ok()`, ta có thể đơn giản hóa như sau
```java
@PostMapping("/users")
@ResponseStatus(HttpStatus.CREATED) // 201
public UserModel createUser(@RequestBody UserDto dto) {
    return userService.createUser(dto);
}
```
---
#### Sử dụng các Exception class có sẵn
###### Vấn đề
Trong app sẽ chia ra 2 loại exception: 
1. **Technical exception**: do code gây nên, cần fix.
2. **Business exception**: sai về mặt nghiệp vụ, cần đưa ra thông báo yêu cầu user điều chỉnh và thử lại.
###### Giải pháp
1. Phân biệt và cài đặt exception tương ứng với 2 loại trên.
2. Cài đặt logging cho Technical Exception.
---

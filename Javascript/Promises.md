- handle exception
- avoid bad practice and messy code
- make code reasonable and easy to read

#### note

Callback from a Promise not be moved into the Callback Queue
=> Callbacks of Promise has their own queue
=> Microtasks queue 
![[Pasted image 20220211103117.png]]
![[Pasted image 20220211103430.png]]
Microtasks queue **has priority over** callback queue
=> Callback in Microtasks queue luôn được execute trước callback in callback queue

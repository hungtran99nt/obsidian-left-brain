# Xâu nhị phân kế tiếp
1. **Duyệt ngược xâu S** đã cho đến khi thấy **phần tử S[i] = 0**
=> Set các phần tử S[i] = 0

2. Duyệt xong, nếu i >= 0, set phần tử S[i] = 1

# Sinh tổ hợp

Tổ hợp chập k của n
**i = k**
1. Duyệt ngược đến khi phần tử **A[i] != n - k + i**
2. Duyệt xong, nếu i > 0, set **A[i] = A[i] + 1**
	1. Duyệt xuôi từ **j = i + 1 --> k**
	2. Set A[j] = A[i] + j - i

``` java
public static void generate() {  
    int i, j;  
    i = k;  
    while (i > 0 && a[i] == n - k + i) i--;  
    if (i > 0) {  
        a[i] = a[i] + 1;  
        for (j = i + 1; j <= k; j++) {  
            a[j] = a[i] + j - i;  
        }  
        // print loop 0 -> k, a[i]  
    } else {  
        // print loop 0 -> k, i  
    }  
}
```

# Sinh tổ hợp ngược

Tổ hợp chập k của n
**i = k**
1. Duyệt ngược đến khi phần tử **A[i] != A[i - 1] + 1
2. Duyệt xong, nếu **i == 1**
	1. Duyệt ngược từ **j = k --> 1**
	2. Set **A[j] = n - k + j**

``` java
public static void generate() {  
    int i = k, j;  
    while (i > 0 && a[i] == a[i - 1] + 1) i--;  
    if (i == 1) {  
        for (j = k; j >= 1; j--) {  
            a[j] = n - k + j;  
        }  
        isTheLast = true;  
    } else {  
        a[i]--;  
        for (j = i + 1; j <= k; j++) {  
            a[j] = n - k + j;  
        }  
    }  
}
```
# Sinh hoán vị 
## Backtrack
```java
public static void Try(int i){  
    int j;  
    for (j = 1; j<=n-1; j++){  
        if (check[j] == 0){  
            check[j] = 1;  
            a[i] = j;  
            if (i == n-1) in();  
            else Try(i+1);  
            check[j] = 0;  
        }  
    }  
}
```


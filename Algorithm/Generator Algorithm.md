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

# Sinh tổ hợp ngược

Tổ hợp chập k của n
**i = k**
1. Duyệt ngược đến khi phần tử **A[i] != A[i - 1] + 1
2. Duyệt xong, nếu **i == 1**
	1. Duyệt xuôi từ **j = i + 1 --> k**
	2. Set A[j] = A[i] + j - i

# Sinh hoán vị 
## Backtrack


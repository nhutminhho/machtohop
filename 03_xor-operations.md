# Các Định Lý Về Phép Toán XOR (⊕)

## I. Giới Thiệu Về Phép XOR

### 1. Định Nghĩa
XOR (Exclusive OR) là phép toán logic cho kết quả 1 khi và chỉ khi hai đầu vào khác nhau.

### 2. Bảng Chân Lý XOR
```
x  y | x ⊕ y
0  0 |   0
0  1 |   1
1  0 |   1
1  1 |   0
```

## II. Các Định Lý Cơ Bản

### 1. XOR với 1 (x ⊕ 1 = x̄)
- **Định lý**: XOR một biến với 1 cho kết quả là phủ định của biến đó
- **Ví dụ thực tế**: 
  + Trong mạch điện: Đảo trạng thái đèn (bật→tắt, tắt→bật)
  + Trong lập trình: Toggle bit (0→1, 1→0)

### 2. XOR với Chính Nó (x ⊕ x = 0)
- **Định lý**: XOR một biến với chính nó luôn cho kết quả 0
- **Ví dụ thực tế**:
  + Mã hóa: Mã hóa hai lần với cùng key sẽ về dạng ban đầu
  + Kiểm tra lỗi: Phát hiện thay đổi trong dữ liệu

### 3. XOR với Phủ Định (x ⊕ x̄ = 1)
- **Định lý**: XOR một biến với phủ định của nó luôn cho kết quả 1
- **Ví dụ thực tế**:
  + Kiểm tra tính đúng đắn: Công tắc phải ở một trong hai trạng thái
  + Xác minh đầu vào: Tín hiệu phải là 0 hoặc 1

### 4. Tính Giao Hoán (x ⊕ y = y ⊕ x)
- **Định lý**: Thứ tự các toán hạng không ảnh hưởng đến kết quả
- **Ví dụ thực tế**:
  + Mã hóa: Thứ tự áp dụng key không quan trọng
  + Mạch so sánh: So sánh hai tín hiệu bất kỳ thứ tự nào

### 5. Tính Kết Hợp ((x ⊕ y) ⊕ z = x ⊕ (y ⊕ z))
- **Định lý**: Có thể nhóm các phép tính theo thứ tự tùy ý
- **Ví dụ thực tế**:
  + Mã hóa nhiều lớp: Thứ tự mã hóa không ảnh hưởng
  + Xử lý tín hiệu: Thứ tự xử lý các tín hiệu không quan trọng

### 6. Tính Phân Phối (x(y ⊕ z) = xy ⊕ xz)
- **Định lý**: Phép AND phân phối qua phép XOR
- **Ứng dụng**: 
  + Tối ưu hóa mạch logic
  + Thiết kế mạch số học

### 7. Phép Phủ Định XOR ((x ⊕ y)̄ = x̄ ⊕ ȳ = x̄ȳ + xy)
- **Định lý**: Phủ định của XOR có thể biểu diễn qua các phép toán khác
- **Ứng dụng**:
  + Kiểm tra tính tương đương
  + Tối ưu hóa mạch logic

## III. Ứng Dụng Thực Tế

### 1. Trong Mã Hóa
```
Mã hóa đơn giản:
Plaintext ⊕ Key = Ciphertext
Ciphertext ⊕ Key = Plaintext

Ví dụ:
Data:    1 0 1 1
Key:     1 1 0 1
Encoded:  0 1 1 0
```

### 2. Trong Kiểm Tra Lỗi
```
Checksum = Data₁ ⊕ Data₂ ⊕ Data₃
Nếu có lỗi, checksum sẽ khác với giá trị ban đầu
```

### 3. Trong Mạch So Sánh
```
Compare = A ⊕ B
- Nếu A = B, Compare = 0
- Nếu A ≠ B, Compare = 1
```

## IV. Bài Tập Thực Hành

### 1. Thiết Kế Mạch So Sánh 2-bit
```
Input: A[2], B[2]
Output: Equal = (A₁ ⊕ B₁) ⊕ (A₀ ⊕ B₀)
```

### 2. Mã Hóa Đơn Giản
```
Bài toán: Mã hóa 4-bit data với key
Data = 1010
Key  = 1100
Encoded = Data ⊕ Key = 0110
```

---
*Lưu ý: Phép XOR là một trong những phép toán cơ bản nhất trong thiết kế mạch số và bảo mật thông tin.*
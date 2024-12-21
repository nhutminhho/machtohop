# Biểu Diễn Hàm Boolean: Maxterm và Don't Care

## I. Tích Chuẩn Đầy Đủ (Maxterm)

### 1. Khái Niệm Cơ Bản
- **Maxterm**: Tổng các biến (OR) cho giá trị 0 tại một tổ hợp đầu vào cụ thể
- **Biểu thức**: f = ΠCBA(các hàng có Y=0) + d(don't care terms)
- **Ký hiệu**: M₀, M₁, M₂,... hoặc M(0), M(1), M(2),...

### 2. Cách Xác Định Maxterm
```
Quy tắc:
- Với Y = 0: Tạo maxterm
- Nếu bit = 0: Giữ nguyên biến
- Nếu bit = 1: Phủ định biến
- Liên kết các biến bằng dấu +
```

## II. Phân Tích Ví Dụ

### 1. Bảng Sự Thật Mẫu
```
Dec | C B A | Y | Maxterm
----|-------|---|----------
 2  | 0 1 0 | 0 | C + B̄ + A
 4  | 1 0 0 | 0 | C̄ + B + A
 7  | 1 1 1 | 0 | C̄ + B̄ + Ā
 5  | 1 0 1 | x | don't care
```

### 2. Xây Dựng Biểu Thức
```
f = ΠCBA(2,4,7)d(5)
  = (C + B̄ + A)(C̄ + B + A)(C̄ + B̄ + Ā)
```

## III. Ví Dụ Thực Tế: Hệ Thống Điều Khiển Máy Lạnh

### 1. Định Nghĩa Đầu Vào
```
C: Nhiệt độ
   0: Thấp (<25°C)
   1: Cao (≥25°C)

B: Độ ẩm
   0: Thấp (<60%)
   1: Cao (≥60%)

A: Chế độ tiết kiệm điện
   0: Tắt
   1: Bật
```

### 2. Các Trường Hợp Không Hoạt Động (Y=0)
```
M₂: Nhiệt độ thấp, độ ẩm cao, không tiết kiệm
    → (C + B̄ + A)

M₄: Nhiệt độ cao, độ ẩm thấp, không tiết kiệm
    → (C̄ + B + A)

M₇: Nhiệt độ cao, độ ẩm cao, tiết kiệm
    → (C̄ + B̄ + Ā)
```

### 3. Don't Care (d₅)
```
Trường hợp bảo trì:
- Nhiệt độ cao (C=1)
- Độ ẩm thấp (B=0)
- Tiết kiệm bật (A=1)
```

## IV. Lợi Ích Của Don't Care

### 1. Tối Ưu Hóa Mạch
- Giảm số lượng cổng logic
- Đơn giản hóa biểu thức
- Tăng hiệu suất mạch

### 2. Linh Hoạt Trong Thiết Kế
```
Don't care có thể được chọn là 0 hoặc 1:
- Chọn 0 để thêm maxterm
- Bỏ qua để đơn giản hóa biểu thức
```

## V. Bài Tập Thực Hành

### 1. Thiết Kế Hệ Thống Báo Cháy
```
Inputs:
C: Cảm biến khói
B: Cảm biến nhiệt
A: Chế độ kiểm tra

Yêu cầu:
1. Xác định các trường hợp không báo động
2. Xác định don't care (trường hợp bảo trì)
3. Viết biểu thức maxterm
```

### 2. Hệ Thống Đèn Thông Minh
```
Inputs:
C: Cảm biến ánh sáng
B: Phát hiện chuyển động
A: Chế độ ban đêm

Thiết kế:
1. Vẽ bảng sự thật
2. Xác định maxterm và don't care
3. Tối ưu hóa biểu thức
```

## VI. Lưu Ý Quan Trọng

### 1. Khi Sử Dụng Don't Care
- Xem xét kỹ các trường hợp thực tế
- Đảm bảo không ảnh hưởng đến an toàn
- Tận dụng để tối ưu hóa mạch

### 2. Trong Thực Tế
- Don't care thường là:
  + Trạng thái bảo trì
  + Trường hợp không xảy ra
  + Điều kiện không quan trọng

---
*Lưu ý: Kết hợp maxterm và don't care giúp thiết kế mạch hiệu quả hơn.*
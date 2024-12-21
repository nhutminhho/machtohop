# Thiết Kế Mạch Logic Tổ Hợp: Quy Trình và Ví Dụ

## I. Quy Trình Thiết Kế

### 1. Bước 1: Lập Bảng Sự Thật
- Xác định đầu vào và đầu ra
- Liệt kê tất cả tổ hợp có thể
- Xác định đầu ra cho mỗi tổ hợp

### 2. Bước 2: Biểu Thức Boolean
- Chuyển từ bảng sự thật sang biểu thức
- Có thể dùng minterm hoặc maxterm
- Biểu diễn theo yêu cầu bài toán

### 3. Bước 3: Rút Gọn
- Áp dụng định lý Boolean
- Sử dụng bản đồ Karnaugh
- Tối ưu hóa biểu thức

### 4. Bước 4: Thiết Kế Mạch
- Chuyển biểu thức thành mạch
- Sử dụng cổng logic cơ bản
- Tối ưu hóa số cổng

## II. Ví Dụ: Mạch Biểu Quyết

### 1. Phân Tích Yêu Cầu
```
Đầu vào: 3 tín hiệu A, B, C
Đầu ra: Y = 1 khi có ít nhất 2 đầu vào mức cao (1)
```

### 2. Lập Bảng Sự Thật
```
C B A | Y
------|---
0 0 0 | 0
0 0 1 | 0
0 1 0 | 0
0 1 1 | 1
1 0 0 | 0
1 0 1 | 1
1 1 0 | 1
1 1 1 | 1
```

### 3. Xây Dựng Biểu Thức
```
Minterm: Y = m₃ + m₅ + m₆ + m₇
Y = ABC + AB'C + A'BC + ABC

Hoặc:
Y = AB + BC + AC (sau khi tối ưu)
```

### 4. Thiết Kế Mạch
```
Sử dụng:
- 3 cổng AND 2 đầu vào
- 1 cổng OR 3 đầu vào
```

## III. Ứng Dụng Thực Tế

### 1. Hệ Thống Biểu Quyết
```
Inputs:
A, B, C: Phiếu bầu của 3 thành viên
Output:
Y: Kết quả (thông qua khi đa số đồng ý)
```

### 2. Hệ Thống An Toàn
```
Inputs:
A: Cảm biến nhiệt
B: Cảm biến khói
C: Cảm biến áp suất
Output:
Y: Báo động khi ít nhất 2 cảm biến phát hiện nguy hiểm
```

## IV. Lưu Ý Khi Thiết Kế

### 1. Tối Ưu Hóa
- Giảm số lượng cổng logic
- Giảm độ trễ
- Tăng độ tin cậy

### 2. Kiểm Tra
- Xác nhận tất cả tổ hợp
- Kiểm tra điều kiện biên
- Đảm bảo yêu cầu thời gian

---
*Lưu ý: Quy trình này áp dụng cho mọi bài toán thiết kế mạch tổ hợp.*
# Thiết Kế Mạch Logic Tổ Hợp: Bảng Sự Thật

## I. Giới Thiệu Về Bảng Sự Thật

### 1. Định Nghĩa
Bảng sự thật (Truth Table) là cách biểu diễn đầy đủ mối quan hệ giữa đầu vào và đầu ra của một hàm Boolean.

### 2. Thành Phần Cơ Bản
- Các cột đầu vào (Input variables)
- Cột đầu ra (Output)
- Các hàng biểu diễn tổ hợp có thể
- Giá trị don't care (x)

## II. Cấu Trúc Bảng Sự Thật

### 1. Quy Ước Giá Trị
```
0: Logic 0 (FALSE)
1: Logic 1 (TRUE)
x: Don't care (có thể là 0 hoặc 1)
```

### 2. Ví Dụ Minh Họa
Xét mạch với 3 đầu vào (A, B, C) và 1 đầu ra (Y):
```
Decimal | C B A | Y
--------|-------|---
   0    | 0 0 0 | 0
   1    | 0 0 1 | 1
   2    | 0 1 0 | 0
   3    | 0 1 1 | 1
   4    | 1 0 0 | x
   5    | 1 0 1 | x
   6    | 1 1 0 | 0
   7    | 1 1 1 | 0
```

## III. Ứng Dụng Thực Tế

### 1. Hệ Thống Bảo Mật Đơn Giản
```
Inputs:
A: Cảm biến cửa (0: đóng, 1: mở)
B: Thời gian (0: ngày, 1: đêm)
C: Chế độ bảo vệ (0: tắt, 1: bật)

Output:
Y: Báo động (0: tắt, 1: bật)
```

### 2. Điều Khiển Đèn Tự Động
```
Inputs:
A: Cảm biến ánh sáng (0: sáng, 1: tối)
B: Phát hiện chuyển động (0: không, 1: có)
C: Chế độ tiết kiệm (0: tắt, 1: bật)

Output:
Y: Đèn (0: tắt, 1: bật)
```

## IV. Cách Đọc và Sử Dụng

### 1. Phân Tích Theo Hàng
Ví dụ với hàng Decimal = 3:
```
C = 0, B = 1, A = 1 → Y = 1
Nghĩa là: Khi đầu vào là 011, đầu ra sẽ là 1
```

### 2. Don't Care Conditions
- Trường hợp x (don't care) cho phép linh hoạt trong thiết kế
- Có thể chọn 0 hoặc 1 tùy theo yêu cầu tối ưu

## V. Tối Ưu Hóa Mạch

### 1. Sử Dụng Don't Care
```
Khi gặp x, chọn giá trị để:
- Đơn giản hóa mạch
- Giảm số cổng logic
- Tăng tốc độ xử lý
```

### 2. Ví Dụ Tối Ưu
```
Trước khi tối ưu:
Y = ABC + AB'C + ABC'

Sau khi tối ưu (với x = 1):
Y = AB + AC
```

## VI. Bài Tập Thực Hành

### 1. Thiết Kế Hệ Thống Đèn Giao Thông
```
Inputs:
A: Thời gian (0: ngày, 1: đêm)
B: Lưu lượng xe (0: ít, 1: nhiều)
C: Chế độ khẩn cấp

Output:
Y: Thời gian đèn xanh
```

### 2. Thiết Kế Điều Khiển Quạt
```
Inputs:
A: Nhiệt độ (0: thấp, 1: cao)
B: Độ ẩm (0: thấp, 1: cao)
C: Chế độ tiết kiệm điện

Output:
Y: Tốc độ quạt
```

---
*Lưu ý: Bảng sự thật là công cụ cơ bản và quan trọng trong thiết kế mạch số.*
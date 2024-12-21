# Biểu Diễn Hàm Boolean: Dạng Tổng Chuẩn Đầy Đủ (Minterm)

## I. Khái Niệm Cơ Bản

### 1. Định Nghĩa Minterm
- Minterm là một tích các biến Boolean, trong đó mỗi biến xuất hiện đúng một lần, hoặc ở dạng phủ định hoặc không phủ định
- Mỗi minterm cho giá trị 1 tại đúng một tổ hợp đầu vào

### 2. Ký Hiệu
```
- Biến không phủ định: A, B, C,...
- Biến phủ định: Ā, B̄, C̄,...
- Minterm thứ i: mi hoặc M(i)
```

## II. Cách Xây Dựng Minterm

### 1. Quy Tắc Cơ Bản
1. Với n biến đầu vào, có 2ⁿ minterm
2. Mỗi minterm tương ứng với một hàng trong bảng sự thật
3. Chỉ xét các hàng có đầu ra Y = 1

### 2. Ví Dụ Minh Họa
```
Với 3 biến C, B, A:
m₁ (001) = C̄B̄A   (minterm 1)
m₃ (011) = C̄BA    (minterm 3)

f = Σ(1,3) = C̄B̄A + C̄BA
```

## III. Phân Tích Bảng Sự Thật

### 1. Bảng Sự Thật Mẫu
```
Decimal | C B A | Y | Minterm
--------|-------|---|--------
   0    | 0 0 0 | 0 |   -
   1    | 0 0 1 | 1 | C̄B̄A
   2    | 0 1 0 | 0 |   -
   3    | 0 1 1 | 1 | C̄BA
   4    | 1 0 0 | 0 |   -
   5    | 1 0 1 | 0 |   -
   6    | 1 1 0 | 0 |   -
   7    | 1 1 1 | 0 |   -
```

### 2. Cách Đọc Bảng và Tạo Biểu Thức
1. Tìm các hàng có Y = 1
2. Viết minterm cho mỗi hàng đó
3. Cộng các minterm lại với nhau

## IV. Ứng Dụng Thực Tế

### 1. Hệ Thống Báo Động
```
Inputs:
C: Cảm biến chuyển động (0: không, 1: có)
B: Thời gian (0: ngày, 1: đêm)
A: Chế độ bảo vệ (0: tắt, 1: bật)

f = C̄B̄A + C̄BA
Nghĩa là: Báo động khi
- Không có chuyển động, ban ngày, bảo vệ bật
- Không có chuyển động, ban đêm, bảo vệ bật
```

### 2. Điều Khiển Đèn Tự Động
```
Inputs:
C: Cảm biến ánh sáng (0: tối, 1: sáng)
B: Phát hiện chuyển động (0: không, 1: có)
A: Chế độ tiết kiệm (0: tắt, 1: bật)

f = C̄B̄A + C̄BA
Nghĩa là: Bật đèn khi
- Trời tối, không có người, chế độ tiết kiệm bật
- Trời tối, có người, chế độ tiết kiệm bật
```

## V. Bài Tập Thực Hành

### 1. Bài Tập Mẫu
```
Thiết kế mạch điều khiển quạt với 3 đầu vào:
C: Nhiệt độ (0: thấp, 1: cao)
B: Độ ẩm (0: thấp, 1: cao)
A: Chế độ tự động (0: tắt, 1: bật)

Yêu cầu: Quạt hoạt động khi
1. Nhiệt độ thấp, độ ẩm cao, chế độ tự động bật
2. Nhiệt độ cao, độ ẩm thấp, chế độ tự động bật

Giải:
f = C̄BA + CB̄A
```

### 2. Bài Tập Tự Giải
Thiết kế mạch điều khiển đèn giao thông với các yêu cầu:
1. Ba đầu vào: Thời gian, Lưu lượng xe, Chế độ khẩn cấp
2. Xác định các trường hợp đèn xanh sẽ bật
3. Viết biểu thức dưới dạng tổng các minterm

## VI. Lưu Ý Quan Trọng

1. Mỗi minterm là duy nhất cho một tổ hợp đầu vào
2. Tổng các minterm cho biểu diễn duy nhất của hàm
3. Có thể tối ưu hóa biểu thức sau khi có dạng tổng minterm

---
*Ghi chú: Dạng tổng chuẩn đầy đủ là nền tảng cho việc tối ưu hóa mạch logic.*
# Biểu Diễn Hàm Boolean: Tổng Chuẩn và Don't Care

## I. Giới Thiệu Về Trường Hợp Don't Care

### 1. Định Nghĩa Don't Care (x)
- Là trường hợp đầu ra có thể là 0 hoặc 1
- Cho phép linh hoạt trong thiết kế mạch
- Được sử dụng để tối ưu hóa hàm logic

### 2. Ký Hiệu Trong Bảng Sự Thật
```
f = Σ(minterm) + d(don't care terms)
Trong đó:
- Σ: Tổng các minterm
- d: Các trường hợp don't care
```

## II. Phân Tích Ví Dụ Cụ Thể

### 1. Bảng Sự Thật Mẫu
```
Decimal | C B A | Y | Minterm
--------|-------|---|--------
   0    | 0 0 0 | 0 |   -
   1    | 0 0 1 | 1 | C̄B̄A
   2    | 0 1 0 | 0 |   -
   3    | 0 1 1 | 1 | C̄BA
   4    | 1 0 0 | 0 |   -
   5    | 1 0 1 | x |   d₅
   6    | 1 1 0 | 0 |   -
   7    | 1 1 1 | x |   d₇
```

### 2. Cách Xây Dựng Biểu Thức
1. Xác định các minterm (Y = 1): m₁, m₃
2. Xác định các don't care: d₅, d₇
3. Biểu thức: f = Σ(1,3) + d(5,7)

## III. Tối Ưu Hóa Sử Dụng Don't Care

### 1. Quy Tắc Tối Ưu
1. Don't care có thể được chọn là 0 hoặc 1
2. Chọn giá trị để đơn giản hóa biểu thức
3. Ưu tiên giảm số cổng logic

### 2. Ví Dụ Tối Ưu
```
Ban đầu: f = C̄B̄A + C̄BA

Xét don't care d₅ và d₇:
- Nếu chọn d₅ = 1: thêm CB̄A
- Nếu chọn d₇ = 1: thêm CBA
```

## IV. Ứng Dụng Thực Tế

### 1. Hệ Thống Điều Khiển Thang Máy
```
Inputs:
C: Cảm biến quá tải
B: Nút dừng khẩn cấp
A: Cảm biến cửa

Don't care:
- Trường hợp không xảy ra trong thực tế
- Trường hợp bảo trì
```

### 2. Điều Khiển Máy Lạnh
```
Inputs:
C: Nhiệt độ (0: thấp, 1: cao)
B: Độ ẩm (0: thấp, 1: cao)
A: Chế độ tiết kiệm điện

Don't care:
- Trường hợp mất điện
- Trường hợp bảo trì
```

## V. Bài Tập Thực Hành

### 1. Bài Tập Phân Tích
```
Thiết kế hệ thống điều khiển đèn với:
- 3 đầu vào: Cảm biến ánh sáng, chuyển động, thời gian
- Các trường hợp don't care: bảo trì, lỗi cảm biến
```

### 2. Bài Tập Thiết Kế
```
Yêu cầu:
1. Vẽ bảng sự thật
2. Xác định minterm và don't care
3. Viết biểu thức tối ưu
4. Thiết kế mạch logic
```

## VI. Lưu Ý Quan Trọng

### 1. Khi Sử Dụng Don't Care
- Cân nhắc kỹ các trường hợp don't care
- Đảm bảo không ảnh hưởng đến hoạt động chính
- Tận dụng để tối ưu hóa mạch

### 2. Trong Thực Tế
- Don't care thường là các trường hợp:
  + Không xảy ra trong thực tế
  + Trạng thái lỗi hoặc bảo trì
  + Không quan trọng với hệ thống

---
*Lưu ý: Don't care là công cụ quan trọng trong tối ưu hóa mạch logic.*
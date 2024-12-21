# Biểu Diễn Hàm Boolean: Dạng Tích Chuẩn Đầy Đủ (Maxterm)

## I. Cơ Sở Lý Thuyết

### 1. Định Nghĩa Maxterm
- Maxterm là một tổng các biến Boolean
- Mỗi biến xuất hiện đúng một lần (dạng phủ định hoặc không phủ định)
- Cho kết quả 0 tại đúng một tổ hợp đầu vào

### 2. Ký Hiệu
```
- Tổng các biến: C + B + A
- Maxterm thứ i: Mi hoặc M(i)
- Tích các maxterm: Π (Pi)
```

## II. Phương Pháp Xây Dựng

### 1. Quy Tắc Cơ Bản
1. Xác định các hàng có Y = 0 trong bảng sự thật
2. Với mỗi hàng, tạo maxterm bằng cách:
   - Biến = 0 → không phủ định
   - Biến = 1 → phủ định
3. Lấy tích các maxterm

### 2. Ví Dụ Phân Tích
```
Với hàng Decimal = 2 (CBA = 010):
- C = 0 → C
- B = 1 → B̄
- A = 0 → A
Maxterm = C + B̄ + A
```

## III. Ứng Dụng Thực Tế

### 1. Hệ Thống An Ninh
```
Inputs:
C: Cảm biến cửa
B: Chế độ bảo vệ
A: Thời gian

Maxterm = (C + B̄ + A)(C̄ + B + A)
Nghĩa là: Hệ thống KHÔNG báo động khi:
- Cửa đóng HOẶC chế độ bảo vệ tắt HOẶC ban ngày
- Cửa mở HOẶC chế độ bảo vệ bật HOẶC ban ngày
```

### 2. Điều Khiển Điều Hòa
```
Inputs:
C: Nhiệt độ
B: Độ ẩm
A: Chế độ tiết kiệm

f = (C + B̄ + A)(C̄ + B + A)
KHÔNG hoạt động khi:
- Nhiệt độ thấp HOẶC độ ẩm thấp HOẶC tiết kiệm bật
- Nhiệt độ cao HOẶC độ ẩm cao HOẶC tiết kiệm bật
```

## IV. So Sánh Minterm và Maxterm

### 1. Đặc Điểm
```
Minterm:
- Tổng các tích
- Y = 1
- AND các biến

Maxterm:
- Tích các tổng
- Y = 0
- OR các biến
```

### 2. Chuyển Đổi
```
Minterm → Maxterm:
f = Σm(1,3,5,6,7) = ΠM(0,2,4)

Maxterm → Minterm:
f = ΠM(2,4) = Σm(0,1,3,5,6,7)
```

## V. Bài Tập Thực Hành

### 1. Bài Tập Phân Tích
```
Cho hệ thống điều khiển đèn:
C: Cảm biến ánh sáng
B: Phát hiện chuyển động
A: Chế độ tiết kiệm

Yêu cầu:
1. Vẽ bảng sự thật
2. Xác định các maxterm
3. Viết biểu thức tích chuẩn
```

### 2. Bài Tập Thiết Kế
```
Thiết kế hệ thống điều khiển cửa tự động:
1. Xác định các điều kiện KHÔNG mở cửa
2. Lập bảng sự thật
3. Viết biểu thức dưới dạng maxterm
4. Tối ưu hóa biểu thức
```

## VI. Lưu Ý Quan Trọng

### 1. Khi Nào Dùng Maxterm
- Khi cần mô tả các điều kiện KHÔNG hoạt động
- Khi có nhiều trường hợp Y = 1 hơn Y = 0
- Khi cần tối ưu hóa mạch theo dạng tích

### 2. Ưu Điểm
- Dễ dàng xác định điều kiện không hoạt động
- Phù hợp với một số cấu trúc mạch
- Có thể tối ưu hóa hiệu quả

---
*Lưu ý: Việc chọn biểu diễn minterm hay maxterm phụ thuộc vào bài toán cụ thể.*
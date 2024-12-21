# Thiết kế mạch phát hiện lỗi mã BCD

## 1. Phân tích yêu cầu
- Đầu vào: Mã BCD 4 bit A₃A₂A₁A₀ (A₃ là MSB)
- Đầu ra: 1 bit báo lỗi (HIGH khi có lỗi)
- Yêu cầu: Phát hiện tất cả các trường hợp mã không hợp lệ

## 2. Phân tích điều kiện lỗi

### 2.1 Đặc điểm mã BCD hợp lệ
- BCD (Binary-Coded Decimal) chỉ biểu diễn các số từ 0 đến 9
- Dãy bit hợp lệ: 0000 đến 1001
- Các mã từ 1010 đến 1111 là không hợp lệ

### 2.2 Các trường hợp lỗi
Mã BCD sẽ bị coi là lỗi khi:
1. Giá trị vượt quá 9 (1001)
2. Cụ thể là các mã: 1010, 1011, 1100, 1101, 1110, 1111

## 3. Xây dựng bảng truth table

### 3.1 Bảng truth table đầy đủ

| A₃ | A₂ | A₁ | A₀ | Error |
|----|----|----|----|----|
| 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 0 | 1 | 0 |
| 0 | 0 | 1 | 0 | 0 |
| 0 | 0 | 1 | 1 | 0 |
| 0 | 1 | 0 | 0 | 0 |
| 0 | 1 | 0 | 1 | 0 |
| 0 | 1 | 1 | 0 | 0 |
| 0 | 1 | 1 | 1 | 0 |
| 1 | 0 | 0 | 0 | 0 |
| 1 | 0 | 0 | 1 | 0 |
| 1 | 0 | 1 | 0 | 1 |
| 1 | 0 | 1 | 1 | 1 |
| 1 | 1 | 0 | 0 | 1 |
| 1 | 1 | 0 | 1 | 1 |
| 1 | 1 | 1 | 0 | 1 |
| 1 | 1 | 1 | 1 | 1 |

## 4. Rút ra biểu thức logic

### 4.1 Phân tích các trường hợp lỗi
Từ bảng truth table, ta thấy Error = 1 khi:
- A₃ = 1 VÀ (A₂ = 1 HOẶC (A₁ = 1))

### 4.2 Biểu thức logic tối giản
Error = A₃·(A₂ + A₁)

## 5. Thiết kế mạch logic

### 5.1 Các cổng logic cần thiết
1. 1 cổng OR để tổng hợp A₂ + A₁
2. 1 cổng AND để kết hợp với A₃

### 5.2 Sơ đồ mạch logic
```
A₂ ─────┐
        ├─OR──┐
A₁ ─────┘     │
              ├─AND───► Error
A₃ ───────────┘
```

## 6. Tối ưu hóa

### 6.1 Các phương án tối ưu
1. Sử dụng cổng NAND thay vì AND và OR (theo định lý De Morgan)
2. Có thể triển khai bằng mạch so sánh (comparator)

### 6.2 Ưu điểm của mạch
1. Đơn giản, ít cổng logic
2. Thời gian trễ thấp
3. Dễ dàng mở rộng cho các ứng dụng khác

## 7. Kết luận

Mạch phát hiện lỗi BCD được thiết kế thành công với:
- 4 đầu vào: A₃, A₂, A₁, A₀
- 1 đầu ra: Error
- Sử dụng 2 cổng logic cơ bản
- Phát hiện được tất cả các trường hợp mã không hợp lệ
- Dễ dàng triển khai trên thực tế
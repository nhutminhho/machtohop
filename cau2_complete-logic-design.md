# Thiết kế mạch logic từ bảng sự thật

## Bảng sự thật ban đầu

| A | B | C | Y |
|---|---|---|---|
| 0 | 0 | 0 | 1 |
| 0 | 0 | 1 | 0 |
| 0 | 1 | 0 | 1 |
| 0 | 1 | 1 | 1 |
| 1 | 0 | 0 | 1 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 0 |
| 1 | 1 | 1 | 1 |

## 1. Phân tích bảng sự thật
- **Đầu vào:** 3 biến A, B, C
- **Đầu ra:** Y
- Y = 1 với các tổ hợp đầu vào:
  * (0,0,0)
  * (0,1,0)
  * (0,1,1)
  * (1,0,0)
  * (1,1,1)

## 2. Xác định biểu thức Boolean 

### 2.1. Phương pháp tổng các tích (SOP):
Y = A'B'C' + A'BC + AB'C' + ABC

### 2.2. Giải thích từng thành phần:
- A'B'C': Tổ hợp khi A=0, B=0, C=0
- A'BC: Tổ hợp khi A=0, B=1, C=0 hoặc C=1
- AB'C': Tổ hợp khi A=1, B=0, C=0
- ABC: Tổ hợp khi A=1, B=1, C=1

## 3. Thiết kế mạch

### 3.1. Các cổng logic cần sử dụng:

1. Cổng NOT (3 cái):
   - Tạo A' từ A
   - Tạo B' từ B
   - Tạo C' từ C

2. Cổng AND (4 cái):
   - Gate 1: tạo tích A'B'C'
   - Gate 2: tạo tích A'BC
   - Gate 3: tạo tích AB'C'
   - Gate 4: tạo tích ABC

3. Cổng OR (1 cái):
   - Kết hợp tất cả các tích để tạo đầu ra Y

### 3.2. Sơ đồ kết nối:
```
A ─┬──NOT───┬─────AND1──┐
   │        │           │
B ─┼──NOT───┼─────AND2──┼───OR───Y
   │        │           │
C ─┴──NOT───┴─────AND3──┘
```

## 4. Kiểm tra và xác minh

### 4.1. Kiểm tra các trường hợp Y = 1:
1. (0,0,0): A'B'C' = 1
2. (0,1,0): A'BC' = 1
3. (0,1,1): A'BC = 1
4. (1,0,0): AB'C' = 1
5. (1,1,1): ABC = 1

### 4.2. Kiểm tra các trường hợp Y = 0:
- Tất cả các tổ hợp còn lại cho Y = 0

## 5. Tối ưu hóa

### 5.1. Phương pháp tối ưu:
1. Áp dụng định lý De Morgan
2. Gom nhóm các biến giống nhau
3. Giảm thiểu số lượng cổng logic

### 5.2. Ưu điểm của mạch:
- Sử dụng các cổng logic cơ bản
- Dễ dàng triển khai và kiểm tra
- Độ tin cậy cao

## 6. Kết luận
- Mạch đã được thiết kế đáp ứng đúng bảng sự thật
- Sử dụng tổng cộng 8 cổng logic (3 NOT, 4 AND, 1 OR)
- Có thể triển khai bằng IC cổng logic cơ bản
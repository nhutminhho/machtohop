# Thiết kế mạch so sánh số nhị phân 4 bit

## 1. Yêu cầu thiết kế
- **Đầu vào:** 4 bit A3A2A1A0 (A0 là LSB)
- **Đầu ra:** Y = 1 khi 0010 < A3A2A1A0 < 1000
- **Phạm vi:** Số nhị phân từ 3 đến 7 (0011 đến 0111)

## 2. Bảng sự thật đầy đủ

| A3 | A2 | A1 | A0 | Số thập phân | Y | Ghi chú |
|----|----|----|----|----|---|----------|
| 0 | 0 | 0 | 0 | 0 | 0 | < 3 |
| 0 | 0 | 0 | 1 | 1 | 0 | < 3 |
| 0 | 0 | 1 | 0 | 2 | 0 | < 3 |
| 0 | 0 | 1 | 1 | 3 | 1 | Hợp lệ |
| 0 | 1 | 0 | 0 | 4 | 1 | Hợp lệ |
| 0 | 1 | 0 | 1 | 5 | 1 | Hợp lệ |
| 0 | 1 | 1 | 0 | 6 | 1 | Hợp lệ |
| 0 | 1 | 1 | 1 | 7 | 1 | Hợp lệ |
| 1 | 0 | 0 | 0 | 8 | 0 | > 7 |
| 1 | 0 | 0 | 1 | 9 | 0 | > 7 |
| ... | ... | ... | ... | ... | 0 | > 7 |
| 1 | 1 | 1 | 1 | 15 | 0 | > 7 |

## 3. Phân tích biểu thức logic

### 3.1 Các trường hợp Y = 1:
```
Y = A3'A2'A1A0 +    // số 3
    A3'A2A1'A0' +   // số 4
    A3'A2A1'A0 +    // số 5
    A3'A2A1A0' +    // số 6
    A3'A2A1A0       // số 7
```

### 3.2 Rút gọn biểu thức:
```
Y = A3'(A2'A1A0 + A2A1'A0' + A2A1'A0 + A2A1A0' + A2A1A0)
  = A3'[A2'A1A0 + A2(A1'A0' + A1'A0 + A1A0' + A1A0)]
  = A3'(A2'A1A0 + A2)
```

## 4. Thiết kế mạch

### 4.1 Các cổng logic cần dùng:
1. NOT gates:
   - Đảo A3 thành A3'
   - Đảo A2 thành A2'

2. AND gates:
   - AND1: A2'A1A0
   - AND2: A3'A2
   - AND3: kết hợp các điều kiện

3. OR gate:
   - Kết hợp các tích để tạo Y

### 4.2 Kết nối mạch:
```
A3 ──NOT── ┬────AND2──┐
           │          │
A2 ──┬─NOT─┤          OR──Y
     │     │          │
A1 ──┴─────┴────AND1──┘
     │
A0 ──┘
```

## 5. Kiểm tra và xác minh

### 5.1 Kiểm tra các trường hợp Y = 1:
- 0011 (3): A3'A2'A1A0 = 1
- 0100 (4): A3'A2A1'A0' = 1
- 0101 (5): A3'A2A1'A0 = 1
- 0110 (6): A3'A2A1A0' = 1
- 0111 (7): A3'A2A1A0 = 1

### 5.2 Kiểm tra các trường hợp Y = 0:
- Số < 3: 0000, 0001, 0010
- Số > 7: 1000 trở lên

## 6. Kết luận
- Mạch hoạt động chính xác theo yêu cầu
- Biểu thức đã được tối giản
- Dễ dàng triển khai bằng IC cổng logic
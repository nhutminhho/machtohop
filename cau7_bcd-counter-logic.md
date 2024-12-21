# Thiết kế mạch logic cho bộ đếm BCD

## 1. Phân tích yêu cầu
### 1.1 Đặc điểm bộ đếm BCD:
- 4 bit đầu ra DCBA (BCD)
- Đếm từ 0000 đến 1001 (0-9)
- Reset về 0000 sau số 9

### 1.2 Yêu cầu mạch logic:
- Đầu vào: 4 bit DCBA từ bộ đếm
- Đầu ra X = 1 khi đếm đến số:
  * 2 (0010)
  * 3 (0011)
  * 9 (1001)
- Đầu ra X = 0 với các số khác

## 2. Bảng sự thật

| D | C | B | A | Số thập phân | X | Ghi chú |
|---|---|---|---|--------------|---|----------|
| 0 | 0 | 0 | 0 | 0 | 0 | |
| 0 | 0 | 0 | 1 | 1 | 0 | |
| 0 | 0 | 1 | 0 | 2 | 1 | HIGH |
| 0 | 0 | 1 | 1 | 3 | 1 | HIGH |
| 0 | 1 | 0 | 0 | 4 | 0 | |
| 0 | 1 | 0 | 1 | 5 | 0 | |
| 0 | 1 | 1 | 0 | 6 | 0 | |
| 0 | 1 | 1 | 1 | 7 | 0 | |
| 1 | 0 | 0 | 0 | 8 | 0 | |
| 1 | 0 | 0 | 1 | 9 | 1 | HIGH |

## 3. Thiết kế mạch logic

### 3.1 Biểu thức logic:
```
X = D'C'BA + D'C'B'A + DC'B'A
```

### 3.2 Phân tích biểu thức:
1. D'C'BA: Phát hiện số 3
2. D'C'B'A: Phát hiện số 2
3. DC'B'A: Phát hiện số 9

### 3.3 Các cổng logic cần dùng:
1. Cổng NOT (2 cái):
   - NOT D
   - NOT C
   - NOT B

2. Cổng AND (3 cái):
   - Cho số 2: D'C'B'A
   - Cho số 3: D'C'BA
   - Cho số 9: DC'B'A

3. Cổng OR (1 cái):
   - Kết hợp 3 đầu ra AND

## 4. Kiểm tra và xác minh

### 4.1 Kiểm tra các trường hợp X = 1:
1. Số 2 (0010):
   - D'C'B'A = 1
   - Các tích khác = 0
   - X = 1

2. Số 3 (0011):
   - D'C'BA = 1
   - Các tích khác = 0
   - X = 1

3. Số 9 (1001):
   - DC'B'A = 1
   - Các tích khác = 0
   - X = 1

### 4.2 Kiểm tra các trường hợp X = 0:
- Khi DCBA là các số khác 2, 3, 9
- Tất cả các tích = 0
- X = 0

## 5. Ưu điểm thiết kế
1. Sử dụng cổng logic cơ bản
2. Dễ dàng triển khai
3. Độ trễ thấp (3 tầng logic)
4. Dễ mở rộng cho các số khác

## 6. Kết luận
- Mạch hoạt động chính xác theo yêu cầu
- Đơn giản, hiệu quả
- Sử dụng 6 cổng logic (2 NOT, 3 AND, 1 OR)
- Dễ dàng tích hợp với bộ đếm BCD
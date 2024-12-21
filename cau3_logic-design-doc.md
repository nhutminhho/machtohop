# Thiết kế mạch logic với 2 ngõ vào LOW

## 1. Yêu cầu bài toán
- 3 ngõ vào: A, B, C
- Ngõ ra Y = HIGH (1) khi có đúng 2 ngõ vào ở mức LOW (0)
- Các trường hợp khác Y = LOW (0)

## 2. Bảng sự thật

| A | B | C | Y | Chú thích |
|---|---|---|---|------------|
| 0 | 0 | 0 | 0 | 3 ngõ LOW |
| 0 | 0 | 1 | 1 | 2 ngõ LOW |
| 0 | 1 | 0 | 1 | 2 ngõ LOW |
| 0 | 1 | 1 | 0 | 1 ngõ LOW |
| 1 | 0 | 0 | 1 | 2 ngõ LOW |
| 1 | 0 | 1 | 0 | 1 ngõ LOW |
| 1 | 1 | 0 | 0 | 1 ngõ LOW |
| 1 | 1 | 1 | 0 | 0 ngõ LOW |

## 3. Biểu thức logic
Y = A'B'C + A'BC' + AB'C'

### Giải thích:
- A'B'C: Trường hợp A=0, B=0, C=1
- A'BC': Trường hợp A=0, B=1, C=0
- AB'C': Trường hợp A=1, B=0, C=0

## 4. Thiết kế mạch

### 4.1. Các cổng logic cần dùng:
1. Cổng NOT (3 cái):
   - Đảo A thành A'
   - Đảo B thành B'
   - Đảo C thành C'

2. Cổng AND (3 cái):
   - Tạo tích A'B'C
   - Tạo tích A'BC'
   - Tạo tích AB'C'

3. Cổng OR (1 cái):
   - Kết hợp các tích để tạo Y

### 4.2. Nguyên lý hoạt động:
1. Các cổng NOT đảo giá trị đầu vào
2. Các cổng AND kiểm tra các trường hợp có 2 ngõ vào LOW
3. Cổng OR cho ra kết quả Y=1 nếu một trong các trường hợp trên xảy ra

## 5. Kiểm tra mạch
- Mạch sẽ cho Y=1 khi có đúng 2 ngõ vào LOW
- Dễ dàng kiểm tra bằng bảng sự thật
- Có thể mở rộng cho các trường hợp khác

## 6. Kết luận
- Mạch đáp ứng đúng yêu cầu đề bài
- Sử dụng 7 cổng logic cơ bản
- Dễ dàng triển khai trên thực tế
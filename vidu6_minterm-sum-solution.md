# Thiết Kế Mạch Logic: Tổng Các Minterm

## Đề bài
Thiết kế mạch cho hàm:
Y = ∑(ABCD)(1,11,13)

## Phân tích đề bài

### Thông tin cơ bản
- Hàm dạng tổng các minterm: Y = ∑m(1,11,13)
- Số biến đầu vào: 4 (A, B, C, D)
- Các minterm cần xét: m₁, m₁₁, m₁₃

### Ý nghĩa
- Đây là dạng SOM (Sum of Minterms)
- Y = 1 tại các hàng có chỉ số 1, 11, và 13 trong bảng chân lý
- Y = 0 tại các hàng còn lại

## Giải chi tiết

### 1. Chuyển đổi chỉ số sang nhị phân
- m₁  = 0001₂
- m₁₁ = 1011₂
- m₁₃ = 1101₂

### 2. Bảng chân lý

| A | B | C | D | Số thứ tự | Y |
|---|---|---|---|------------|---|
| 0 | 0 | 0 | 0 | 0  | 0 |
| 0 | 0 | 0 | 1 | 1  | **1** |
| 0 | 0 | 1 | 0 | 2  | 0 |
| 0 | 0 | 1 | 1 | 3  | 0 |
| 0 | 1 | 0 | 0 | 4  | 0 |
| 0 | 1 | 0 | 1 | 5  | 0 |
| 0 | 1 | 1 | 0 | 6  | 0 |
| 0 | 1 | 1 | 1 | 7  | 0 |
| 1 | 0 | 0 | 0 | 8  | 0 |
| 1 | 0 | 0 | 1 | 9  | 0 |
| 1 | 0 | 1 | 0 | 10 | 0 |
| 1 | 0 | 1 | 1 | 11 | **1** |
| 1 | 1 | 0 | 0 | 12 | 0 |
| 1 | 1 | 0 | 1 | 13 | **1** |
| 1 | 1 | 1 | 0 | 14 | 0 |
| 1 | 1 | 1 | 1 | 15 | 0 |

### 3. Xác định các minterm

#### Minterm m₁ (0001)
- Tổ hợp biến: A = 0, B = 0, C = 0, D = 1
- Biểu thức: m₁ = A'B'C'D

#### Minterm m₁₁ (1011)
- Tổ hợp biến: A = 1, B = 0, C = 1, D = 1
- Biểu thức: m₁₁ = AB'CD

#### Minterm m₁₃ (1101)
- Tổ hợp biến: A = 1, B = 1, C = 0, D = 1
- Biểu thức: m₁₃ = ABC'D

#### Biểu thức cuối cùng
Y = m₁ + m₁₁ + m₁₃ = A'B'C'D + AB'CD + ABC'D

### 4. Thiết kế mạch

#### Các thành phần chính
1. **Cổng NOT:**
   - Để đảo tín hiệu A, B, C khi cần

2. **Cổng AND:**
   - Ba cổng AND 4 ngõ vào cho mỗi minterm

3. **Cổng OR:**
   - Một cổng OR 3 ngõ vào để tổng hợp kết quả

## Giải thích hoạt động

### 1. Minterm m₁ (A'B'C'D)
- **Đầu vào:**
  * A qua NOT
  * B qua NOT
  * C qua NOT
  * D trực tiếp
- **Xử lý:**
  * AND bốn tín hiệu
  * Cho kết quả = 1 khi A=0, B=0, C=0, D=1

### 2. Minterm m₁₁ (AB'CD)
- **Đầu vào:**
  * A trực tiếp
  * B qua NOT
  * C trực tiếp
  * D trực tiếp
- **Xử lý:**
  * AND bốn tín hiệu
  * Cho kết quả = 1 khi A=1, B=0, C=1, D=1

### 3. Minterm m₁₃ (ABC'D)
- **Đầu vào:**
  * A trực tiếp
  * B trực tiếp
  * C qua NOT
  * D trực tiếp
- **Xử lý:**
  * AND bốn tín hiệu
  * Cho kết quả = 1 khi A=1, B=1, C=0, D=1

### 4. Ngõ ra Y
- **Xử lý:**
  * OR ba kết quả từ các minterm
  * Y = 1 khi bất kỳ minterm nào = 1
  * Y = 0 khi tất cả minterm = 0

## Tối ưu hóa mạch

### 1. Giảm độ trễ
- Sắp xếp các cổng logic hợp lý
- Tối thiểu hóa số cổng NOT

### 2. Tối ưu kết nối
- Tận dụng các tín hiệu đảo chung
- Sắp xếp đường đi tín hiệu ngắn nhất

## Kiểm tra và xác minh

### 1. Kiểm tra các trường hợp
- Tất cả tổ hợp đầu vào có thể
- Đặc biệt chú ý các trường hợp Y = 1
- Xác nhận chuyển trạng thái đúng

### 2. Đo đạc thực tế
- Độ trễ tín hiệu qua mạch
- Mức điện áp đầu ra
- Độ nhiễu và nhiễu xuyên âm

## Kết luận
1. Mạch được thiết kế theo đúng yêu cầu của hàm SOM
2. Hoạt động chính xác theo bảng chân lý đã cho
3. Cấu trúc đơn giản với 3 cổng AND và 1 cổng OR
4. Có thể tối ưu thêm tùy theo yêu cầu thực tế
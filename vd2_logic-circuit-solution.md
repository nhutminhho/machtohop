# Thiết Kế Mạch Logic 3 Ngõ Vào

## Đề bài
Thiết kế một mạch logic 3 ngõ vào A, B, C với yêu cầu ngõ ra sẽ ở mức cao khi giá trị thập phân của các ngõ vào ABC = 1₁₀, 4₁₀, 5₁₀.

## Giải chi tiết

### Bước 1: Xác định bảng chân lý

1. Đầu tiên cần chuyển đổi các giá trị thập phân sang nhị phân:
   - 1₁₀ = 001₂
   - 4₁₀ = 100₂
   - 5₁₀ = 101₂

2. Lập bảng chân lý đầy đủ:

| A | B | C | Giá trị thập phân | Y |
|---|---|---|------------------|---|
| 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 1 | 1 |
| 0 | 1 | 0 | 2 | 0 |
| 0 | 1 | 1 | 3 | 0 |
| 1 | 0 | 0 | 4 | 1 |
| 1 | 0 | 1 | 5 | 1 |
| 1 | 1 | 0 | 6 | 0 |
| 1 | 1 | 1 | 7 | 0 |

### Bước 2: Xác định biểu thức boolean

Sử dụng phương pháp tổng các minterm (Sum of Minterms):

1. Xác định các minterm:
   - Minterm m₁ = A'B'C  (cho 1₁₀)
   - Minterm m₄ = AB'C'  (cho 4₁₀)
   - Minterm m₅ = AB'C   (cho 5₁₀)

2. Viết biểu thức boolean:
   Y = m₁ + m₄ + m₅
   Y = A'B'C + AB'C' + AB'C

### Bước 3: Tối giản biểu thức

1. Nhóm các số hạng có AB':
   - AB'C' + AB'C = AB'(C' + C) = AB'

2. Biểu thức cuối cùng:
   Y = A'B'C + AB'

### Bước 4: Thiết kế mạch logic

Mạch logic được thiết kế với các thành phần:
- 2 cổng AND
- 1 cổng OR
- 1 cổng NOT (để đảo tín hiệu B)

## Giải thích chi tiết

### 1. Chức năng mạch
- Mạch nhận 3 tín hiệu đầu vào A, B, C
- Tạo ra tín hiệu đầu ra Y = 1 khi tổ hợp đầu vào là:
  * 001 (1₁₀)
  * 100 (4₁₀)
  * 101 (5₁₀)
- Các trường hợp khác cho Y = 0

### 2. Cấu trúc mạch
- Sử dụng 2 cổng AND để thực hiện phép AND giữa các tín hiệu
- 1 cổng OR để kết hợp kết quả từ hai cổng AND
- 1 cổng NOT để đảo tín hiệu B
- Các cổng được kết nối để thực hiện biểu thức Y = A'B'C + AB'

### 3. Hoạt động của mạch
1. Xét trường hợp Y = 1:
   - Khi A'B'C = 1:
     * A = 0 (A' = 1)
     * B = 0 (B' = 1)
     * C = 1
     * Ngõ ra cổng AND thứ nhất = 1
   
   - Khi AB' = 1:
     * A = 1
     * B = 0 (B' = 1)
     * Ngõ ra cổng AND thứ hai = 1

2. Cổng OR cuối cùng:
   - Cho Y = 1 nếu một trong hai cổng AND có ngõ ra = 1
   - Cho Y = 0 nếu cả hai cổng AND có ngõ ra = 0

## Kết luận
Mạch logic được thiết kế đảm bảo:
1. Đáp ứng đúng yêu cầu đề bài
2. Sử dụng số lượng cổng tối thiểu nhờ tối giản biểu thức
3. Hoạt động ổn định và chính xác cho tất cả các tổ hợp đầu vào
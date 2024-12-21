# Thiết Kế Mạch Tổ Hợp 4 Ngõ Vào

## Đề bài
Thiết kế mạch tổ hợp bốn ngõ vào (ABCD) và một ngõ ra Y. Ngõ ra chỉ ở mức cao khi có đồng thời ba ngõ vào ở mức cao hoặc 4 ngõ vào ở mức thấp.

## Phân tích yêu cầu

### Thông số mạch:
- **Ngõ vào:** 4 tín hiệu (A, B, C, D)
- **Ngõ ra:** 1 tín hiệu (Y)
- **Điều kiện Y = 1:**
  * Trường hợp 1: Có chính xác 3 ngõ vào mức cao (1) và 1 ngõ vào mức thấp (0)
  * Trường hợp 2: Tất cả 4 ngõ vào đều ở mức thấp (0)

## Giải chi tiết

### 1. Bảng chân lý

| A | B | C | D | Số bit 1 | Y |
|---|---|---|---|----------|---|
| 0 | 0 | 0 | 0 | 0 | 1 |
| 0 | 0 | 0 | 1 | 1 | 0 |
| 0 | 0 | 1 | 0 | 1 | 0 |
| 0 | 0 | 1 | 1 | 2 | 0 |
| 0 | 1 | 0 | 0 | 1 | 0 |
| 0 | 1 | 0 | 1 | 2 | 0 |
| 0 | 1 | 1 | 0 | 2 | 0 |
| 0 | 1 | 1 | 1 | 3 | 1 |
| 1 | 0 | 0 | 0 | 1 | 0 |
| 1 | 0 | 0 | 1 | 2 | 0 |
| 1 | 0 | 1 | 0 | 2 | 0 |
| 1 | 0 | 1 | 1 | 3 | 1 |
| 1 | 1 | 0 | 0 | 2 | 0 |
| 1 | 1 | 0 | 1 | 3 | 1 |
| 1 | 1 | 1 | 0 | 3 | 1 |
| 1 | 1 | 1 | 1 | 4 | 0 |

### 2. Biểu thức Boolean

#### Xác định các minterm:
- m₀ = A'B'C'D' (tất cả bằng 0)
- m₇ = A'BCD (3 bit 1)
- m₁₁ = AB'CD (3 bit 1)
- m₁₃ = ABC'D (3 bit 1)
- m₁₄ = ABCD' (3 bit 1)

#### Biểu thức tổng các minterm:
Y = m₀ + m₇ + m₁₁ + m₁₃ + m₁₄
Y = A'B'C'D' + A'BCD + AB'CD + ABC'D + ABCD'

### 3. Thiết kế mạch

Mạch bao gồm các thành phần:
1. **Các cổng NOT:**
   - Để đảo tín hiệu A, B, C, D khi cần

2. **Các cổng AND:**
   - Cổng AND 4 ngõ vào cho m₀
   - Các cổng AND 4 ngõ vào cho các tổ hợp 3 bit 1

3. **Cổng OR:**
   - Để tổng hợp kết quả từ các cổng AND

## Giải thích hoạt động

### 1. Trường hợp tất cả ngõ vào = 0
- A = B = C = D = 0
- Các tín hiệu đảo A', B', C', D' = 1
- Ngõ ra cổng AND đầu tiên = 1
- Y = 1

### 2. Trường hợp có 3 ngõ vào = 1
Ví dụ khi A = 0, B = C = D = 1:
- Tín hiệu A' = 1
- B = C = D = 1
- Ngõ ra của cổng AND tương ứng = 1
- Y = 1

### 3. Các trường hợp khác
- Khi có 1, 2 hoặc 4 ngõ vào = 1
- Không có tổ hợp nào thỏa mãn
- Y = 0

## Chú ý khi thiết kế

### 1. Tối ưu hóa mạch
- Có thể sử dụng phương pháp Karnaugh để tối giản biểu thức
- Tận dụng các tín hiệu đảo đã có
- Gộp các cổng logic khi có thể

### 2. Các điểm cần lưu ý
1. **Số lượng cổng:**
   - Cần nhiều cổng AND và NOT
   - Một cổng OR lớn hoặc nhiều cổng OR nhỏ
   
2. **Độ trễ tín hiệu:**
   - Xem xét độ trễ qua các cổng
   - Đảm bảo tín hiệu đồng bộ

3. **Kiểm tra:**
   - Thử nghiệm tất cả các trường hợp
   - Đặc biệt chú ý các trường hợp chuyển trạng thái

## Kết luận
1. Mạch được thiết kế đáp ứng đầy đủ yêu cầu đề bài
2. Hoạt động ổn định và chính xác cho mọi tổ hợp đầu vào
3. Có thể được sử dụng trong các ứng dụng thực tế cần phát hiện số lượng tín hiệu cao/thấp
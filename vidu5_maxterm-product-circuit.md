# Thiết Kế Mạch Logic: Tích Các Maxterm

## Đề bài
Thiết kế mạch cho hàm:
Y = ∏(ABC)(2,5)

## Phân tích đề bài

### Thông tin cơ bản
- Hàm dạng tích các maxterm: Y = ∏M(2,5)
- Số biến đầu vào: 3 (A, B, C)
- Các maxterm cần xét: M₂ và M₅

### Ý nghĩa
- Đây là dạng POM (Product of Maxterms)
- Y = 0 tại các hàng có chỉ số 2 và 5 trong bảng chân lý
- Y = 1 tại các hàng còn lại

## Giải chi tiết

### 1. Bảng chân lý

| A | B | C | Số thứ tự | Y |
|---|---|---|-----------|---|
| 0 | 0 | 0 | 0 | 1 |
| 0 | 0 | 1 | 1 | 1 |
| 0 | 1 | 0 | 2 | **0** |
| 0 | 1 | 1 | 3 | 1 |
| 1 | 0 | 0 | 4 | 1 |
| 1 | 0 | 1 | 5 | **0** |
| 1 | 1 | 0 | 6 | 1 |
| 1 | 1 | 1 | 7 | 1 |

### 2. Xác định các maxterm

#### Maxterm M₂ (i = 2)
- Tổ hợp biến: A = 0, B = 1, C = 0
- Biểu thức: M₂ = (A + B' + C)

#### Maxterm M₅ (i = 5)
- Tổ hợp biến: A = 1, B = 0, C = 1
- Biểu thức: M₅ = (A' + B + C')

#### Biểu thức cuối cùng
Y = M₂ · M₅ = (A + B' + C)(A' + B + C')

### 3. Thiết kế mạch

#### Các thành phần chính
1. **Cổng NOT:**
   - Để đảo tín hiệu B và C cho M₂
   - Để đảo tín hiệu A và C cho M₅

2. **Cổng OR:**
   - OR-1 cho M₂: tổng hợp (A + B' + C)
   - OR-2 cho M₅: tổng hợp (A' + B + C')

3. **Cổng AND:**
   - Để nhân hai maxterm lại với nhau

## Giải thích hoạt động

### 1. Maxterm M₂
- **Đầu vào:**
  * A trực tiếp
  * B qua NOT
  * C trực tiếp
- **Xử lý:**
  * Thực hiện OR ba tín hiệu
  * Cho kết quả = 0 khi A=0, B=1, C=0

### 2. Maxterm M₅
- **Đầu vào:**
  * A qua NOT
  * B trực tiếp
  * C qua NOT
- **Xử lý:**
  * Thực hiện OR ba tín hiệu
  * Cho kết quả = 0 khi A=1, B=0, C=1

### 3. Ngõ ra Y
- **Xử lý:**
  * AND hai kết quả từ M₂ và M₅
  * Y = 0 khi một trong hai maxterm bằng 0
  * Y = 1 trong các trường hợp còn lại

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
- Đặc biệt chú ý các trường hợp Y = 0
- Xác nhận chuyển trạng thái đúng

### 2. Đo đạc thực tế
- Độ trễ tín hiệu qua mạch
- Mức điện áp đầu ra
- Độ nhiễu và nhiễu xuyên âm

## Kết luận
1. Mạch được thiết kế theo đúng yêu cầu của hàm POM
2. Hoạt động chính xác theo bảng chân lý đã cho
3. Cấu trúc đơn giản, dễ hiểu và dễ thực hiện
4. Có thể tối ưu thêm tùy theo yêu cầu thực tế
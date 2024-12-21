# Thiết Kế Mạch Tổ Hợp 3 Ngõ Vào

## Đề bài
Thiết kế mạch tổ hợp ba ngõ vào (CBA) và một ngõ ra Y. Ngõ ra chỉ ở mức cao khi có ít nhất hai ngõ vào ở mức cao.

## Phân tích yêu cầu

### Thông số mạch
- **Ngõ vào:** 3 tín hiệu (C, B, A)
- **Ngõ ra:** 1 tín hiệu (Y)
- **Điều kiện:** Y = 1 khi có ≥ 2 ngõ vào ở mức cao

## Giải chi tiết

### 1. Bảng chân lý

| C | B | A | Số bit 1 | Y |
|---|---|---|----------|---|
| 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 1 | 0 |
| 0 | 1 | 0 | 1 | 0 |
| 0 | 1 | 1 | 2 | 1 |
| 1 | 0 | 0 | 1 | 0 |
| 1 | 0 | 1 | 2 | 1 |
| 1 | 1 | 0 | 2 | 1 |
| 1 | 1 | 1 | 3 | 1 |

### 2. Xác định biểu thức Boolean

#### Xác định các minterm (các hàng có Y = 1):
- m₃ = C'BA (có 2 bit 1)
- m₅ = CB'A (có 2 bit 1)
- m₆ = CBA' (có 2 bit 1)
- m₇ = CBA (có 3 bit 1)

#### Biểu thức tổng các minterm:
Y = m₃ + m₅ + m₆ + m₇  
Y = C'BA + CB'A + CBA' + CBA

### 3. Thiết kế mạch

#### Thành phần mạch
1. **Cổng NOT:**
   - Để đảo tín hiệu C, B, A khi cần

2. **Cổng AND:**
   - 4 cổng AND 3 ngõ vào cho các minterm

3. **Cổng OR:**
   - 1 cổng OR để tổng hợp kết quả

## Giải thích hoạt động

### 1. Trường hợp có 2 bit 1
Ví dụ: C = 0, B = 1, A = 1
- Tín hiệu C' = 1
- B = A = 1
- Ngõ ra cổng AND thứ nhất = 1
- Y = 1

### 2. Trường hợp có 3 bit 1
C = B = A = 1
- Tất cả tín hiệu đầu vào = 1
- Ngõ ra cổng AND cuối = 1
- Y = 1

### 3. Các trường hợp khác
- Khi có 0 hoặc 1 bit 1
- Không có tổ hợp nào thỏa mãn
- Y = 0

## Tối ưu hóa thiết kế

### 1. Tối ưu mức cổng logic
- **Giảm số cổng:**
  * Kết hợp các cổng cùng loại
  * Tái sử dụng tín hiệu đã đảo

- **Giảm độ trễ:**
  * Sắp xếp cổng logic hợp lý
  * Tối thiểu hóa đường đi tín hiệu

### 2. Tối ưu tín hiệu
- **Xử lý đồng bộ:**
  * Đảm bảo tín hiệu đến cùng lúc
  * Tránh hiện tượng trễ tín hiệu

- **Chống nhiễu:**
  * Thiết kế đường tín hiệu hợp lý
  * Thêm các mạch lọc nhiễu nếu cần

## Các điểm cần lưu ý

### 1. Kiểm tra mạch
1. **Kiểm tra các trường hợp:**
   - Tất cả tổ hợp đầu vào
   - Các trường hợp chuyển trạng thái
   - Các trường hợp đặc biệt

2. **Đo đạc và hiệu chỉnh:**
   - Độ trễ tín hiệu
   - Mức điện áp đầu ra
   - Độ nhiễu

### 2. Ứng dụng thực tế
1. **Các ứng dụng:**
   - Hệ thống điều khiển
   - Mạch phát hiện sự kiện
   - Mạch so sánh số lượng

2. **Yêu cầu thực tế:**
   - Độ ổn định cao
   - Thời gian đáp ứng nhanh
   - Chi phí hợp lý

## Kết luận
1. Mạch được thiết kế đáp ứng đầy đủ yêu cầu đề bài
2. Hoạt động ổn định và chính xác cho mọi tổ hợp đầu vào
3. Có thể tối ưu thêm tùy theo yêu cầu cụ thể
4. Phù hợp cho các ứng dụng cần phát hiện số lượng tín hiệu cao
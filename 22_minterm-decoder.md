# Thiết Kế Mạch Logic Sử Dụng Decoder

## I. Phân Tích Hàm Logic

### 1. Hàm Boolean Ban Đầu
```
F = ΣXYZ(0,2,3,5)
F = X̄ȲZ̄ + X̄YZ̄ + X̄YZ + XȲZ
```

### 2. Cấu Trúc Minterm
```
Minterm 0: X̄ȲZ̄ (000)
Minterm 2: X̄YZ̄ (010)
Minterm 3: X̄YZ  (011)
Minterm 5: XȲZ  (101)
```

## II. Thiết Kế Sử Dụng Decoder

### 1. IC Sử Dụng
```
1. 74LS138: Decoder 3-to-8
   - Đầu vào: X, Y, Z
   - Đầu ra: Y0-Y7 (active low)

2. 74LS20: NAND 4 đầu vào
   - Sử dụng làm OR gate
   - Kết hợp các minterm
```

### 2. Kết Nối
```
Decoder 74LS138:
- A = Z (LSB)
- B = Y
- C = X (MSB)
- G1 = 1 (enable)
- G2A = G2B = 0 (enable)

NAND 74LS20:
- Đầu vào: Y0, Y2, Y3, Y5
- Đầu ra: F
```

## III. Hoạt Động Mạch

### 1. Giải Mã Địa Chỉ
```
Input    | Active Output
---------|---------------
000      | Y0 = 0
010      | Y2 = 0
011      | Y3 = 0
101      | Y5 = 0
Khác     | Tất cả = 1
```

### 2. Tạo Hàm Logic
```
1. Decoder tạo các minterm:
   - Y0 = X̄ȲZ̄
   - Y2 = X̄YZ̄
   - Y3 = X̄YZ
   - Y5 = XȲZ

2. NAND gate kết hợp:
   F = Y0 + Y2 + Y3 + Y5
```

## IV. Ưu Điểm Thiết Kế

### 1. Hiệu Quả
```
- Giảm số lượng cổng logic
- Đơn giản hóa thiết kế
- Dễ mở rộng và sửa đổi
```

### 2. Thực Tế
```
- Sử dụng IC tiêu chuẩn
- Chi phí thấp
- Độ tin cậy cao
```

## V. Lưu Ý Khi Thiết Kế

### 1. Timing
```
- Độ trễ qua decoder
- Độ trễ qua NAND
- Tổng độ trễ mạch
```

### 2. Điện
```
- Fan-out của decoder
- Điện áp logic
- Công suất tiêu thụ
```

---
*Lưu ý: Phương pháp này đặc biệt hiệu quả cho các hàm có nhiều minterm.*
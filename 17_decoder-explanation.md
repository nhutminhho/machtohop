# Mạch Giải Mã (Decoder)

## I. Định Nghĩa và Đặc Điểm

### 1. Định Nghĩa
- Mạch giải mã (decoder) là mạch logic chuyển đổi từ N-bit đầu vào thành 2ᴺ đường ngõ ra
- Chỉ có một đầu ra ở mức tích cực (thường là 1) tại một thời điểm
- Mỗi tổ hợp đầu vào kích hoạt một và chỉ một đầu ra

### 2. Đặc Điểm Chính
```
Đầu vào: N bit (A₀, A₁, ..., Aₙ₋₁)
Đầu ra: M = 2ᴺ đường (O₀, O₁, ..., O₂ᴺ₋₁)
Quan hệ: M = 2ᴺ
```

## II. Nguyên Lý Hoạt Động

### 1. Quy Tắc Cơ Bản
```
- Mỗi tổ hợp N bit đầu vào là một số nhị phân
- Số này chọn một trong M đường ra
- Đầu ra được chọn ở mức 1, các đầu ra khác ở mức 0
```

### 2. Ví Dụ: Decoder 2-to-4
```
Đầu vào: A₁A₀ | Đầu ra: O₀O₁O₂O₃
00         1000
01         0100
10         0010
11         0001
```

## III. Các Loại Decoder Phổ Biến

### 1. Decoder 2-to-4
```
- 2 đầu vào: A₁, A₀
- 4 đầu ra: O₀, O₁, O₂, O₃
- Thường dùng IC 74LS139
```

### 2. Decoder 3-to-8
```
- 3 đầu vào: A₂, A₁, A₀
- 8 đầu ra: O₀ đến O₇
- Thường dùng IC 74LS138
```

### 3. Decoder 4-to-16
```
- 4 đầu vào: A₃, A₂, A₁, A₀
- 16 đầu ra: O₀ đến O₁₅
- Thường dùng IC 74LS154
```

## IV. Ứng Dụng Thực Tế

### 1. Bộ Nhớ
```
- Chọn địa chỉ bộ nhớ
- Giải mã lệnh
- Định địa chỉ thiết bị
```

### 2. Điều Khiển Hiển Thị
```
- Điều khiển LED 7 đoạn
- Ma trận LED
- Màn hình LCD
```

### 3. Hệ Thống Số
```
- Bàn phím số
- Máy ATM
- Hệ thống bảo mật
```

## V. Thiết Kế Mạch

### 1. Sử Dụng Cổng Cơ Bản
```
- AND gates cho giải mã
- NOT gates cho đảo bit
- Enable input cho điều khiển
```

### 2. Tối Ưu Hóa
```
- Giảm độ trễ
- Tiết kiệm cổng logic
- Tăng độ tin cậy
```

## VI. Ví Dụ Thiết Kế: Decoder 2-to-4

### 1. Phương Trình Logic
```
O₀ = Ā₁·Ā₀
O₁ = Ā₁·A₀
O₂ = A₁·Ā₀
O₃ = A₁·A₀
```

### 2. Hiện Thực
```
- 2 cổng NOT cho Ā₁, Ā₀
- 4 cổng AND 2 đầu vào
- 1 enable input (tùy chọn)
```

---
*Lưu ý: Decoder là thành phần cơ bản trong nhiều hệ thống số, đặc biệt quan trọng trong việc giải mã địa chỉ và điều khiển.*
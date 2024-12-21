# Mở Rộng Mạch Giải Mã: 4-to-16 Decoder

## I. Nguyên Lý Mở Rộng

### 1. Cấu Trúc Cơ Bản
```
Sử dụng:
- 2 IC 74LS138 (3-to-8 decoder)
- 4 bit đầu vào: A0, A1, A2, A3
- 16 đầu ra: DEC0-DEC15
```

### 2. Phương Pháp Kết Nối
```
IC Trên (U1):
- Đầu vào: A0, A1, A2
- Enable: G1=1, G2A=G2B=0
- Đầu ra: DEC0-DEC7

IC Dưới (U2):
- Đầu vào: A0, A1, A2
- Enable: G1=A3, G2A=EN, G2B=0
- Đầu ra: DEC8-DEC15
```

## II. Chi Tiết Kết Nối

### 1. Đầu Vào Địa Chỉ
```
Chung cho cả hai IC:
- A0 → pin A
- A1 → pin B
- A2 → pin C

Bit chọn IC:
- A3: điều khiển enable của IC dưới
```

### 2. Điều Khiển Enable
```
IC Trên:
- G1 = 1 (VCC)
- G2A = Ā3
- G2B = 0 (GND)

IC Dưới:
- G1 = EN
- G2A = 0 (GND)
- G2B = 0 (GND)
```

## III. Hoạt Động

### 1. Chọn IC
```
A3 = 0:
- IC trên hoạt động (DEC0-DEC7)
- IC dưới bị vô hiệu hóa

A3 = 1:
- IC trên bị vô hiệu hóa
- IC dưới hoạt động (DEC8-DEC15)
```

### 2. Giải Mã Địa Chỉ
```
Ví dụ:
A3A2A1A0 = 0101:
- A3=0 → Chọn IC trên
- A2A1A0=101 → DEC5 active

A3A2A1A0 = 1011:
- A3=1 → Chọn IC dưới
- A2A1A0=011 → DEC11 active
```

## IV. Ứng Dụng Thực Tế

### 1. Hệ Thống Bộ Nhớ
```
- Giải mã địa chỉ ROM/RAM
- Chọn chip trong hệ thống lớn
- Điều khiển thiết bị ngoại vi
```

### 2. Hệ Thống Điều Khiển
```
- Điều khiển ma trận LED
- Hệ thống chọn kênh
- Bàn phím ma trận
```

## V. Lưu Ý Thiết Kế

### 1. Timing
```
- Độ trễ tích lũy qua các IC
- Setup time cho enable
- Hold time cho địa chỉ
```

### 2. Fan-out
```
- Kiểm tra tải đầu ra
- Đệm tín hiệu nếu cần
- Xử lý nhiễu
```

---
*Lưu ý: Có thể mở rộng thêm bằng cách ghép nhiều IC để tạo decoder 5-to-32 hoặc lớn hơn.*
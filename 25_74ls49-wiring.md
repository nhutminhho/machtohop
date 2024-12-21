# Sơ Đồ Kết Nối IC 74LS49 Với LED 7 Đoạn

## I. Cấu Trúc Chân IC 74LS49

### 1. Chân Đầu Vào
```
- A0 (pin 5): LSB của BCD
- A1 (pin 1): Bit 1 BCD
- A2 (pin 2): Bit 2 BCD
- A3 (pin 4): MSB của BCD
- BI (pin 3): Blanking Input, nối VCC
- VCC (pin 14): Nguồn dương
- GND (pin 7): Nối đất
```

### 2. Chân Đầu Ra (a-g)
```
- a (pin 11): Đoạn trên
- b (pin 10): Đoạn phải trên
- c (pin 9): Đoạn phải dưới
- d (pin 8): Đoạn dưới
- e (pin 6): Đoạn trái dưới
- f (pin 13): Đoạn trái trên
- g (pin 12): Đoạn giữa
```

## II. Kết Nối LED 7 Đoạn

### 1. LED 7 Đoạn Cathode Chung
```
Đoạn LED:
- a-g: Kết nối qua điện trở 270Ω
- C1, C2 (pin 3,8): Cathode chung nối GND
- Điện trở bảo vệ: R1 = 270Ω × 8 đoạn
```

### 2. Điện Trở Hạn Dòng
```
Tính toán:
- R = (VCC - VF) / IF
- VCC = 5V
- VF ≈ 2V (LED)
- IF ≈ 10-20mA
- R = (5-2)/0.02 = 270Ω
```

## III. Các Kết Nối Quan Trọng

### 1. Nguồn Cung Cấp
```
- VCC: +5V DC
- Nối pin 14 của IC với VCC
- Nối pin 7 của IC với GND
- Nối BI (pin 3) với VCC
```

### 2. Đầu Vào BCD
```
- 4 bit BCD: A3A2A1A0
- Nối với các công tắc/nguồn tín hiệu
- Mức logic TTL (0V/5V)
```

## IV. Lưu Ý Khi Lắp Đặt

### 1. Về Điện
```
- Kiểm tra nguồn 5V ổn định
- Điện trở đúng giá trị
- Nối đất đầy đủ
```

### 2. Về Kết Nối
```
- Đúng chân IC
- Đúng cực LED
- Không đoản mạch
```

### 3. Về Vận Hành
```
- Kiểm tra BI hoạt động
- Test từng số BCD
- Độ sáng đồng đều
```

## V. Kiểm Tra Hoạt Động

### 1. Test Cơ Bản
```
- Nhập BCD 0000 → hiển thị số 0
- Nhập BCD 0001 → hiển thị số 1
- Kiểm tra độ sáng các đoạn
```

### 2. Test Đặc Biệt
```
- Test BI (tắt/mở)
- Test các số 0-9
- Kiểm tra nhiễu
```

---
*Lưu ý: Mạch này là cơ bản cho hiển thị số đơn, có thể mở rộng thành nhiều chữ số.*
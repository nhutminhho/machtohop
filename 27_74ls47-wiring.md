# Sơ Đồ Kết Nối IC 74LS47 Với LED 7 Đoạn Anode Chung

## I. Sơ Đồ Chân IC 74LS47

### 1. Các Chân Đầu Vào
```
Đầu vào BCD:
- A0: Pin 7 (LSB)
- A1: Pin 1
- A2: Pin 2
- A3: Pin 6 (MSB)

Chân Điều Khiển:
- LT (Lamp Test): Pin 3, nối VCC
- RBI (Ripple Blanking Input): Pin 5, nối VCC
- BI/RBO: Pin 4

Nguồn:
- VCC: Pin 16
- GND: Pin 8
```

### 2. Các Chân Đầu Ra (Tích cực mức thấp)
```
- a: Pin 13
- b: Pin 12
- c: Pin 11
- d: Pin 10
- e: Pin 9
- f: Pin 15
- g: Pin 14
```

## II. Kết Nối LED 7 Đoạn

### 1. LED Anode Chung
```
- VCC nối vào chân chung (C1, C2)
- Mỗi đoạn LED qua điện trở 270Ω
- Cathode của mỗi đoạn nối với đầu ra tương ứng của IC
```

### 2. Điện Trở Bảo Vệ
```
Thông số:
- R = 270Ω cho mỗi đoạn
- 8 điện trở giống nhau
- Công suất: 1/4W
```

## III. Các Kết Nối Quan Trọng

### 1. Nguồn Điện
```
- VCC +5V cho IC (Pin 16)
- VCC cho LED anode chung
- GND chung (Pin 8)
```

### 2. Tín Hiệu Điều Khiển
```
- LT = H (nối VCC): hoạt động bình thường
- RBI = H (nối VCC): hiển thị số 0
- BI/RBO có thể nối cho nhiều LED
```

## IV. Lưu Ý Khi Lắp Ráp

### 1. Kiểm Tra Trước
```
- Đúng chân IC
- Đúng cực LED
- Đúng giá trị điện trở
- Nguồn ổn định
```

### 2. Khi Vận Hành
```
- Kiểm tra hiển thị đủ sáng
- Test tất cả các số
- Kiểm tra chức năng điều khiển
```

### 3. Xử Lý Sự Cố
```
- LED không sáng: kiểm tra điện trở và kết nối
- Hiển thị sai: kiểm tra đầu vào BCD
- Độ sáng không đều: kiểm tra điện trở
```

## V. Mở Rộng Hệ Thống

### 1. Nhiều Chữ Số
```
- Nối BI/RBO giữa các IC
- Tín hiệu BCD riêng cho mỗi số
- Điều khiển độc lập
```

### 2. Chức Năng Đặc Biệt
```
- Tắt số 0 vô nghĩa
- Test tất cả đoạn
- Điều khiển độ sáng
```

---
*Lưu ý: Mạch này là cơ sở cho các ứng dụng hiển thị số phức tạp hơn.*
# Bộ Giải Mã LED 7 Đoạn

## I. Cấu Tạo LED 7 Đoạn

### 1. Cấu Trúc Cơ Bản
```
7 đoạn LED (a-g):
- Đoạn a: Trên cùng
- Đoạn b,c: Phải trên, dưới
- Đoạn d: Dưới cùng
- Đoạn e,f: Trái dưới, trên
- Đoạn g: Giữa
```

### 2. Hai Loại Cấu Hình
```
1. Cathode Chung:
   - Cathode các LED nối chung và nối GND
   - Điều khiển bằng logic 1 (HIGH)
   - Cần điện áp dương để sáng

2. Anode Chung:
   - Anode các LED nối chung và nối VCC
   - Điều khiển bằng logic 0 (LOW)
   - Cần điện áp âm để sáng
```

## II. Bộ Giải Mã BCD-to-7-Segment

### 1. Đặc Điểm
```
Đầu vào:
- 4 bit BCD (0-9)
- Giá trị từ 0000 đến 1001

Đầu ra:
- 7 tín hiệu điều khiển (a-g)
- Phù hợp với loại LED (anode/cathode chung)
```

### 2. IC Phổ Biến
```
1. 7447: Cho LED anode chung
   - Đầu ra active LOW
   - Có các chân điều khiển đặc biệt

2. 7448: Cho LED cathode chung
   - Đầu ra active HIGH
   - Tương thích TTL
```

## III. Bảng Mã Hiển Thị

### 1. Các Số Thập Phân
```
Số | a b c d e f g
-----------------
0  | 1 1 1 1 1 1 0
1  | 0 1 1 0 0 0 0
2  | 1 1 0 1 1 0 1
3  | 1 1 1 1 0 0 1
4  | 0 1 1 0 0 1 1
5  | 1 0 1 1 0 1 1
6  | 1 0 1 1 1 1 1
7  | 1 1 1 0 0 0 0
8  | 1 1 1 1 1 1 1
9  | 1 1 1 1 0 1 1
```

### 2. Các Ký Tự Đặc Biệt
```
Hex | a b c d e f g
A   | 1 1 1 0 1 1 1
b   | 0 0 1 1 1 1 1
C   | 1 0 0 1 1 1 0
d   | 0 1 1 1 1 0 1
E   | 1 0 0 1 1 1 1
F   | 1 0 0 0 1 1 1
```

## IV. Thiết Kế Mạch

### 1. Thành Phần Cần Thiết
```
- IC giải mã BCD-7seg
- LED 7 đoạn
- Điện trở hạn dòng
- Nguồn cung cấp
```

### 2. Tính Toán Điện Trở
```
R = (Vcc - Vf) / If
Trong đó:
- Vcc: Điện áp nguồn
- Vf: Điện áp thuận LED (~2V)
- If: Dòng định mức (~10-20mA)
```

## V. Ứng Dụng Thực Tế

### 1. Hiển Thị Số
```
- Đồng hồ số
- Máy tính
- Thiết bị đo
```

### 2. Hiển Thị Thông Tin
```
- Bảng điều khiển
- Thiết bị gia dụng
- Hệ thống điều khiển
```

---
*Lưu ý: Cần chọn đúng loại IC giải mã phù hợp với loại LED 7 đoạn (anode/cathode chung).*
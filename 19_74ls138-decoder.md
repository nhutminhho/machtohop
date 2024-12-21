# IC 74LS138: Giải Mã 3-to-8 với Ngõ Ra Mức Thấp

## I. Đặc Điểm IC 74LS138

### 1. Chân Tín Hiệu
```
Đầu Vào:
- A, B, C: Đầu vào địa chỉ (pins 1, 2, 3)
- G1: Enable (pin 6)
- G2A, G2B: Enable phủ định (pins 4, 5)

Đầu Ra:
- Y0-Y7: Đầu ra mức thấp (pins 15-7)
- VCC: Pin 16
- GND: Pin 8
```

### 2. Điều Kiện Hoạt Động
```
Enable:
- G1 = 1
- G2A = G2B = 0
Khi đó:
- Chỉ một đầu ra ở mức thấp (0)
- Các đầu ra khác ở mức cao (1)
```

## II. Nguyên Lý Hoạt Động

### 1. Bảng Enable
```
G2A | G2B | G1 | Output
-----|-----|----|---------
0    | 0   | 1  | Giải mã bình thường
1    | X   | X  | Tất cả đầu ra = 1
X    | 1   | X  | Tất cả đầu ra = 1
X    | X   | 0  | Tất cả đầu ra = 1
```

### 2. Ví Dụ Hoạt Động
```
Khi Enable hoạt động (G1=1, G2A=G2B=0):

CBA = 000: Y0 = 0, Y1-Y7 = 1
CBA = 100: Y4 = 0, Y0-Y3,Y5-Y7 = 1
```

## III. Ứng Dụng Thực Tế

### 1. Giải Mã Địa Chỉ
```
- Chọn chip trong hệ thống máy tính
- Giải mã địa chỉ bộ nhớ
- Điều khiển thiết bị ngoại vi
```

### 2. Điều Khiển
```
- Điều khiển LED ma trận
- Chọn kênh trong multiplexer
- Điều khiển thiết bị số
```

## IV. Lưu Ý Thiết Kế

### 1. Về Điện
```
- VCC = 5V ± 5%
- Mức logic TTL chuẩn
- Fan-out: 10 TTL loads
```

### 2. Về Timing
```
- Propagation delay: ~20ns
- Setup time cho enable: ~20ns
- Hold time: ~5ns
```

## V. Ví Dụ Kết Nối

### 1. Kết Nối Cơ Bản
```
1. VCC và GND
2. Đầu vào địa chỉ A, B, C
3. Enable G1 = 1, G2A = G2B = 0
4. Đầu ra Y0-Y7 đến thiết bị cần điều khiển
```

### 2. Cascading (Nối Tầng)
```
- Có thể nối nhiều IC 74LS138 để tạo decoder lớn hơn
- Sử dụng enable để chọn IC hoạt động
```

---
*Lưu ý: IC 74LS138 là một trong những decoder phổ biến nhất trong thiết kế số nhờ tính linh hoạt và độ tin cậy cao.*
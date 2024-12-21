# Phân Tích IC 74LS47 - BCD to 7-Segment Decoder

## I. Đặc Điểm Cơ Bản

### 1. Thông Số Chính
```
- Đầu vào: 4 bit BCD (A0-A3)
- Đầu ra: 7 đoạn (a-g)
- Ngõ ra tích cực mức thấp (L)
- Dùng cho LED anode chung
- 3 chân điều khiển đặc biệt (LT, RBI, BI/RBO)
```

### 2. Chân Điều Khiển Đặc Biệt
```
1. LT (Lamp Test):
   - L: Tất cả đèn sáng (test)
   - H: Hoạt động bình thường

2. RBI (Ripple Blanking Input):
   - L: Cho phép tắt số 0 đầu
   - H/X: Hoạt động bình thường

3. BI/RBO (Blanking Input/Ripple Blanking Output):
   - L: Tắt hiển thị
   - H: Hoạt động bình thường
```

## II. Bảng Chân Lý (Truth Table)

### 1. Hoạt Động Bình Thường (LT=H, RBI=X, BI/RBO=H)
```
BCD | Hiển Thị
----|----------
0000| Số 0
0001| Số 1
0010| Số 2
...  | ...
1001| Số 9
```

### 2. Các Chế Độ Đặc Biệt
```
1. Test Mode (LT=L):
   - Tất cả đoạn LED sáng
   - Không phụ thuộc đầu vào khác

2. Blanking Mode (BI=L):
   - Tất cả đoạn LED tắt
   - Dùng để tắt các số 0 vô nghĩa

3. Ripple Blanking:
   - Tự động tắt số 0 đầu tiên
   - Cần nối RBI và RBO đúng cách
```

## III. Ứng Dụng Thực Tế

### 1. Hiển Thị Đơn Lẻ
```
- Hiển thị số 0-9
- LED 7 đoạn anode chung
- Điện trở hạn dòng cho mỗi đoạn
```

### 2. Hiển Thị Nhiều Chữ Số
```
- Nối RBO với RBI chữ số kế tiếp
- Tự động tắt các số 0 vô nghĩa
- Tiết kiệm năng lượng
```

## IV. Lưu Ý Thiết Kế

### 1. Điện Áp và Dòng Điện
```
- VCC = 5V ± 5%
- IOL(min) = 8mA/đoạn
- Điện trở hạn dòng phù hợp
```

### 2. Kết Nối
```
1. Nguồn:
   - VCC nối pin 16
   - GND nối pin 8

2. Điều khiển:
   - LT thường nối H
   - RBI tùy ứng dụng
   - BI/RBO theo yêu cầu
```

## V. Tính Năng Đặc Biệt

### 1. Tự Động Tắt Số 0
```
Ví dụ: Hiển thị 0025
- Không tắt: "0025"
- Có tắt: "  25"
```

### 2. Kiểm Tra LED
```
- LT=L: Test tất cả đoạn
- Phát hiện LED hỏng
- Kiểm tra kết nối
```

---
*Lưu ý: IC 74LS47 phổ biến trong các ứng dụng hiển thị số với LED anode chung.*
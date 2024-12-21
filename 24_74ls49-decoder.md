# Phân Tích IC 74LS49: BCD to 7-Segment Decoder

## I. Đặc Điểm Cơ Bản

### 1. Thông Số Chung
```
- Đầu vào: 4 bit BCD (A3-A0)
- Đầu ra: 7 đoạn (a-g)
- Ngõ ra tích cực mức cao (H)
- Dùng cho LED cathode chung
- Có chân điều khiển Blanking Input (BI)
```

### 2. Chân Tín Hiệu
```
Đầu vào:
- A0: LSB
- A1, A2
- A3: MSB
- BI: Blanking Input

Đầu ra:
- a-g: điều khiển 7 đoạn LED
```

## II. Phân Tích Bảng Hàm

### 1. Hoạt Động Cơ Bản
```
Khi BI = H (bình thường):
- Giải mã BCD sang 7 đoạn
- Đầu ra H làm LED sáng
- Đầu ra L làm LED tắt

Khi BI = L (chế độ tắt):
- Tất cả đầu ra = L
- Tất cả LED tắt
```

### 2. Các Số Đặc Biệt
```
Số 0: abcdef   (0000)
Số 1: bc       (0001)
Số 2: abdeg    (0010)
Số 3: abcdg    (0011)
Số 4: bcfg     (0100)
Số 5: acdfg    (0101)
```

## III. Đặc Điểm Quan Trọng

### 1. Blanking Input (BI)
```
BI = H (bình thường):
- IC hoạt động bình thường
- Hiển thị theo giá trị BCD

BI = L (tắt):
- Tất cả đầu ra = L
- Tắt hiển thị
- Không phụ thuộc đầu vào
```

### 2. Giới Hạn Đầu Vào
```
- Chỉ giải mã 0-9
- Các giá trị 10-15 có mã riêng
- X = không quan trọng
```

## IV. Ứng Dụng Thực Tế

### 1. Thiết Kế Cơ Bản
```
1. Cấp nguồn:
   - VCC = 5V
   - GND

2. Điện trở hạn dòng:
   - R = (5V - 2V) / 20mA
   - R ≈ 150Ω cho mỗi LED
```

### 2. Mạch Ứng Dụng
```
- Hiển thị số
- Đồng hồ số
- Bộ đếm
- Thiết bị đo
```

## V. Lưu Ý Thiết Kế

### 1. Về Điện
```
- Logic TTL tiêu chuẩn
- Fan-out giới hạn
- Cần điện trở hạn dòng
```

### 2. Về Hoạt Động
```
- Kiểm tra BI trước khi dùng
- Xác nhận mức logic
- Đảm bảo tương thích LED
```

---
*Lưu ý: IC 74LS49 được thiết kế đặc biệt cho LED 7 đoạn cathode chung, với ngõ ra tích cực mức cao.*
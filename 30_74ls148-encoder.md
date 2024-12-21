# IC 74LS148: Mã Hóa Ưu Tiên Octal-to-Binary

## I. Cấu Trúc Chân IC

### 1. Đầu Vào
```
- 8 đầu vào D0-D7 (active-low): Pin 10-13, 1-4
- EI (Enable Input): Pin 5
- VCC: Pin 16
- GND: Pin 8
```

### 2. Đầu Ra
```
- 3 bit mã hóa Q0-Q2 (active-low): Pin 9, 7, 6
- GS (Group Select): Pin 14
- EO (Enable Output): Pin 15
```

## II. Đặc Điểm Chính

### 1. Hoạt Động Cơ Bản
```
- Mã hóa 8 đầu vào thành 3 bit nhị phân
- Tất cả tín hiệu đều active-low
- Có chức năng ưu tiên (D7 cao nhất, D0 thấp nhất)
```

### 2. Tín Hiệu Đặc Biệt
```
1. GS (Group Select):
   - GS = 0: Khi có ít nhất 1 đầu vào active
   - GS = 1: Khi không có đầu vào nào active

2. EO (Enable Output):
   - EO = 0: Khi EI = 0 và không có đầu vào active
   - EO = 1: Trong các trường hợp khác
```

## III. Các Chế Độ Hoạt Động

### 1. Chế Độ Bình Thường
```
- EI = 0 (Enable)
- Một hoặc nhiều đầu vào active
- Mã hóa đầu vào ưu tiên cao nhất
```

### 2. Chế Độ Cascade
```
- Có thể nối tiếp nhiều IC
- Sử dụng EO và EI để nối
- Mở rộng số đầu vào
```

## IV. Ứng Dụng Thực Tế

### 1. Hệ Thống Ngắt
```
- Xử lý nhiều nguồn ngắt
- Ưu tiên ngắt quan trọng
- Phản hồi trạng thái qua GS, EO
```

### 2. Bàn Phím Ma Trận
```
- Quét nhiều phím
- Xử lý nhấn đồng thời
- Báo trạng thái qua GS
```

## V. Lưu Ý Khi Sử Dụng

### 1. Về Điện
```
- Pull-up cho đầu vào không dùng
- Bypass capacitors
- Chống nhiễu cho đầu vào
```

### 2. Về Logic
```
- Active-low cho tất cả tín hiệu
- Ưu tiên từ D7 xuống D0
- Kiểm tra GS và EO để xác định trạng thái
```

### 3. Kết Nối Cascade
```
1. Nối tiếp:
   - EO của IC này → EI của IC kế
   - GS để báo trạng thái nhóm

2. Ví dụ mở rộng:
   - 2 IC: 16 đầu vào
   - 3 IC: 24 đầu vào
```

---
*Lưu ý: IC 74LS148 thường được sử dụng trong các ứng dụng cần xử lý ưu tiên với nhiều đầu vào.*
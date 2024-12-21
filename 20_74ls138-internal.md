# Cấu Trúc Bên Trong IC 74LS138

## I. Tổng Quan Cấu Trúc

### 1. Các Khối Chính
```
1. Khối đầu vào địa chỉ:
   - A₂ (MSB)
   - A₁
   - A₀ (LSB)
   
2. Khối enable:
   - G₁ (active high)
   - G₂A, G₂B (active low)

3. Khối giải mã:
   - 8 cổng NAND 
   - Y₀ đến Y₇ (active low)
```

### 2. Luồng Tín Hiệu
```
1. Đầu vào → Inverters
2. Inverters → Mạng kết nối
3. Mạng kết nối → NAND gates
4. NAND gates → Đầu ra
```

## II. Chi Tiết Các Khối

### 1. Khối Đầu Vào Địa Chỉ
```
- Mỗi bit địa chỉ qua 2 inverter
- Tạo ra cả tín hiệu gốc và đảo
- Đảm bảo tải đồng đều
```

### 2. Khối Enable
```
- NAND gate 3 đầu vào
- Điều kiện hoạt động:
  * G₁ = 1
  * G₂A = G₂B = 0
```

### 3. Khối Giải Mã
```
- 8 cổng NAND 4 đầu vào
- Mỗi cổng nhận:
  * Tín hiệu từ enable
  * 3 tín hiệu từ mạng kết nối
```

## III. Nguyên Lý Hoạt Động

### 1. Quá Trình Giải Mã
```
1. Enable kiểm tra:
   - G₁·G₂A·G₂B = 1
   
2. Địa chỉ xử lý:
   - A₂A₁A₀ xác định đầu ra
   
3. Đầu ra kích hoạt:
   - Một trong Y₀-Y₇ = 0
   - Còn lại = 1
```

### 2. Ví Dụ Cụ Thể
```
Input: A₂A₁A₀ = 010
Enable: G₁=1, G₂A=G₂B=0

Kết quả:
- Y₂ = 0 (active)
- Y₀,Y₁,Y₃-Y₇ = 1 (inactive)
```

## IV. Đặc Điểm Thiết Kế

### 1. Ưu Điểm
```
- Thiết kế đối xứng
- Độ trễ tối thiểu
- Fan-out cân bằng
```

### 2. Xem Xét Timing
```
- Độ trễ qua inverter
- Độ trễ qua NAND
- Thời gian enable
```

## V. Ứng Dụng Thực Tế

### 1. Cấu Hình Cơ Bản
```
- Giải mã địa chỉ đơn giản
- Chọn thiết bị
- Điều khiển LED
```

### 2. Cấu Hình Mở Rộng
```
- Nối tầng nhiều IC
- Tạo decoder lớn hơn
- Hệ thống phức tạp
```

---
*Lưu ý: Hiểu rõ cấu trúc bên trong giúp tối ưu hóa việc sử dụng IC trong các ứng dụng thực tế.*
# Phân Tích Mạch NAND 4 Đầu Vào

## I. Phân Tích Bảng Sự Thật

### 1. Thông Tin Cơ Bản
- 4 đầu vào: X₁, X₀, Y₁, Y₀
- 1 đầu ra: Z
- IC sử dụng: 74LS08 (cổng NAND)

### 2. Các Trường Hợp Z = 1
```
X₁X₀Y₁Y₀ | Z
---------|---
0 0 0 0  | 1
0 1 0 1  | 1
1 0 1 0  | 1
1 1 1 1  | 1
```

## II. Phân Tích Mạch

### 1. Cấu Trúc Mạch
```
- 2 cổng NAND 2 đầu vào ở tầng đầu
- 1 cổng NAND 2 đầu vào ở tầng sau
```

### 2. Các Khối Chức Năng
```
NAND1: Xử lý X₁, X₀
NAND2: Xử lý Y₁, Y₀
NAND3: Tổng hợp kết quả
```

## III. Quy Luật Logic

### 1. Điều Kiện Kích Hoạt (Z = 1)
1. Khi tất cả đầu vào là 0 (0000)
2. Khi X₁=0, X₀=1, Y₁=0, Y₀=1 (0101)
3. Khi X₁=1, X₀=0, Y₁=1, Y₀=0 (1010)
4. Khi tất cả đầu vào là 1 (1111)

### 2. Quy Luật
```
Z = 1 khi:
- Các cặp bit đối xứng giống nhau (0000, 1111)
- Hoặc các cặp bit đối xứng đảo nhau (0101, 1010)
```

## IV. Ứng Dụng Thực Tế

### 1. So Sánh Số Nhị Phân
```
- X₁X₀: Số thứ nhất
- Y₁Y₀: Số thứ hai
Z = 1 khi:
- Hai số bằng nhau
- Hoặc hai số đối xứng
```

### 2. Kiểm Tra Tính Đối Xứng
```
Ứng dụng trong:
- Mã hóa dữ liệu
- Kiểm tra lỗi
- Truyền thông số
```

## V. Hiện Thực Bằng IC

### 1. Yêu Cầu Phần Cứng
```
- 1 IC 74LS08 (chứa 4 cổng NAND)
- Cần sử dụng 3 cổng NAND
```

### 2. Kết Nối
```
- Nối X₁, X₀ vào NAND1
- Nối Y₁, Y₀ vào NAND2
- Nối đầu ra NAND1, NAND2 vào NAND3
```

## VI. Testing

### 1. Kiểm Tra Các Trường Hợp Cơ Bản
```
- 0000 → 1
- 0101 → 1
- 1010 → 1
- 1111 → 1
Tất cả các trường hợp khác → 0
```

### 2. Lưu Ý
- Kiểm tra độ trễ của mạch
- Đảm bảo mức điện áp ổn định
- Xử lý nhiễu nếu cần

---
*Lưu ý: Mạch này thể hiện tính chất đối xứng trong xử lý dữ liệu số.*
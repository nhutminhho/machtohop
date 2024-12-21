# Mạch Mã Hóa (Encoder)

## I. Nguyên Lý Cơ Bản

### 1. Định Nghĩa
```
- Ngược với mạch giải mã (decoder)
- Chuyển N đầu vào thành M đầu ra mã hóa
- Chỉ một đầu vào được kích hoạt tại một thời điểm
- M = log₂N (số bit tối thiểu để mã hóa N đầu vào)
```

### 2. Đặc Điểm Quan Trọng
```
1. Đầu vào:
   - N đường tín hiệu
   - Chỉ một đầu vào active tại một thời điểm
   - Thường là active-high hoặc active-low

2. Đầu ra:
   - M bit mã nhị phân
   - M < N
   - Biểu diễn vị trí của đầu vào được kích hoạt
```

## II. Ví Dụ Thực Tế: Encoder 8-to-3

### 1. Cấu Trúc
```
Đầu vào:
- 8 đường (A0-A7)
- Chỉ một đường active

Đầu ra:
- 3 bit (O0-O2)
- Mã hóa vị trí đầu vào active
```

### 2. Bảng Chân Lý
```
Input (A7-A0) | Output (O2 O1 O0)
--------------|------------------
00000001      | 000
00000010      | 001
00000100      | 010
00001000      | 011
00010000      | 100
00100000      | 101
01000000      | 110
10000000      | 111
```

## III. Ứng Dụng Thực Tế

### 1. Bàn Phím
```
- Mã hóa phím nhấn
- Chuyển đổi vị trí phím thành mã số
- Giảm số dây kết nối
```

### 2. Cảm Biến Vị Trí
```
- Mã hóa vị trí cơ khí
- Xác định hướng chuyển động
- Điều khiển động cơ bước
```

### 3. Hệ Thống Điều Khiển
```
- Lựa chọn chế độ
- Xác định trạng thái
- Truyền thông tin
```

## IV. Các Loại Encoder

### 1. Priority Encoder
```
- Có ưu tiên
- Đầu vào có thể active đồng thời
- Chọn đầu vào ưu tiên cao nhất
```

### 2. Decimal-to-BCD Encoder
```
- 10 đầu vào (0-9)
- 4 bit BCD đầu ra
- Phổ biến trong thiết bị số
```

### 3. Gray Code Encoder
```
- Mã hóa theo mã Gray
- Chỉ thay đổi 1 bit giữa các mã liên tiếp
- Dùng trong cảm biến góc quay
```

## V. Lưu Ý Thiết Kế

### 1. Xử Lý Đồng Thời
```
- Xác định độ ưu tiên
- Xử lý conflict
- Đảm bảo tín hiệu stable
```

### 2. Nhiễu và Timing
```
- Lọc nhiễu đầu vào
- Đồng bộ tín hiệu
- Xử lý trễ
```

---
*Lưu ý: Encoder là thành phần quan trọng trong việc giảm số lượng bit cần xử lý trong hệ thống số.*
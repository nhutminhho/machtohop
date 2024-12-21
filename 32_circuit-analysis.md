# Phân Tích và Đơn Giản Hóa Mạch Logic

## I. Phân Tích Mạch Ban Đầu

### 1. Các Thành Phần
```
Đầu vào:
- 3 tín hiệu: M, N, O

Các cổng logic:
- 2 cổng NOT (đảo)
- 3 cổng NAND đầu tiên
- 1 cổng NAND cuối cùng

Đầu ra:
- Tín hiệu X
```

### 2. Cấu Trúc Mạch
```
Tầng 1:
- Cổng NOT cho M
- Cổng NOT cho O

Tầng 2:
- NAND1: Kết hợp M, N, O
- NAND2: Kết hợp N và Ō
- NAND3: Kết hợp O và M̄

Tầng 3:
- NAND cuối: Kết hợp 3 đầu ra NAND trước
```

## II. Quá Trình Đơn Giản Hóa

### 1. Viết Biểu Thức Logic
```
Gọi các đầu ra NAND trung gian là A, B, C:

A = (M.N.O)̄  (NAND trên cùng)
B = (N.Ō)̄    (NAND giữa)
C = (O.M̄)̄    (NAND dưới cùng)

Đầu ra: X = (A.B.C)̄
```

### 2. Áp Dụng Định Lý DeMorgan
```
A = M̄ + N̄ + Ō  (từ M.N.O)
B = N̄ + O      (từ N.Ō)
C = Ō + M      (từ O.M̄)
```

### 3. Phân Tích Điều Kiện
```
Để X = 1:
- Tất cả đầu vào của NAND cuối phải = 0
- Nghĩa là A = B = C = 0

Điều này có nghĩa:
- (M̄ + N̄ + Ō) = 0 → M = N = O = 1
- (N̄ + O) = 0    → N = 1, O = 0
- (Ō + M) = 0    → O = 1, M = 0
```

## III. Kết Quả Đơn Giản Hóa

### 1. Biểu Thức Cuối Cùng
```
X = MNO

Ý nghĩa:
- X = 1 chỉ khi M = N = O = 1
- X = 0 trong mọi trường hợp khác
```

### 2. Mạch Đơn Giản Hóa
```
Mạch mới chỉ cần:
- 1 cổng AND 3 đầu vào
- Các đầu vào trực tiếp M, N, O
```

## IV. Bảng Chân Lý

### 1. Bảng Chân Lý Đầy Đủ
```
M N O | X
------|---
0 0 0 | 0
0 0 1 | 0
0 1 0 | 0
0 1 1 | 0
1 0 0 | 0
1 0 1 | 0
1 1 0 | 0
1 1 1 | 1
```

### 2. Giải Thích
```
- Chỉ có 1 tổ hợp cho X = 1
- 7 tổ hợp còn lại cho X = 0
- Thể hiện rõ tính chất AND
```

## V. Ưu Điểm Của Mạch Đơn Giản Hóa

### 1. Về Cấu Trúc
```
- Ít cổng logic hơn
- Độ trễ thấp hơn
- Dễ hiện thực
```

### 2. Về Hiệu Năng
```
- Tiêu thụ công suất thấp hơn
- Độ tin cậy cao hơn
- Dễ bảo trì
```

---
*Lưu ý: Mạch gốc có thể được thiết kế phức tạp hơn vì lý do đặc biệt về timing hoặc fan-out.*
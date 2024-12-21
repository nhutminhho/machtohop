# Thiết Kế Mạch Logic Từ Bảng Sự Thật

## I. Phân Tích Bảng Sự Thật

### 1. Thông Tin Ban Đầu
```
Đầu vào: A, B, C (3 biến)
Đầu ra: Y
Y = 1 khi: 000, 010, 011, 100, 111
Y = 0 khi: 001, 101, 110
```

### 2. Xác Định Minterm
```
Y = Σm(0,2,3,4,7)
   = m₀ + m₂ + m₃ + m₄ + m₇
   = ĀB̄C̄ + ĀBC̄ + ĀBC + AB̄C̄ + ABC
```

## II. Quá Trình Tối Ưu Hóa

### 1. Phương Pháp Bản Đồ Karnaugh
```
     BC
A    00  01  11  10
0    1   0   1   1
1    1   0   1   0

Nhóm các ô có giá trị 1:
- Nhóm 1: ĀB (011, 010)
- Nhóm 2: B̄C̄ (000, 100)
- Nhóm 3: BC (111)
```

### 2. Biểu Thức Tối Giản
```
Y = ĀB + B̄C̄ + ABC

Giải thích:
- ĀB: A=0, B=1 (bất kể C)
- B̄C̄: B=0, C=0 (bất kể A)
- ABC: A=1, B=1, C=1
```

## III. Thiết Kế Mạch

### 1. Các Cổng Logic Cần Thiết
```
- Cổng NOT: cho A, B, C
- Cổng AND: 2 cổng 2 đầu vào, 1 cổng 3 đầu vào
- Cổng OR: 1 cổng 3 đầu vào
```

### 2. Kết Nối Mạch
```
Bước 1: Tạo tín hiệu phủ định
- Ā từ A qua NOT
- B̄ từ B qua NOT
- C̄ từ C qua NOT

Bước 2: Tạo các tích (AND)
- P1 = ĀB
- P2 = B̄C̄
- P3 = ABC

Bước 3: Tổng cuối cùng (OR)
Y = P1 + P2 + P3
```

## IV. Hiện Thực Mạch

### 1. Sử Dụng IC Chuẩn
```
IC NOT: 7404 (6 cổng)
IC AND: 7408 (4 cổng 2 đầu vào)
IC OR:  7432 (4 cổng 2 đầu vào)
```

### 2. Thứ Tự Kết Nối
```
1. Tạo các tín hiệu Ā, B̄, C̄
2. Tạo các tích AND
3. Kết hợp bằng OR
```

## V. Kiểm Tra Mạch

### 1. Bảng Kiểm Tra
```
Kiểm tra từng tổ hợp đầu vào:
- 000 → 1
- 001 → 0
- 010 → 1
...vv
```

### 2. Xử Lý Vấn Đề
```
- Kiểm tra glitch
- Đảm bảo timing
- Xử lý nhiễu
```

---
*Lưu ý: Mạch này có thể được tối ưu thêm tùy theo yêu cầu cụ thể về tốc độ, diện tích hoặc công suất.*
# Giải Bài Tập Thiết Kế Mạch Logic

## Câu 3: Mạch Logic 2 Ngõ Vào LOW

### 1. Phân Tích Yêu Cầu
```
Đầu vào: A, B, C
Đầu ra: Y = 1 khi có đúng 2 đầu vào = 0
```

### 2. Bảng Sự Thật
```
A B C | Y
------|---
0 0 0 | 0
0 0 1 | 1
0 1 0 | 1
0 1 1 | 0
1 0 0 | 1
1 0 1 | 0
1 1 0 | 0
1 1 1 | 0
```

### 3. Biểu Thức Logic
```
Y = ĀB̄C + ĀBC̄ + AB̄C̄
```

## Câu 4: So Sánh Số 4-bit

### 1. Phân Tích Yêu Cầu
```
Đầu vào: A3A2A1A0 (4-bit)
Điều kiện: 0010 < số < 1000
Tức là: 3 ≤ số ≤ 7
```

### 2. Bảng Sự Thật (Một Phần)
```
A3 A2 A1 A0 | Y
------------|---
0 0 1 1 | 1  (3)
0 1 0 0 | 1  (4)
0 1 0 1 | 1  (5)
0 1 1 0 | 1  (6)
0 1 1 1 | 1  (7)
```

### 3. Biểu Thức Logic
```
Y = Ā3(A2 + A1A0)
```

## Câu 5: Thực Thi Bằng NAND (Câu 3)

### 1. Chuyển Đổi Biểu Thức
```
Bước 1: Y = ĀB̄C + ĀBC̄ + AB̄C̄
Bước 2: Sử dụng NAND:
Y = ((ĀB̄C)' (ĀBC̄)' (AB̄C̄)')'
```

### 2. Cấu Trúc Mạch
```
1. Tạo phủ định bằng NAND
2. Tạo các tích bằng NAND-NAND
3. Kết hợp bằng NAND cuối cùng
```

## Câu 6: Thực Thi Bằng NAND (Câu 4)

### 1. Chuyển Đổi
```
Từ: Y = Ā3(A2 + A1A0)
Sang dạng NAND:
Y = ((A3)' ((A2)' (A1A0)')')'
```

### 2. Cấu Trúc Mạch NAND
```
1. NAND cho A3 (tạo Ā3)
2. NAND cho A1A0
3. NAND cho kết quả A2 + A1A0
4. NAND cuối cùng
```

## Phân Tích Chung

### 1. Ưu Điểm Dùng NAND
```
- NAND là cổng vạn năng
- Dễ tìm IC trên thị trường
- Chi phí thấp
- Độ tin cậy cao
```

### 2. Lưu Ý Thiết Kế
```
- Kiểm tra fan-out
- Tính toán độ trễ
- Xử lý nhiễu
- Tối ưu số cổng
```

## Kiểm Tra và Tối Ưu

### 1. Kiểm Tra Chức Năng
```
- Test từng khối mạch
- Kiểm tra tất cả cases
- Xác nhận timing
```

### 2. Tối Ưu Hóa
```
- Giảm số cổng
- Giảm độ trễ
- Tăng độ tin cậy
```

---
*Lưu ý: Các mạch này có thể được tối ưu thêm tùy theo yêu cầu cụ thể về tốc độ và diện tích.*
# Thiết Kế Mạch Logic Kiểm Tra Giá Trị Thập Phân

## I. Phân Tích Yêu Cầu

### 1. Đầu Vào
- 3 bit đầu vào: A, B, C
- Cần kiểm tra các giá trị: 1₁₀, 4₁₀, 5₁₀

### 2. Chuyển Đổi Số
```
1₁₀ = 001₂ = ABC = 0 0 1
4₁₀ = 100₂ = ABC = 1 0 0
5₁₀ = 101₂ = ABC = 1 0 1
```

## II. Lập Bảng Sự Thật

### 1. Bảng Đầy Đủ
```
Decimal | C B A | X | Minterm
--------|-------|---|--------
   0    | 0 0 0 | 0 |
   1    | 0 0 1 | 1 | ĀB̄C
   2    | 0 1 0 | 0 |
   3    | 0 1 1 | 0 |
   4    | 1 0 0 | 1 | AB̄C̄
   5    | 1 0 1 | 1 | AB̄C
   6    | 1 1 0 | 0 |
   7    | 1 1 1 | 0 |
```

## III. Xây Dựng Biểu Thức Boolean

### 1. Tổng Các Minterm
```
X = ĀB̄C + AB̄C̄ + AB̄C
```

### 2. Tối Ưu Hóa
```
X = ĀB̄C + AB̄(C̄ + C)
X = ĀB̄C + AB̄
X = B̄(ĀC + A)
```

## IV. Thiết Kế Mạch

### 1. Sử dụng X = B̄(ĀC + A)
Cần các cổng:
- 1 cổng AND cho ĀC
- 1 cổng OR cho (ĀC + A)
- 1 cổng AND cuối với B̄
- Các cổng NOT cho Ā và B̄

### 2. Sử Dụng IC 74LS Series
```
- 74LS04: Cổng NOT
- 74LS08: Cổng AND
- 74LS32: Cổng OR
```

## V. Ứng Dụng Thực Tế

### 1. Bộ So Sánh Số
```
Ví dụ: Hệ thống đếm sản phẩm
- Kích hoạt khi đạt số lượng 1, 4, hoặc 5
- Dùng trong dây chuyền sản xuất
```

### 2. Hệ Thống Điều Khiển
```
Ví dụ: Thang máy
- Dừng tại tầng 1, 4, hoặc 5
- Bỏ qua các tầng khác
```

## VI. Kiểm Tra Và Xác Minh

### 1. Test Cases
```
Đầu vào: 001 (1₁₀) → X = 1
Đầu vào: 100 (4₁₀) → X = 1
Đầu vào: 101 (5₁₀) → X = 1
Tất cả các giá trị khác → X = 0
```

### 2. Xác Minh Hoạt Động
- Kiểm tra từng cổng logic
- Đo độ trễ
- Test nhiễu và độ ổn định

---
*Lưu ý: Mạch này có thể được tối ưu thêm tùy theo yêu cầu cụ thể về tốc độ hoặc số lượng cổng.*
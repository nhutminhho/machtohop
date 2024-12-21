# Giải Bài Tập Mạch Logic: Ví Dụ 5 và 6

## Ví Dụ 5: Y = ∏(ABC)(2,5)

### 1. Phân Tích Yêu Cầu
- 3 ngõ vào: A, B, C
- Biểu diễn dưới dạng tích các maxterm
- Các maxterm: M₂, M₅

### 2. Chuyển Đổi Số
```
M₂ = 010₂: C + B̄ + A
M₅ = 101₂: C̄ + B + Ā
```

### 3. Bảng Sự Thật
```
A B C | Y | Giải thích
------|---|------------
0 0 0 | 1 | 
0 0 1 | 1 |
0 1 0 | 0 | M₂
0 1 1 | 1 |
1 0 0 | 1 |
1 0 1 | 0 | M₅
1 1 0 | 1 |
1 1 1 | 1 |
```

### 4. Biểu Thức Boolean
```
Y = (C + B̄ + A)(C̄ + B + Ā)
```

## Ví Dụ 6: Y = ∑(ABCD)(1,11,13)

### 1. Phân Tích Yêu Cầu
- 4 ngõ vào: A, B, C, D
- Biểu diễn dưới dạng tổng các minterm
- Các minterm: m₁, m₁₁, m₁₃

### 2. Chuyển Đổi Số
```
m₁  = 0001₂: ĀBCD
m₁₁ = 1011₂: ABC̄D
m₁₃ = 1101₂: ABCD̄
```

### 3. Bảng Sự Thật (Một Phần)
```
A B C D | Y | Minterm
---------|---|--------
0 0 0 0 | 0 |
0 0 0 1 | 1 | m₁
...     
1 0 1 1 | 1 | m₁₁
1 1 0 1 | 1 | m₁₃
...
```

### 4. Biểu Thức Boolean
```
Y = ĀBCD + ABC̄D + ABCD̄
```

## Thiết Kế Mạch

### Ví Dụ 5: Y = (C + B̄ + A)(C̄ + B + Ā)
```
Cần sử dụng:
- Cổng NOT: cho Ā, B̄, C̄
- Cổng OR: cho (C + B̄ + A) và (C̄ + B + Ā)
- Cổng AND: cho kết quả cuối
```

### Ví Dụ 6: Y = ĀBCD + ABC̄D + ABCD̄
```
Cần sử dụng:
- Cổng NOT: cho Ā, B̄, C̄, D̄
- Cổng AND 4 đầu vào: cho mỗi tích
- Cổng OR 3 đầu vào: cho tổng cuối cùng
```

## Ứng Dụng Thực Tế

### Ví Dụ 5: Hệ Thống Kiểm Soát
```
3 điều kiện (A, B, C):
- Nhiệt độ
- Áp suất
- Độ ẩm

Y = 0 chỉ khi:
- Áp suất cao, nhiệt độ thấp (M₂)
- Nhiệt độ cao, độ ẩm thấp (M₅)
```

### Ví Dụ 6: Hệ Thống Bảo Mật
```
4 điều kiện (A, B, C, D):
- Thẻ từ
- Mật khẩu
- Vân tay
- Khuôn mặt

Y = 1 trong các trường hợp:
- Chỉ có khuôn mặt (m₁)
- Thẻ từ + mật khẩu + khuôn mặt (m₁₁)
- Thẻ từ + mật khẩu + vân tay (m₁₃)
```

## Hiện Thực Bằng IC

### Ví Dụ 5:
```
- 74LS04: Cổng NOT
- 74LS32: Cổng OR
- 74LS08: Cổng AND
```

### Ví Dụ 6:
```
- 74LS04: Cổng NOT
- 74LS21: Cổng AND 4 đầu vào
- 74LS27: Cổng OR 3 đầu vào
```

---
*Lưu ý: Các biểu thức có thể được tối ưu thêm tùy theo yêu cầu cụ thể về phần cứng.*
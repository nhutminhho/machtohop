# Giải Bài Tập Mạch Tổ Hợp

## Ví Dụ 3: Mạch 4 Ngõ Vào

### 1. Phân Tích Yêu Cầu
- 4 ngõ vào: A, B, C, D
- Y = 1 khi:
  + Có 3 ngõ vào ở mức cao, HOẶC
  + Có 4 ngõ vào ở mức thấp

### 2. Bảng Sự Thật
```
Case 1: Có 3 ngõ vào cao (1)
1110 → Y = 1
1101 → Y = 1
1011 → Y = 1
0111 → Y = 1

Case 2: Có 4 ngõ vào thấp (0)
0000 → Y = 1

Tất cả trường hợp khác → Y = 0
```

### 3. Biểu Thức Boolean
```
Y = ABCD̄ + ABC̄D + AB̄CD + ĀB̄C̄D̄ + ĀBCD

Tối ưu:
Y = ABC(D + D̄) + AB(CD + C̄D) + ĀBCD + ĀB̄C̄D̄
Y = ABC + AB(CD + C̄D) + ĀBCD + ĀB̄C̄D̄
```

## Ví Dụ 4: Mạch 3 Ngõ Vào

### 1. Phân Tích Yêu Cầu
- 3 ngõ vào: C, B, A
- Y = 1 khi có ít nhất 2 ngõ vào mức cao

### 2. Bảng Sự Thật
```
C B A | Y | Giải thích
------|---|------------
0 0 0 | 0 | Không đủ 2 bit 1
0 0 1 | 0 | Chỉ có 1 bit 1
0 1 0 | 0 | Chỉ có 1 bit 1
0 1 1 | 1 | 2 bit 1
1 0 0 | 0 | Chỉ có 1 bit 1
1 0 1 | 1 | 2 bit 1
1 1 0 | 1 | 2 bit 1
1 1 1 | 1 | 3 bit 1
```

### 3. Biểu Thức Boolean
```
Y = CB + CA + BA

Tối ưu:
Y = AB + (A + B)C
```

### 4. So Sánh Hai Phương Án
```
Phương án 1: Y = CB + CA + BA
- 3 cổng AND
- 1 cổng OR 3 đầu vào

Phương án 2: Y = AB + (A + B)C
- 1 cổng OR
- 2 cổng AND
- 1 cổng OR 2 đầu vào
```

## Ứng Dụng Thực Tế

### Ví Dụ 3: Hệ Thống An Toàn
```
4 cảm biến độc lập:
- Báo động khi 3 cảm biến phát hiện nguy hiểm
- Hoặc khi tất cả cảm biến đều tắt (mất nguồn)
```

### Ví Dụ 4: Hệ Thống Biểu Quyết
```
3 thành viên hội đồng:
- Quyết định được thông qua khi có ít nhất 2 phiếu đồng ý
```

## Hiện Thực Mạch

### Ví Dụ 3: Sử dụng IC 74LS
```
- 74LS08: Cổng AND
- 74LS32: Cổng OR
- 74LS04: Cổng NOT
```

### Ví Dụ 4: Sử dụng IC 74LS
```
- 74LS08: Cổng AND (2 input)
- 74LS32: Cổng OR (2 input)
```

---
*Lưu ý: Các biểu thức có thể được tối ưu thêm tùy theo yêu cầu cụ thể về phần cứng.*
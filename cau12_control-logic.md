# Thiết kế mạch logic điều khiển có điều kiện

## 1. Phân tích yêu cầu

### 1.1 Các tín hiệu vào/ra
- Tín hiệu dữ liệu: A
- Tín hiệu điều khiển 1: B
- Tín hiệu điều khiển 2: C
- Tín hiệu ra: X

### 1.2 Điều kiện hoạt động
1. X = A khi B = C (B và C giống nhau)
2. X = 1 (HIGH) khi B ≠ C (B và C khác nhau)

## 2. Xây dựng bảng truth table

| A | B | C | X | Ghi chú |
|---|---|---|---|---------|
| 0 | 0 | 0 | 0 | B=C, X=A |
| 0 | 1 | 1 | 0 | B=C, X=A |
| 1 | 0 | 0 | 1 | B=C, X=A |
| 1 | 1 | 1 | 1 | B=C, X=A |
| 0 | 0 | 1 | 1 | B≠C, X=1 |
| 0 | 1 | 0 | 1 | B≠C, X=1 |
| 1 | 0 | 1 | 1 | B≠C, X=1 |
| 1 | 1 | 0 | 1 | B≠C, X=1 |

## 3. Phân tích và rút ra biểu thức logic

### 3.1 Phân tích điều kiện
1. Điều kiện B và C giống nhau:
   - (B·C) + (B̄·C̄)
2. Điều kiện B và C khác nhau:
   - (B·C̄) + (B̄·C)

### 3.2 Biểu thức logic
X = A·(B⊕C̄) + (B⊕C)

Trong đó:
- ⊕ là phép XOR
- · là phép AND
- + là phép OR

## 4. Thiết kế mạch logic

### 4.1 Các cổng logic cần thiết
1. 1 cổng NOT để phủ định C
2. 1 cổng XOR để so sánh B và C
3. 1 cổng AND để kết hợp với A
4. 1 cổng OR để tổng hợp kết quả cuối cùng

### 4.2 Sơ đồ mạch
```
     ┌─NOT─┐
C ───┤     ├───┐
     └─────┘   │
B ─────────────┼─XOR─┐
               │     │
A ─────────────┼─AND─┼─OR───► X
               │     │
B ─────────────┼─XOR─┘
C ─────────────┘
```

## 5. Tối ưu hóa

### 5.1 Phương án tối ưu
1. Sử dụng cổng XNOR thay vì XOR và NOT
2. Có thể sử dụng multiplexer 2-to-1
3. Áp dụng định lý De Morgan để giảm số cổng

### 5.2 Ưu điểm của mạch
1. Đáp ứng đầy đủ yêu cầu
2. Thời gian trễ chấp nhận được
3. Có thể mở rộng cho các ứng dụng khác

## 6. Kết luận

Mạch logic được thiết kế thành công với:
- Truyền tín hiệu A khi B và C giống nhau
- Duy trì mức HIGH khi B và C khác nhau
- Thiết kế tối ưu và hiệu quả
- Dễ dàng triển khai trên thực tế
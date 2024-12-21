# Thiết kế mạch logic có điều khiển

## 1. Phân tích yêu cầu

### 1.1 Các tín hiệu vào/ra
- Tín hiệu dữ liệu: A
- Tín hiệu điều khiển 1: B
- Tín hiệu điều khiển 2: C
- Tín hiệu ra: Y

### 1.2 Điều kiện hoạt động
1. Y = A khi:
   - B = 0 (LOW)
   - C = 1 (HIGH)
2. Y = 0 (LOW) cho tất cả các trường hợp còn lại

## 2. Xây dựng bảng truth table

| A | B | C | Y | Ghi chú |
|---|---|---|---|---------|
| 0 | 0 | 1 | 0 | Điều kiện đúng |
| 1 | 0 | 1 | 1 | Điều kiện đúng |
| 0 | 0 | 0 | 0 | C sai |
| 1 | 0 | 0 | 0 | C sai |
| 0 | 1 | 1 | 0 | B sai |
| 1 | 1 | 1 | 0 | B sai |
| 0 | 1 | 0 | 0 | B và C sai |
| 1 | 1 | 0 | 0 | B và C sai |

## 3. Phân tích và rút ra biểu thức logic

### 3.1 Điều kiện cho Y = 1
Y sẽ bằng 1 khi:
- A = 1 VÀ
- B = 0 VÀ
- C = 1

### 3.2 Biểu thức logic
Y = A·B̄·C

Trong đó:
- B̄ là phủ định của B
- Dấu · biểu thị phép AND

## 4. Thiết kế mạch logic

### 4.1 Các cổng logic cần thiết
1. 1 cổng NOT để phủ định B
2. 1 cổng AND 3 đầu vào để kết hợp A, B̄ và C

### 4.2 Sơ đồ mạch
```
     ┌─NOT─┐
B ───┤     ├───┐
     └─────┘   │
A ─────────────┼─AND───► Y
C ─────────────┘
```

## 5. Đánh giá và tối ưu hóa

### 5.1 Ưu điểm
1. Mạch đơn giản, ít cổng logic
2. Độ trễ thấp
3. Dễ triển khai

### 5.2 Phương án tối ưu
1. Có thể sử dụng cổng NAND thay thế (áp dụng định lý De Morgan)
2. Có thể kết hợp với các mạch khác để tạo hệ thống phức tạp hơn

## 6. Kết luận

Mạch logic được thiết kế đáp ứng đầy đủ yêu cầu:
- Truyền tín hiệu A ra Y khi B=0 và C=1
- Ngăn chặn tín hiệu trong các trường hợp khác
- Thiết kế đơn giản, hiệu quả
- Dễ dàng triển khai trên thực tế
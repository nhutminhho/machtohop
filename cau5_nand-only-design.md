# Thiết kế mạch dùng toàn bộ cổng NAND

## 1. Phân tích mạch ban đầu
### 1.1 Yêu cầu
- 3 ngõ vào: A, B, C
- Ngõ ra Y = HIGH khi có đúng 2 ngõ vào ở mức LOW
- Biểu thức: Y = A'B'C + A'BC' + AB'C'

### 1.2 Các cổng logic cần thay thế
1. Cổng NOT: 3 cái (cho A', B', C')
2. Cổng AND: 3 cái (cho mỗi tích)
3. Cổng OR: 1 cái (kết hợp các tích)

## 2. Chuyển đổi sang cổng NAND

### 2.1 Quy tắc chuyển đổi
1. **Cổng NOT**
   - Dùng 1 NAND với 2 đầu vào nối với nhau
   - NOT(A) = NAND(A,A)

2. **Cổng AND**
   - Dùng 1 NAND rồi đảo đầu ra bằng NAND khác
   - AND(A,B) = NAND(NAND(A,B), NAND(A,B))

3. **Cổng OR**
   - Áp dụng định lý De Morgan
   - OR(A,B) = NAND(A',B')
   - Đầu vào phải qua NOT trước

### 2.2 Số lượng cổng NAND cần dùng
1. Thay thế NOT:
   - 3 cổng NAND (cho A', B', C')

2. Thay thế AND:
   - 6 cổng NAND (mỗi AND cần 2 NAND)

3. Thay thế OR:
   - 2 cổng NAND (1 cho phép OR, 1 để đảo)

Tổng cộng: 11 cổng NAND

## 3. Sơ đồ kết nối

```
A ──┬────NAND(A,A)────┐
    │                 │
B ──┼────NAND(B,B)───┼────NAND───NAND───Y
    │                 │
C ──┴────NAND(C,C)───┘
```

## 4. Bảng sự thật giữ nguyên

| A | B | C | Y | Chú thích |
|---|---|---|---|------------|
| 0 | 0 | 0 | 0 | 3 ngõ LOW |
| 0 | 0 | 1 | 1 | 2 ngõ LOW |
| 0 | 1 | 0 | 1 | 2 ngõ LOW |
| 0 | 1 | 1 | 0 | 1 ngõ LOW |
| 1 | 0 | 0 | 1 | 2 ngõ LOW |
| 1 | 0 | 1 | 0 | 1 ngõ LOW |
| 1 | 1 | 0 | 0 | 1 ngõ LOW |
| 1 | 1 | 1 | 0 | 0 ngõ LOW |

## 5. Ưu điểm của việc dùng toàn NAND
1. Đơn giản hóa việc triển khai (chỉ cần 1 loại cổng)
2. Giảm chi phí sản xuất
3. Dễ dàng bảo trì và sửa chữa
4. NAND là cổng logic phổ biến, dễ tìm IC

## 6. Kết luận
- Mạch hoạt động tương đương mạch ban đầu
- Sử dụng 11 cổng NAND
- Dễ dàng triển khai trên thực tế
- Phù hợp cho sản xuất hàng loạt
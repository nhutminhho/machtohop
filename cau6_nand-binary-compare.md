# Thiết kế mạch so sánh số nhị phân dùng cổng NAND

## 1. Phân tích mạch ban đầu

### 1.1 Yêu cầu và thông số
- Đầu vào: 4 bit A3A2A1A0 (A0 là LSB)
- Đầu ra Y = 1 khi: 0010 < A3A2A1A0 < 1000
- Biểu thức: Y = A3'(A2'A1A0 + A2)

### 1.2 Các cổng cần thay thế
1. Cổng NOT: cho A3', A2'
2. Cổng AND: cho các tích
3. Cổng OR: cho phép cộng

## 2. Quy tắc chuyển đổi sang NAND

### 2.1 Các quy tắc cơ bản
1. **NOT → NAND**
   ```
   NOT(A) = NAND(A,A)
   ```

2. **AND → NAND+NAND**
   ```
   AND(A,B) = NAND(NAND(A,B), NAND(A,B))
   ```

3. **OR → NAND**
   ```
   OR(A,B) = NAND(NOT(A), NOT(B))
            = NAND(NAND(A,A), NAND(B,B))
   ```

### 2.2 Chuyển đổi biểu thức
Y = A3'(A2'A1A0 + A2)

Các bước chuyển đổi:
1. A3' = NAND(A3,A3)
2. A2' = NAND(A2,A2)
3. A2'A1A0 = NAND(NAND(NAND(A2,A2), A1), A0)
4. OR = NAND(input1', input2')
5. Kết quả cuối = NAND(NAND các kết quả trên)

## 3. Thiết kế mạch NAND

### 3.1 Số lượng cổng NAND cần dùng
1. Phần NOT:
   - 2 cổng (cho A3', A2')

2. Phần AND:
   - 4 cổng (cho tích A2'A1A0)
   - 2 cổng (cho phép AND cuối)

3. Phần OR:
   - 2 cổng (thực hiện OR)

Tổng cộng: 10 cổng NAND

### 3.2 Sơ đồ kết nối mạch NAND
```
A3 ──NAND(A3,A3)───┐
                   │
A2 ──NAND(A2,A2)──┼──NAND──NAND──Y
                   │
A1 ────────────────┤
                   │
A0 ────────────────┘
```

## 4. Bảng sự thật (không thay đổi)

| A3 | A2 | A1 | A0 | Số | Y |
|----|----|----|----|----|---|
| 0 | 0 | 1 | 1 | 3 | 1 |
| 0 | 1 | 0 | 0 | 4 | 1 |
| 0 | 1 | 0 | 1 | 5 | 1 |
| 0 | 1 | 1 | 0 | 6 | 1 |
| 0 | 1 | 1 | 1 | 7 | 1 |
| Khác | | | | | 0 |

## 5. Ưu điểm của thiết kế dùng NAND

1. **Đơn giản hóa sản xuất:**
   - Chỉ cần một loại cổng logic
   - Giảm chi phí sản xuất
   - Dễ dàng bảo trì

2. **Hiệu quả:**
   - NAND là cổng phổ biến nhất
   - Dễ dàng tìm IC thay thế
   - Tiêu thụ năng lượng đồng đều

3. **Độ tin cậy:**
   - Ít sai sót trong lắp ráp
   - Dễ dàng kiểm tra và sửa lỗi

## 6. Kết luận
- Mạch hoàn toàn tương đương với mạch gốc
- Sử dụng 10 cổng NAND
- Dễ dàng triển khai trên thực tế
- Phù hợp cho sản xuất hàng loạt
- Bảo trì và sửa chữa đơn giản
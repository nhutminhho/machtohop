# Thiết kế mạch nhân hai số nhị phân 2 bit

## 1. Phân tích yêu cầu
- Đầu vào: Hai số nhị phân 2 bit X₁X₀ và Y₁Y₀
- Đầu ra: Kết quả nhân Z₃Z₂Z₁Z₀
- Yêu cầu: Thiết kế mạch logic thực hiện phép nhân

## 2. Xây dựng bảng truth table

### 2.1 Phân tích phép nhân 2 bit
Khi nhân hai số 2 bit, kết quả có thể lên đến 4 bit:
- Số thứ nhất: X₁X₀ (giá trị từ 0 đến 3)
- Số thứ hai: Y₁Y₀ (giá trị từ 0 đến 3)
- Kết quả: Z₃Z₂Z₁Z₀ (giá trị từ 0 đến 9)

### 2.2 Bảng truth table đầy đủ

| X₁ | X₀ | Y₁ | Y₀ | Z₃ | Z₂ | Z₁ | Z₀ |
|----|----|----|----|----|----|----|----| 
| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 0 | 1 | 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 1 | 0 | 0 | 0 | 0 |
| 0 | 1 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 1 | 0 | 1 | 0 | 0 | 0 | 1 |
| 0 | 1 | 1 | 0 | 0 | 0 | 1 | 0 |
| 0 | 1 | 1 | 1 | 0 | 0 | 1 | 1 |
| 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 1 | 0 | 0 | 1 | 0 | 0 | 1 | 0 |
| 1 | 0 | 1 | 0 | 0 | 1 | 0 | 0 |
| 1 | 0 | 1 | 1 | 0 | 1 | 1 | 0 |
| 1 | 1 | 0 | 0 | 0 | 0 | 0 | 0 |
| 1 | 1 | 0 | 1 | 0 | 0 | 1 | 1 |
| 1 | 1 | 1 | 0 | 0 | 1 | 1 | 0 |
| 1 | 1 | 1 | 1 | 1 | 0 | 0 | 1 |

## 3. Rút ra các biểu thức logic

Từ bảng truth table, ta có thể rút ra các biểu thức logic cho từng bit đầu ra:

### Z₀ (LSB)
Z₀ = X₀·Y₀

### Z₁
Z₁ = X₀·Y₁ + X₁·Y₀

### Z₂
Z₂ = X₁·Y₁ + (X₀·Y₁·Y₀ + X₁·X₀·Y₁)

### Z₃ (MSB)
Z₃ = X₁·X₀·Y₁·Y₀

## 4. Thiết kế mạch logic

Dựa vào các biểu thức logic trên, mạch nhân 2 bit sẽ được thiết kế bằng cách sử dụng:
- Các cổng AND để thực hiện phép nhân bit
- Các cổng OR để cộng các tích trung gian
- Các cổng XOR để thực hiện phép cộng có nhớ

### Sơ đồ khối tổng quát:
1. Khối tạo tích từng bit (AND gates)
2. Khối cộng các tích trung gian (Half/Full Adders)
3. Khối tạo kết quả cuối cùng

## 5. Tối ưu hóa

Có thể tối ưu hóa mạch bằng cách:
1. Sử dụng các cổng NAND thay vì AND và OR
2. Giảm thiểu số lượng cổng logic bằng cách áp dụng định lý De Morgan
3. Sử dụng bản đồ Karnaugh để tối giản các biểu thức

## 6. Kết luận

Mạch nhân 2 bit được thiết kế thành công với:
- 4 đầu vào: X₁, X₀, Y₁, Y₀
- 4 đầu ra: Z₃, Z₂, Z₁, Z₀
- Các cổng logic cơ bản: AND, OR, XOR

Mạch này có thể được sử dụng như một khối cơ bản để xây dựng các mạch nhân có số bit lớn hơn.
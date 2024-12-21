# Kiến Thức Cơ Bản về Minterm và Maxterm

## Định Nghĩa Cơ Bản

### Minterm
- Là một "tích" (AND) chứa tất cả các biến trong dạng đúng hoặc phủ định
- F = 1 ở những hàng (tổ hợp giá trị biến) được liệt kê
- Ký hiệu: mᵢ, với i là chỉ số thập phân khi đọc (x,y,z) dưới dạng nhị phân

### Maxterm
- Là một "tổng" (OR) chứa tất cả các biến trong dạng đúng hoặc phủ định
- F = 0 ở những hàng được liệt kê
- Ký hiệu: Mᵢ, với i là chỉ số thập phân khi đọc (x,y,z)

### Dạng Chuẩn Tắc
- Dạng SOM (Sum of Minterms): F = ∑mᵢ
  - Là OR của các minterm tương ứng với hàng F = 1
- Dạng POM (Product of Maxterms): F = ∏Mⱼ
  - Là AND của các maxterm tương ứng với hàng F = 0

## Bài Tập Minh Họa

### Bài 1
Cho 2 biến x,y. Bảng sự thật của F₁:

| x | y | F₁ |
|---|---|-----|
| 0 | 0 | 0   |
| 0 | 1 | 1   |
| 1 | 0 | 1   |
| 1 | 1 | 1   |

#### Dạng SOM
1. Xác định các hàng F₁ = 1:
   - Hàng (0,1) → i = 1 → m₁ = x'y
   - Hàng (1,0) → i = 2 → m₂ = xy'
   - Hàng (1,1) → i = 3 → m₃ = xy
2. Kết quả: F₁ = m₁ + m₂ + m₃ = x'y + xy' + xy

#### Dạng POM
1. Xác định các hàng F₁ = 0: chỉ có (0,0) → i = 0
2. Maxterm: M₀ = (x + y)
3. Kết quả: F₁ = M₀ = (x + y)

### Bài 2
Cho 2 biến x,y. Bảng sự thật của F₂:

| x | y | F₂ |
|---|---|-----|
| 0 | 0 | 1   |
| 0 | 1 | 1   |
| 1 | 0 | 0   |
| 1 | 1 | 1   |

#### Dạng SOM
1. Xác định các hàng F₂ = 1:
   - (0,0) → i = 0 → m₀ = x'y'
   - (0,1) → i = 1 → m₁ = x'y
   - (1,1) → i = 3 → m₃ = xy
2. Kết quả: F₂ = m₀ + m₁ + m₃ = x'y' + x'y + xy

#### Dạng POM
1. Chỉ có hàng (1,0) cho F₂ = 0 → i = 2
2. Maxterm: M₂ = (x' + y)
3. Kết quả: F₂ = M₂ = (x' + y)

### Bài 3
Cho 3 biến x,y,z. Bảng sự thật của F₃:

| x | y | z | F₃ |
|---|---|---|-----|
| 0 | 0 | 0 | 0   |
| 0 | 0 | 1 | 1   |
| 0 | 1 | 0 | 0   |
| 0 | 1 | 1 | 1   |
| 1 | 0 | 0 | 1   |
| 1 | 0 | 1 | 1   |
| 1 | 1 | 0 | 1   |
| 1 | 1 | 1 | 0   |

#### Dạng SOM
1. Các hàng F₃ = 1:
   - i = 1 → m₁ = x'y'z
   - i = 3 → m₃ = x'yz
   - i = 4 → m₄ = xy'z'
   - i = 5 → m₅ = xy'z
   - i = 6 → m₆ = xyz'
2. Kết quả: F₃ = m₁ + m₃ + m₄ + m₅ + m₆ = x'y'z + x'yz + xy'z' + xy'z + xyz'

#### Dạng POM
1. Các hàng F₃ = 0:
   - i = 0 → M₀ = (x + y + z)
   - i = 2 → M₂ = (x + y' + z)
   - i = 7 → M₇ = (x' + y' + z')
2. Kết quả: F₃ = M₀·M₂·M₇ = (x + y + z)(x + y' + z)(x' + y' + z')

### Bài 4
Cho 3 biến a,b,c. Bảng sự thật của F₄:

| a | b | c | F₄ |
|---|---|---|-----|
| 0 | 0 | 0 | 1   |
| 0 | 0 | 1 | 0   |
| 0 | 1 | 0 | 1   |
| 0 | 1 | 1 | 0   |
| 1 | 0 | 0 | 0   |
| 1 | 0 | 1 | 0   |
| 1 | 1 | 0 | 1   |
| 1 | 1 | 1 | 1   |

#### Dạng SOM
1. Các hàng F₄ = 1:
   - i = 0 → m₀ = a'b'c'
   - i = 2 → m₂ = a'bc'
   - i = 6 → m₆ = abc'
   - i = 7 → m₇ = abc
2. Kết quả: F₄ = m₀ + m₂ + m₆ + m₇ = a'b'c' + a'bc' + abc' + abc

#### Dạng POM
1. Các hàng F₄ = 0:
   - i = 1 → M₁ = (a + b + c')
   - i = 3 → M₃ = (a + b' + c')
   - i = 4 → M₄ = (a' + b + c)
   - i = 5 → M₅ = (a' + b + c')
2. Kết quả: F₄ = M₁·M₃·M₄·M₅

### Bài 5
Cho 3 biến x,y,z. F₅ = 1 khi (x,y,z) ∈ {(0,0,1), (0,1,0), (1,0,1)}

#### Bảng Sự Thật Đầy Đủ

| x | y | z | F₅ |
|---|---|---|-----|
| 0 | 0 | 0 | 0   |
| 0 | 0 | 1 | 1   |
| 0 | 1 | 0 | 1   |
| 0 | 1 | 1 | 0   |
| 1 | 0 | 0 | 0   |
| 1 | 0 | 1 | 1   |
| 1 | 1 | 0 | 0   |
| 1 | 1 | 1 | 0   |

#### Dạng SOM
F₅ = m₁ + m₂ + m₅ = x'y'z + x'yz' + xy'z

#### Dạng POM
F₅ = M₀·M₃·M₄·M₆·M₇
- M₀ = (x + y + z)
- M₃ = (x + y' + z')
- M₄ = (x' + y + z)
- M₆ = (x' + y' + z)
- M₇ = (x' + y' + z')

## Tóm Tắt Các Điểm Quan Trọng

1. **Quy tắc xác định minterm/maxterm:**
   - Minterm mᵢ tương ứng với các hàng F = 1
   - Maxterm Mᵢ tương ứng với các hàng F = 0

2. **Ưu điểm của dạng chuẩn tắc:**
   - Biểu diễn chính xác và duy nhất cho mỗi hàm Boolean
   - Dễ dàng chuyển đổi giữa bảng chân lý và biểu thức đại số

3. **Ứng dụng thực tế:**
   - Phục vụ cho việc tối ưu hóa mạch logic
   - Làm cơ sở cho các phương pháp rút gọn (bản đồ Karnaugh, QuineMcCluskey)

4. **Lưu ý quan trọng:**
   - Dạng SOM và POM là dạng chuẩn tắc, có thể tiếp tục rút gọn
   - Cần cẩn thận trong việc xác định chỉ số i cho minterm và maxterm
   - Kiểm tra kỹ các giá trị 0,1 trong bảng sự thật
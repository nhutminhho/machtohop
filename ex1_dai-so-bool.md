# Các Tính Chất và Chứng Minh trong Đại Số Bool

## 1. Phép Giao Hoán
### Bài 1
Chứng minh: x + y = y + x

**Cách 1: Dùng bảng chân lý**

| x | y | x + y | y + x |
|---|---|-------|-------|
| 0 | 0 |   0   |   0   |
| 0 | 1 |   1   |   1   |
| 1 | 0 |   1   |   1   |
| 1 | 1 |   1   |   1   |

So sánh hai cột x + y và y + x, ta thấy chúng hoàn toàn giống nhau.

**Cách 2: Lập luận**
- x + y (OR) nghĩa là "x = 1 hoặc y = 1"
- y + x là "y = 1 hoặc x = 1"
- Hai diễn đạt này là một, nên chúng bằng nhau

### Bài 2
Chứng minh: x⋅y = y⋅x

**Bảng chân lý:**

| x | y | x⋅y | y⋅x |
|---|---|------|------|
| 0 | 0 |  0   |  0   |
| 0 | 1 |  0   |  0   |
| 1 | 0 |  0   |  0   |
| 1 | 1 |  1   |  1   |

**Lập luận:**
- x⋅y = 1 khi cả x = 1 và y = 1
- y⋅x = 1 khi cả y = 1 và x = 1
- Đều yêu cầu cả x lẫn y phải 1, nên hai biểu thức tương đương

## 2. Phép Kết Hợp
### Bài 3
Chứng minh: x + (y + z) = (x + y) + z

**Bảng chân lý:**

| x | y | z | y + z | x + (y + z) | x + y | (x + y) + z |
|---|---|---|-------|-------------|-------|-------------|
| 0 | 0 | 0 |   0   |     0       |   0   |     0       |
| 0 | 0 | 1 |   1   |     1       |   0   |     1       |
| 0 | 1 | 0 |   1   |     1       |   1   |     1       |
| 0 | 1 | 1 |   1   |     1       |   1   |     1       |
| 1 | 0 | 0 |   0   |     1       |   1   |     1       |
| 1 | 0 | 1 |   1   |     1       |   1   |     1       |
| 1 | 1 | 0 |   1   |     1       |   1   |     1       |
| 1 | 1 | 1 |   1   |     1       |   1   |     1       |

Quan sát cột x + (y + z) và (x + y) + z, hoàn toàn giống nhau ⇒ chúng bằng nhau.

### Bài 4
Chứng minh: x(yz) = (xy)z

**Bảng chân lý:**

| x | y | z | y⋅z | x⋅(y⋅z) | x⋅y | (x⋅y)⋅z |
|---|---|---|-----|----------|-----|----------|
| 0 | 0 | 0 |  0  |    0     |  0  |    0     |
| 0 | 0 | 1 |  0  |    0     |  0  |    0     |
| 0 | 1 | 0 |  0  |    0     |  0  |    0     |
| 0 | 1 | 1 |  1  |    0     |  0  |    0     |
| 1 | 0 | 0 |  0  |    0     |  0  |    0     |
| 1 | 0 | 1 |  0  |    0     |  0  |    0     |
| 1 | 1 | 0 |  0  |    0     |  1  |    0     |
| 1 | 1 | 1 |  1  |    1     |  1  |    1     |

## 3. Phép Phân Phối
### Bài 5
Chứng minh: x(y + z) = xy + xz

**Bảng chân lý:**

| x | y | z | y + z | x(y + z) | xy | xz | xy + xz |
|---|---|---|-------|----------|----|----|---------|
| 0 | 0 | 0 |   0   |    0     | 0  | 0  |    0    |
| 0 | 0 | 1 |   1   |    0     | 0  | 0  |    0    |
| 0 | 1 | 0 |   1   |    0     | 0  | 0  |    0    |
| 0 | 1 | 1 |   1   |    0     | 0  | 0  |    0    |
| 1 | 0 | 0 |   0   |    0     | 0  | 0  |    0    |
| 1 | 0 | 1 |   1   |    1     | 0  | 1  |    1    |
| 1 | 1 | 0 |   1   |    1     | 1  | 0  |    1    |
| 1 | 1 | 1 |   1   |    1     | 1  | 1  |    1    |

### Bài 6
Chứng minh: (w + x)(y + z) = wy + wz + xy + xz

Bảng chân lý (4 biến → 16 dòng). Ở đây chỉ minh họa cấu trúc:

| w | x | y | z | w + x | y + z | (w + x)(y + z) | wy | wz | xy | xz | wy + wz + xy + xz |
|---|---|---|---|-------|-------|----------------|----|----|----|----|-------------------|
| 0 | 0 | 0 | 0 |   0   |   0   |       0        | 0  | 0  | 0  | 0  |         0         |
| ... | ... | ... | ... | ... | ... | ... | ... | ... | ... | ... | ... |

## 4. Định Lý Đặc Biệt và Rút Gọn
### Bài 7
Chứng minh: x + xy = x

**Lập luận:**
- Nếu x = 0, thì x + xy = 0 + 0⋅y = 0, và biểu thức rút gọn cũng là x = 0
- Nếu x = 1, thì x + xy = 1 + 1⋅y = 1 + y = 1, và biểu thức rút gọn cũng là x = 1
- => Kết quả luôn bằng x

**Bảng chân lý:**

| x | y | xy | x + xy | Rút gọn |
|---|---|----|---------| --------|
| 0 | 0 | 0  |    0    |   x=0   |
| 0 | 1 | 0  |    0    |   x=0   |
| 1 | 0 | 0  |    1    |   x=1   |
| 1 | 1 | 1  |    1    |   x=1   |

### Bài 8
Chứng minh: x + x̄y = x + y

**Bảng chân lý:**

| x | y | x̄ | x̄y | x + x̄y | x + y |
|---|---|----|----|---------|-------|
| 0 | 0 | 1  | 0  |    0    |   0   |
| 0 | 1 | 1  | 1  |    1    |   1   |
| 1 | 0 | 0  | 0  |    1    |   1   |
| 1 | 1 | 0  | 0  |    1    |   1   |

### Bài 9
Chứng minh: (x + y)(x + ȳ) = x

**Khai triển đại số:**
1. (x + y)(x + ȳ) = x⋅x + x⋅ȳ + y⋅x + y⋅ȳ
2. = x + xȳ + xy + yȳ
3. Vì x⋅x = x và y⋅ȳ = 0:
4. = x + xȳ + xy + 0
5. = x + x(ȳ + y)
6. = x + x⋅1
7. = x + x = x

**Bảng chân lý:**

| x | y | ȳ | x + y | x + ȳ | (x + y)(x + ȳ) | x |
|---|---|---|-------|-------|----------------|---|
| 0 | 0 | 1 |   0   |   1   |       0        | 0 |
| 0 | 1 | 0 |   1   |   0   |       0        | 0 |
| 1 | 0 | 1 |   1   |   1   |       1        | 1 |
| 1 | 1 | 0 |   1   |   1   |       1        | 1 |

## 5. Bài Tập Tổng Hợp
### Bài 10
Biểu thức: (x + y)(x + z)

**a) Khai triển theo phép phân phối:**
(x + y)(x + z) = x⋅x + x⋅z + y⋅x + y⋅z = x + xz + xy + yz
(vì x⋅x = x)

**b) Rút gọn:**
Từ dạng x + xz + xy + yz:
1. Nhóm x + xz = x
2. Nhóm x + xy = x
3. Dạng rút gọn cuối cùng: x + yz

**c) Kiểm tra bằng bảng chân lý:**

| x | y | z | x + y | x + z | (x + y)(x + z) | Khai triển | Rút gọn |
|---|---|---|-------|-------|----------------|------------|----------|
| 0 | 0 | 0 |   0   |   0   |       0        |     0      |    0     |
| 0 | 0 | 1 |   0   |   1   |       0        |     0      |    0     |
| 0 | 1 | 0 |   1   |   0   |       0        |     0      |    0     |
| 0 | 1 | 1 |   1   |   1   |       1        |     1      |    1     |
| 1 | 0 | 0 |   1   |   1   |       1        |     1      |    1     |
| 1 | 0 | 1 |   1   |   1   |       1        |     1      |    1     |
| 1 | 1 | 0 |   1   |   1   |       1        |     1      |    1     |
| 1 | 1 | 1 |   1   |   1   |       1        |     1      |    1     |

## Tóm Tắt Các Tính Chất Quan Trọng

1. **Phép giao hoán:**
   - x + y = y + x
   - x⋅y = y⋅x

2. **Phép kết hợp:**
   - x + (y + z) = (x + y) + z
   - x(yz) = (xy)z

3. **Phép phân phối:**
   - x(y + z) = xy + xz
   - (w + x)(y + z) = wy + wz + xy + xz

4. **Các định lý đặc biệt:**
   - x + xy = x
   - x + x̄y = x + y
   - (x + y)(x + ȳ) = x
   - Tổng hợp: (x + y)(x + z) = x + yz

Các phép chứng minh có thể thực hiện qua bảng chân lý hoặc lập luận dùng các quy tắc OR (tổng logic), AND (tích logic), và các định lý đã biết. Kiểm chứng cuối cùng bằng bảng chân lý để đảm bảo biểu thức rút gọn tương đương với biểu thức ban đầu.
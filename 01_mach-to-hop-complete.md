# Mạch Tổ Hợp: Từ Lý Thuyết Đến Thực Tế

## I. Cơ Sở Lý Thuyết Và Ứng Dụng

### 1. Định Nghĩa
Mạch tổ hợp là mạch logic số mà các tín hiệu đầu ra tại một thời điểm chỉ phụ thuộc vào tổ hợp các tín hiệu đầu vào tại chính thời điểm đó.

#### Ví dụ thực tế: Máy Pha Cà Phê Tự Động
```
Đầu vào (Input):
- Chọn loại cà phê (X₁: Đen/Sữa)
- Chọn kích cỡ (X₂: Nhỏ/Vừa/Lớn)
- Chọn đường (X₃: Có/Không)

Đầu ra (Output):
- Bơm nước (Y₁)
- Xay cà phê (Y₂)
- Thêm sữa (Y₃)
- Thêm đường (Y₄)
```

### 2. Đặc Trưng Cơ Bản
- Không có phần tử nhớ
- Không có mạch phản hồi
- Phản ứng tức thời với đầu vào

#### Ví dụ thực tế: Khóa Cửa Điện Tử
```
Đầu vào:
- Mã PIN (X₁X₂X₃X₄)
- Cảm biến vân tay (X₅)
- Thẻ từ (X₆)

Đầu ra:
- Khóa mở (Y₁)
- Đèn báo (Y₂)
- Còi báo động (Y₃)
```

## II. Các Thành Phần Cơ Bản

### 1. Cổng Logic Cơ Bản
| Cổng | Ký Hiệu | Ứng Dụng Thực Tế |
|------|----------|------------------|
| AND  | AND Gate | Kiểm tra nhiều điều kiện cùng đúng |
| OR   | OR Gate  | Kiểm tra một trong các điều kiện đúng |
| NOT  | NOT Gate | Đảo trạng thái |
| NAND | NAND Gate| Phổ biến trong IC |
| NOR  | NOR Gate | Mạch điều khiển |
| XOR  | XOR Gate | Mạch so sánh |

### 2. Ví Dụ Ứng Dụng: Hệ Thống Điều Khiển Thang Máy
```
Điều kiện an toàn (AND Gate):
- Cửa đóng hoàn toàn
- Không quá tải
- Nút tầng được nhấn

Output: Thang máy chỉ hoạt động khi TẤT CẢ điều kiện đều đúng
```

## III. Ứng Dụng Trong Thực Tế

### 1. Thiết Bị Điện Tử Gia Dụng
#### a. Lò Vi Sóng
```
Đầu vào:
- Cài đặt thời gian (X₁)
- Cài đặt công suất (X₂)
- Cảm biến cửa (X₃)

Đầu ra:
- Động cơ quay đĩa (Y₁)
- Phát sóng (Y₂)
- Đèn bên trong (Y₃)
- Màn hình hiển thị (Y₄)
```

#### b. Máy Giặt Số
```
Đầu vào:
- Chọn chương trình giặt (X₁X₂)
- Nhiệt độ nước (X₃)
- Tốc độ vắt (X₄)

Đầu ra:
- Van cấp nước (Y₁)
- Bộ gia nhiệt (Y₂)
- Động cơ quay (Y₃)
- Bơm thoát nước (Y₄)
```

### 2. Hệ Thống An Ninh
#### Bảng Mã Hóa Trạng Thái
```
Trạng thái | Cửa | Chuyển động | Thời gian | Báo động
-------------------------------------------------------
Bình thường | Đóng |    Không   |   Ngày    |   Tắt
Cảnh báo    | Mở   |    Có      |   Đêm     |   Bật
Khẩn cấp    | Phá  |    Có      |     -     |   Bật
```

## IV. Phương Pháp Thiết Kế Thực Tế

### 1. Quy Trình Thiết Kế
1. Phân tích yêu cầu
2. Xác định input/output
3. Thiết kế logic
4. Tối ưu hóa
5. Kiểm thử

### 2. Ví Dụ: Thiết Kế Đèn Giao Thông
```
Input:
- Thời gian (T)
- Cảm biến xe (S)
- Chế độ khẩn cấp (E)

Output:
- Đèn đỏ (R)
- Đèn vàng (Y)
- Đèn xanh (G)

Bảng trạng thái:
T  S  E | R  Y  G
0  0  0 | 1  0  0  (Đèn đỏ)
0  1  0 | 0  0  1  (Đèn xanh)
1  x  0 | 0  1  0  (Đèn vàng)
x  x  1 | 1  1  0  (Khẩn cấp)
```

## V. Bài Tập Thực Hành

### 1. Thiết Kế Hệ Thống Đèn Thông Minh
```
Yêu cầu:
1. Tự động bật khi trời tối
2. Tự động tắt khi có ánh sáng
3. Có thể điều khiển bằng tay
4. Chế độ tiết kiệm điện

Thiết kế:
- Input: Cảm biến ánh sáng, công tắc tay, timer
- Output: Điều khiển đèn, đèn báo trạng thái
```

### 2. Mạch Điều Khiển Máy Lạnh
```
Điều kiện:
- Nhiệt độ > 25°C
- Có người trong phòng
- Không mở cửa sổ

Logic:
IF (Nhiệt độ > 25°C) AND (Có người) AND (Cửa đóng)
THEN Bật máy lạnh
ELSE Tắt máy lạnh
```

## VI. Lưu Ý Khi Thiết Kế

### 1. An Toàn
- Xử lý trường hợp lỗi
- Bảo vệ quá tải
- Chế độ khẩn cấp

### 2. Hiệu Quả
- Tối ưu năng lượng
- Giảm độ trễ
- Tăng độ tin cậy

### 3. Bảo Trì
- Thiết kế module
- Dễ thay thế
- Khả năng mở rộng

## VII. Tài Liệu Tham Khảo
1. Digital Design: Principles and Practices
2. Fundamentals of Digital Logic
3. Computer Organization and Design

---
*Lưu ý: Tài liệu này kết hợp lý thuyết và thực hành, phù hợp cho cả sinh viên và kỹ sư.*
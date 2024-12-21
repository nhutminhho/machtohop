# Thiết Kế Mạch Logic: Mạch Biểu Quyết 3 Đầu Vào

## I. Phân Tích Yêu Cầu

### 1. Đặc Tả Bài Toán
```
Đầu vào: 3 tín hiệu A, B, C
Đầu ra: X = 1 khi có ít nhất 2 đầu vào mức cao (1)
```

### 2. Tạo Bảng Sự Thật
```
A B C | X | Giải thích
------|---|------------
0 0 0 | 0 | Không đủ 2 đầu vào mức cao
0 0 1 | 0 | Chỉ có 1 đầu vào mức cao
0 1 0 | 0 | Chỉ có 1 đầu vào mức cao
0 1 1 | 1 | Có 2 đầu vào mức cao (B,C)
1 0 0 | 0 | Chỉ có 1 đầu vào mức cao
1 0 1 | 1 | Có 2 đầu vào mức cao (A,C)
1 1 0 | 1 | Có 2 đầu vào mức cao (A,B)
1 1 1 | 1 | Có 3 đầu vào mức cao
```

## II. Quá Trình Tối Ưu Hóa

### 1. Biểu Thức Ban Đầu (Tổng các minterm)
```
X = ĀBC + AB̄C + AB C̄ + ABC
```

### 2. Các Bước Tối Ưu
```
Bước 1: Nhóm các minterm
X = ĀBC + AB̄C + AB C̄ + ABC

Bước 2: Tìm các tích chung
X = BC(Ā + A) + AC(B̄ + B) + AB(C̄ + C)

Bước 3: Đơn giản hóa
X = BC + AC + AB
```

### 3. Biểu Thức Tối Ưu
```
Cách 1: X = BC + AC + AB
Cách 2: X = (B + A)C + AB
```

## III. Thiết Kế Mạch

### 1. Sử Dụng X = BC + AC + AB
```
Cần:
- 3 cổng AND 2 đầu vào (cho BC, AC, AB)
- 1 cổng OR 3 đầu vào (cộng kết quả)
```

### 2. Sử Dụng X = (B + A)C + AB
```
Cần:
- 1 cổng OR 2 đầu vào (cho B + A)
- 2 cổng AND 2 đầu vào
- 1 cổng OR 2 đầu vào (cho kết quả cuối)
```

## IV. Ứng Dụng Thực Tế

### 1. Hệ Thống Biểu Quyết
```
A, B, C: 3 thành viên hội đồng
X = 1: Quyết định được thông qua
```

### 2. Hệ Thống An Toàn
```
A: Cảm biến nhiệt
B: Cảm biến khói
C: Cảm biến áp suất
X = 1: Kích hoạt hệ thống báo động
```

## V. Lưu Ý Thiết Kế

### 1. Tối Ưu Hóa
- Chọn phương án ít cổng logic nhất
- Giảm thiểu độ trễ
- Tăng độ tin cậy

### 2. Kiểm Tra
- Kiểm tra tất cả tổ hợp đầu vào
- Xác nhận đúng yêu cầu đề bài
- Test các trường hợp biên

---
*Lưu ý: Cả hai biểu thức tối ưu đều đúng và có thể sử dụng tùy theo yêu cầu cụ thể của thiết kế.*
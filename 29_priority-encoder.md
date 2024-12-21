# Mạch Mã Hóa Ưu Tiên 8-3 (Priority Encoder)

## I. Nguyên Lý Hoạt Động

### 1. Đặc Điểm Cơ Bản
```
Đầu vào: 
- 8 đường (I7-I0)
- Ưu tiên từ cao đến thấp (I7 → I0)

Đầu ra:
- 3 bit mã nhị phân (A2, A1, A0)
- Mã hóa vị trí đầu vào cao nhất đang active
```

### 2. Quy Tắc Ưu Tiên
```
- I7 có độ ưu tiên cao nhất
- I0 có độ ưu tiên thấp nhất
- Chỉ mã hóa đầu vào ưu tiên cao nhất khi nhiều đầu vào cùng active
```

## II. Bảng Chân Lý Chi Tiết

### 1. Mã Hóa Cơ Bản
```
Input         | Output
I7 I6...I0   | A2 A1 A0
-------------|----------
0000 0001    | 000  (I0)
0000 0010    | 001  (I1)
0000 0100    | 010  (I2)
0000 1000    | 011  (I3)
0001 0000    | 100  (I4)
0010 0000    | 101  (I5)
0100 0000    | 110  (I6)
1000 0000    | 111  (I7)
```

### 2. Xử Lý Ưu Tiên
```
Ví dụ:
Input: I5=1, I3=1, I1=1
Output: 101 (mã của I5)
Lý do: I5 có độ ưu tiên cao hơn I3 và I1
```

## III. Ứng Dụng Thực Tế

### 1. Hệ Thống Ngắt
```
- Xử lý đa ngắt
- Ưu tiên ngắt quan trọng
- Điều phối tài nguyên
```

### 2. Bàn Phím Ma Trận
```
- Quét nhiều phím
- Xử lý nhấn đồng thời
- Ưu tiên phím chức năng
```

### 3. Hệ Thống Điều Khiển
```
- Xử lý tín hiệu cảm biến
- Phân cấp cảnh báo
- Điều khiển tự động
```

## IV. Đặc Điểm Thiết Kế

### 1. Ưu Điểm
```
- Xử lý nhiều đầu vào đồng thời
- Tự động phân cấp ưu tiên
- Đơn giản hóa mạch logic
```

### 2. Lưu Ý
```
- Độ trễ do xử lý ưu tiên
- Cần xử lý chống dội
- Đồng bộ tín hiệu
```

## V. Hiện Thực Mạch

### 1. Sử Dụng IC 74148
```
- IC encoder 8-3 chuẩn
- Đầu vào active-low
- Có chân enable và cascade
```

### 2. Kết Nối
```
- Pull-up cho đầu vào không sử dụng
- Điện trở chống nhiễu
- Bypass capacitors
```

---
*Lưu ý: X trong bảng chân lý nghĩa là "don't care" - có thể là 0 hoặc 1 không ảnh hưởng đến kết quả.*
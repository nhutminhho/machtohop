# Thiết kế mạch logic điều khiển công tắc

## 1. Phân tích yêu cầu
### 1.1 Đặc điểm công tắc:
- 4 công tắc SW1, SW2, SW3, SW4
- Trạng thái mặc định: mở (0)
- Đóng (1) khi có giấy đi qua
- SW1 và SW4 không thể cùng đóng

### 1.2 Yêu cầu mạch:
- Đầu ra X = 1 khi ≥ 2 công tắc đóng
- Loại bỏ các trường hợp SW1=SW4=1

## 2. Bảng sự thật

| SW1 | SW2 | SW3 | SW4 | X | Ghi chú |
|-----|-----|-----|-----|---|----------|
| 0 | 0 | 0 | 0 | 0 | Không SW nào đóng |
| 0 | 0 | 0 | 1 | 0 | 1 SW đóng |
| 0 | 0 | 1 | 0 | 0 | 1 SW đóng |
| 0 | 0 | 1 | 1 | 1 | 2 SW đóng |
| 0 | 1 | 0 | 0 | 0 | 1 SW đóng |
| 0 | 1 | 0 | 1 | 1 | 2 SW đóng |
| 0 | 1 | 1 | 0 | 1 | 2 SW đóng |
| 0 | 1 | 1 | 1 | 1 | 3 SW đóng |
| 1 | 0 | 0 | 0 | 0 | 1 SW đóng |
| 1 | 0 | 1 | 0 | 1 | 2 SW đóng |
| 1 | 1 | 0 | 0 | 1 | 2 SW đóng |
| 1 | 1 | 1 | 0 | 1 | 3 SW đóng |
| 1 | 0 | 0 | 1 | X | Không xảy ra |
| 1 | 0 | 1 | 1 | X | Không xảy ra |
| 1 | 1 | 0 | 1 | X | Không xảy ra |
| 1 | 1 | 1 | 1 | X | Không xảy ra |

## 3. Thiết kế mạch logic

### 3.1 Biểu thức logic:
X = SW2·SW3 + SW2·SW4 + SW3·SW4 + SW1·SW2 + SW1·SW3

### 3.2 Phân tích biểu thức:
- SW2·SW3: công tắc 2 và 3 đóng
- SW2·SW4: công tắc 2 và 4 đóng
- SW3·SW4: công tắc 3 và 4 đóng
- SW1·SW2: công tắc 1 và 2 đóng
- SW1·SW3: công tắc 1 và 3 đóng

### 3.3 Các cổng logic cần dùng:
1. Cổng AND (5 cái):
   - Cho từng tổ hợp 2 công tắc

2. Cổng OR (1 cái):
   - Kết hợp các tích

## 4. Kiểm tra và xác minh

### 4.1 Kiểm tra các trường hợp X = 1:
- Khi có 2 công tắc bất kỳ đóng (trừ SW1+SW4)
- Khi có 3 công tắc đóng (trừ trường hợp có SW1+SW4)

### 4.2 Kiểm tra các trường hợp X = 0:
- Khi không có công tắc nào đóng
- Khi chỉ có 1 công tắc đóng

## 5. Ưu điểm thiết kế
1. Đơn giản, dễ triển khai
2. Độ tin cậy cao
3. Dễ bảo trì và sửa chữa
4. Phù hợp cho ứng dụng máy copy

## 6. Kết luận
- Mạch hoạt động đúng theo yêu cầu
- Sử dụng 6 cổng logic (5 AND, 1 OR)
- An toàn với điều kiện SW1 và SW4 không đóng đồng thời
- Dễ dàng tích hợp vào hệ thống máy copy
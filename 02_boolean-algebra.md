# Các Định Lý Cơ Bản Của Đại Số Boolean

## I. Các Tiền Đề Cơ Bản

### 1. Phép Nhân Với 0 và 1
#### 1.1 x.0 = 0 (Quy tắc nhân với 0)
- **Ý nghĩa**: Khi một biến logic nhân với 0, kết quả luôn là 0
- **Ví dụ thực tế**: 
  + Trong mạch điện: Khi một công tắc ở trạng thái TẮT (0), dù đầu vào (x) là gì thì đèn vẫn không sáng
  + Trong hệ thống an ninh: Khi cảm biến hỏng (0), dù có chuyển động (x) cũng không báo động

#### 1.2 x.1 = x (Quy tắc nhân với 1)
- **Ý nghĩa**: Khi một biến logic nhân với 1, giá trị không thay đổi
- **Ví dụ thực tế**:
  + Trong mạch điện: Khi công tắc đang BẬT (1), đèn sẽ sáng theo đúng tín hiệu điều khiển
  + Trong hệ thống điều khiển: Khi hệ thống hoạt động bình thường (1), thiết bị phản ứng đúng theo tín hiệu

### 2. Phép Nhân và Bù
#### 2.1 x.x = x (Quy tắc tự nhân)
- **Ý nghĩa**: Một biến logic nhân với chính nó cho kết quả không đổi
- **Ví dụ thực tế**:
  + Bấm nút bật đèn hai lần liên tiếp không làm thay đổi trạng thái
  + Xác nhận mật khẩu hai lần giống nhau không thay đổi kết quả

#### 2.2 x.x̄ = 0 (Quy tắc phủ định)
- **Ý nghĩa**: Một biến logic nhân với phủ định của nó luôn cho kết quả 0
- **Ví dụ thực tế**:
  + Không thể vừa BẬT vừa TẮT công tắc cùng lúc
  + Cửa không thể vừa mở vừa đóng

### 3. Phép Cộng Với 0 và 1
#### 3.1 x + 0 = x (Quy tắc cộng với 0)
- **Ý nghĩa**: Cộng với 0 không làm thay đổi giá trị
- **Ví dụ thực tế**:
  + Thêm một công tắc hỏng (0) song song không ảnh hưởng đến hoạt động của mạch
  + Thêm một cảm biến tắt không ảnh hưởng đến hệ thống báo động

#### 3.2 x + 1 = 1 (Quy tắc cộng với 1)
- **Ý nghĩa**: Bất kỳ giá trị nào cộng với 1 đều cho kết quả 1
- **Ví dụ thực tế**:
  + Trong mạch song song, chỉ cần một công tắc BẬT, đèn sẽ sáng
  + Trong hệ thống báo động, chỉ cần một cảm biến phát hiện xâm nhập là kích hoạt

## II. Định Lý DeMorgan

### 1. Định Lý Thứ Nhất: x̄ + ȳ = (x.y)̄
- **Ý nghĩa**: Phủ định của tổng bằng tích các phủ định
- **Ví dụ thực tế**:
  + Hệ thống báo cháy: Không có khói VÀ không có nhiệt = KHÔNG (có khói HOẶC có nhiệt)
  + Hệ thống khóa: Không có vân tay đúng VÀ không có mật khẩu đúng = KHÔNG (có vân tay đúng HOẶC có mật khẩu đúng)

### 2. Định Lý Thứ Hai: (x.y)̄ = x̄ + ȳ
- **Ý nghĩa**: Phủ định của tích bằng tổng các phủ định
- **Ví dụ thực tế**:
  + Hệ thống an toàn: KHÔNG (cửa đóng VÀ khóa hoạt động) = cửa mở HOẶC khóa hỏng
  + Điều khiển thang máy: KHÔNG (nút bấm VÀ cửa đóng) = không bấm nút HOẶC cửa mở

## III. Ứng Dụng Trong Thực Tế

### 1. Hệ Thống An Ninh Thông Minh
```
Điều kiện báo động = Chuyển động VÀ (Ban đêm HOẶC Chế độ vắng nhà)
Công thức: Alarm = Motion AND (Night OR Away)
```

### 2. Điều Khiển Điều Hòa
```
Hoạt động = (Nhiệt độ cao HOẶC Độ ẩm cao) VÀ Có người VÀ KHÔNG(Cửa mở)
Công thức: AC = (HighTemp OR HighHumid) AND Present AND (NOT Door)
```

---
*Lưu ý: Các định lý này là nền tảng cho việc thiết kế mạch số và hệ thống điều khiển logic.*
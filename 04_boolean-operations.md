# Các Phép Giao Hoán, Kết Hợp và Phân Phối Trong Đại Số Boolean

## 1. Phép Giao Hoán (Commutative Laws)

### 1.1. Phép Cộng: x + y = y + x
- **Định nghĩa**: Thứ tự các số hạng không ảnh hưởng đến kết quả
- **Ví dụ thực tế**: 
  + Hai công tắc song song: Bật công tắc A rồi B = Bật công tắc B rồi A
  + Hệ thống báo động: Cảm biến cửa + cảm biến chuyển động = cảm biến chuyển động + cảm biến cửa

### 1.2. Phép Nhân: x.y = y.x
- **Định nghĩa**: Thứ tự các thừa số không ảnh hưởng đến kết quả
- **Ví dụ thực tế**:
  + Hai công tắc nối tiếp: Kiểm tra khóa A rồi B = Kiểm tra khóa B rồi A
  + Xác thực 2 lớp: (Mật khẩu AND vân tay) = (Vân tay AND mật khẩu)

## 2. Phép Kết Hợp (Associative Laws)

### 2.1. Phép Cộng: x + (y + z) = (x + y) + z = x + y + z
- **Định nghĩa**: Cách nhóm các số hạng không ảnh hưởng đến kết quả
- **Ví dụ thực tế**:
  ```
  Hệ thống báo cháy:
  (Khói + (Nhiệt + Khí gas)) = ((Khói + Nhiệt) + Khí gas)
  = Khói + Nhiệt + Khí gas
  ```

### 2.2. Phép Nhân: x(yz) = (xy)z = xyz
- **Định nghĩa**: Cách nhóm các thừa số không ảnh hưởng đến kết quả
- **Ví dụ thực tế**:
  ```
  Hệ thống an ninh ba lớp:
  Vân tay.(Mật khẩu.Thẻ từ) = (Vân tay.Mật khẩu).Thẻ từ
  ```

## 3. Phép Phân Phối (Distributive Laws)

### 3.1. Phân phối nhân qua cộng: x(y + z) = xy + xz
- **Định nghĩa**: Nhân một biểu thức với tổng bằng tổng các tích
- **Ví dụ thực tế**:
  ```
  Hệ thống điều khiển:
  Công tắc chính.(Đèn phòng khách + Đèn phòng ngủ) 
  = (Công tắc chính.Đèn phòng khách) + (Công tắc chính.Đèn phòng ngủ)
  ```

### 3.2. Phân phối phức tạp: (w + x)(y + z) = wy + xy + wz + xz
- **Ví dụ thực tế**:
  ```
  Hệ thống điều hòa:
  (Nhiệt độ cao + Độ ẩm cao)(Ban ngày + Có người) =
  (Nhiệt độ cao.Ban ngày) + (Nhiệt độ cao.Có người) +
  (Độ ẩm cao.Ban ngày) + (Độ ẩm cao.Có người)
  ```

## 4. Các Định Lý Đặc Biệt

### 4.1. x + xy = x
- **Ý nghĩa**: x OR (x AND y) = x
- **Ví dụ thực tế**:
  ```
  Đèn tự động = Cảm biến chuyển động + (Cảm biến chuyển động.Trời tối)
  = Cảm biến chuyển động
  ```

### 4.2. x + x̄y = x + y
- **Ví dụ thực tế**:
  ```
  Hệ thống báo động:
  (Cảm biến chuyển động) + (Không có chuyển động.Cửa mở)
  = (Cảm biến chuyển động) + (Cửa mở)
  ```

### 4.3. (x + y)(x + ȳ) = x
- **Ví dụ thực tế**:
  ```
  Xác thực người dùng:
  (Mật khẩu + Vân tay).(Mật khẩu + Không vân tay) = Mật khẩu
  ```

## 5. Bài Tập Thực Hành

### Ví dụ 1: Thiết kế hệ thống báo động
```
Điều kiện kích hoạt = 
(Cảm biến chuyển động + Cảm biến nhiệt).(Ban đêm + Chế độ vắng nhà)

Áp dụng phép phân phối:
= (Chuyển động.Ban đêm) + (Chuyển động.Vắng nhà) +
  (Nhiệt.Ban đêm) + (Nhiệt.Vắng nhà)
```

### Ví dụ 2: Điều khiển đèn thông minh
```
Điều kiện bật đèn =
(Trời tối + Chuyển động).(Không ngủ + Tiết kiệm điện)

Tối ưu hóa sử dụng các định lý:
= Trời tối.Không ngủ + Trời tối.Tiết kiệm +
  Chuyển động.Không ngủ + Chuyển động.Tiết kiệm
```

---
*Lưu ý: Các định lý này là nền tảng cho việc tối ưu hóa mạch logic và thiết kế hệ thống số.*
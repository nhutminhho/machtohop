# Phân tích mạch Boolean (Hình 5.11)

## 1. Phân tích mạch
- **Đầu vào:** 3 biến M, N, O
- **Đầu ra:** X
- **Các cổng logic:**
  - 2 cổng NOT (Inverter)
  - 3 cổng AND
  - 1 cổng OR

## 2. Tìm biểu thức logic
### Các nút trung gian:
- F1 = M.N.O (cổng AND đầu tiên)
- F2 = NOT(N) (cổng NOT đầu tiên)
- F3 = NOT(O) (cổng NOT thứ hai)
- F4 = M.F2.O (cổng AND thứ hai)
- F5 = M.N.F3 (cổng AND thứ ba)
- X = F1 + F4 + F5 (cổng OR cuối cùng)

## 3. Rút gọn biểu thức
1. X = M.N.O + M.N'.O + M.N.O'
2. = M.O.(N + N') + M.N.O'
3. = M.O + M.N.O'

## 4. Bảng chân trị

| M | N | O | X |
|---|---|---|---|
| 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 0 |
| 0 | 1 | 0 | 0 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 0 | 0 |
| 1 | 0 | 1 | 1 |
| 1 | 1 | 0 | 1 |
| 1 | 1 | 1 | 1 |

## 5. Nhận xét
1. Đầu ra X = 1 khi:
   - M = 1 và O = 1
   - HOẶC M = 1, N = 1 và O = 0

2. Mạch sẽ cho đầu ra 1 trong 3 trường hợp như thể hiện trên bảng chân trị

3. Đầu ra phụ thuộc nhiều nhất vào biến M (phải = 1 để có đầu ra)

## 6. Kết luận
Biểu thức tối giản cuối cùng: X = M.O + M.N.O'
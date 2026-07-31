## Data Handling

Các giai đoạn chính trong Data handling:
- Bước 1: Thu thập dữ liệu 
- Bước 2: Làm sạch dữ liệu (giá trị thiếu, nhóm dữ liệu, lọc)
- Bước 3: Biến đổi, chuẩn hóa dữ liệu 
- Bước 4: Lưu trữ

## 1. Numpy
```python
import numpy as np
```
### 1.1. Định nghĩa
Numpy là thư viện hỗ trợ tính toán các **mảng** nhiều chiều, kích thước lớn, tính toán đại số.
- Kiểu dữ liệu: số tự nhiên, boolean

### 1.2. Bảng chức thành phần
|tên|Chức năng|Ví dụ|
|---|---|---|
.array()|tạo mảng k chiều|np.array([1,7,6]) --> Mảng 1 chiều, không âm, số chiều = rank, shape = tuple (size,size)|
|.ones(), .zeros(),..|Khởi tạo một mảng có các giá trị giống nhau 0, 1,..|np.full((size,size), val)|
|.arrange()|Thay đổi phần tử|
|a[i,j] hoặc a[i:,:j]| Truy xuất giá trị theo vị trí Slicing|a[:2,1:3]|
|.add()|Tổng hai mảng|np.add(x,y) --> Cùng kích thước|
|.subtract()|Hiệu hai mảng|np.substract(x,y)|
|.multiply()|Nhân từng phần tử của mảng 1 với mảng 2|np.multiply(x,y)|
|.divide()|Thương từng phần tử x với từng phần tử y|np.divide(x,y)|
|.sqrt()|Bình phương từng phần tử trong mảng|np.sqrt(x)|
|.dot()|Ma trận x Ma trận / vector x Ma trận|np.dot(x,y) hoặc x.dot(y)|
|.T|Ma trận chuyển vị|v.T|
|Broadcasting|Tính toán giữa 2 mảng không cùng kích thước||

### 1.3. Mục đích
- Thực hiện phép tính đại số: liên quan đến ma trận (nhân, cộng, giá trị riêng, chuyển vị)
- Xử lý mảng nhiều chiều trong hình ảnh
- Tốc độ nhanh khi xử lý dãy số thực

## 2. Pandas
### 2.1. Định nghĩa
Pandas là thư viện hỗ trợ phân tích/xử lý dữ liệu bao gồm: làm sạch, lọc dữ liệu, xử lý dữ liệu thiếu. Có chức năng time-series (nhóm dữ liệu)
- Kiểu dữ liệu: file csv (NaN, Null, số tự nhiên, boolean, chuỗi ký tự)

```python
import pandas as pd
```

2 cấu trúc dữ liệu chính:
- Series: mảng 1 chiều giống Numpy (có thêm 1 cột đánh label) --> Giá trị đồng nhất
- DataFrame: mảng 2 chiều được dán label (giống SpreadSheet) --> Giá trị không đồng nhất (int, float, bool, str,..)

### 2.2. Ví dụ

|Tên hàm|Chức năng|Ví dụ|
|---|---|---|
|.Series()|Tạo một list/Dictionary|pd.Series(np.array()) --> 1 chiều|
|.DataFrame()|Tập hợp của nhiều Series|pd.DataFrame(List), tạo từ dictionary thì sẽ tạo các cột --> chèn list index={}|


### 2.3. Mục đích
- Làm việc với bảng dữ liệu csv, excel, SQL,...
- Nhóm dữ liệu, xử lý chuỗi thời gian,...
- Chuẩn hóa dữ liệu về dạng mong muốn.

## 3. Ứng dụng thực tế
- Pandas thường hay sử dụng Preprocessing để làm sạch dữ liệu hoặc phân tích dữ liệu cho doanh nghiệp.
- Numpy áp dụng các công thức toán học phức tạp, xử lý ảnh (chiều cao, chiều dộng, channels) --> Edit ảnh.
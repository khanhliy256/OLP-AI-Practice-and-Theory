## 1. Numpy
```python
import numpy as np
```
### 1.1. Định nghĩa
Numpy là thư viện hỗ trợ tính toán các mảng nhiều chiều, kích thước lớn, tính toán đại số.

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

## 2. Pandas
### 2.1. Định nghĩa
Pandas là thư viện hỗ trợ phân tích/xử lý dữ liệu bao gồm: làm sạch, lọc dữ liệu, xử lý dữ liệu thiếu. Có chức năng time-series (nhóm dữ liệu)

```python
import pandas as pd
```

2 cấu trúc dữ liệu chính:
- Series
- DataFrame

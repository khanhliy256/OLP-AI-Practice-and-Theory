## 1. Matplotlib
```python
import matplotlib.pyplot as plt
```
- `pyplot` chứa sẵn một vài hàm phổ biến để tạo biểu đồ 
### 1.1 Định nghĩa
- Matplotlib là thư viện hỗ trợ chuyển dữ liệu sang các hình ảnh trực quan (đồ họa cơ bản)

### 1.2. Các hàm thông dụng
`plt.plot()`: Tạo 2 trục Ox, Oy biểu diễn các giá trị trong ngoặc.
- plt.plot(data, hình dạng,..)

`plt.show()`: mở khung biểu đồ

|Tên|Chức năng|Ví dụ|
|---|---|---|
|.title()|tiêu đề|..|
|.tick_params()|Thay đổi kích thước của labels||
|.scatter()|chuỗi số|plt.scatter(x,y,..)|
|.axis()|range của cột|plt.axis(list)|
|.set_visible()|Loại bỏ các trục|plt.axes().get_xasis().set_visible(False)|

Các loại biểu đồ:
- `.bar()`: biểu đồ cột (bar chart)
- `.plot()`: biểu đồ đường (line graph)

## 2. Seaborn
```python
import seaborn as sns
```
- Seaborn trực quan hóa dữ liệu đẹp hơn (heatmap, boxplot,...)
- Dùng trực tiếp DataFrame để vẽ

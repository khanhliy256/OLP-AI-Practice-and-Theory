## Định nghĩa
Scikit-learn là thư viện hỗ trợ cho các bài toán học máy. 
- Tác vụ: phân tích dữ liệu + xây dựng mô hình ML
    + Phân loại: gán nhãn 
    + Hồi quy: dự đoán và ước tính 
    + Phân nhóm: tự động gộp nhóm

- Cơ chế: thực hiện nhờ vào `numpy` tính toán đại số, xử lý mảng arrays.

|Tính năng||
|---|---|
|Data Splitting|Chia nhỏ dữ liệu để train + test|
|Feature Scaling|Chuẩn hóa các giá trị|
|Feature Selection|Chọn các đặc trưng phù hợp|
|Feature extraction|Tạo đặc trưng mới từ dữ liệu sẵn có|

## Thư viện
```python
import sklearn
```

### Xây dựng mô hình trong Scikit-learn
- Bước 1: Load dữ liệu 
X = input biến, 
y = giá trị dự đoán
```python
# Thư viện - Ví dụ
sklearn.datasets 
```
- Bước 2: Chia nhỏ dữ liệu
Training set + Testing set --> 
```python
# Thư viện
sklearn.model_selection 
# Hàm 
train_test_split(X, y, test_size = ..., random_state = ...)
```
--> Cố định seeds (random_state = number)

- Bước 3: Xử lý dữ liệu --> Phân loại
* Label Encoding: Mã hóa 1 biến thành số nguyên
Ví dụ: 'apple' = 0, 'banana' = 1, 'orange' = 2
```python 
# Thư viện 
sklearn.preprocssing 
# Hàm 
LabelEncode().
fit_transform(list)
```
* One-Hot Encoding: Đưa về cột nhị phân = 1 biến
```python
# Hàm
OneHotEncoder(sparse_output=False) 
fit_transform(2D_shape)
```
--> Ma trận thưa --> mảng Numpy đầy đủ.

- Bước 4: Huấn luyện mô hình
Áp dụng các thuật toán Regression 

- Bước 5: Dự đoán
```python
.predict(X)
```

- Bước 6: Đánh giá độ chính xác của mô hình

```python
.accuracy(y_test, y_predict)
```
--> Xác suất [0,1], càng gần 1 thì độ chính xác càng cao.

## Các bài toán
### 1.1. Preprocessing
Trích xuất và chuẩn hóa đặc trưng (features)
- Ứng dụng: Chuyển đổi dữ liệu chữ/ảnh --> áp dụng thuật toán ML.

### 1.2. Classification
Xác định mục/lớp/label nào.
- Ứng dụng: Spam detection, Image recognition

|Thuật toán|Giải thích|
|---|---|
|SVM & Kernel SVM|Support Vector Machine: Tách lớp (dimensions) số chiều vector|
|Radial Basis Function Kernel||
|Decision Tree|tách đệ quy, nút lá = label|
|Random Forest||
|KNN classifier||
|Gaussian Naive Bayes||

### 1.3. Regression
Tạo mô hình học máy dự báo dựa trên dữ liệu vào 
- Ứng dụng: theo dõi biến động giá, chỉ số sinh học, thời tiết,...

|Thuật toán|Giải thích|
|---|---|
|Linear Regression||
|Multiple Linear Regression||
|Decision Tree Regression||
|Stochastic Gradient Descent Regressor||

Nhiều thế!

### 1.4. Clustering
Phân cụm các điểm dữ liệu có tính tương đồng 
- Ứng dụng: Phân khúc khách hàng, nhóm kết quả thí nghiệm

|Thuật toán|Giải thích|
|---|---|
|K-Means clustering|khoảng cách|
|Hierarchical Clustering||



### 1.5. Dimensionality Reduction
Giảm chiều dữ liệu giúp lược bớt số lượng biến ngẫu nhiên (dữ liệu ngoại lai, ít thông tin)
- Ứng dụng: Trực quan rõ ràng hơn, tăng hiệu quả sử dụng bộ dữ liệu (phù hợp với bối cảnh nhất định)

--> Principal Component Analysis (PCA)
DBSCAN algorithm |
Gaussian Mixture Models (GMM) |
Manifold Learning methods |

### 1.6. Model Selection
Lựa chọn mô hình dựa trên
- So sánh
- Xác thực
- Tham số tối ưu 

|Thuật toán|Giải thích|
|---|---|
|Cross-Validation||
|Accuracy and scoring metrics||
|Euclidean Distance||
|Classification Metrics||
|R2 with Scikit-Learn||
|RMSE calculation||
|Clustering Evaluation Metrics||

### 1.7. Pipeline
Xây dựng chuỗi công việc 

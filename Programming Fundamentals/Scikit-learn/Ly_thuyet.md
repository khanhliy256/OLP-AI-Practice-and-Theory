## Định nghĩa
Scikit-learn là thư viện hỗ trợ cho các bài toán học máy. 
- Tác vụ: phân tích dữ liệu + xây dựng mô hình ML
    + Phân loại: gán nhãn 
    + Hồi quy: dự đoán và ước tính 
    + Phân nhóm: tự động gộp nhóm

- Cơ chế: thực hiện nhờ vào `numpy` tính toán đại số, xử lý mảng arrays.

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

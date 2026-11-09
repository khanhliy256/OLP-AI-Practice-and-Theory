## Linear Regression là gì?
Linear = tuyến tính (line, phẳng)
- Đây là thuật toán hồi quy tuyến tính dựa vào các dữ liệu cho trước, thuật toán xây dựng một line để dự đoán các điểm tiếp theo.

> Bài toán dự đoán giá trị đầu ra dựa trên vector đặc trưng đầu vào 

Linear có 2 phần: Features và Labels (tương ứng).

Dựa vào dữ liệu đầu vào $y = xw + b$, ta đưa ra một $\hat y \approx y$ có dạng $\hat y = \textbf{x}^T\textbf{w}$ trong đó $x$ là một vector đặc trưng $\textbf{x} = [x_1  x_2...x_n]^T$, $w$ là vector hệ số (trọng số - *weight vector*) $\textbf{w} = [w_1 w_2...w_n]^T$

$\Rightarrow y$ = Giá trị thực tế.

$\Rightarrow \hat y$ = Giá trị dự đoán.

## Hàm mất mát
Sai số $e = |y - \hat y|$ nhưng hàm trị tuyệt đối không liên tục, do vậy cần biểu diễn sai số theo cách sau $e^2 = (y - \hat y)^2$.
> Tại sao phải bình phương mà không phải mũ 4, 6?? Dựa vào công thức xác suất gì?

- Công thức sai số: $e^2 = (y - \textbf{x}^T\textbf{w})^2$

> Làm sao để sai số là nhỏ nhất?

Công thức hàm mất mát:
$L(w) = \frac{1}{2N}\sum_{i=1}^{N}(y_i - \hat y_i)$ với N là số điểm dữ liệu biết trước.

Trả lời bài toán: Tìm $\textbf{w}$ để $L(w)$ đạt giá trị min $\Rightarrow \hat{\textbf{w}} = argmin_w (L(w))$

> Tính đạo hàm, tìm nghiệm cho $L(w)$

Phân tích: $min(L(w))$ tại nghiệm của đạo hàm. Vì $L(w)$ là hàm bậc 2 có cực trị hình parabol, đáy dưới. Như vậy, để tìm $w$, bản chất là tính đạo hàm và đặt $=0$.

Coi $w$ là biến, $y_i, x_i$ là các hằng số. 

Công thức hàm mất mát dưới dạng Norm $l_2$:
$L(w) = \frac{1}{2N}\|y - X^Tw\|_2^2$

Nháp:

$(\frac{1}{2}(y_i-x_i^Tw)^2)'=(y_i-x_i^Tw)x_i^T$

Khi sắp xếp thành một vector, ta thu được

Đạo hàm = $\frac{1}{N}X(X^Tw - y) = 0 \Rightarrow XX^Tw = Xy$

Nhận xét: $XX^T$ khả nghịch, phương trình có nghiệm duy nhất $w = (XX^T)^{-1}Xy$.

Còn không sẽ có 1 giá trị giả nghịch đảo.

> Một cách vectorization

- `Mean Squared Error` (MSE):

$L(\theta) = \frac{1}{N}\sum_{i=1}^{N}(\hat y_i - y_i)^2$.

 Do đó, đặt $e_i = \hat y_i - y$, thì thu được $\sum_{i=1}^{N}(\hat y_i - y_i)^2=e^\top e$.

Khai triển ma trận bằng tính chất $(A-B)^\top=A^\top - B^\top, (AB)^\top = B^\top A^\top$. Áp dụng vào $L(\theta)$, ta có:

$L(\theta) = \frac{1}{N}(X\theta-y)^\top(X\theta -y) \\
=\frac{1}{N}(\theta^\top X^\top - y^\top)(X\theta - y) \\
= L(\theta) = \frac{1}{N} \left( \theta^\top X^\top X \theta - \theta^\top X^\top y - y^\top X \theta + y^\top y \right)$ 

và $$(\theta^\top X^\top y)^\top = y^\top (X\theta) = y^\top X \theta$$

Ta biến đổi thành

$$L(\theta) = \frac{1}{N} \left( \theta^\top X^\top X \theta - 2 \theta^\top X^\top y + y^\top y \right)$$

> Tính đạo hàm theo vector, sử dụng quy tắc đạo hàm ma trận tiêu chuẩn 

$\frac{\partial (\theta^\top A \theta)}{\partial \theta} = 2 A \theta$ (khi $A = X^\top X$ là ma trận đối xứng)

$\frac{\partial (\theta^\top b)}{\partial \theta} = b$ (với $b = X^\top y$)

$\frac{\partial (y^\top y)}{\partial \theta} = \mathbf{0}$ (hằng số đối với $\theta$)

Áp dụng các quy tắc trên vào biểu thức $L(\theta)$:
$$\nabla_{\theta} L = \frac{1}{N} \left( 2 X^\top X \theta - 2 X^\top y \right)$$

Đặt $2 X^\top$ làm nhân tử chung:$$\nabla_{\theta} L = \frac{2}{N} X^\top (X\theta - y)$$

$\textbf{Loss} = \frac{1}{N}(\hat y - y)^\top(\hat y - y)$ với $\hat y = X\theta$

## Bài tập code 
### Sử dụng công thức

$\hat y_i = w*x_i+b$

Ví dụ:

|area|price|predicted|error|
|---|---|---|---|
|6.7|9.1|||
|4.6|5.9|||
|3.5|4.6|||
|5.5|6.7|||

Với các giá trị $w = 1.17, b = 0.26$ thì đường thẳng sẽ như nào? `error` càng nhỏ thì càng tốt.

Thực hiện theo các bước tính theo đạo hàm, lựa chọn loss nhỏ để tìm nghiệm.
- Bước 1: Hàm tính $\hat y$
```python
def predict_func(w, b, x):
    return w*x + b
```
- Bước 2: Tính Loss $L(w) = \frac{1}{2}(\hat y - y)^2$
```python
def compute_loss(y_hat, y):
    return 1/2*(y_hat-y)**2
```
- Bước 3: Tính đạo hàm của hàm Loss
```python
def compute_gradient(y_hat, y, x):
    return (y_hat - y), x * (y_hat - y)
```
- Bước 4: Cập nhật hệ số w, b mới
```python
def update(w, b, grad_w, grad_b, alpha):
    w = w - alpha*grad_w
    b = b - alpha*grad_b
    return w, b
```
### Sử dụng thư viện Scikit-learn

```python
# Thư viện
sklearn
# Hàm
linear_model
# Trong model đó có:
LinearRegression()
# Dùng hàm fit(X,y) --> nghiệm 
.fit(X, y) 
# Hệ số weight
.coef_
# Hệ số bias
.intercept_
```

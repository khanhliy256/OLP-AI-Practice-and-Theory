## Logistic Regression là gì?

> Tại sao cần Logistic Regression?

Trong một số tập dữ liệu, có thể sẽ chứa một một nhóm dữ liệu tách rời nhau, khi đó, một đường tuyến tính Linear nối giữa các cụm tách rời đó có thể không chính xác, khi dữ liệu thực tế và dữ liệu dự đoán quá lệch nhau.

Để giải quyết các kiểu dữ liệu này, mô hình cần áp dụng Logistic Regression.

--> Hàm `logistic`

> Bài toán phân loại

Phương trình vi phân: $\frac{dy}{dt}=r*y*(1-\frac{y}{K})$ với $K$ là kích thước lớn nhất, $y$ là kích thước tại thời gian $t$.

Giải phương trình vi phân, ta thu được:
`Sigmoid_Function`$\sigma(y) = \frac{1}{1+e^{-y}}$

> Lấy đạo hàm của $\sigma$

$\sigma'(y)=\sigma(y)(1-\sigma(y))$ với $y$ có dạng $y=wx+b$ $\Rightarrow$ điểm dễ tính toán, sử dụng rộng rãi.

Hàm liên tục trên giá trị thực, bị chặn $[0,1]$ bằng cách tính $lim_{y\rightarrow -\infty}=0$ và $lim_{y\rightarrow +\infty}=1$

## Hàm mất mát
Công thức MSE, RMSE

Mean Squared Error (MSE):

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

> Kết luận:

$\textbf{Loss} = -y*\text{log}(\hat y)-(1-y)\text*{log}(1-\hat y)$

$\textbf{Loss}=log(\hat y)^ylog(1-\hat y)^{1-y}$

$\textbf{Loss} = \frac{1}{N}(\hat y - y)^\top(\hat y - y)$ với $\hat y = X\theta$


## Bài tập code Python

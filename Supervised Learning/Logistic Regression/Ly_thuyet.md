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

## Bài tập code Python

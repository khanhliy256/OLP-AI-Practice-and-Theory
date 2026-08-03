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

## Bài tập code 
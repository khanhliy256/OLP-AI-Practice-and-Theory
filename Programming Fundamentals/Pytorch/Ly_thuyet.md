## Định nghĩa
`Pytorch` là một thư viện/công cụ/mã nguồn, tương đồng với Numpy. 
|Numpy|Pytorch|
|---|---|
|CPU|tối ưu cả CPU và GPU|
|Tính toán đại số, mảng nhiều chiều cơ bản|Xây dựng, huấn luyện DL|
|Cấu trúc: ndarray|Tensor|
|Phần đạo hàm phải tự tính|Tự động tính đạo hàm|
|Không có sẵn module nơ-ron|Có cung cấp|
|Pandas, matplotli, Scikit-learn|Huấn luyện neuron, tập dữ liệu cần GPU, đạo hàm phức tạp|


## Cấu trúc
Pytorch Tensor: ma trận có 2 chiều, tensor có thể có nhiều hơn 2 chiều. 
```python 
torch.tensor(array)
# Chuyển numpy sang tensor
tensor = torch.from_numpy(array)
# Chuyển tensor sang numpy
numpy = tensor.numpy()
```

### Autograd: tính đạo hàm 
```python
# Define tensors with requires_grad=True to track computation history
torch.tensor(2.0, requires_grad=True)
# Compute gradients
.backward()
print(.grad)
```

### Neural Networks 
Mạng nơ-rôn - Cấu trúc mạng tự thiết kế (theo class)

- Bước 1: Định nghĩa lớp neural 
```python
import torch.nn as nn
import torch.optim as optim

class MyModel(nn.Module):
    def __init__(self):
        # Định nghĩa
    def forward(self, x):
        # Kết nối các layer 
```

- Bước 2: Chuẩn bị dữ liệu X, y 
- Bước 3: Khởi tạo mô hình
- Bước 4: Huấn luyện mô hình 
Data Handling 
```python
# Thư viện
torch.utils.data
# Hàm đảm bảo dữ liệu loop mượt 
Dataset()
DataLoader()
```
```python
# Thư viện
torchvision.transorms
# Hàm (xoay, lật, phóng to) --> Image
transforms
.RandomHorizontalFlip()
ToTensor()
```

Neuron có nhiều lớp, có tính kế thừa, luôn bao gồm 2 thành phần:
- __init__()
- forward()

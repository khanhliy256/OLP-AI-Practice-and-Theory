![Minh họa CPU và GPU](cpu-vs-gpu-cores.png)

Trong huấn luyện mô hình, thời gian và bộ nhớ là 2 yếu tố quyết định quan trọng cho hiệu quả của *code*. Nhanh hơn và tiết kiệm bộ nhớ hơn là hai bài toán cần tối ưu.

3 bước cơ bản trong thuật toán học máy:
- Decision process: dự đoán, phân loại 
- Error function: tự đánh giá đầu ra dựa vào các lỗi đã biết
- Model optimization process: Liên tục đánh giá các dự đoán (lặp quá trình, chính xác theo thời gian)

## CPU
Central Processing Unit = RAM + Cache + CU + AU. 

**`Thực hiện tuần tự`**

> Khi nào dùng CPU?

Trong môi trường web server, app AI hay ChatBot (mô hình đã được huấn luyện sẵn), tính toán cơ bản, hệ thống chỉ cần suy luận nhanh nhất có thể. Lúc này CPU được sử dụng phổ biến nhất, vì:
- Suy luận nhẹ không cần đến GPU
- Tốc độ phản hồi thấp
- Postprocessing


## GPU
Graphical Processing Unit = [CPU CPU CPU]. GPU tính toán lượng công việc lớn cùng một lúc. Hầu hết các mạng neural đều được huấn luyện qua GPU device. 

**`Thực hiện song song`**

> Khi nào cần GPU?

## Huấn luyện mô hình trên CPU 
- [Training AI Models on CPU](https://towardsdatascience.com/training-ai-models-on-cpu-3903adc9f388/)
- [Training Models - Pytorch step-by-step](https://www.codegenes.net/blog/pytorch-cpu-training/)

### Tensors 
```python
# Kiểm tra thiết bị 
tensor_array = torch.tensor([1.5, 8.9, 3], [2.3, 4.4, 9.802])
print(f"Thiết bị lưu trữ: {tensor_array.device}")
```

### Computational Graph
```python

```

|Batch Size|Step time (s)|Throughput (sps)|
|---|---|---|

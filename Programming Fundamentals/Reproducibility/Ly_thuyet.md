Trước tiên, việc random mọi thứ đều là start của Neural Networks

- Bước 1: Random numbers
- Bước 2: Tạo tensors
- Bước 3: Cập nhật các random numbers để thành một khối dữ liệu cần thiết
- Bước 4: Loop

```python
torch.rand(size, row, colum) # [0, 1]
```

## Random Seed
> Tại sao cần seed giống nhau?

```python
torch.manual_seed(size)
```
Trong một tập test, dữ liệu Input có thể random nhưng khi lặp lại quá trình để kiểm tra độ chính xác, tập input random tiếp theo sẽ thay đổi. Do vậy, để đảm bảo tính nhất quán, việc ngẫu nhiên chỉ xảy ra ở nhập input lần đầu.
`manual_seed` giữ tập dữ liệu không thay đổi.

Giảm sự ngẫu nhiên trong mạng neural, PyTorch cung cấp 1 tập random seed. Vì máy tính không thể tạo một random hoàn toàn, do đó vẫn cần một điểm xuất phát là `seeds_count` trong *manual_seed(seeds_count)*
# 1. Định nghĩa
Random forest là thuật toán cây quyết định (rẽ nhánh)
- Phục vụ cho bài toán phân loại: thư rác, tin nhắn giả mạo $\rightarrow$ Dự đoán.
- Structure: Nút quyết định (parent node) + nhánh (branch) + nút lá (child node) 

> Làm sao các nhóm chia thuần hơn? \
> Gini/Entropy 

# 2. Overftting

# 3. Cách vận hành
- Mỗi nút chỉ được chọn 1 số feature: người gửi, từ khóa, dạng link...

|Dataset|Bootstrap|N cây|Dự đoán|Tổng hợp||
|---|---|---|---|---|---|
|Sử dụng bootstrap cho bài toán xác suất|

```python
model = RandomForestClassify()
```

Ví dụ: bài toán phân loại hoa
- Chia dữ liệu
- Huấn luyện K cây
- Đánh giá 
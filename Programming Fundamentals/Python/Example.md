Link tài liệu: [Python Crash Course](https://drive.google.com/file/d/1Hu_Rd-spILyNWmoBw1HubHWrkmfz0zKh/view)
## 1. List và Loops
### 1.1. Vòng lặp 'for'
```python
Trees = ['Apple', 'Banana', 'Cherry']
print(Trees[2]) # Trả về Cherry 
for i in Trees:
    if i is 'Banana':
        print("Đã tìm thấy cây Chuối")

```

### 1.2. Vòng lặp 'while'
```python
age = 1
while age < 18:
    age += 1
    # Dừng vòng while khi age đủ 18 
print("Bạn đã trưởng thành!")
```

Game
```python
Real_pass = "UIA CAT"
User = "A"
while True:
    Door_Pass = input("Nhập mật khẩu: ")
    if Door_Pass != Real_pass:
        print("Quit!")
        break 
    else: 
        new_p = chr(ord("A") + len(Door_Pass))
        Real_pass += new_p
        print(f"Hint tiếp theo là: {new_p}")
```

## 2. Functions
Nhập vào thông tin cá nhân --> In ra một văn bản hoàn chỉnh giới thiệu bản thân
```python
def Introduction(Name, Age, School, Major):
    print(f"Tôi tên là {Name}, năm nay tôi {Age}, hiện tôi đang theo học tại {School} với chuyên ngành {Major}.")
    print("Chào mừng thành viên mới!")
    if Age < 18:
        print("Thành viên mới chưa trưởng thành!")
    elif Major != "CNTT":
        print("Thành viên mới cần học về C++, DSA")
    dem = 0 
    while Age <= 18:
        dem += 1
    print(f"Thành viên mới cần {dem} năm nữa thì uống được bia")

Introduction(Ly, 7, Meo, "CNNN")
```
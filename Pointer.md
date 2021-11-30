# Pointer

có thể thêm dấu "&" để xuất ra địa chỉ của biến



## Virtual memory & Physical memory

chúng ta không thể làm việc trực tiếp đối với bộ nhớ của máy tính mà phải thông qua bước trung gian đó là thông qua một bộ nhớ ảo.

Ở con trỏ ta có thể hiểu rằng, biến khởi tạo là vùng nhớ ảo chứa địa chỉ tại vùng nhớ vật lý.

cách khai báo con trỏ: 

```c++
int *x;
```

với cú pháp <kiểu dữ lieu> *<tên biến>

Đối với 1 biến bình thường ta có thể xuất ra địa chỉ của biến đó bằng cách:

```c++
 int x=5; 
 cout<<x<<'\n';//in ra gia tri cua bien 
 cout<<&x<<'\n';//in ra dia chi cua bien
```

Bằng cách thêm dấu "&" ta có thể xuất địa chỉ của biến ở vùng nhớ vật lý cách này gọi là address-of operator

lưu ý ta chỉ có thể lưu vào con trỏ địa chỉ của vùng nhớ, tức là không thể lưu giá trị, kể cả địa chỉ dưới dạng thập lục phân cũng không thể lưu vd như: 

```c++
int *x;
int a=10;
x=&a;
```

Đây là 1 cách gán hợp lệ.

```c++
int *x;
x=10;
```

```c++
int *x;
x=0012FF7c;
```

cả hai cách trên đều sai!

Ta cũng có thể  gán địa chỉ của 2 con trỏ với nhau.

```c++
int *con_tro1, *con_tro2;
int number=10;
con_tro1=&number;
con_tro2=con_tro1;
```

Kết quả sẽ là địa chỉ của number gán cho con trỏ 1 và 2;

với mảng thì các thành phần trong mảng sẽ lưu ở những địa chỉ khác nhau tuy nhiên chúng lại liền kề nhau

LƯU Ý: chúng ta chỉ có thể gán địa chỉ cho con trỏ khi địa chỉ bên trong cùng kiểu dữ liệu với con trỏ 

Cách thức để lấy giá trị từ con trỏ ta sử dụng cú pháp: *<địa chỉ>

```c++
int *x;
int number=5;
x=&number;
cout<<*x;
cout<<*(&number);

cả hai cách trên đều đúng và cho ra giá trị là 5
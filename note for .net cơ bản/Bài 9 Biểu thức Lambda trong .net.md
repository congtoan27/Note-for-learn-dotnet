

Khi mà muốn ghi rõ kiểu của từng tham số thì dùng Func<> tham số ở giữa lần lượt là kiểu của a và b cuối cùng là kiểu của kết quả trả về. 
Lamda hiểu ngắn gọn như là viết nhanh gán một phương thức cho biến, có gì gọi biến đó
 
statement lambda thì dùng Action<> nha tham số tương tự Func
khi có 1 tham số có thể bỏ 2 dấu ngoặc.
Mình khai báo "s" không cần khai báo kiểu dữ liệu vì Action mình đã có khai báo rồi, khi dùng var thay Action thì phải khai báo kiểu cho "s" .

Khi mà mình trả về kết quả có 2 kiểu dữ liệu khác nhau thì sẽ bị lỗi
1 là mình khai báo giống cùng 1 kiểu 
2 là  ép kiểu nó bằng kiểu dữ liệu cha của 2 kiểu dữ liệu đó.


Sử dụng lambda khi cần viết hàm mà mình có thể thay đổi cách sử dụng nó ( như ảnh trên)

Hiểu đơn giản LINQ là dùng để truy vấn dữ liệu. ( không bao gồm sửa xóa cập nhật ).
Chúng ta thường gán linq vào một biến trước khi gọi đến nó vì một câu lệnh linq khá là dài.
Trong Entity framework thì khi viết một câu linq thì nó thật ra vẫn chưa thực thi, chỉ khi nào gọi hay dùng tới kết quả của nó thì nó mới thực thi.
thêm select thì cũng tương tự SQL, chỉ lấy cái Name

sắp xếp nếu năm sinh bằng nhau thì sắp xếp theo tên.

Kiểu như khi nào cần tính sum hay count thì phải dùng method syntax để gọi phương thức.

Hình dưới 3 dòng màu xanh gọi là queries syntax
dòng tô xanh là method syntax

Có thể  thay thế điều kiện bằng phương thức như hình dưới.



xem thêm lệnh take,skip,firstordefault
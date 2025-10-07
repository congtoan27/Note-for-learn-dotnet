Hiểu đơn giản LINQ là dùng để truy vấn dữ liệu. ( không bao gồm sửa xóa cập nhật ).
Chúng ta thường gán linq vào một biến trước khi gọi đến nó vì một câu lệnh linq khá là dài.
Trong Entity framework thì khi viết một câu linq thì nó thật ra vẫn chưa thực thi, chỉ khi nào gọi hay dùng tới kết quả của nó thì nó mới thực thi.
thêm select thì cũng tương tự SQL, chỉ lấy cái Name

sắp xếp nếu năm sinh bằng nhau thì sắp xếp theo tên.

Kiểu như khi nào cần tính sum hay count thì phải dùng method syntax để gọi phương thức.

Hình dưới 3 dòng màu xanh gọi là queries syntax
dòng tô xanh là method syntax

Có thể thay thế điều kiện bằng phương thức như hình dưới.

khi mà dùng linq với Enumerable thì gọi là linq to object vì là dùng truy vấn những nguồn dữ liệu đã nằm bên trong bộ nhớ
từ khóa entity framework core

xem thêm lệnh take,skip,firstordefault

bản thân kết quả trả về của linq cũng có implement IEnumerable

linq có 2 phần một là phần ngôn ngữ được tích hợp trong c# ,trình dịch c# sẽ dịch các câu truy vấn thành các
lệnh để gọi lên các nguồn dữ liệu hoặc có thể tạo ra các cấu trúc cây để biểu đạt câu lệnh đó (expression tree)
,chung ta có thể dịch các expression tree thành những câu truy vấn nào đó(như EF core,linqtoobject) trong trường hợp cần thiết,

phần diễn dịch từ ngôn ngữ truy vấn bên trong c# thì do trình biên dịch ,phần xử lí các expression tree sẽ do driver làm.

có thể nối lệnh (ví dụ như orderby) ,kiểu như thực hiện cái viết trước trước rồi cái viết sau thực hiện sau.


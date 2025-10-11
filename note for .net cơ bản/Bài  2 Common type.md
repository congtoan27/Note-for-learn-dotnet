Value type và reference type
Quy ước đặt tên
dotnet data type
string là reference type nên phải new nó trước khi dùng
ưu tiên dùng interpolation string (trình dịch nó sẽ dùng stringbuilder để chạy interpolation string còn @ thì nó kiểu in chuỗi bình thường)
khi dùng method toUpper() hoặc các method tương tự để in ra chữ hoa hoặc bla bla thì thực chất là in ra một chuỗi khác biệt không liên quan biến đã gọi tới.
StringBuilder nó có bộ nhớ đệm thì khi add một chuỗi vào thì nếu chuỗi đó lớn hơn bộ nhớ đệm thì cấp phát thêm còn không thì nó thêm vào bộ nhớ đệm thôi.
Dotnet là môi trường an toàn kiểu nên khi khai báo biến thì khi dịch sẽ kiểm tra kiểu có hợp lệ không và khi chạy nó sẽ kiểm tra lại lần nữa.(dynamic thì bỏ qua kiểm tra ở bước dịch). ví dụ khi lớp A có hàm f() thì mình code A.f() thì sẽ không hiện lỗi ,chỉ khi run thì mới biết lỗi vì trình dịch không kiểm tra kiểu dynamic
HasValue()
![[Pasted image 20250922224416.png]]
như ảnh trên thì trong c# coi chuỗi đó như object luôn còn java thì không.


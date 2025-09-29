cũng tương tự exception trong java
stackTrace là kiểu ghi lại exception được phát hiện ở đâu á. nếu hàm được gọi bởi hàm khác thì nó cũng sẽ list ra.
học được thêm từ khóa throw thì kiểu mình throw exception đã được bắt lỗi thì nhập ex.stackTrace (trong trường hợp này) trong mục name của debug thì nó bị thay đổi thành dòng "throw ex;" luôn
Để mà ko bị thay đổi stackTrace thì bỏ "ex" ở dòng throw đó đi.(chỉ dùng throw;) để lấy được đúng vị trí sinh ra lỗi. mà khi throw ex; thì stacktrace sẽ chỉ hiện lỗi ở dòng throw ex; đó
finally sẽ luôn chạy ngay cả khi có lỗi hay không có lỗi.
Khi ko xử lí exeption nào đó thì .net sẽ kết thúc chương trình luôn ,có thể là trc khi tới dòng finnally thì finally cũng ko thể thực thi.
Học được thêm là ko cần phải học thuộc tên exception mà chỉ cần catch Exception rồi toString ra sau đó copy tên thôi:)))


![[Pasted image 20240924234655.png]]


1 khối try có thể có nhiều khối catch
có thể try catch lồng try catch thì try catch ngoài  bắt lỗi được throw ra bởi try catch bên trong.
có thể tạo Exeption bằng new()

- Exception là cách thức .NET thông báo lỗi chương trình, chúng có thể được phát ra khi gặp một lỗi (ví dụ như chia cho 0, truy cập vào phần tử null...), hoặc cũng có thể do chương trình phát ra (dùng throw).
- Ta có thể bắt các exception bằng cách đặt đoạn lệnh sinh ra lỗi trong khối try ... catch ... finally.
- Một khối try có thể có nhiều khối catch để bắt các loại exception khác nhau.
- Khối finally luôn luôn được thực hiện, kể cả khi một exception khác xảy ra khi đang thực hiện catch.
- Exception tốn kém chi phí để tạo ra nên khi cần hiệu năng cao ta nên tránh dùng nó (ví dụ nên dùng int.TryParse thay vì int.Parse).
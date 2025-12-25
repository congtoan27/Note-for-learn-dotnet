Trong clip này chúng ta tìm hiểu kỹ hơn về các thao tác CRUD với Sql Server bằng ADO.NET. Ngoài ta chúng ta cũng học cách:

- Lưu connection string trong file config thay vì hard-coded.
- Sql injection là gì và cách sử dụng SqlParameter để tránh.
- Sử dụng transaction.

Chi nhớ:

- Dùng SqlCommand.ExecuteReader khi muốn duyệt qua một bảng trả về bởi một câu lệnh SELECT.
- Dùng SqlCommand.ExecuteNonQuery() để thực thi các câu lệnh DELETE, UPDATE, kết quả trả về là số dòng bị ảnh hưởng.
- Dùng SqlCommand.ExecuteScalar() để thực hiện một câu lệnh SQL với duy nhất một kết quả trả về, ví dụ COUNT, SUM... nếu câu lệnh SQL trả về nhiều hơn một dòng hoặc một cột thì ExecuteScalar sẽ trả về giá trị đầu tiên nhất (cột 1, dòng 1).

Quan trọng: Luôn dùng using khi cần để đảm bảo tài nguyên luôn được giải phóng một cách đúng đắn.
và khi thêm một file appsettings.json thì có thể sẽ lỗi vì nó sẽ không được thêm vào thư mục biên dịch và để thêm vào thư mục biên dịch thì click chuột phải và chọn copy if newer hoặc always.


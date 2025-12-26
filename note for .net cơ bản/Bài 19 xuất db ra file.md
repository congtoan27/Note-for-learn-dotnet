![[Pasted image 20251226235429.png]]
![[Pasted image 20251226235613.png]]
![[Pasted image 20251226235628.png]]
![[Pasted image 20251226235644.png]]
![[Pasted image 20251227000821.png]]
abstract factory pattern cũng là factory pattern nhưng tạo dựa trên một đối tượng nào đó


### Tóm tắt kiến thức từ video "Học lập trình .NET - Phần 19 - Giải bài tập: chương trình xuất dữ liệu từ database ra file"

Video này hướng dẫn giải bài tập xây dựng chương trình .NET để xuất dữ liệu từ cơ sở dữ liệu (database) ra file, với trọng tâm vào thiết kế mở rộng, sử dụng các pattern như Builder và Factory để đảm bảo tính linh hoạt và dễ bảo trì. Chương trình hỗ trợ kết nối SQL Server (có thể mở rộng sang MySQL, Oracle), thực thi query SELECT, và xuất ra định dạng CSV, SQL, hoặc nén ZIP.

#### Mục tiêu chính
- Sao chép dữ liệu từ database sang file.
- Dễ mở rộng: Thêm nguồn dữ liệu mới, định dạng file mới mà không sửa nhiều code.

#### Nguyên tắc thiết kế
- **Tập trung core domain**: Sao chép dữ liệu là chính, các phần khác (nguồn, định dạng, nén) là phụ.
- **Phân chia subsystem độc lập**:
  1. **Thu thập tham số**: Nhận input từ command-line (connection string, query SELECT, file name, format, compress...).
  2. **Kết nối & đọc dữ liệu**: Kết nối DB, lấy DbDataReader.
  3. **Xuất dữ liệu**: Viết dữ liệu ra file theo định dạng.
  4. **Điều phối**: Kết nối các phần lại.

#### Các pattern và thành phần chính
- **Builder Pattern**: Sử dụng `ExportOptionBuilder` để xây dựng đối tượng `ExportOption` chứa tất cả tùy chọn (DatabaseOptions: connection, query, server type; ExportOptions: file, format, compress).
- **Factory Pattern**:
  - `DatabaseBuilderFactory`: Tạo builder cho loại DB cụ thể (e.g., SqlServerDatabaseBuilder) để mở connection và lấy reader.
  - `IDataWriterFactory`: Tạo writer cho định dạng (e.g., CsvDataWriter, TsqlDataWriter).
- **Interface chính**:
  - `ExportSource`: Chứa connection và DbDataReader, triển khai IDisposable để tự động đóng tài nguyên (sử dụng `using`).
  - `IDataWriter`: Interface để viết dữ liệu từ reader ra stream (file hoặc ZIP).

#### Các bước thực hiện chương trình
1. **Xây dựng ExportOption**:
   - Parse command-line args.
   - Build options với builder (thêm timestamp vào file name nếu cần).

2. **Tạo nguồn dữ liệu (ExportSource)**:
   - Dùng factory lấy DatabaseBuilder phù hợp.
   - Mở connection, execute query, lấy reader.
   - Trả về ExportSource (auto dispose).

3. **Tạo writer và xuất dữ liệu**:
   - Dùng factory lấy IDataWriter dựa trên format.
   - Nếu compress, tạo ZIP stream.
   - Gọi `WriteData(reader, stream)` để loop qua dữ liệu và viết ra file.

#### Lưu ý quan trọng
- **Mở rộng**: Để thêm định dạng mới, chỉ cần implement IDataWriter mới và đăng ký factory. Tương tự cho nguồn DB.
- **Quản lý tài nguyên**: Sử dụng `using` để tránh leak connection/reader.
- **Test**: Tách logic (e.g., GetCurrentTimestamp) để dễ mock trong unit test.
- **Repository**: Link code mẫu: https://github.com/daohainam/dbexporter.

Video nhấn mạnh cách thiết kế phần mềm tốt trong .NET: tách biệt trách nhiệm, sử dụng pattern để code sạch, dễ mở rộng. Nếu bạn đang học .NET, đây là ví dụ thực tế về áp dụng OOP và design pattern trong project console app.


![[Pasted image 20251227002822.png]]
có hàm func ở trên để được gán là Date.now nhưng thay vì mình viết date.now ở trong hàm luôn thì mình lại dùng func ở trên là để mình có thể test được dễ dàng hơn vì khi chạy nếu viết trong hàm thì sẽ luôn lấy thời gian hiện tại mà mình lại muốn test thời gian khác mà mình tạo date cụ thể để test.
![[Pasted image 20251227003026.png]]
đây là lớp test khi dùng func trên.
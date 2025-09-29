các phương thức public trong controller được gọi là action method.
Một vài quy tắc đặc biệt như home , index thì được gọi đến khi ko cung cấp một url nào.
Luôn luôn có 1 object của controller được tạo mới mỗi khi gửi request lên (được hỗ trợ bởi DI)
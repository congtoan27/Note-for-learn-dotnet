![[Pasted image 20250125230813.png]]
Xem lại OOP, vì lớp ConsoleMessageWriter phải có mức độ truy cập cao hơn lớp Worker

Tổng hợp thì là mình đăng kí Interface đó sẽ tạo ra object theo kiểu của class nào (đã implement interface) thì mình đăng kí bằng addTrancient hoặc addSingleton hoặc addScope( cái này thì có một video riêng hãy nhớ xem)  rồi sau đó tạo interface thì nó sẽ tự động lấy object kiểu đó.Hoặc cũng có thể dùng constructor injection để gọi tới ( kiểu là khai báo interface trong constructor của lớp )
IServiceCollection là để mình đăng kí object hoặc constructor tạo object theo kiểu nào.
còn IServiceProvider thì nó sẽ tự cung cấp mỗi khi mình gọi tới.
![[Pasted image 20250125231728.png]]
Có thể viết theo kiểu này (ảnh trên getRequiredService vì trong constructor cảu ConsoleMessageWriter có tham số là một interface )
![[Pasted image 20250125231749.png]]
hoặc kiểu này

![[Pasted image 20250125232437.png]]
Nếu dòng nullInterface không có dấu chấm hỏi thì buộc phải có một constructor để gán giá trị cho nó tức là nó phải luôn có một giá trị nào đó.

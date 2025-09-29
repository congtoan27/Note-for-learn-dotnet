![[Pasted image 20250316005233.png]]
Note:
Cái RequestServices là khi addScope(),Transient,Singleton thì nó sẽ tăng 1 ServiceDescriptor.
Cái lớp HttpContext này chứa thông tin về các thông tin request được đưa vào bằng trình duyệt hoặc middware.
Item là chứa dữ liệu để xử lí bên trong request.


![[Pasted image 20250316005646.png]]
Freatures có tác dụng là xem thử chương trình mình đang chạy có được cấu hình để sử dụng 1 middleware nào đó hay không
Hàm User là thông tin về user đăng nhập vào kết nối
Hàm TraceIndentifier là chứa id của việc xử lí request
Hàm Session là khi mình sử dụng session middware thì session middleware đó gửi giá trị vào cái hàm session này trước khi action method gọi. Sesstion middleware cũng phụ trách tạo cookies và session id.

Không phải ứng dụng nào cũng cần tới session và cả những ứng dụng dùng tới session thì ko phải method nào cũng cần truy cập session.
Cơ chế: Cái session middleware phải check xem các cookies gửi lên có session  nào có tên trùng tên với tên đã được định nghĩa trước cho session id hay không, nếu có thì nó sẽ lấy giá trị đó ra và check bên trong bộ chứa của nó xem có mục nào có  id trùng với cái id được gửi bên trong cái session id đó không.
Trước khi gọi đến Action method thì sẽ load dữ liệu từ trong session từ trong server đó vào trong server hiện tại,và khi action method xử lí xong thì cập nhật dữ liệu đó lại vào trong session server.

![[Pasted image 20250316012339.png]]
cú pháp lạ mà t ko biết

Và hãy xem lại cách viết hàm extension.
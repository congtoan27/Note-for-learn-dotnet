1. Khi khai báo từ khóa static cho biến thì chỉ truy cập một biến duy nhất đó mà thôi ( Kiểu bình thường thì khi khai báo biến như lúc thường thì thì tạo một object của một class thì chúng ta sẽ có thêm 1 thuộc tính á).
2. Khi là một thuộc tính static của một class thì khi new đối tượng sẽ không gán được giá trị theo kiểu ( x=1000 , tương tự  vậy á) và nó không gắn liền với một object cụ thể nào nên ko thể new một đối tượng rồi dùng tên đối tượng đó để gọi biến static, muốn gọi biến đó là dùng tên class đó gọi ( class là cái type của đối tượng) và cũng như là gán giá trị được cho nó luôn nha.
3. Trong 1 method static thì chỉ truy cập được các biến static mà thôi (method bình thường thì truy cập biến nào cũng được và gọi method cũng tương tự nha), khi sử dụng method static cũng không cần tạo object.
	
Nếu khai báo method không static thì chúng ta phải tạo object mới gọi được phương thức đó

Hãy đặt method là static nếu có thể . vì khi muốn gọi một method ko static thì ta phải tạo object mà khi tạo vậy thì sẽ tạo thêm các trường với mỗi object sẽ tốn bộ nhớ hơn.

STATIC constuctor thì cũng tương tự mà khi mình khai báo không cần access modifier và không tham số vì nó được gọi tự động nên không có cách nào truyền tham số.

CLASS static
một class stastic chỉ chứa các thành phần static
và thường được dùng để viết các extension method
extension method thì như cái tên của nó là ví dụ khi một lớp là của ng khác mình không thể sửa hay viết code thêm vào được thì mình viết extension method



ví dụ extension method
chú ý 'this Person person' từ khóa this giúp ta viết extension method cho lớp Person

Design pattern singleton là để quản lí các biến static tốt hơn
Singleton: Khi muốn truy cập một biến static bắt buộc phải qua lớp singleton

ảnh trên là ví dụ về singleton


đây cũng là ví dụ cho singleton kế tiếp cái trên vì cái trên  khi tạo object nó sẽ new một đối tượng đầu tiên nên đối với việc kết nối DB thì như vậy là ko hợp lí nên là viết kiểu như trên.

Và khi không có dòng lock (_lock){} thì sẽ có lẽ là không đúng khi có nhiều thread đồng thời kết nối vì  thread đầu chạy tới kiểm tra null chưa kịp tạo instance thì thread thứ hai đã chạy thì cái việc tạo instance sẽ diễn ra 2 lần, vậy thì chúng ta chỉ sử dụng dc cái instance cuối cùng của thread cuối cùng.  
Giải thích khi khai báo object lock và từ khóa lock(_lock) khi viết như vậy thì chỉ có duy nhất một thread được chạy vào vùng code lock này thôi thread tiếp theo sẽ chờ thread trước thoát ra vùng lock



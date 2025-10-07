1. Khi khai báo từ khóa static cho biến thì chỉ truy cập một biến duy nhất đó mà thôi ( Kiểu bình thường thì khi khai báo biến như lúc thường thì thì tạo một object của một class thì chúng ta sẽ có thêm 1 thuộc tính á).
2. Khi là một thuộc tính static của một class thì khi new đối tượng sẽ không gán được giá trị theo kiểu ( x=1000 , tương tự  vậy á) và nó không gắn liền với một object cụ thể nào nên ko thể new một đối tượng rồi dùng tên đối tượng đó để gọi biến static, muốn gọi biến đó là dùng tên class đó gọi ( class là cái type của đối tượng) và cũng như là gán giá trị được cho nó luôn nha.
3. Trong 1 method static thì chỉ truy cập được các biến static mà thôi (method bình thường thì truy cập biến nào cũng được và gọi method cũng tương tự tức gọi phương thức bình thường hay static cũng được), khi sử dụng method static cũng không cần tạo object.
	
Nếu khai báo method không static thì chúng ta phải tạo object mới gọi được phương thức đó

Hãy đặt method là static nếu có thể . vì khi muốn gọi một method ko static thì ta phải tạo object mà khi tạo vậy thì sẽ tạo thêm các trường với mỗi object sẽ tốn bộ nhớ hơn.

STATIC constuctor thì cũng tương tự mà khi mình khai báo không cần access modifier và không tham số vì nó được gọi tự động nên không có cách nào truyền tham số. tự động dùng khi dùng kiểu dữ liệu đó lần đầu tiên



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



biến static gắn liền với kiểu chứa nó, và mỗi một kiểu dữ liệu chỉ được load 1 lần , ví dụ như tạo 1 đối tượng hay khai báo 1 biến x nào đó thuộc kiểu C thì kiểu C đó sẽ được nạp vào bộ nhớ và nó sẽ ở cố định 1 địa chỉ cho đến khi kết thúc chương trình và biến x cũng thế(chỉ được nạp 1 lần tức chỉ tồn tại  1 lần nên truy cập biến x ở chỗ nào thì cũng chỉ truy cập vào đúng biến x đó). ví dụ áp dụng là tính số người truy cập ứng dụng là tạo 1 biến static ,cứ 1 request tới thì biến static đó tăng lên 1





người khác tóm tắt được chủ kênh paste trong mô tả 
Trong bài này chúng ta sẽ học về từ khóa static. Ta có thể khai báo:

- static field
- static method
- static constructor
- static class

Ta cũng học cách viết các extension method và làm quen với design pattern thông qua Singleton, với eager loading và lazy loading. Ngoài ra, clip này cũng giúp các bạn làm quen với lock, giúp kiểm soát các critial section trong lập trình multi thread. Tóm tắt: (cảm ơn bạn @tientranphuc1547 đã viết giúp phần tóm tắt này) 1. Biến static gắn liền với class chứa nó và được tạo duy nhất 1 lần, tồn tại đến khi kết thúc chương trình Biến không phải static sẽ gắn liền với object 2. Khi khai báo hàm là static, chỉ có thể truy cập vào biến static (vì hàm static gắn liền với class, không gắn với một object cụ thể, trong khi biến bình thường gắn liền với object cụ thể) 3. Constructor static được gọi tự động khi class được sử dụng lần đầu tiên 4. Class static chỉ chứa các thành phần là static (hạn chế dùng, thường dùng khi viết extension method - là các method làm việc trên kiểu dữ liệu nào đó) 5. Tạo extension method bằng cách: tạo một lớp static, tạo 1 hàm static, tham số nhận vào là this + kiểu dữ liệu + tên biến Reference type 6. Phải gán giá trị cho kiểu reference type nếu nó không nullable (dùng require hoặc gán giá trị mặc định) Singleton 7. Vấn đề khi sử dụng static: khó kiểm soát vì có thể truy cập từ bất kì đâu trong chương trình, nếu thay đổi giá trị của nó sẽ ảnh hưởng đến tất cả những nơi sử dụng biến static này, dùng singleton pattern để khắc phục 8. Singleton pattern giúp kiểm soát được: quản lý vòng đời, kiểm soát truy cập, sửa đổi, ... 9. Nội dung: Thay vì cho người dùng truy cập thẳng vào biến static, thì ta bắt buộc phải thông qua 1 lớp đặc biệt, gọi là singleton 10. Dùng singleton phải kiểm soát truy cập đồng thời từ nhiều thread Dùng lock: Chỉ cho duy nhất 1 thread chạy vào vùng lock, nếu đang có thread chạy vào mà có thread chạy đến thì thread mới chạy đến phải chờ thread kia chạy xong vùng lock

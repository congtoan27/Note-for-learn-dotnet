Interface cũng tương tự bên java , bổ sung thêm là có thể thêm các thuộc tính trong lớp interface.
Có thể định nghĩa được thêm các static constructor và các static method.

Khi một lớp implement 1 interface thì phải implement các phương thức và thuộc tính của interface đó, và static method cũng vậy( khi viết static method cho interface thì những lớp implement sẽ mặc nhiên thừa hưởng cái nội dung method đó)
Có thể viết extendsion method cho interface
và cái extension method này có thể áp dụng cho các interface con của IReadable.

Có thể tạo ra interface và cho phép chúng kế thừa lẫn nhau và khi một lớp implement một interface đã kế thừa từ interface khác thì nó sẽ phải implement tất cả thông tin từ cả hai interface đó.

khi viết extension method cho một interface thì ta đã nhận vào một IReadable rồi thì con (interafce kế thừa IReadable) của IReadable vẫn có thể gọi ex method đó

Khi viết DatabaseReadable kế thừa từ IReadable thì chúng ta sẽ không khai báo một biến DatabaseReadable là một IDoubleReadable được dù IDoubleReadable đã kế thừa từ IReadable , và nếu muốn được thì chúng ta sẽ sửa lại như ảnh 1 .

Nguyên tắc solid là trong một interface chỉ tập trung vào một tập chức năng có cùng mục đích mà thôi.

sự khác nhau giữa abstract class và interface
\_Hỏi đáp: Q: Abstract class và interface khác nhau thế nào? A: Abstract class là một lớp được tạo ra với mục đích trở thành một lớp cha trong cây thừa kế, tức là khi có nhiều lớp với những đặc điểm tương tự, có thể xếp chung vào một loại, khi đó việc tạo ra một lớp chứa những đặc điểm chung và cho các lớp con thừa kế từ đó sẽ giúp bạn sử dụng lại code, dễ quản lý, áp dụng đa hình... Lớp cha có thể không đủ cụ thể để hiện thực hóa toàn bộ, do vậy một số, thậm chí có thể toàn bộ các phương thức sẽ chỉ là trừu tượng. Trong khi đó, interface là một danh mục các phương thức, thuộc tính... mà một lớp cần hỗ trợ. Mỗi interface được coi là một contract, hoặc một "chuẩn" để các lớp implement nó hỗ trợ. Hãy nghĩ đến ví dụ cổng sạc của điện thoại, USB-C là một chuẩn, nó không phải là một thứ cụ thể mà chỉ là danh sách các thứ mà một chiếc điện thoại phải tuân theo nếu muốn hỗ trợ USB-C: định dạng cổng, chân, điện áp, tín hiệu, quy trình kết nối... nhà sản xuất điện thoại chỉ cần theo đúng từng mục trong quy định đó để làm ra một chiếc điện thoại hỗ trợ chuẩn này. Trong trường hợp này USB-C chính là một interface, và một dòng điện thoại hỗ trợ USB-C là một class có implement interface này, mỗi chiếc điện thoại là một object thuộc class, và tất nhiên bạn hoàn toàn có thể sạc hoặc copy dữ liệu dùng chuẩn USB-C với chiếc điện thoại đó, dù nhà sản xuất cáp và điện thoại có thể chưa từng làm việc trực tiếp với nhau. Q: Vậy nhưng thay vì dùng interface, em vẫn có thể sử dụng abstract class? A: Đúng là như vậy, em có thể tạo một danh sách chức năng cần hỗ trợ trong một abstract class thay vì trong một interface, và tất nhiên một lớp thừa kế từ class này cũng phải implement các phương thức đó. Nhưng điều này dẫn đến cách sử dụng sai mục đích, và em sẽ gặp khó khăn khi sử dụng về sau. Em sẽ làm thế nào để một class hỗ trợ 2 (hay nhiều hơn) "danh sách chức năng cần hỗ trợ"? Không được! Vì một lớp chỉ có thể thừa kế từ một lớp cha. Khi người khác đọc code cũng vậy, vì tất cả đã cùng quy ước sử dụng interface để định nghĩa các contract, họ chắc chắn sẽ gặp khó khăn khi đọc code của em. Code chạy được, code chạy tốt, và thậm chí là code dễ bảo trì là những câu chuyện khác nhau. Anh công nhân ngoài công trường có thể đội mũ bảo hiểm khi đi xe máy khi làm việc không? Tất nhiên là được, nó cũng có thể bảo vệ, nhưng em có thấy nó kỳ cục không? Q: Có cách nào nói ngắn gọn hơn không? A:

- Khi có lớp B thừa kế từ lớp A, ta nói B là con A, một object B cũng chính là một object A.
- Khi có lớp B implement interface I, ta nói B hỗ trợ I, B "hiện thực hóa" những chức năng mà I yêu cầu.

Tất nhiên, giải thích ngắn gọn không phải lúc nào cũng dễ hiểu hơn giải thích đầy đủ :)

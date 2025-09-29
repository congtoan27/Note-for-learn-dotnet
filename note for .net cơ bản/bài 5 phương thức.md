Khi truyền tham số vào phương thức thì quan trọng thứ tự truyền vào.
By-by-value là khi truyền tham số thì thực sự tham số được truyền vào được nhân bản và sử dụng cái nhân bản đó.


Từ khóa ref là khi muốn Pass-by-reference , nghĩa là mình muốn sử dụng và thay đổi biến gốc luôn.
![[Pasted image 20250929214155.png]]
Trong dotnet có 2 kiểu dữ liệu 1 là value type 2 là reference type

(đang nói kiểu reference type nha) bản thân value đã là 1 reference thì mình chỉ thay đổi cái value đó thì không ảnh hưởng thì tới nội dung mà value đó trỏ tới.

![[Pasted image 20250929220323.png]]


Hiểu là khi mà tạo 1 biến mc và new Myclass() thì biến mc sẽ lưu ở 1 địa chỉ còn object tạo bằng new Myclass() sẽ lưu ở 1 địa chỉ và khi vào hàm Update..() thì sẽ cấp phát 1 địa chỉ khác cho biến mc trong phương thức đó và cũng sẽ trỏ tới object khi new ở hàm main()  và khi new object trong phương thức đó thì  sẽ tạo 1 object  và được cấp phát 1 địa chỉ khác nữa




![[Pasted image 20250929220905.png]]


ảnh trên là minh họa lời giải thích đã hiểu trong video, nếu mc.M=200; thì đã chỉnh sửa chính cái object new ở hàm main() vì mc trong phương thức đó được ví dụ được cấp phát địa chỉ là 2000 cũng trỏ tới object 9000 (là object tạo bằng new() ở main) nên khi không new() ở phương thức để tạo object riêng với địa chỉ riêng cho phương thức đó thì khi mc.M sẽ sửa cái object 9000.
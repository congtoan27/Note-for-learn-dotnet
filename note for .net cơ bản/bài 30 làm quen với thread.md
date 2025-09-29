Khi chạy vào hàm main thì sẽ có 1 thread chính của chương trình nữa.

Background thread là khi main thread kết thúc thì dù có mấy background thread thì chương trình cũng sẽ kết thúc
Còn foreground thread thì còn 1 foreground thread thì chương trình vẫn sẽ chạy.

Cách set background thread này hơi thô, vì lỡ thread cần giải phóng tài nguyên  gì đó nhưng bị bắt buộc ngừng thì ko dc

Cách phổ biến là tạo một biến quy định
![[Pasted image 20250218233545.png]]



khi new thread thì cho tham số là ThreadStart(phương thức) là cho trường hợp tái sử dụng phương thức và nếu phương thức có tham số nữa thì new ParameterizedThreadStart thay cho Threadstart.
![[Pasted image 20250218234518.png]]



![[Pasted image 20250218234637.png]]
Dùng as thì nếu không tương thích thì sẽ trả về null còn ép kiểu thường sẽ trả về exception

![[Pasted image 20250218234838.png]]
nếu hp null thì sẽ trả về null ,còn khác null sẽ trả về giá trị thuộc tính name
![[Pasted image 20250218235102.png]]
Dấu hai chấm hỏi là giá trị nếu hp null.


CancellationToken là cái quyết định một thread có chạy tiếp nữa hay không( hãy coi lại doc hoặc video nếu quên).
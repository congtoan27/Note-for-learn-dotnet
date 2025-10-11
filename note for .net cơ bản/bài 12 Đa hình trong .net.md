1. Khi mà mình khai báo một lớp cha và một lớp con của nó thì ở lớp cha nếu
   mình muốn lớp con nó override phương thức nào ở lớp cha thì phương thức đó dùng từ khóa "virtual"
   và phương thức ở lớp con cũng phải được đánh dấu với từ khóa override.
2. Nếu không có virtual và override thì khi mình gọi phương thức đó thì nó sẽ là
   một sự gọi hàm trực tiếp (tức lời gọi hàm đó sẽ được dịch ra và chỉ đến địa chỉ cố định
   của hàm đó trong bộ nhớ). Khi gọi bằng virtual và overide thì sẽ dc gọi qua một bảng gọi hàm ảo.
3. Từ khóa "sealed" để ngăn lớp con overide lại phương thức có từ khóa sealed của lớp cha.
4. Giả sử trong lớp cha có phương thức A với từ khóa virtual và lớp con cũng có 1
   phương thức A nhưng không có từ khóa override thì khi khai báo như hình dưới thì nó vẫn sẽ gọi phương
   thức ở lớp cha.Và chỉ khi mình khai báo biến đó là lớp con thì mới gọi đến phương thức ở lớp con.
   TÓM TẮT:
   Dùng từ khóa virtual để cho phép một hàm có thể được override lại trong lớp thừa kế.
   Dùng từ khóa override khi bạn muốn nạp chồng một phương thức, nếu thiếu từ khóa này,
   method của bạn sẽ là một method mới và không được tự động gọi nếu bạn gọi thông qua một biến thuộc lớp cha.
   Dùng từ khóa sealed nếu không muốn các lớp con override.
   ![[Pasted image 20251008000434.png]]
   ví dụ như lớp cha có phương thức A và lớp con kế thừa lớp cha và lớp con lai viết thêm phương thức A và phương thức A ở lớp cha không có virtual và phương thức A ở lớp con cũng không có overridden thì phương thức A của lớp con sẽ chỉ hoạt động khi tạo một object có kieur của lớp con (chú ý là kiểu ,đừng hiểu nhầm là tạo ra đối tượng lớp con ,Bird b1= new ....) và như ảnh trên là cách dùng new để nói rằng mình cố tình viết phương thức cùng tên phương thức ở lớp cha để có không warning

1. Khi mà mình khai báo một lớp cha và một lớp con của nó thì ở lớp cha nếu mình muốn lớp con nó override phương thức nào ở lớp cha thì phương thức đó dùng từ khóa "virtual" và phương thức ở lớp con cũng phải được đánh dấu với từ khóa override.
2. Nếu không có virtual và override thì khi mình gọi phương thức đó thì nó sẽ là một sự gọi hàm trực tiếp (tức lời gọi hàm đó sẽ được dịch ra và chỉ đến địa chỉ cố định của hàm đó trong bộ nhớ). Khi gọi bằng virtual và overide thì sẽ dc gọi qua một bảng gọi hàm ảo.
3. Từ khóa "sealed" để ngăn lớp con overide lại phương thức có từ khóa sealed của lớp cha.
4. Giả sử trong lớp cha có phương thức A với từ khóa virtual và lớp con cũng có 1 phương thức A nhưng không có từ khóa override thì khi khai báo như hình dưới thì nó vẫn sẽ gọi phương thức ở lớp cha.Và chỉ khi mình khai  báo biến đó là lớp con thì mới gọi đến phương thức ở lớp con.

 






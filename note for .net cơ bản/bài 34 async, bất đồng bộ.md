Task là lớp chưa thông tin của 1 phương thức bất đồng bộ gồm trạng thái, kết quả trả về, exception....
và để tạo một phương thức bất đồng bộ thì khai báo thêm "Task" và không có kiểu trả về là void với Task nhá vì Task chứa toàn bộ thông tin của 1 hàm async mà nó trả về void tức là không có gì nên dotnet không biết là await để đợi nó hoàn thành mà trả về máy trạng thái được.Thêm async trước Task.
await phải nằm ở trong hàm async và ngược lại thì nó mới có ý nghĩa.

Cơ chế
Trong hàm async nó chạy thì tới await thì nó sẽ trả về một object nội bộ (máy trạng thái) và máy trạng thái là các lệnh IO hay tạo thread gì đó rồi nó sẽ trả về luôn xong rồi mới thực hiện những dòng code ở dưới dòng await. tóm gọn là cứ tới await là nó return luôn rồi từ từ mới thực hiện mấy cái khác sau.



Note : Nếu có thể viết được 1 phương thức async thì ưu tiên viết vì hàm async có lợi nhiều hơn.
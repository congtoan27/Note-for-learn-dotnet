![[Pasted image 20250313003242.png]]
Cái hàm View() có hai option ,1 là nhận vào một object thì sẽ coi object đó là model, còn 2 là nhận vào một string thì sẽ coi nó là ViewName.
Khi mà route ở chỗ program với attribute MapControllerRoute thì thứ tự ưu tiên từ trên xuống dưới.
còn attribute UseRouting() là khi dùng sẽ map các url vào action method(không rõ vì nghe tới middleware gì đó)
Cách 2 :
![[Pasted image 20250313004122.png]]
như trên để chỉnh link, và int là để quy định kiểu đưa vào link đó.

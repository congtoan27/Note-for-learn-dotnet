
Cái lớp eventwaithandle này như người cầm cây cờ , khi dơ cờ có dữ liệu thì các thread vào lấy dữ liệu và ngược lại. có tham số là AutoReset hoặc ManualReset là tự tắt cờ tự động hay làm thủ công. Và thắc mắc tại sao ko chỉ dùng một biến bool để làm cây cờ mà phải dùng lớp này thì là do chúng ta sẽ phải dùng các vòng for lãng phí tài nguyên chỉ để kiểm tra giá trị của biến bool.

![[Pasted image 20250219004806.png]]

Set như là dơ cây cờ lên báo hiệu có dữ liệu. Ở đây đã khai báo chế độ auto reset nên ko cần code lệnh reset sau waitOne(), và giá trị true nghĩa là có dữ liệu ban đầu, và đoạn code trên sẽ lỗi vì Queue không có dữ liệu ban đầu mà mình set true nên nó chạy qua waitone nên lỗi.
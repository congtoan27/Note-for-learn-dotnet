![[Pasted image 20250122200827.png]]
Chú ý dòng 22 thì khi đặt tên nên đặt tên biến ngắn vì nó cũng sẽ tốn thời gian để pass chuỗi đó vào biến, vì khi log nhiều sẽ tốn thời gian nhiều hơn.
![[Pasted image 20250122201221.png]]
Ảnh trên để ghi chú là hàm IsEnabled để kiểm tra cấp độ logging đó đã được bật hay chưa, vì chương trình cũng sẽ tốn thời gian để tạo chuối (như LogTrace...) và cũng như kiểm tra thông tin này có được in ra hay không cũng tốn thời gian.
![[Pasted image 20250122201722.png]]
có thể định dạng thông tin (như trong ảnh là X là theo kiểu hexa).Search String.format để xem thêm các option khác nếu cần.

![[Pasted image 20250122201944.png]]
Có thể tạo filter cho logger bằng hàm addFilter( như trong ảnh là chỉ in log cấp độ warning và infomation


![[Pasted image 20250122202112.png]]
Khi thêm filter là trace thì nó sẽ cũng in ra trace mặc dù cấp đọ min là debug thôi , là vì trong filter nó sẽ override lại cả cái setMinLevel().

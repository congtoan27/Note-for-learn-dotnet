																					bộ nhớ trong (RAM hoặc ROM) thì có thể được đọc bởi CPU theo cơ chế đánh dấu địa chỉ còn bộ nhớ ngoài thì phải được đọc và ghi vào bộ nhớ trong thông qua một phương tiện gì đó như bus để đọc vào bộ nhớ trong (RAM  hoặc ROM) thì mới đọc được dữ liệu. Và quá trình đọc ghi dữ liệu từ bộ nhớ ngoài vào RAM hoặc từ RAM ra bộ nhớ ngoài thì thực hiện bằng stream.
																				khi mở file bộ nhớ ngoài thì hệ điều hành sẽ cấp phát vùng đệm để nhanh hơn vì bộ nhớ ngoài rất chậm so với bộ nhớ trong.
																				có cơ chế khóa, như là khi mình đang mở file con của 1 thư mục thì mình ko xóa được thư mục đó.




các bước là phải có path source hoặc des nếu move hoặc copy gì đó 
sau nó tạo vùng đệm buffer với kích thước tùy chọn
mở quyền đọc file (dòng 1 trong ảnh)
mở quyền viết
xong rồi đọc bằng cách lấy quyền đọc gọi lệnh Read()
while là để khi nào hết dữ liệu thì đóng stream bằng 2 dòng cuối
Từ khóa using thì không cần dùng 2 dòng cuối vì khi kết thúc thì sẽ tự động close stream lại.

![[Pasted image 20240925235858.png]]
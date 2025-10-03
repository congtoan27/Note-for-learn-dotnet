	bộ nhớ trong (RAM hoặc ROM) thì có thể được đọc bởi CPU theo cơ chế đánh dấu địa chỉ còn bộ nhớ ngoài 
    thì phải được đọc và ghi vào bộ nhớ trong thông qua một phương tiện gì đó như bus để đọc vào bộ nhớ
    trong (RAM  hoặc ROM) thì mới đọc được dữ liệu. Và quá trình đọc ghi dữ liệu từ bộ nhớ ngoài vào RAM hoặc 
    từ RAM ra bộ nhớ ngoài thì thực hiện bằng stream.
	khi mở file bộ nhớ ngoài thì hệ điều hành sẽ cấp phát vùng đệm để nhanh hơn vì bộ nhớ ngoài rất chậm 
    so với bộ nhớ trong.

    . quá trình mở file để đọc hoặc ghi thì hệ điều hành sẽ cấp phát thông tin hoặc cấu trúc dữ liệu liên quan tới file đó.
	có cơ chế khóa, như là khi mình đang mở file con của 1 thư mục thì mình ko xóa được thư mục đó.



  các bước là phải có path source hoặc des nếu move hoặc copy gì đó 
  sau nó tạo vùng đệm buffer với kích thước tùy chọn
mở quyền đọc file (dòng 1 trong ảnh)
mở quyền viết
xong rồi đọc bằng cách lấy quyền đọc gọi lệnh Read()
while là để khi nào hết dữ liệu thì đóng stream bằng 2 dòng cuối
Từ khóa using thì không cần dùng 2 dòng cuối vì khi kết thúc thì sẽ tự động close stream lại.

![[Pasted image 20240925235858.png]]




Tóm tắt:

- Stream ([https://learn.microsoft.com/en-us/dot...](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbEI5Nks2a0dqbjBqSUxMWHRfbXBnSnlDaWdpUXxBQ3Jtc0ttd2Q1OEtBcDczZHpobWxRUUQxNjBMT1huN21BS0tZWkdob0lKa181bW1IMF9DZC1kbk9lb09xQ3hqM2ZxUnpJZ3hmY244LTNid3NEUVlURmRDcllzNmhnY3Z0MUZOdVBTLTdocm0yR0RzMkRreGVCQQ&q=https%3A%2F%2Flearn.microsoft.com%2Fen-us%2Fdotnet%2Fapi%2Fsystem.io.stream&v=Rn9KEVEbLyE)) là kiểu dùng để đọc hoặc ghi dữ liệu lưu trữ trong các thiết bị ngoại vi, ví dụ như để đọc/ghi file hoặc socket mạng.
- Một số kiểu stream chỉ pho phép ghi, một số chỉ cho phép đọc, và một số cho phép cả hai.
- Để làm việc với file ta dùng FileStream.
- Các thao tác làm việc với file bao gồm: mở, đọc/ghi, đóng.
- Thao tác đóng luôn phải được thực hiện để giải phóng các tài nguyên chiếm giữ khi mở, đồng thời đẩy dữ liệu còn lại trong bộ đệm ra file. Để đảm bảo thao tác này luôn được thực hiện, ta có thể sử dụng cấu trúc try...catch...finally hoặc dùng using.
- Một số stream cho phép chúng ta nối vào một stream khác để cung cấp thêm tính năng cho nó, ví dụ BufferedStream cung cấp thêm bộ đệm dữ liệu giúp các thao tác đọc ghi trên các stream khác hiệu quả hơn.
- MemoryStream là một stream đặc biệt, nó không làm việc với thiết bị ngoại vi mà cung cấp khả năng đọc ghi dữ liệu trong bộ nhớ theo kiểu tuần tự.

Demo: Sử dụng System.IO để viết lệnh DIR và lệnh COPY. Bài tập: Viết một chương trình nhận vào tham số trên dòng lệnh là đường dẫn đến một thư mục, vẽ cây thư mục đó (giống lệnh tree: [https://www.geeksforgeeks.org/tree-co...](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbjJzb3l1bE5pc1d1b21DX0ttTVBuSnFVdmp0UXxBQ3Jtc0trMFJxZnR6NDNLbXRDeE9BSlBBeWlobE1OSWxGNngyQ2s5bHRucHpaQ0k0WF90OXN2VDYzd0tTV0x0SkpkMWxaLUp1c3NQQk4tUVpVblNGcUItZXpQQkJZd09PTFFjMk1scTJOZjhkQ2daaGNvV1ZYVQ&q=https%3A%2F%2Fwww.geeksforgeeks.org%2Ftree-command-unixlinux%2F&v=Rn9KEVEbLyE))

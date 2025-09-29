![[Pasted image 20250302144416.png]]
ở đây là có 2 cancelationToken là stopiingToken và CancelationTokenSource và sẽ tạo một cái token chung (là con của 2 token  vừa nói trên) và chúng ta sẽ code để token con đó sẽ ngừng khi 1 trong 2 cha ngừng. Ở trong bối cảnh video là để không cho phép 1 client nào giữ 1 connection quá lâu.

![[Pasted image 20250302145736.png]]
coi lại đoạn code này
![[Pasted image 20250302151410.png]]
![[Pasted image 20250302151809.png]]

![[Pasted image 20250304235519.png]]
Note: 1 http response bao gồm 1 dòng status sau và sau là 1 tập gồm không hoặc nhiều các header và sau header cuối cùng thì sẽ là 1 dòng trống và nếu response có nội dung trả về thì sau dòng trống đó là nội dung trả về (binary).


![[Pasted image 20250308004044.png]]
enum này dựa trên kiểu int
![[Pasted image 20250309194211.png]]

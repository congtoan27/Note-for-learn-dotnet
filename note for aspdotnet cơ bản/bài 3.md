Thì bình thường là một method public trong Controller thì nó sẽ được coi là 1 Action method và được map với 1 Url tương ứng, và sử dụng thuộc tính [NoneAction] cho method thì sẽ khiến method đó ko còn dc coi là Action method và không được map với url , tương tự với [NoneController] các hàm trong lớp không được định nghĩa là controller thông qua attribute này cũng sẽ không được map url .(NoneController có tình kế thừa nghĩa là lớp nào kế thừa lớp được gán NoneController thì cũng bị ảnh hưởng)
Nhóm thuộc tính http
HttpGet ,HttpPost...
Nhóm thuộc tính From: được áp dụng đối với các tham số trong Action method và quyết định nơi để lấy tham số đó ra và truyển vào cho Action method khi nó gọi.
From..,
Route


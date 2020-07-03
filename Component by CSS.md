==Nút trượt on/off==
- HTML : sử dụng thẻ input type checkbox
- CSS : 
+ sử dụng appearance: none để reset tất cả các thuộc tính của checkbox => không có gì như một thẻ div.
+  sau đó sử dụng :before để thêm nút tròn vào checkbox, bằng cách set height=width => hình vuông, radius => hình tròn, nhớ thêm position để set vị trí ban đầu khi chưa check. 
+  Sử dụng :checked kết hợp after để set vị trí của nút cho trạng thái checkbox đã click
==Form login==
- Có hiệu ứng khi click vào input thì User name sẽ trồi lên thành label của input
- HTML: 
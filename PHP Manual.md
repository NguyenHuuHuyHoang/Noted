==PHP Syntax==
	==PHP tags==
	- ![[Pasted image 20210513214307.png]]
	- Khi PHP thông dịch một file nó sẽ tìm kiếm thẻ mở và thẻ đóng, cặp thẻ sẽ báo cho PHP biết nơi bắt đầu và kết thúc thông dịch của đoạn code giữa cặp thẻ.
	- với cặp <?php ?> là cặp thẻ thông thường và <?= ?> là cách ghi tắt của nó
	- Ngoài ra còn có <? ?> là cặp thẻ ghi tắt cũng có tác dụng tương tự nhưng nó liên quan tới vấn đề tương thích vì vậy không khuyến cáo được sử dụng, nó hoạt động dựa vào giá trị short_open_tag trong file php.ini do đó thông người ta sẽ không được khuyến khích sử dụng cặp thẻ này
	- Trong trường hợp file php chỉ có mỗi code php không có code gì khác thì không cần phải có thẻ đóng chỉ cần thẻ mở thôi để ngăn chặn khoảng trắng ngẫu nhiên hoặc các dòng mới được thêm vào sau thẻ đóng PHP.
	==Escaping from HTML==
	- Mọi thứ sau cặp thẻ mở và thẻ đóng của PHP sẽ được trình thông dịch bỏ qua, điều đó giúp cho file php có thể chứa nhiều nội dung khác nhau, điều này cho phép chúng ta có thể nhúng các đoạn code PHP vào các văn bản HTML VD như tạo các bản mẫu
	- ![[Pasted image 20210513215936.png]] Khi trình thông dịch PHP đọc thấy thẻ đóng thì nó sẽ xuất tất cả những gì nó đọc được cho tới khi nó gặp tiếp thẻ mở.
		==VD 1 **Advanced escaping using conditions**==
		- ![[Pasted image 20210513220357.png]] - PHP sẽ bỏ qua những đoạn mà điều kiện không phù hợp, ngay cả khi chúng nằmg ngoài thẻ đóng và thẻ mở PHP, PHP bỏ qua chúng theo điều kiện vì trình thông dịch PHP nhảy qua các khối chứa điều kiện không phù hợp
		- Trong trường hợp với những đoạn văn bản lớn, việc bỏ chế độ phân tích cú pháp PHP thường hiệu quả hơn việc gửi tất cả văn bản thông qua echo hoặc prints
==Giới thiệu PHP==
+ PHP viết hồi quy của PHP Hypertext Preprocessor
+ PHP là ngôn ngữ lập trình kịch bản viết cho máy chủ được nhúng thẳng vào code HTML. Nó được sử dụng để xử lý nội dung động, DB, Session tracking,..
+ Nó được thích hợp với một số DB thông dụng như MySQL, PostgreSQL, Oracle, Sybase, Informix, và Microsoft SQL Server.
+ PHP thực thi rất tuyệt vời, đặc biệt khi được biên dịch như là một Apache Module trên Unix side. MySQL server, khi được khởi động thực thi các truy vấn phức tạp với các tập hợp kết quả khổng lồ trong thời gian record-setting.
+ PHP hỗ trợ một số lượng rộng rãi các giao thức lớn như POP3, IMAP, và LDAP. PHP4 bổ sung sự hỗ trợ cho Java và các cấu trúc đối tượng phân phối (COM và CORBA).
+ Cú pháp PHP là giống C.
==Lịch sử PHP==
+ PHP khởi đầu như là một dự án mã nguồn mở nhỏ, nhưng theo đà phát triển, ngày càng nhiều người thấy rằng nó càng ngày càng hữu ích.
+ PHP được phát triển từ một sản phẩm có tên là PHP/FI được tạo ra năm 1994, ban đầu nó được xem như là một tập con đơn giản của các mã kịch bản Perl để theo dõi tình hình truy cập đến bản sơ yếu lý lịch, nó được đặt tên là Personal Home Page Tools.
+ Khi cần đến các chức năng rộng hơn, tác giả đã viết ra một bộ thực thi bằng C lớn hơn để có thể truy vấn đến DB và giúp cho người sử dụng phát triển các ứng dụng web đơn giản. Tác giả (Rasmus) đã quyết định công bố mã nguồn của PHP/FI cho mọi người xem, sử dụng cũng như sửa các lỗi có trong nó, đồng thời cải tiến mã nguồn.
==Sự sử dụng chung của PHP==
+ PHP thực hiện các hàm hệ thống.  VD: từ các file trên một hệ thống, nó có thể tạo, mở, độc, ghi và đóng chúng.
+ PHP có thể xử lý các form. VD: thu thập dữ liệu từ file, lưu dữ liệu vào một file, thông qua email bạn có thể gửi dữ liệu, trả về dữ liệu tới người dùng.
+ Có thể CRUD các phần tử bên trong DB thông qua PHP
+ Truy cập các biến Cookie và thiết lập Cookie
+ Sử dụng PHP thì có thể hạn chế người dùng truy cập vào một số trang trong website
+ Có thể mã hóa dữ liệu
==Đặc trưng của PHP==
+ Đơn giản hóa
+ Hiệu quả
+ Bảo mật cao
+ Linh động
+ Thân thiện
==Code PHP trong HTML==
+ file HTML chứa code PHP sẽ được lưu dưới định dạng .php
+ Tất cả các code PHP phải được bao bên trong 1 trong 3 thẻ đánh dấu đặc biệt :
	+ <?php code ?> - Phổ biến nhất
	+ <? cođe ?>
	+ <script language="php"> code </script>
+ Đối với các site tĩnh hay là các website HTML khi người dùng yêu cầu xem một trang web thì yêu cầu đó sẽ được gửi về phí Server. Server ở đây chỉ đơn giản là gửi nội dung trang web mà người dùng muốn xem về trình duyệt cho người dùng.
+ Đối với các trang PHP khi có yêu cầu người xem trang web thì Server sẽ tiến hành phát sin htrang web đó từ mã nguồn PHP sang mã nguồn HTML, sau đó mới chuyển mã nguồn đó về trình duyệt web cho người dùng xem. Vì các trình duyệt web không thể đọc được các mã nguồn PHP mà chỉ đọc được các mã nguồn HTML.
==Cài đặt môi trường==
+ Để phát triển và chạy các trang PHP thì cần cài đặt:
	+ Web Server - PHP sẽ làm việc với hầu như tất cả phần mềm Web Server, bao gồm Internet Information Server (IIS) của Microsoft, nhưng sau đó Apache Server thường được sử dụng phổ biến hơn.
	+ DB - PHP sẽ làm việc với hầu như tất cả các phần mềm DB, gồm Oracle và Sybase, nhưng sau đó MySQL DB được sử dụng phổ biến nhất.
	+ PHP Parser - Để xử lý các lệnh PHP Script, một parser phải được cài đặt để tạo HTML output mà có thể được gửi tới trình duyệt web.
+ 
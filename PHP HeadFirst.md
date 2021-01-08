==Note==
- Đoạn code PHP được bọc trong <?php 'code thực thi' ?>
- Mọi dòng PHP statement phải được kết thúc bằng ;
- Nếu có bất kỳ code PHP nào trong 1 trang web, thì đặt tên .php thay vì .html
- Tên biến PHP phải bắt đầu bằng $
==Introducion==
- PHP is a server-side programming language - it runs on a web server
- PHP scripts must be run on a web server or they dont work
- form action="report.php" method="post" khi click vào thì form sẽ kích hoạt script report.php chạy trên server để xử lý dữ liệu form
- để kiểm tra web server đã được cài đạt PHP chưa sử dụng phpinfo(), nhớ delete sau khi kiểm tra.
- Trường hợp không có cài đặt PHP trên web server thì kiểm tra Appendix ii
- $_POST('email') dùng để lấy giá trị input của id email được gửi lên từ form thông qua phương thức POST
- $tên biến = dùng để lấy giá trị đang chứa của biến đó
==Finding perfect variable name==
- Ký tự đầu tiên phải được bắt đầu bằng $
- Tên biến phải dài ít nhất một ký tự
- Ký tự đầu tiên sau dấu $ có thể là một chữ hoặc một dấu gạch dưới và 1 chữ, một dấu gạch dưới hoặc một số
- Space hoặc ký tự đặc biệt không phải là _ hoặc $ không được tồn tại trong tên biến
- sử dụng toàn bộ chữ thường cho tên biến
- Sử dụng _ thay cho space giữa các chữ trong 1 chuỗi ký tự
- 
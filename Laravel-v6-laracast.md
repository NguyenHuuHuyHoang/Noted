==1. At a glance==
- Khi client truy cập 1 đường dẫn, thì nó sẽ gửi request tới server
- Server sẽ phân tích đường dẫn đó nó truy cập trang gì - route
- Sau đó sẽ chuyển đến controller tương ứng với trang đó
- Controller sẽ lấy nhưng dữ liệu cần thiết từ data base - eloquent Model
- Sau khi Controller đã lấy dữ liệu rồi thì nó sẽ gọi View và đổ dữ liệu đã lấy được vào đó để ra file HTML và trả lại cho client - blade
==2. Install PHP, SQL and composer==
- XAMPP - composer
==3. Laravel Installer==
- composer global require laravel/installer : để cài đặt Laravel Installer vào máy tính
- Kiểm tra đường dẫn %USERPROFILE%\Appdata\Roaming\Composer\vendor\bin bằng lệnh echo $PATH
- Tạo dự án mới bằng lệnh laravel new tên-dự-án
- Chạy dự án bằng lệnh php artisan serve
==4. Laravel Valet==
- Valet là môi trường ảo phát triển laravel không cần phải cài đặt Apache/Nginx.
- Yêu cầu hệ điều hành Mac và Homebrew.
==5. Basic Routing and Views==
- Các file route sẽ được đặt ở trong thư mục routes
- Trong 1 file route sẽ chứa các phương thức nhận vào request và trả về view
- Các file view được đặt trong folder resources->views
- Trong file view sẽ chứa các code html, css, js
- Đặt tên file view là tên-file.blade.php
- Trong trường hợp Route trả về 1 chuỗi string thay cho view file thì kết quả trả ra là chuỗi string đó ra màn hình
- Nếu trả về 1 Associative array thì sẽ trả về là json
- Tạo Route mới thì cần phải ::phương-thức('dường dẫn', hàm) trong hàm trả về view-string hoặc mảng kết hợp
==6. Pass request Data to Views==
- Trường hợp url có chứa data vd ?name=abc
- Thì ở trong route để bóc dữ liệu ra chúng ta sử dụng request('tên-key') - trong vd trên là name
- Ở trong view muốn xuất dữ liệu gì ra màn chình ta chỉ cần gọi tên biến đó ra VD: <h1><?= $name; ?></h1> thay vì echo
- Ngoài ra còn cách nữa là xài cặp dấu móc nhọn {{ }} và tên biến ở giữa, không cần phải mở và đóng tag php nó sẽ được complie thành dạng echo ở đường dẫn storage -> framework -> views -> các file php. Khi sử dụng {{}} thì laravel tự gọi htmlspecialchars xử lý trong đó luôn. Nếu {!!  biến  !!} thì sẽ không gọi htmlspecialchars mà chỉ in ra bình thường
- Trường hợp muốn truyền dữ liệu vào trong view thì chúng ta sẽ truyền tham số thứ 2 vào hàm view là một mảng gồm các key và value, VD ['name'=> $name] hoặc ['name'=> request('name')] 
- Chú ý nếu trường hợp url có chứa code script thì nó sẽ thực thi code vd ?name=<script>alert('hello');</script>
- Do đó ở trong view khi xử lý ta phải sử dụng htmlspecialchars(dữ liệu, ENT_QUOTES) thì khi đó nó không chạy script mà sẽ in ra thôi
==7. Route Wildcards==
- Trường hợp ở trong route chúng ta đặt param là '/posts/{post}' thì khi đó truyền bất cứ thứ gì sau /posts/xxxx thì cũng vào được route đó
- Và ở function trong route chúng ta truyền vào $post thì chúng ta sẽ có thể bắt được bất cứ thứ gì mọi người truyền vào sau posts/ VD posts/123 => $post = 123
- 
==Session 1 Prerequirisites and Setup==
==1. Introduction to MVC==
- Khi client truy cập 1 đường dẫn, thì nó sẽ gửi request tới server
- Server sẽ phân tích đường dẫn đó nó truy cập trang gì - route
- Sau đó sẽ chuyển đến controller tương ứng với trang đó
- Controller sẽ lấy nhưng dữ liệu cần thiết từ data base - eloquent Model
- Sau khi Controller đã lấy dữ liệu rồi thì nó sẽ gọi View và đổ dữ liệu đã lấy được vào đó để ra file HTML và trả lại cho client - blade
==2. Thiết lập môi trường và composer==
- Cài đặt composer
- Tạo 1 dự án laravel mới bằng lệnh composer create-project laravel/larvel example-app => cd example-app => php artisan serve
==3. The laravel installer tool==
- Cài đặt larvel installer ở global bằng composer global require laravel/installer 
- Tạo dự án bằng laravel new tên-dự-án => php artisan serve
==4. Why do we use tools==
==Session 2 The basics==
==5. How a route load a view==
- Các file route được đặt trong folder routes
- Tên của các file sẽ phụ thuộc vào ứng dụng của chúng vd: api, web, channel,...
- Channel.php là route phụ trách việc broadcasting, khi có điều gì đó xảy ra ở server sẽ gửi thông báo tới client. VD: Ứng dụng nhắn tin giữa các người dùng trong hệ thống, Khi A gửi tin nhắn cho B, thì sẽ thông báo cho B theo thời gian thực. Có thể hiển thị cửa sổ popup hoặc cảnh báo thông báo cho B về tin nhắn mới. Có thể kết hợp với thư viện Pusher để thực hiện việc gửi thông báo
- Mỗi một file route là một call back function, nó nhận vào 2 tham số, tham số 1 là param url, tham số 2 là 1 function trả về một view, '/' có nghĩa là homepage. Trường hợp request tới server không có cái route nào thì sẽ trả về 404
- View ở đây có thể là JSON nếu trả ra một mảng kết hợp - associative array, hoặc trả ra đoạn text nếu là string, trả ra 1 trang html nếu là 1 file view
- Các file view nằm trong resources/views. Tên file view được đặt theo cú pháp tên.blade.php. Ở trong view của route ta chỉ cần gõ view('tên') là laravel đủ hiểu ta gọi tên.blade.php
- Trong file view chứa các code html và css
==6. Include CSS and JS==
- File css sẽ được đặt trong folder public
- Trong file view, ở phần href của tag link tới file css sẽ theo đường dẫn "/tên_file.css"
- File js cũng được đặt trong folder public
- Trong file view, chúng ta link tư tượng như với file css với đường dẫn là "tên_file.js"
- Ngoài ra để quản lý file tốt hơn ta có thể đặt các folder css, js và bỏ các file vào
==7. Make a route and link to it==
- Tạo 1 route và ở route trả về 1 view
- Tạo 1 file view có tên trùng với view mà route đã tạo gọi
- Nội dung của file view là html
- Trong 1 file view để link tới 1 route khác thì ta dùng /post cho href của thẻ a
==8. Store Blog Post as HTML file==
- Thay vì sử dụng các file code thuần HTML ta có thể render ra nội dung dựa vào dữ liệu qua các biến truyền vào view
- Để làm được điều đó thì ở phần return của view ta sẽ truyền thêm 1 tham số là một associative array, Mảng này sẽ được truyền vào view, và ở trong view ta có thể lấy dữ liệu ra thông qua $'tên key' và đẩy vào giữa tag html
- Trong trường hợp ta tạo 1 folder ở resource và trong folder đó chứa các file html. Thì ở phần mảng truyền vào view ta có thể sử dụng file_get_contents($filename) VD: file_get_contents(__DIR__ . '/../resources/tên folder/tên file html. html'). __DIR__ trả về đường dẫn của file từ nơi nó được gọi, ở trong trường hợp này là folder routes
- Để bắt tất cả các path url sau /posts thì ở file route chúng ta sử dụng path 'posts/{post}' khi đó những gì sau dấu / của posts sẽ được truyền dưới tên post, khi đó ở function sau path chúng ta sẽ khai báo nhận vào 1 biến, ta có thể đặt tên bất kỳ, laravel sẽ tự truyền giá trị post vào biến đó. VD: 'posts/{post}', function ($slug) thì ở trong hàm function ta có thể lấy giá trị thông qua biến $slug và truyền vào file_get_contents trên kia để dynamic cái tên file html dựa vào url
- Tuy nhiên trường hợp truyền vào 1 tham số mà không có file sẽ gây ra lỗi cho nên chúng ta sẽ sử dụng file_exists($path) để kiểm tra xem có file không trước khi xử lý.
- Chúng ta có thể sử dụng dd($giá trị) để xem kết quả trả là cái gì, ở trường hợp trên có thể dd('file is not exist') ở trong vòng if, nếu xài ddd thì có nghĩa là dump, die, debug. Trường hợp ta sử dụng abort(404) thì sẽ trả ra 404 Not Found cho client hoặc nếu return redirect('/') thì sẽ chuyển ngược về homepage
==9. Route Wildcard Constraints==
- Với trường hợp truyền theo dạng {post} thì post có thể là bất cứ thứ gì, vì vậy ta có thể giới hạn lại nó có thể chỉ là số hoặc chữ mà thôi.
- Để làm việc đó thì ở ) cuối của phương thức get - route ta dùng 1 mũi tên hướng sang where(). VD -> where()
- Trong where chúng ta sẽ truyền vào tham số thứ nhất là tên biến đại diện cho giá trị, ở đây là post và tham số thứ 2 là 1 regex mà dựa vào nó kiểm tra xem có hợp lệ hay không. VD: where('post', '[A-z_\-]+') thì sẽ chấp nhận chữ và dấu - trong url, trường hợp truyền sai thì nó sẽ vào 404 luôn chứ không chạy vào route
- Cách đơn giản hơn là sử dụng whereAlpha('post') thay cho where ở trên, lưu ý là whereAlpha chỉ chấp nhận chữ thôi, có - sẽ không chấp nhận, do đó cần fix hàm gốc nếu cần -
- ngoài ra chúng ta cũng có các hàm where khác như whereAlphaNumeric, whereNumber
==10. Use Caching for expensive operations==
- Đối với những route nào mà có hoạt động nhiều, được truy cập nhiều thì để giảm thiểu việc xử lý ta nên xử dụng caching.
- Thường thì sử dụng để lưu dữ liệu thường xuyên được query từ DB
- Để sử dụng caching thì ta gọi cache()->remember()
- Trong remember, tham số 1 là key tên của cache, tham số 2 là thời gian lưu được tính bằng s, tham số 3 là 1 function, mà nó sẽ trả ra giá trị cần lưu. VD: cache() -> remember("posts.{slug}", 5, function() use (path) {return file_get_contents(path)}) - do ở bên trong function có xài biến path nên phải có use path
- Toàn bộ cục cache trên sẽ được gán cho 1 biến, biến đó chứa dữ liệu đã được cache trong vòng 5s, nếu ta refesh trang, dữ liệu còn trong 5s thì nó sẽ không chạy vào function, nếu qua 5s thì nó sẽ chạy vào function
- function trên có thể viết tắt là fn() => file_get_contents(path) thay cho phải có use
- Ở phần thời gian mặc định là s thì ta phải ngồi nhân từng số để ra với phút-giờ-ngày-tuần tương ứng thì ta có thể sử dụng now->addHour(số giờ) hoặc addDay, addWeeks, addMinutes,...
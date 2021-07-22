==1. Tại sao chọn PHP==
- Mã nguồn mở miễn phí
- Mạnh mẽ: 99% yêu cầu về web thì php có thể làm được và làm tốt
- Được sử dụng nhiều
- Chuyên viết cho môi trường web
- Có thể lập trình dưới dạng hướng đối tượng
- Có nhiều hỗ trợ và tài liệu hướng dẫn
- An toàn
==2. php info==
- Cách tiêu chuẩn <?php ?>, còn 1 cách khác gọn hơn là <? ?>
- phpinfo() là hàm dùng để xem cách cài đặt của server
- Trường hợp nếu chỉ có 1 dòng code thì khỏi ; cũng được
- Nếu đặt file là html thì các dòng code php đã bỏ qua không xử lý nên phải đặt file .php
==3. hello world==
- echo là language construct vì nó không có () mà là echo "hello world"
- print syntax cũng y chang print "Hello World"; nó hoạt động gần giống echo, nhưng nhanh hơn
- echo 3*5; //15
- dùng dấu . để nối hai chuỗi lại với nhau
==4. Nguyên lý hoạt động PHP==
- Trình duyệt gửi request đến server trang php, server sẽ đọc trang php đó xử lý thành html và gửi lại cho client
==5. Comment==
- Trong PHP có 3 cách 
- Comment 1 dòng thì sử dụng // hoặc dấu #, thường người ta sử dụng dấu // hơn vì không cần phải shift
- Comment 2 dòng hoặc nhiều hơn thì sử dụng /*nội dung comment*/
==6. Variables==
- Biến luôn phải bắt đầu bằng ký hiệu $
- Biến có thể là chữ số, gạch dưới, gạch ngang, nhưng không có dấu cách
- Ký tự ngay đằng sau ký hiệu $ phải là gạch dưới hoặc chữ không phải là số
- Biến trong PHP phân biệt giữa in hoa và in thường
- Biến phải được nằm trong dấu ngoặc kép khi muốn in
- Không nên đặt tên biến theo kiểu $_ vì php sẽ hiểu là global variable, VD $_SERVER (super global variable)
- Khi echo biến thì nên đặt giữa ngoặc nhọn và trong nháp kép {$bien}
- $_SERVER['SCRIPT_FILENAME'] = file đang xem
- $_SERVER['HTTP_USER_AGENT'] = thông tin của trình duyệt người dùng
- $_SERVER['SERVER_SOFTWARE'] = thông tin của server
==7. String==
- Sử dụng .= để nối chuỗi nhanh 
- strlen(string): đến số lượng ký tự
- strtoupper(string): Biến tất cả thành chữ viết hoa
- strtolower(string): Biến tất cả thành chữ thường
- ucfirst(string): in hoa chữ đầu tiên còn lại bt
- ucwords(string): in hoa mỗi chữ cái đầu
- str_replace(tim, thay the, chuoi tim): thay thế từ vào chỗ từ tìm được trong chuỗi nào đó
==8. Constant==
- Hằng số là những số có giá trị không đổi.
- Cách khai báo hằng số: define('TEN_HANG_SO', 'gia tri')
- hằng số thì không in bằng {$biến} được mà chỉ có thể sử dụng . để nối chuỗi với hằng số khi in ra
- PHP_VERSION : hằng số có sẵn của PHP - chứa phiên bản PHP
- PHP_OS: hệ điều hành
- Dùng để khai báo các giá trị không thay đổi vd user name, host, password khi kết nối DB
==9. Array==
- Nếu dùng 1 biến để chứa dữ liệu, VD: 1000 sinh viên thì phải dùng 1000 biến => do đó người ta sử dụng array để lưu trữ dữ liệu
- Có thể hình dung array như một ngăn kéo, nó chứa nhiều tệp khác nhau được sắp xếp từ 0 -> ++
- Khai báo 1 array thì như biến nhưng ở phần gán thì gán cho array(giá trị, giá trị, ...)
- Để lấy dữ liệu ra khỏi array thì sử dụng $tênbiến[vị trí]
- array có thể chứa array khác
- array có thể đặt lại tên cho từng index thay vì sử dụng 0 -> ... bằng cách array('a'=>'apple') => lấy giá trị bằng $array['a'] sẽ ra apple // associate array
- sử dụng hàm print_r($array) để in array ra màn hình cho dễ nhìn
- count($array) trả về số lượng phần tử có trong array
- max($array) trả về số lớn nhất trong mảng
- min($array) trả về số nhỏ nhất trong mảng
- sort($array) sắp xếp mảng từ nhỏ đến lớn
- rsort($array) sắp xếp mảng từ lớn đến nhỏ
- implode('ký tự nối', $array) nối các ô trong mảng lại thành 1 chuỗi với ký tự nối ở giữa các ô
- explode('ký tự đánh dấu',$string) cắt chuỗi thành array, mỗi ô array tương ứng với từng phần dựa theo ký tự đánh dấu
- end($array) lấy ra phần tử cuối cùng của mảng
- Thêm 1 phần tử vào array thì sử dụng $array[] = giá trị cần thêm vào mảng, nó sẽ được thêm vào cuối mảng
- array_splice($array, vị trí chèn vào, tham số lựa chọn, 'giá trị chèn vào') tham số lựa chọn 0 - chèn vào giữa, còn 1 thì là thay thế tại vị trí đó. 
- unset($array[index]) sẽ xóa index đó ra khỏi array, còn nếu đặt $array[index] = '' thì giá trị thành '' nhưng vẫn tồn tại index đó
- Để xóa nhiều phần tử liên tiếp của 1 array là sử dụng array_splice($array, vị trí bắt đầu xóa, số lượng phần tử xóa)
- array_merge($array1, $array2) dùng để ghép 2 mảng vào với nhau
- Ngoài ra còn có thể dùng dấu cộng để gộp 2 array lại với nhau. Trường hợp array1 có nhiều phần tử hơn array2 thì array1 + array2 thì sẽ không thấy array2 mà chỉ thấy array1 do 2 cái key đè lên nhau, nếu array2 + array1 thì sẽ thấy giá trị của array1 thay bằng array2, những ô mà array1 nhiều hơn vẫn giữ nguyên
- in_array('giá trị cần tìm', $array) nếu giá trị cần tìm có trong $array sẽ trả về true
- shuffle($array) đảo ngẫu nhiên vị trí trong array
- array_rand($array) lấy ngẫu nhiên 1 key trong array
- array_map('hàm muốn sử dụng', $array) chú ý là cái hàm muốn sử dụng dưới dạng string VD array_map('ucfirst', mảng) sẽ biến mọi ô trong array chữ cái đầu tiên thành viết hoa
- Khi làm việc với CSDL thì luôn luôn xuất CSDL dưới dạng array nên cần tìm hiểu array
- Dạy for each dùng với array
==10. Number==
- Có 2 loại là số nguyên và số thập phân
- round($num) sẽ làm tròn thành số nguyên, nếu round(num, 1) thì sẽ làm tròn thành 3,1
- ceil($num) làm tròn lên
- floor($num) làm tròn xuống
- rand() cho ra 1 số ngẫu nhiên
- rand(1,100) cho ra 1 số ngẫu nhiên từ 1-100
- range(1,31) tạo ra 1 mảng chứa giá trị từ 1-31, nếu range(1,31,10) => 10,20,30...
- number_format($num) sẽ format số có dấu phẩy đơn vị, nếu number_format(num, 1) sẽ thêm 1 ký tự thập phân vào sau cùng
==11. If else==
- Mệnh đề điều kiện if..else, nếu đúng thì làm gì, nếu sai làm gì
- DEMO làm chào người dùng theo nam hoặc nữ
- isset($bien) là 1 hàm kiểm tra một giá trị có được set hay không có null hay không. Khi xử lý form thì luôn luôn sử dụng cái này
- Đây là xương sống của một ngôn ngữ lập trình, để phân luồng xử lý code
==12. logical operator==
- demo bằng việc upload hình, cho giả sử gửi hình phải có đuôi jpg, png, gif và dung lượng dưới 500KB thì mới được gửi
- Sử dụng explode để bóc cái đuôi của tên file lấy phần mở rộng, sử dụng end để lấy cái đuôi ra
==13. switch==
- Demo cho bắt level, nếu 1 thì user, 2 là edit, 3 là delete, còn lại đăng ký
==14. for loop==
- Đa phần vòng for dùng như 1 bộ đếm
- VD làm phân trang

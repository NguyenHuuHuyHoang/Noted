- $user = "John" - khai báo và gán giá trị cho biến
- echo $user - in ra màn hình giá trị của biến
- PHP có nhiều loại biến, nhưng những kiểu biến cơ bản là integer, float, strings và boolean
- Biến có thể đặt giá trị là NULL, có nghĩa là biến tồn tại nhưng không có bất kỳ giá trị gì
==simple array==
- Array là một kiểu biến đặt biệt mà nó chứa nhiều biến dưới dạng một danh sách
- $odd_numbers = [1,3,5,7,9] - Khai báo một array
- Chúng ta có thể truy xuất giá trị của từng ô trong array thông qua index của nó. VD $odd_numbers[0] => 1
- sử dụng print_r(array) để in ra màn hình giá trị của array (các index và giá trị chứa trong index đó)
- Một số hàm thông dụng
	- count(array) - trả ra số lượng phần tử mà mảng có
	- reset(array) - trả ra giá trị của phần tử đầu tiên của mảng ngược với reset là end, trả về giá trị của phần tử cuối cùng của mảng, ngoài cách sử dụng end chúng ta có thể sử dụng count để tìm số index cuối cùng của array và truy xuất vào.
- Stack and queue functions
	- Để thêm một phần tử vào mảng từ cuối cùng chúng ta sử dụng array_push(tên mảng, giá trị đẩy vào)
	- Để đẩy phần tử cuối cùng của mảng ra, chúng ta sử dụng array_pop(tên mảng).
	- Để thêm một phần tử vào mảng từ đầu thì chúng ta sử dụng array_unshift(tên mảng, giá trị).
	- Để đẩy phần tử đầu tiên của mảng ra ngoài chúng ta sử dụng array_shift(tên mảng)
- Để nối hai hoặc nhiều mảng lại với nhau thành một mảng chúng ta sử dụng array_merge(tên mảng 1, tên mảng 2, tên mảng 3) -> cần 1 biến hứng giá trị trả ra
- Để sắp xếp mảng theo tăng dần chúng ta sử dụng sort(tên mảng) - mảng sẽ bị thay đổi. Để sort theo giảm dần chúng ta sử dụng rsort(tên mảng)
- Advanced array functions
	- array_slice(mảng, số lượng phần tử) sẽ trả ra một mảng mới chứa các phần tử của mảng cũ theo quy tắc, nếu số phần tử là dương thì sẽ là những phần tử còn lại sau khi bỏ số lượng phần tử ra (tính từ đầu). Nếu là số âm thì sẽ trả ra số phần tử (tính từ cuối mảng). VD array_slide([1,2,3,4,5,6], số phần tử). Nếu số phần từ là 2 thì trả ra là 3,4,5,6 nếu -2 thì trả ra 5,6
	- array_slice(mảng, số phần tử bỏ ra (tính từ đầu mảng), số phần tử lấy (tính từ đầu mảng sau khi bỏ ra n phần tử)) vd array_slide([1,2,3,4,5,6],3,2) trả ra là 4,5
	- array_splice(mảng, số phần tử bỏ ra, số phần tử lấy) phương thức này trả ra giống giá trị array_slice nhưng khác ở chỗ nó làm thay đổi mảng ban đầu còn slice thì không.
==array with keys==
	- PHP array thực chất là một bản đồ, có nghĩa là mọi giá trị của mảng đều có key. Khi sử dụng mảng như những danh sách cơ bản thì key là các giá trị 0,1,2,3,... mỗi phần tử được thêm vào mảng sẽ được gắn cho key có giá trị tăng thêm 1
	- Một ví dụ tốt cho việc sử dụng array with keys là một danh bạ điện thoại, mỗi tên một người sẽ có một số điện thoại, mình sẽ truy xuất số điện thoại của 1 người nào đó bằng tên người đó.
	- $phone_numbers = ["Alex" => "415-235-8573", "Jessica " => "415-492-4856"] - Cách khai báo mảng với các khóa
	- Để thêm một phần tử vào một mảng sử dụng một khóa chúng ta sử dụng cú pháp $phone_numbers["Michael"] = "415-32534-323";
	- Để kiểm tra một khóa đã tồn tại trong mảng hay chưa chúng ta sử dụng hàm array_key_exists. Cú pháp array_key_exists(tên khóa, mảng), giá trị trả ra là true or false
	- array_keys(mảng) trả về một mảng các keys của mảng đó.
	- array_values(mảng) trả về một mảng các giá trị của mảng đó.
==multidimesional arrays==
- Mảng nhiều chiều là một mảng chứa một mảng khác trong nó.
- print_r vẫn có thể in được mảng nhiều chiều ra màn hình.
==Strings==
- string là một biến lưu trữ đoạn văng bản, VD: chứa tên
- Để nối hai chuổi lại với nhau sử dụng . (dấu chấm) VD: $name = $first_name . " " . $last_name;
- Để đếm số lượng ký tự trong một chữ sử dụng strlen($string), kết quả trả về là số lượng ký tự chứa trong chuỗi.
- Để cắt một phần chuỗi và trả về nó dưới dạng một chuỗi mới, chúng ta có thể sử dụng hàm substr(chuỗi, số lượng ký tự cắt), sẽ trả về chuỗi sau khi cắt n ký tự, trường hợp số ký tự truyền vào là số âm thì sẽ trả về chuỗi số ký tự tính từ đuôi chuỗi
- Chúng ta có thể ghép những array thành chuỗi cũng như có thể cắt chuỗi thành array thông qua explode(" ", chuỗi) và implode(" ", array). Kết quả trả về là array với explode và string với implode.
==For loop==
- Vòng lặp for là những vòng lặp đơn giản giúp chúng ta duyệt qua các giá trị bằng cách sử dụng index, có hai loại vòng lặp for là for loop và foreach loop
- Vòng lặp for rất hiệu quả khi chúng ta cần duyệt qua một mảng và tham chiếu đến phần tử của mảng đó thông qua giá trị index. 
- for (inittialization; condition; increment) { nội dung xử lý cho từng vòng lặp}.
==Foreach loop==
- vòng lặp foreach lặp qua một phần tử có trạng thái lặp đi lặp lại nhiều lần (iterable element), như là một mảng hoặc một đối tượng, nó cung cấp những phần tử trong một biến đặt biệt tại một thời điểm
- cú pháp foreach(mảng as phần tử mảng) - duyệt mảng cơ bản
- đối với mảng kèm keys thì sử dụng cú pháp foreach(mảng as key => giá trị)
==while loop==
- Vòng lặp while là những block code đơn giản sẽ thực thi lặp đi lặp lại cho tới khi điều kiện lặp không thỏa.
- cú pháp while (điều kiện) {}
- Sự khác biệt chính giữa vòng lặp for và while là for thì thường được sử dụng để lặp qua một mảng hoặc một đối tượng, while thì thực hiện với số lần không biết được, tùy thuộc vào điều kiện biến, ví dụ một người nhập vào giá trị đúng.
- Những vòng lặp được điều khiển bằng cách sử dụng break và continue. Nó có ít trong vòng lặp while rất nhiều. Break sẽ ngay lập tức thoát khỏi vòng lặp, trong khi continue sẽ trở lên trên cùng của vòng lặp while, kiểm tra lại điều kiện lặp.
==functions==
- Các hàm là những khối code đơn giản có thể được gọi từ bất cứ đâu.
- Có  hai loại hàm là hàm thư viện và hàm người sử dụng . Hàm thư viện như: array_push là một phần của thư viện PHP và có thể sử dụng bởi bất cứ ai. tuy nhiên chúng ta có thể viết những hàm của chúng ta và sử dụng nó trong xuyên suốt code của chúng ta.
- Một mà nhận một danh sách các tham số được phân tách ra bằng dấu phấy. Mọi  tham số chỉ tồn tại bên trong hàm, có nghĩa là chúng nó trở thành những biến bên trong khố hàm, những không được định nghĩa bên ngoài của khối hàm.
- Sau khi định nghĩa hàm, chúng ta có thể load những file PHP khác vào một file khác, vậy vậy chúng ta có thể khai bao tất cả các hàm trong một file và load chúng cho một file khác. load thông qua include(tên file).
==Objects==
- PHP là một ngôn ngữ hướng đối tượng, mặc dù nó không phải được sử dụng như một ngôn ngữ, vì hầu hết các hàm PHP không phải là hướng đối tượng.
- Trong việc lập trình hướng đối tượng, một lớp được định nghĩa là một đối tượng,  trong khi một đối tượng là một thể hiện của một đối tượng, nghĩa là từ một lớp có thể tạo ra nhiều đối tượng.
- VD: khởi tạo đối tượng ![[Pasted image 20210111210050.png]]. Lớp Student có một hàm khởi tạo, nó sẽ được thực thi mỗi khi một đối tượng được tạo. Hàm khởi tạo nhận các tham số mà nó sẽ được cung cấp khi khởi tạo đối tượng bằng từ khóa new. 
	- hàm khởi tạo tên là __construct.
	- khai báo thuộc tính của đối tượng bằng cú pháp: $this -> tên thuộc tính = giá trị thuộc tính.
	- truy xuất giá trị thuộc tính bằng $this->tên thuộc tính.
	- gọi tên phương thức của đối tượng bằng cú pháp đối-tượng -> tên phương thức().
	- tạo một thể hiện của một lớp bằng cú pháp tên-biến = new tên-lớp();
- Class: xác định cách thức mà đối tượng hoạt động. Classes không chứa dữ liệu.
- Objects: là những thể hiện của lớp đối tượng, nó chứa dữ liệu.
- Members: là những biếng mà thuộc về một đối tượng
- Methods: là những hàm bà thuộc về một đối tượng, và có thể truy cập đến những member của nó.
- Constructor là một phương thức đặt biệt mà nó sẽ được thực thi khi một đối tượng được tạo ra.
	- ==Inheritance==: đặc tính quan trọng nhất của một ngôn ngữ lập trình hướng đối tượng là sự kế thừa. Đặc tính này cho phép chúng ta tái sử dụng code mà chúng ta đã viết và mở rộng nó. cú pháp khai báo là class tên-lớp-kế-thừa extends tên-lớp-cha.
	- Lớp con sẽ có hàm khởi tạo và phương thức của lớp cha, khi khai báo một phương thức mới cho lớp con, thì phương thức này cũng truy xuất được các thuộc tính đã được khai báo ở lớp cha.
- ==Public và Private functions==
	- Chúng ta có thể sử dụng public và private để xác định phương thức nào có thể được truy xuất bên ngoài lớp, phương thức nào không. Điều này làm tăng tính bảo mật, giúp tách biệt những phương thức nào sử dụng nội bộ, những phương thức nào có thể được sử dụng ở bên ngoài
==PHP exceptions==
- PHP có mô hình ngoại lệ gần giống với những ngôn ngữ lập trình khác. Một ngoại lệ có thể được đưa ra và bắt trong PHP. Code có thể được bọc bởi một khối try, để tạo tạo điều kiện bắt ra những lỗi tìm ẩnh, mỗi lần try phải có ít nhất một catch hoặc finally.
- Ví dụ: ![[Pasted image 20210111214819.png]]. Nhiều khối catch có thể được sử dụng để bắt các ngoại lệ khác nhau.
- Trong trường hợp không sử dụng try - catch thì có thể sử dụng throw new Exception("nội dung"). ![[Pasted image 20210111221128.png]]. Khi một ngoại lệ được quăng ra thì code PHP tiếp theo sẽ không được thực thi.
- Từ PHP 5.5++, finally block có thể được khai báo sau hoặc thay cho catch block. Các code trong finally block luôn được thực thi, bất kể ngay cả khi một ngoại lệ được đưa ra, thì code vẫn được thực thi bình thường. ![[Pasted image 20210111221605.png]]

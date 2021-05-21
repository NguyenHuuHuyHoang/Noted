==Basic PHP Syntax==
- Một PHP script có thể đặt bất kỳ đâu trong văn bản
- Một PHP script bắt đầu bằng <?php và kết thúc với ?>
- Một file php bình thường chứa các thẻ HTML và một số code PHP
- Một đoạn PHP kết thúc với dấu ; nếu không có sẽ bị lỗi
- Trong PHP có một hàm được xây dựng sẵn để xuất dữ liệu trên một trang web là echo
==PHP Case Sensitivy==
- Trong PHP các từ khóa như if, else, while,... classes, functions và các hàm tự định nghĩa thì không có phân biệt chữ hoa và chữ thường, VD: ECHO echo EcHo điều chạy được
-  Tuy nhiên tất cả các tên biến điều phân biệt chữ hoa thường, VD: $color khác với $Color
==PHP Comments==
- Comments trong PHP là những đoạn code không được thực thi như một phần của chương trình, khi PHP engine nó thông dịch các comment nó sẽ bỏ qua.
- Comment có thể được sử dụng để: người khác hiểu code của mình, để nhắc nhở bản thân mình những gì mình đã làm.
- Các cách để comment code:
- Comment 1 dòng bằng ký tự // hoặc # ở đầu nội dung muốn comment, nếu muốn comment cho 1 đoạn code nào đó thì các ký tự // hoặc # phải được đặt ở sau dấu ;
- Comment nhiều dòng bằng ký tự /* ở bắt đầu và */ ở kết thúc, cái này còn có thể loại bỏ 1 phần đoạn code mà không cần ảnh hưởng phần còn lại.
==PHP Variables==
- Biến là những vật chứa nhằm lưu trữ dữ liệu
- Trong PHP một biến được bắt đầu bằng dấu $, theo sau nó là tên của biến
- Tên của một biến phải được bắt đầu với một ký tự hoặc một ký tự gạch dưới (_), không được bắt đầu bằng số, Tên của biến có thể chứa các ký tự từ A-z, 0 - 9 và _
- Biến phân biệt hoa thường, $age và $AGE là hai biến khác nhau
- Khi chúng ta gán một văn bản cho một biến thì phải đặt nó giữa cặp dấu ngoặc kép
- Không giống như các ngôn ngữ lập trình khác, PHP không có lệnh khai báo một biến, nó được tạo ngay thời điểm gán giá trị cho nó lần đầu.
- echo thường được dùng để xuất giá trị ra màn hình
==PHP Variable Scope==
- Trong PHP 1 biến có thể được khai báo bất cứ đâu trong code
- Tầm vực biến là một phần của đoạn code nơi biến có thể được tham chiếu hoặc sử dụng
- Có ba loại tầm vực biến khác nhau là: local, global, static
	==Global and Local Scope==
	- Các biến được khai báo bên ngoài function có tầm vực là global, nó có thể được gọi trong các hàm
	- Các biến được khai báo bên trong function có tầm vực là local, nó chỉ có thể gọi được bên trong hàm mà nó được khai báo, ra ngoài khỏi hàm là không thể gọi được nữa.
	- Chúng ta có thể có các biến có tên giống nhau trong những hàm khác nhau bởi vì những biến local chỉ có thể nhận biết bởi những hàm mà nó được khai báo bên trong
	==PHP The global keyword==
	- Từ khóa global được sử dụng để truy cập 1 biến toàn cục trong một hàm, để làm được điều đó chúng ta phải sử dụng global trước biến trong 1 function ![[Pasted image 20210514192324.png]]
	- PHP cũng lưu trữ tất cả các biến toàn cục trong một array được gọi là $GLOBALS[index]. index là tên của biến, array này cũng được truy xuất bên trong của một function và có thể được sử dụng để cập nhật trực tiếp giá trị của biến toàn cục
	==PHP The static keyword==
	- Thông thường khi một function được thực thi, tất cả mọi biến của nó sẽ được xóa. Tuy nhiên đôi khi chúng ta muốn một biến cục bộ không bị xóa, chúng ta cần nó cho một công việc nào đó trong tương lai, để làm được điều đó chúng ta sử dụng từ khóa static khi khai báo biến lần đầu.
	- ![[Pasted image 20210514192733.png]]
	- Khi này mỗi lần function được gọi, biến đó sẽ vẫn lưu trữ giá trị mà nó chứa trong lần cuối cùng function được gọi, Lưu ý biến static vẫn có tầm vực biến là local đối với function
==PHP echo and print Statement==
- Với PHP có hai phương pháp xuất dữ liệu cơ bản là echo và print
- echo và print có điểm giống nhau là được sử dụng để xuất dữ liệu ra màn hình
- điểm khác nhau là: echo không trả về giá trị trong khi print thì trả về giá trị là 1 vì vậy nó có thể được sử dụng trong các biểu thức. Ngoài ra echo có thể nhận nhiều tham số trong khi print chỉ có thể nhận được 1 tham số. echo nhanh hơn print một chút
- echo có thể được sử dụng có hoặc không có (): echo hoặc echo()
- print có thể được sử dụng có hoặc không có (): print hoặc print()
==PHP Data Types==
- Biến có thể chứa nhiều kiểu dữ liệu khác nhau, và những kiểu dữ liệu khác nhau có thể thực hiện các việc khác nhau
- Các kiểu dữ liệu PHP hỗ trợ là String, Integer, Float (dấu phẩy động, còn gọi là double), Boolean, Array, Object, NULL, Resource
	==PHP String==
	- Chuỗi là một chuỗi các ký tự, một chuỗi có thể là bất kỳ văn bản nào bên trong dấu ngoặc kép hoặc ngoặc đơn
	==PHP Integer==
	- Một số nguyên là một số không có dấu phẩy nằm giữa -2,147,483,648 và 2,147,483,647
	- Một số nguyên phải có ít nhất một chữ số
	- Một số nguyên không được có dấu thập phân
	- Một số nguyên có thể là số dương hoặc số âm
	- Trong PHP có hàm var_dump() để trả về kiểu dữ liệu và giá trị của một biến ![[Pasted image 20210514194922.png]]
	==PHP Float==
	- Một số thực (số dấu phẩy động) là một số có đấu thập phân hoặc một số ở dạng hàm mũ ![[Pasted image 20210514195118.png]]
	==PHP Boolean==
	- Một Boolean có hai trạng thái là true hoặc false
	- Boolean thường được sử dụng trong kiểm tra điều kiện
	==PHP Array==
	- Một mảng chứa nhiều giá trị trong một biến
	- ![[Pasted image 20210514195253.png]]
	==PHP Object==
	- Các lớp và các đối tượng là hai khía cạnh chính lập trình hướng đối tượng.
	- Một lớp là một khuôn mẫu cho các đối tượng và một đối tượng là thể hiện của một lớp
	- Khi các đối tượng riêng lẻ được tạo ra, chúng có tất cả các thuộc tính và phương thức từ lớp, nhưng mỗi đối tượng sẽ có các giá trị thuộc tính khác nhau
	- Giả sử ta có lớp Car, từ lớp này ta thể hiện ra thực tế các đối tượng như Volvo, BMW,.. thì các đối tượng này sẽ có các thuộc tính và phương thức từ lớp Car nhưng mỗi đối tượng sẽ có các giá trị thuộc tính khác nhau
	- Nếu chúng ta khai báo một hàm __construct(), PHP sẽ tự động gọi hàm này khi tạo một đối tượng từ một lớp
	==PHP NULL Value==
	- Null là một kiểu giá trị đặc biệt, nó chỉ có một giá trị duy nhất là NULL
	- Một biến giá trị NULL là một biến không có giá trị nào gán vào nó, nếu chúng ta khai báo một biến mà không có một giá trị, nó sẽ được tự động gán giá trị là NULL
	- Một biến có thể được cho rỗng bằng các gán giá trị NULL cho nó
	==PHP Resource==
	- Đây là một kiểu tài nguyên đặc biệt, nó không phải là kiểu dữ liệu thực tế. Nó là việc lưu trữ một tham chiếu đến các hàm và tài nguyên bên ngoài PHP
	- Một ví dụ phổ biến của việc sử dụng kiểu dữ liệu tài nguyên là một cuộc gọi lên cơ sở dữ liệu
==PHP Strings==
- Một chuỗi là một đoạn chuỗi các ký tự
- strlen() là hàm trả về chiều dài của một chuỗi
- str_word_count() là hàm trả về số lượng từ trong chuỗi, VD: Hello world! ra là 2
- strrev() là hàmg sẽ đảo ngược lại chuỗi
- strpos() là hàm sẽ tìm một đoạn chữ trong một chuỗi, nếu tìm được nó sẽ trả về vị trí của ký tự đầu tiên của kết quả tìm được, nếu không tìm được nó sẽ trả về false. echo strpos("Hello world!", "world"); // outputs 6.
- Lưu ý ký tự đầu tiên của một chuỗi là 0 không phải là 1
- str_replace() thay thế một số ký tự với một số ký tự khác trong một chuỗi. echo str_replace("world", "Dolly", "Hello world!"); // outputs Hello Dolly!
- explode() biến một chuỗi thành một mảng
==PHP Numbers==
- PHP tự động chuyển đổi kiểu dữ liệu  vì vậy khi chúng ta gán một số nguyên cho một biến, kiểu dữ liệu của biến đó sẽ là integer, sau đó nếu ta gán một chuỗi cho cùng biến thì kiểu dữ liệu sẽ chuyển thành string, việc chuyển đổi kiểu dữ liệu tự động này đôi khi sẽ gây ra lỗi code
- Một số nguyên có giá trị từ -2147483648 đến 2147483647 trong hệ thống 32 bit và từ -9223372036854775808 đến 9223372036854775807 với hệ thống 64 bit. Một giá trị lớn hơn hoặc nhỏ hơn các giá trị trên sẽ được lưu dưới dạng số thực bởi vị nó vượt quá giới hạn của một số nguyên
- Nếu ta lấy 4 * 2.5 ra 10, thì kết quả vẫn được lưu ở dưới dạng số thực vì một trong toán hạn là số thực
- PHP có các hằng số được xác định cho các số nguyên là:
- PHP_INT_MAX số nguyên lớn nhất được hỗ trợ
- PHP_INT_MIN số nguyên nhỏ nhất được hỗ trợ
- PHP_INT_SIZE kích thước của một số nguyên tính bằng byte
- Ngoài ra PHP còn có các function để kiểm tra xem kiểu của một biến có phải là số nguyên hay không là:
- is_int(), is_integer(), is_long()
==PHP Float==
- Kiểu dữ float có độ chính xác tối đa là 14 chữ số và nó có thể lưu trữ giá trị lên đến 1.7976931348623E+308
- Từ PHP 7.2 thì có các hằng số được xác định cho các số thực là :
- PHP_FLOAT_MAX là số thực có thể biểu diễn lớn nhất
- PHP_FLOAT_MIN là số thực dương nhỏ nhất có thể biểu diễn được
- - PHP_FLOAT_MAX (có dấu trừ ở trước) là số thực âm nhỏ nhất có thể biểu diễn được
- PHP_FLOAT_DIG là số chữ số thập phân có thể được làm tròn thành số float và ngược lại mà không bị mất độ chính xác
- PHP_FLOAT_EPSILON là số dương nhỏ nhất có thể biểu diễn x sao cho x + 1,0! = 1,0
- PHP có các hàm để kiểm tra xem kiểu của một biến có phải là float hay không là is_float(), is_double()
==PHP Infinity==
- Một giá trị số mà nó lớn hơn PHP_FLOAT_MAX được xem như là vô hạn.
- PHP có hàm để kiểm tra một giá trị có hữu hạn hoặc vô hạn là is_finite() và is_infinite(), ngoài ra sử dụng var_dump thì cũng sẽ nhận được kết quả là float(INF) nếu value là số vô hạn
==PHP NaN==
- NaN có nghĩa là không phải là một số (Not a Number)
- NaN thường cho những phép toán bất khả thi
- Trong PHP có hàm để check một giá trị không phải là một số là is_nan()
- Tuy nhiên var_dump cũng sẽ trả ra giá trị là float(NAN)
==PHP Numberical Strings==
- Trong PHP có hàm dùng để kiểm tra 1 biến có phải là một số hay không là is_numeric(). hàm này sẽ trả về giá trị true nếu biến là một số hoặc một chuỗi số
- Từ PHP 7.0 is_numeric() sẽ luôn trả về giá trị false cho một chuỗi số ở dạng thập lục phân, vì nó không được coi là một chuỗi số
- ![[Pasted image 20210514203859.png]]
==Casting Strings and Floats to Integers==
- Đôi khi chúng ta cần phải chuyển một số thành một kiểu dữ liệu khác
- (int), (integer) hoặc intval() là những hàm thường được sử dụng để biến đổi một giá trị thành một số nguyên
- (int)$x -> biến đổi giá trị $x từ float hoặc string thành số nguyên
==PHP Math==
- pi() trả về giá trị của số PI
- min() trả về giá trị nhỏ nhất của một danh sách các tham số truyền vào
- max() trả về giá trị lớn nhất của một danh sách các tham số truyền vào
- abs() là hàm được dùng để trả ra giá trị tuyệt đối của một số
- sqrt() là hàm bình phương một số
- round() là hàm làm tròn một số thực thành số nguyên gần nhất, nếu sau dấu phẩy từ năm trở lên thì sẽ làm trò lên, còn nếu nhỏ hơn 5 sẽ làm tròn xuống
- rand() là hàm để tạo ngẫu nhiên số, nếu không truyền tham số vào thì nó sẽ chạy tự do còn nếu ta truyền 2 tham số vào là min và max thì nó sẽ trả ra giá trị giữa hai số min và max, lưu ý giá trị trả ra là số nguyên
==PHP Constants==
- Hằng số giống nhưng một biến ngoại trừ một việc là khi đã được khai báo thì không thể thay đổi giá trị của nó.
- Tên của một hằng số hợp lệ là bắt đầu bằng một chữ cái hoặc dấu gạch dưới, không có $ ở trước tên của hằng số
- Lưu ý: hằng số luôn luôn có tầm vực biến là toàn cục trên toàn bộ code
- Để khai báo hằng số thì chúng ta có thể sử dụng hàm define(), hàm này nhận vào ba tham số là tên của hằng số, giá trị của hằng số và chỉ định có phân biệt chữ hoa chữ thường hay không, mặc định là không - false (nếu truyền 2 tham số thì sẽ không phân biệt hoa thường)
- Từ PHP 7.0 trở đi thì hằng số có thể chứa dữ liệu của một mảng
==PHP Operators==
	==PHP Arithmetic Operators==
	- +, - , *, / chia lấy thương, % lấy phần dư, * *(lũy thừa vd a* *b sẽ là a^b)
	==PHP Assignment Operators==
	- =, +=, -=, *=, /=, %=
	==PHP Comparison Operators==
	- == so sánh bằng, true nếu x và y cùng giá trị, không xem xét là cùng kiểu dữ liệu hay không
	- === trả về true nếu cùng giá trị và cùng kiểu dữ liệu
	- != Trả về true nếu x không y
	- <> trả về true nếu x không bằng y
	- !== trả về true nếu không cùng giá trị hoặc không cùng kiểu dữ liệu
	- > lớn hơn
	- < nhỏ hơn
	- >= lớn hơn bằng
	- <= nhỏ hơn bằng
	- <=> trả về trừ -1 nếu x nhỏ hơn y, 0 nếu bằng nhau và 1 nếu x lớn hơn y, được giới thiệu từ PHP 7.0
	==PHP Increment / Decrement Operators==
	- ++$x tăng biến x lên một sau đó trả về giá trị x
	- $x++ trả về giá trị x sau đó tăng lên 1
	- Tương tự với --$x và $x--
	==PHP Logical Operator==
	- and trả về true nếu cả x và y là true
	- or trả về true nếu một trong hai x hoặc y là true
	- xor trả về true nếu một trong hai là true, nhưng không phải cả hai
	- && = and
	- || = or
	- ! = note, !$x true nếu x không true
	==PHP String Operators==
	- . nối 2 chuỗi $txt1 . $txt2
	- .= gắn chuỗi 2 vào chuỗi 1 $txt1 .= $txt2
	==PHP Array Operators==
	- Được sử dụng để so sánh các mảng
	- + Union : $x + $y nối hai array lại với nhau
	- == Trả về true nếu $x và $y có cùng cặp giá trị
	- === Trả về true nếu $x và $y có cùng cặp giá trị theo cùng thứ tự và cùng kiểu
	- != trả về true nếu không bằng
	- <> trả về true nếu  không bằng
	- !== trả về true nếu không cả hai không giống nhau
	==PHP Conditional Assignment Operators==
	- ? : -> Toán tử 3 ngôi, $x = expr1 ? expr2 : expr3, x có giá trị expr2 nếu expr1 đúng, sai thì là expr3
	- ?? -> $x = expr1 ?? expr2, x có giá trị là expr1 nếu expr1 tồn tại và không NULL, nếu không tồn tại hoặc nó NULL thì giá trị của x sẽ là expr2, Được giới thiệu từ PHP 7
	==PHP if...else...elseif Statements==
	- Các câu điều kiện thường được sử dụng để thực hiện các hành động khác nhau dựa trên điều kiện khác nhau
	- khi chúng ta viết code chúng ta muốn thực hiện những hành động cho những điều kiện khác nhau là một việc thường xuyên. Chúng ta có thể sử dụng những câu điều kiện trong code để thực hiện việc này.
		==The if statement==
		- Thực hiện một số đoạn code nếu một điều kiện là true
		==The if...else statement==
		- Thực hiện một số đoạn code nếu một điều kiện là true, và code khác nếu điều kiện là false
		==The if...elseif...else statement==
		- Thực hiện những đoạn code khác nhau cho nhiều hơn hai điều kiện
	==PHP The switch statement==
	- Câu switch thường được sử dụng để thực hiện những hành động khác nhau dựa vào những điều kiện khác nhau
	- Sử dụng switch để chọn một trong nhiều khối code để thực thi
	- 
	
	
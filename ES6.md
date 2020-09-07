- ES6 là chuẩn viết JS mới, có hỗ các tính năng mới, cú pháp mới, giúp cho việc viết code, tiết kiệm dòng code và thời gian code. Tuy nhiên ES6 chỉ hỗ trợ một số dòng browser mới, IE cũ sẽ không đọc được JS ES6
==Var, let và const==
- Var là biến toàn cục có tác dụng với tất cả scope
- let dùng để khai báo biến, thay thế và khắc phục một số nhược điểm của var, nó có thể gán giá trị nhiều lần. Nếu chúng ta khai báo cùng tên biến với từ khóa let nhưng 1 cái ở ngoài, 1 cái trong scope function thì JS sẽ hiểu là hai biến khác nhau. Nếu khai báo bên ngoài thì let và var điều có giá trị ở toàn bộ tất cả function.
- const là khai báo biến Hằng số, không thể gán giá trị lại, trường hợp tạo biến const là object thì không thể trỏ vào object khác nhưng có thể thay đổi giá trị trong object đó
==Hoisting var let const==
- Hoisting là khi thực hiện những khai báo biến là var thì sẽ được đưa lên trên cùng.
- Let hoặc const thì phải khai báo biến rồi mới sử dụng được biến đó còn var thì không khai báo biến mà vẫn sử dụng được biến.
==Function scope==
- Là phạm vi khai báo biến bên trong của một hàm, Biến bên trong scope sẽ không lấy được giá trị từ bên ngoài.
- Biến ở bên trong function có thể sử dụng biến bên ngoài nhưng biến bên ngoài không sử dụng được ở bên trong. 
==Block scope==
- là phạm vi khai báo biến bên trong một {}. Biến bên trong scope sẽ không lấy được từ bên ngoài trừ biến khai báo bằng từ khóa var. Do đó let được sinh ra đời, phạm vi hoạt động của let chỉ trong hai dấu {}.
- Trong ES6 thì thường khai báo biến bằng let để hạn chế ảnh hưởng của cơ chế hoisting của var đến kết quả trong function.
==Arrow function==
- là short hand của ES6 nhằm rút gọn.
- let showMessage = () => {}
- Khác với ES5 ở việc thay function bằng mũi tên
- trường hợp trong function chỉ duy nhất 1 return thì có thể bỏ return VD: let tinhDiemTrungBinh = (dToan,dLy,dHoa) => (dToan + dLy + dHoa) / 3; 
- Trước ES6, mỗi khai báo hàm đều có một giá trị this tách biệt. Với hàm mũi tên trong ES6, giá trị của this chính là this trong tầm vực gần nhất với nó (lexical this). Do đó chúng ta không cần phải khai báo biến tạm hay dùng .bind nữa.
- Hàm mũi tên cũng rất hữu ích khi thao tác trên mảng và tiến hành chuyển đổi dữ liệu, giúp mã nguồn dễ đọc và rõ ràng hơn.
- Arrrow function không được coi là phương thức.
- Sử dụng arrow function trong trường hợp 1 cái hàm trong cái hàm đó có function thì sử dụng arrow function cho những hàm bên trong function để cho con trỏ this đúng ngữ nghĩa. (Connect function).
==Khác biệt về ngữ cảnh trong con trỏ this==
- Trường hợp xử lý function trong một phương thức của một object thì sử dụng arrow function sẽ không thay đổi con trỏ this truyền vào từ object, nếu sử dụng khai báo function của es5 thì sẽ bị đứt do không truyền giá trị của object vào trong hàm
- Prototype function là lớp đối tượng.
==Resparameter==
- Các tham số truyền vào sẽ hợp thành một mảng, dùng khi không biết có bao nhiêu tham số đầu vào của một hàm.
- Ở các ngôn ngữ khác có khái niệm Overload còn JS không có chỉ có xét khác số lượng tham số mà điều chỉnh luồng xử lý trong function bằng switch case.
- Toán tử ba chấm. Nếu khai báo function với toán tử ba chấm thì có thể truyền bao nhiêu tham số cũng được, bên trong hàm phải kèm theo switch case check số lượng tham số truyền vào để cho từng trường hợp xử lý, nếu quá số lượng thì trả ra không hợp lệ.
- Cú pháp: function tên function = (...) {}
- Sử dụng được nhiều việc, có thể sử dụng lý thuyết hàm chồng.
==Spread Operator==
- Toán tử ba chấm, dùng để thêm phần tử vào mảng hoặc thêm thuộc tính vào object, ngược với rest nó nhận vào mảng và trả ra từng phần tử. 
- let mangA = [1,2,3,4];
- let mangB = mangA;
- mangB.push = [5,6]; => console.log(mangA); Khi gán mảng b = mảng a, thì theo tính chất con trỏ trong lập trình thì vùng nhớ mảng b sẽ trỏ về mảng a, khi thay đổi mảng b thì thay đổi mảng a luôn và ngược lại. nếu dùng toán tử ba chấm để tạo mảng b từ mảng a thì thay đổi mảng b, mảng a không bị thay đổi theo.
- cú pháp let tên biến mới = {...tên biến cần sao chép hoặc thêm vào} trường hợp trong object đã có key trùng với key thêm vào thì sẽ lấy giá trị của key thêm vào đè key đã có.
- muốn thêm thuộc tính cho object thì clone object đó ra xong sử dụng toán tử ... để thêm đối tượng.
==Default Parameter==
- Cho phép set giá trị mặc định tham số của hàm nếu như không có đối số truyền vào. Nếu mình truyền thì sẽ lấy giá trị của mình, nếu mình không truyền sẽ lấy giá trị mặc định.
- Nếu hàm 2 tham số mà truyền 1 tham số thì thay thế tham số 1 tham số 2 lấy mặc định, thế vào từ trái sang phải, nếu nó đã truyền vào thì thằng kế tiếp phải có tham số mặc định.
- Tham số thứ 3 được sử dụng tham số của 2 tham số phía trước, nếu truyền vào thì lấy giá trị truyền vào nếu không truyền sẽ lấy giá trị a + b.
==Template String==
- Tạo một string vừa tĩnh vừa động.
- String nằm trong dấu ``
- Truyền giá trị động ${tên biến}
==Object literals==
- ES6 nâng cấp object chân phương, cho phép bạn khai báo tắt thuộc
tính của object với biến cùng tên, và khai báo phương thức cho
object.
- Ngoài ra từ ES6 bạn cũng có thể khai báo thuộc tính cho object
một cách linh động bằng cách sử dụng cú pháp [].
- Trường hợp khai báo object có các key là tên biến đã có giá trị thì ra một obj có thuộc tính và giá trị như tên biến.
==For in for of==
- For in duyệt mảng theo index, mỗi lần lặp sẽ trả về giá trị index tương ứng với vị trí của phần tử. Dùng để duyệt các key của Object.
- Firebase lưu trữ dữ liệu dưới dạng object, lưu trữ dưới dạng cấu trúc cây, Tree Node.
- For of lấy về đối tượng của phần tử đó, trong trường hợp mảng object.
==OOP==
- class HocSinh {} <=> function HocSinh () {}
- VD class HocSinh { MaHS; HoTen; constructor (mahs, tenhs) { this.MaHS = mahs; this.HoTen = tenhs;} xuatThongTinHocSinh(){} (Các viết phương thức cho một lớp đối tượng trong ES6) tương đương xuatThongTinHocSinh = function () {}};
==OOP Extends==
- Lớp con bắt buộc phải gọi lại contructor của lớp cha.
- Super() đại diện cho lớp cha để gọi lại constructor hoặc phương thức.
- JS có kế thừa nhưng không có đa hình, bản chất nó là đa hình.	
- VD có class NhanVien thì class QuanLy extends NhanVien {} sẽ lấy tất cả những gì của cha xuống con cho, thằng con thêm những thuộc tính mới mà cha không có nên cần phải định nghĩa lại constructor sử dụng super() để lấy constructor ở cha cho những tham số cha đã có, phương thức cha cũng thể thay đổi bằng super.phương thức lớp cha, ở lớp cha có những tham số gì thì ở thằng con phải có. => tính đa hình
==OOP Import , Export ==
- Trong HTML thẻ script phải để module
- Trước đây JS để sử dụng nhiều file với nhau thì phải chèn vào HTML theo thứ tự.
- Nếu export default khi ta import có thể đặt tên biến tùy ý, dùng cho component
- Nếu export không có từ khóa default, khi import ta phải đặt tên biến giống với tên đã export và có {} 
- Có thể export nhiều biến bằng cách export {....} dùng cho đối tượng.
- Có thể import một hằng số, 1 con số, 1 đối tượng. 
==Filter==
- Trả về một mảng mới chứa các phần tử thỏa điều kiện kiểm tra.
- Gần giống biểu thức biểu thức lambda (lambda expression) trong các ngôn ngữ khác.
==Find==
- Trả về một đối tương đầu tiên tìm được thỏa điều kiện, thường sử dụng khi dựa trên những thuộc tính đặc trưng của đối tượng, vd mã sản phẩm, mã sinh viên. nếu không tìm thấy thì sẽ trả về undefined
==FindIndex==
- Trả về vị trí của phần đó ở trong mảng, thường sử dụng khi dựa trên những thuộc tính đặc trưng của đối tượng, vd mã sản phẩm, mã sinh viên. Nếu không tìm thấy thì sẽ trả về -1
- Thường dùng để xóa phần tử, hoặc dùng để DOM
==foreach==
- Phương thức thực thi một hàm 1 lần cho mỗi phần tử. Nôm na mảng có 8 phần tử thì sẽ thực thi hàm đó 8 lần, hàm nhận tham số đầu vào là từng phần tử của mảng và vị trí. foreach((item, index )=> {})
- VD làm công việc là log ra hoặc duyệt để in ra cái gì đó thì sẽ dùng foreach.
- Nó không return gì hết, chỉ dùng để duyệt mảng tạo nội dung.
==Map==
- Tương tự hàm foreach nhưng khác ở chỗ hàm map có giá trị trả về là một mảng mới được tạo ra từ các đối tượng return trong callback function, khác filter, ở chỗ thỏa điều kiện thì sẽ add, không thỏa điều kiện sẽ bỏ qua còn map sẽ lấy hết, không có gì hết thì lấy giá trị undefined.
- Nó sẽ luôn luôn trả ra giá trị, nếu return không thì sẽ chứa undefined
- Sẽ làm giống foreach nhưng lãnh về giá trị cuối cùng sẽ chứa n lần các phần tử chứa trong đó, dùng để render nội dung để tạo mảng nội dung mới từ nội dung cũ.
==Reduce==
- Hàm reduce thực thi na lần so với n phần tử của mảng nhằm tạo ra 1 giá trị mới (có thể là một biến, 1 mảng, 1 object ... tùy theo xử lý return trong hàm)
- VD dùng để tính tổng giá các sản phẩm có trong giỏ hàng. 
- Nhận vào tham số là giá trị đầu ra, tham số thứ 2 là item, tham số thứ 3 là index, tham số thứ 4 là mảng nhưng ít xài.
- Ngoài tính tổng tiền nó có thể tạo ra giá trị mới vd như tạo một mảng.
- Menu đa cấp thì thường xử dụng reduce rất nhiều.
- Ngoài ra còn có hàm reduceRight duyệt ngược mảng.
==Reverse==
- giúp đảo ngược một mảng, thường dùng trong thuật toán sắp xếp, khi đã sắp xếp rồi thì dùng hàm để lật ngược mảng mà không cần phải viết thuật toán duyệt ngược lại.
- array.reverse()
==Sort==
- dùng để sắp xếp thuộc tính của đối thường theo thứ tự tăng dần hoặc giảm dần, có thể ứng dụng để sắp xếp các mảng đối tượng dựa vào giá trị thuộc tính.
- nhận vào 2 đối số, đối số thứ 1  là object thứ 2, đối số thứ 2 là object đầu tiên. 1-2, 2-3, 3-4, so sánh 4 trước 3
- tạo ra biến tạm lưu trữ giá trị của nó, nếu so sánh text thì phải lowercase để cho chính xác.
- nếu sản phẩm tiếp theo > sản phẩm trước thì return 1 giữ nguyên, ngược lại thì -1,  không có gì thì return 1
- trường hợp so sánh theo số thì return giá trị của thằng 2 - thằng 1, nếu số âm thì đảo vị trí.
==Some==
- Không làm thay đổi mảng ban đầu, trả ra giá trị true nếu trong mảng có chứa 1 phần tử thỏa điều kiện.
- Truyền vào 1 callback function, return giá trị muốn kiểm tra.
==Every==
- Không làm thay đổi ban đầu, trả ra giá trị true nếu tất cả phần tử trong mảng thỏa điều kiện.
- Truyền vào 1 callback function, return giá trị kiểm tra.
==Includes==
- Kiểm tra phần tử đã cho có tồn tại trong mảng hay không
- Nhận vào 2 tham số, tham số 1 là giá trị kiểm tra, tham số 2 là index bắt đầu kiểm tra. Nếu index > index mảng thì sẽ cho ra kết quả false. nếu Index  là số âm, computed index sẽ được dùng làm vị trí bắt đầu để tìm kiếm valueToFind. Nếu computed index nhỏ hơn hoặc bằng -1 * array.length, phần tử đã cho sẽ được tìm kiếm trong toàn bộ mảng (tương tự như fromIndex bằng 0).
==Destructuring==
- Destructuring cho phép lấy ra các phần tử từ array, object và đặt tên cho nó. Rất tiện khu xử lý dữ liệu JSON, các đối tượng lồng nhau, giúp chúng ta rút gọn code.
- ![[Pasted image.png]]
1. Hoán đổi phần tử. ![[Pasted image 2.png]] => Không phải tạo biến temp, ngoài ra còn có thể hoán đổi nhiều số cho nhau nữa [a, b, c] = [b, c, a]
2. Lấy thuộc tính lồng nhau và gán giá trị mặc định. ![[Pasted image 3.png]]
3. Đặt lại tên khác. ![[Pasted image 4.png]]
4. Với array ![[Pasted image 5.png]]
5. Sử dụng computed với destructuring ![[Pasted image 6.png]]
https://blog.duyet.net/2016/05/cach-su-dung-destructuring-javascript-es6.html
- bóc tách phần tử với object, bóc tách phần tử trong mảng.
- let {tenthuoctinh} = object.thuoctinh;
- Có thể dùng mảng để mô tả đối tượng thay vì dùng obj. Đôi lúc API trả dữ liệu về kiểu mảng chứ không phải là object
- let sinhVienArr = [1, 'Nguyễn văn a'];
- let [ma,ten, hienThiThongTIn] = [1, 'Nguyen van a', () => {console.log(1,'Nguyen Van A')}]; //Ánh xạ.
- console.log(ten);
- hienThiThongTin();
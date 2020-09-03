==Introduction==
- Có thể sử dụng để phát triển các ứng dụng chạy ở client-side (Angular2) và server side (NodeJS).
- TypeScript là một dụ án mã nguồn mở được phát triển bởi Microsoft. TypeScipt là một phiên bản nâng cao của JS, nhưng có lai C# (Do phát triển bởi MicroSoft nên nó sẽ giống rất nhiều với C#, nó có các kiểu dữ liệu, lớp đối tượng, những class, interfaces giống như một ngôn ngữ lập trình hoàn thiện hơn không dễ dãi như ở JS).
- TypeScript bổ sung tùy chọn kiểu tĩnh (Kiểu dữ liệu) và lớp hướng đối tượng.
- TypeScript sử dụng tất cả các tính năng của ECMAScript 2015 (ES6) (là một chuẩn của JS được hiệp hội máy tính Châu Âu phát minh ra, trước đây mỗi một đoạn code JS thì mỗi trình duyệt sẽ chạy một cách khác nhau, cùng một đoạn code nhưng trình duyệt này chạy, trình duyệt khác lại không chạy cho nên sinh ra yêu cầu phải có một chuẩn chung để các trình duyệt phát triển theo chuẩn đó, có thể đọc JS một cách giống nhau) như classes, modules.
==Tại sao nên sử dụng TypeScript==
- Dễ phát triển các dự án lớn nhờ vào các kỹ thuật mới nhất và hướng đối tượng.
- Hỗ trợ các tính năng của JS phiên bản mới nhất. Do đó khi chạy thì có thể các trình duyệt cũ không hỗ trợ, vì vậy TS giống như scss sẽ build ra file JS chuẩn cũ để các trình duyệt có thể đọc được.
- Mã nguồn mở => được sử dụng miễn phí và được cộng đồng hỗ trợ.
- Bản chất của TypeScript là JavaScript: Typescript sau khi biên dịch sẽ thành file js.
==Install==
- npm i typescript -g => tạo thư mục chứa dự án => tsc --init => ctrl + shift + b => build => tasks : default build task => tsconfig.json. (trường hợp chọn watch thì mỗi lần save thì nó sẽ tự động complie ra file js luôn)
- Trong file tsconfig.json: 
 + "outDir" => thư mục typescript build ra js. 
 + "target": "es5" => định dạng build js
==Cơ chế khai báo biến==
- Khai báo với từ khóa let. Đối với biến khai báo bằng var thì có thể sử dụng trong cả chương trình, khai báo bằng let thì chỉ sử dụng trong block được khai báo trong dấu {}. Biến let tỏ ra rất là hữu hiệu trong vòng lặp for, ts sẽ build một cách khác so với sử dụng var cho biến đếm i.
 => Không sử dụng var trong mọi trường hợp.
 - Hằng số: Không hỗ trợ hoisting,  bắt buộc phải gán giá trị lúc khai báo, không thể gán lại giá trị, hằng số là object thì không thể new object nhưng có thể gán lại giá trị của object. khai báo bằng từ khóa const.
 ==Các kiểu dữ liệu trong typescript==
 Cách đặt kiểu dữ liệu: let isTrue:boolean = true; let mangNguoiDung: number[] = [1,2,3,4];
 - Boolean: Mang một trong hai giá trị là true hoặc false.
 - Number: Kiểu dữ liệu mang giá trị là số
 - String: Kiểu dữ liệu mang giá trị là một chuỗi.
 - Array: Kiểu dữ liệu mang giá trị là một mảng. let mangKhoaHoc:Array< any > = [1,'2',true]; 
 - Tuple: Kiểu dữ liệu mang giá trị là một mảng hỗn hợp. let mangThanhVien:[string,number] = ['1',1] chỉ được truyền 2 phần tử, nếu truyền hơn sẽ báo lỗi, do chỉ khai báo 2 phần tử.
 - Enum: Kiểu dữ liệu mang các giá trị liệt kê, thường thấy trong C# thường dùng để gán giá trị tham số với một tên mang ý nghĩa tường minh hơn. enum Color {Red=1, Green = 2, Blue= 4}, let c:Color = Color.Green.
 - Any: Kiểu dữ liệu bất kỳ. Có thể là số hoặc chuỗi, object json,... tương tự Dynamic trong C#, hạn chế sử dụng, bắt buộc mới xài. 
 - Void: Kiểu dữ liệu giống như một hàm không trả về giá trị nào cả.
 - Null: Kiểu dữ liệu mang giá trị null
 - Undefined: kiểu dữ liệu mang giá trị undefined.
	Null và Undefined khác nhau ở chỗ null là không có, rỗng hoàn toàn, còn undefined là chúng ta có khai báo nhưng không gán giá trị cho nó.
 - Never: kiểu dữ liệu không bao giờ xảy ra.
==Arrow Function==
- Là một cách viết Function dạng viết tắt được thêm vào từ ES6, bỏ chữ function đi và thay bằng một mũi tên, VD function InHoaDon(title) {} <=> let InHoaDon = (title) => {}
- Lợi: Trong trường hợp hàm chỉ có 1 câu lệnh thì có thể bỏ {}, khi đó => tương ứng với lệnh return
- Trong trường hợp cần setup default parameter thì sử dụng let tinhTong = (a=10, b=10) => a+b; Trường hợp không truyền giá trị vào mặc định là 20.
==Truyền tham số Rest parameter== 
- Ngoài cách truyền tham số thông thường như JS còn hỗ trợ chúng ta truyền tham số không giới hạn tham số truyền vào.
- Cú pháp function(...[thamso]:[kiểu dữ liệu]). Đối số truyền vào là các biến có cùng kiểu dữ liệu với [kiểu dữ liệu] của tham số.
- Nó sẽ gộp tất cả các tham số vào một mảng và chúng ta truy xuất tham số theo thứ tự truyền vào bằng index.
==Spread Operator (Truyền tham số là mảng)==
- Về cú pháp tương tự rest parameter, tuy nhiên cả hai có ý nghĩa khác nhau. Rest parameter được sử dụng khi khai báo hàm, để người dùng truyền tham số vô một cách tùy ý, gộp tham số đầu vào thành một mảng để xử lý, ngược lại spread operator được sử dụng trong các câu lệnh, biểu thức hoặc khi gọi hàm, nó có thể dùng với mảng, có thể dùng với object.
- let mang3 = [...mang1,...mang2] => dùng để nối mảng.
- let hocSinh3 = {...hocSinh1} => clone ra hocSinh3 có các giá trị như object hocSinh1. ngoài ra cũng có thể sử dụng để nối object như nối mảng.
- Làm việc với hàm. VD function tinhTong4So(a,b,c,d) {}, var thamSo = [1,2,3,4]; tinhTong4So(...thamSo) => khi đó nó sẽ lấy từng giá trị của từng phần tử trong mảng bỏ vào các thứ tự a,b,c,d trong hàm.
==Truy xuất phần tử từng mảng,Object==
- Destructuring Array (Bóc tách phần tử trong mảng)
- Destructuring Assignments đơn giản chỉ là cách tách các phần tử của Array hoặc Object thành nhiều biến chỉ bằng một đoạn code duy nhất.
- VD let date = [10,03,2016], let [d,m,y] = date => d = 10, m = 03, y = 2016. let [,,y] = date => y = 2016.
- VD: let hocSinh = { ten: 'hieu', tuoi:12, diem:20}, let {ten,tuoi,dem} = hocSinh => ten= 'hieu'
==String template==
- String template được bắt đầu bằng `'`. Cũng giống như chuỗi nhưng string template hỗ trợ chúng ta đưa tham số vào dễ dàng hơn. Đối với một cấu trúc chuỗi cần đưa vào nhiều tham số thì ta định nghĩa bằng string template code sẽ rõ ràng và dễ hiểu hơn.
- `welcome to ${biến cần lấy giá trị}`
==Duyệt Object==
- Để duyệt một object là một mảng hay chuỗi ta có thể chọn 1 trong 2 kiểu duyệt là for...in lấy ra tên key/index của object và for...of: lấy ra giá trị của từ key trong object (được sử dụng nhiều).
- for (let index/item in/of mảng/object)
==Định nghĩa class==
- Class thực chất là function nhưng không hỗ trợ hoisting, có nghĩa là new 1 lần trên 1 biến không làm được 2 lần (bản chất là prototype trong JS để tạo các lớp đối tượng).
- cú pháp: class NguoiDung {public HoTen:string; public MatKhau:string; public TaiKhoan:string; constructor(hoTen:string, matKhau:string, taiKhoan:string) {this.HoTen=hoTen; this.MatKhau=matKhau; this.TaiKhoan=taiKhoan}}.
- public/private/protected là từ khóa dùng để chỉ phạm vi hoạt động của thuộc tính, HoTen là thuộc tính. 
- public là ở bất kỳ đâu cũng có thể truy xuất để lấy ra các thuộc tính này hết.
- private thì từ bên ngoài không thể truy xuất đến thuộc tính HoTen được, để truy xuất đến HoTen thì cần xây dựng phương thức public getHoTen và setHoTen vd public getHoTen(){return this.HoTen} để tránh việc ở bên ngoài có thể truy xuất trực tiếp đến biến HoTen và sửa nó. 
==Định nghĩa phương thức khởi tạo và phương thức tĩnh==
- constructor là hàm khởi tạo, khi nào class được gọi thì phương thức khởi tạo sẽ được chạy đầu tiên.
- để thiết lập một phương thức thành phương thức tĩnh thì ta sử dụng từ khóa static ở đầu VD: static say() {alert('Xin Chao')}. Khi set phương thức say này là phương thức tĩnh thì mặc định tất cả mọi đối tượng được sinh ra điều có phương thức say ngoài ra chúng ta có thể gọi phương thức thông qua lớp đối tượng VD NguoiDung.say(), phương thức tĩnh cũng là phương thức của lớp đối tượng luôn.
==Kế thừa class==
- Tương tự JS, TS cũng có kế thừa. Đối với hàm tạo nếu class con muốn kế thừa bắt buộc phải có từ khóa super([thamso_HamCha]), đối với các phương thức thì tùy, ta có thể dùng từ khóa super để kế thừa xử lý từ hàm cha hoặc không cần.
- Chúng ta gom tất cả các thuộc tính xài chung thành một class cha và những class con sẽ kế thừa thằng cha này. 
- Ở lớp con thì constructor phải truyền tham số = số lượng tham số của lớp cha và tham số thêm của chính nó. sử dụng từ khóa super(truyền tham số là những thuộc tính của cha) gọi lại contructor của lớp cha, sau đó phải tự gán cái tham số thêm của lớp con. Trường hợp ở lớp con overriding phương thức của lớp cha thì khai báo lại chính tên phương thức đó, trường hợp muốn gọi lại phương thức của lớp cha ở bên trong thì sử dụng super.tên phương thức.
- ![[Pasted image 7.png]]
==Interfaces==
- Interfaces là lớp trừu tượng định nghĩa các phương thức và các thuộc tính nhưng không xử lý, mà để cho các lớp con kế thừa bắt buộc phải xây dựng phương thức xử lý cho nó. (implements)
- Hay nói cách khác interfaces là cái bản mẫu, chúng ta tạo ra những class phải tuân theo bản mẫu đó, nó bắt buộc phải có những phương thức và thuộc tính như bản mẫu (Không thiếu cái nào hết).
- ![[Pasted image 8.png]]
- ?: => có thể có hoặc không cũng được không quan trọng.
- Bắt gặp cái interface và cái implements rất nhiều trong project angular.
==DOM trong TS==
- Khi DOM bằng TS sẽ bị ràng buộc bởi kiểu dữ liệu cho nên cần phải thêm kiểu dữ liệu và trước phương thức getElement
- let btnGet = <HTMLButtonElement'>document.getElementById('btnGetEmail'); => Cho TS thấy rõ rằng cái chúng ta đang DOM tới là một cái Button Element. 
- let email = (<HTMLInputElement'>document.getElementById('txtEmail')).value; Nếu không có HTMLInputEle thì sẽ báo lỗi do TS nhận ra rằng đang DOM tới HTML Element mà nó thì không có value nên không . được.
==BT Thực hành==
- Đề ![[Pasted image 9.png]]
- Tạo Class NhanVien (phải export Class ra để có thể sử dụng Class NhanVien ở các file khác, file khác muốn xài phải import NhanVien từ file NhanVien => Tạo Class DanhSachNhanVien là một mảng đối tượng nhân viên.

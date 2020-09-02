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
- 
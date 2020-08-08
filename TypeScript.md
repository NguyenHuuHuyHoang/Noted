==Introduction==
- TypeScript bổ sung tùy chọn kiểu tĩnh (Kiểu dữ liệu) và lớp hướng đối tượng.
- Có thể sử dụng để phát triển các ứng dụng chạy ở client-side và server side.
==Tại sao nên sử dụng TypeScript==
- Dễ phát triển các dự án lớn nhờ vào các kỹ thuật mới nhất và hướng đối tượng.
- Hỗ trợ các tính năng của JS phiên bản mới nhất.
- Mã nguồn mở.
- Bản chất của TypeScript là JavaScript: Typescript sau khi biên dịch sẽ thành file js.
==Install==
- npm i typescript -g => tạo thư mục chứa dự án => tsc --init => ctrl + shift + b => build => tasks : default build task => tsconfig.json.
- Trong file tsconfig.json: 
 + "outDir" => thư mục typescript build ra js. 
 + "target": "es5" => định dạng build js
==Cơ chế khai báo biến==
- Khai báo với từ khóa let. Đối với biến khai báo bằng var thì có thể sử dụng trong cả chương trình, khai báo bằng let thì chỉ sử dụng trong block được khai báo.
 => Không sử dụng var trong mọi trường hợp.
 - Hằng số: Không hỗ trợ hoistring,  bắt buộc phải gán giá trị lúc khai báo, không thể gán lại giá trị, hằng số là object thì không thể new object nhưng có thể gán lại giá trị của object. khai báo bằng từ khóa const.
 ==Các kiểu dữ liệu trong typescript==
 - Boolean
 - Number
 - String
 - Array
 - Tuple
 - Enum
 - Any
 - Void
 - Null
 - Undefined
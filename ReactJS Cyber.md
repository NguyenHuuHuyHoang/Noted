- React là một thư viện của JS, hỗ trợ SPAs, tăng hiệu suất load trang. VD: FB - react, Youtube - angular, do chỉ load nội dung mà không load lại toàn bộ trang
- React viết trên ngôn ngữ ES6
- create-react-app [tên dự án]
- node_modules:  Chứa các thư viện cài đặt cho ứng dụng
- Đầu tiên trình duyệt sẽ đọc index.html và index.js sau đó sẽ index.js, trong file nãy ReactDOM sẽ được sử dụng để render nội dung của app component ra div root ở ngoài HTML thông qua điều hướng về App.js, ghi toàn bộ nội dung của App lên html.
- App.js chính la component gốc của toàn ứng dụng.
- Những thẻ do react tạo ra gần giống như HTML. 
==Component==
- Component biểu diễn giao diện UI (file.html)
- Là một thành phần của website, là một thẻ do mình định nghĩa, trong thẻ đó chứa các nội dung html do mình biên soạn
- Có hai loại component là class (stateful component) và functional  - stateless component(React Hook - Đầu 2019 ra), cả hai loại đều có hiệu suất ngang nhau, sử dụng loại nào cũng được. Class viết nội dung trong phương thức render , còn function thì viết nội dung không trong phương thức nào hết, nằm trong lệnh return.
- stateless component thực chất chỉ là một function, return về một đoạn mã HTML để hiển thị ra giao diện, không thể sử dụng được state và component lifecycle.
- stateful component (class component) thực chất chỉ là một class, có phương thức là render(), khi component được gọi, render() sẽ chạy và trả về đoạn mã HTML, có thể sử dụng được state và component lifecycle.
- Thẻ react bắt buộc phải viết hoa chữ đầu tiên
- Component không được trùng tên trong dự án
==Cấu trúc JSX==
- Đoạn mã được return trong component tương đố giống HTML nhưng thực chất đó là jsx cho phép chúng ta kết hợp HTML và JS trên một source.
- class -> className, các thẻ khuyết đóng phải đúng cú pháp, bắt buộc phải có "/" VD: <img />
- For -> htmlFor. VD: <label htmlFor="dangnhap"></label>
- Khi lấy source code HTML từ nguồn khác, để sử dụng với react, ta cần convert ra thành jsx. https://transform.now.sh/html-to-jsx/ hoặc sử dụng extention html to jsx.
==Các tổ chức thư mục==
- Thư mục hình sẽ bỏ trong folder public
- Ở folder src sẽ chứa: 
+ Components: để chứa các component nhỏ lẻ cấu hình nên 1 trang: header, footer,...
+ Containers: chứa các component ở mức độ trang.
==Databinding reactjs==
- JSX cho phép ta lồng js vào HTML thông qua dấu { a }
- jsx cho phép chúng ta có thể render biến chuỗi hàm,... tại phần nội dung miễn kết quả trả về là một đoạn jsx
- js sẽ được parse và hiển thị chung với html.
==Xử lý sự kiện trong REACT==
- Các sự kiện onClick, onChange, onSubmit... trong js đều có thể sử dụng trong react. Tuy nhiên sẽ có những khác biệt về cú pháp.
- Cú pháp suKien={callbackfunction} => sự kiện là các sự kiện nêu trên, callback function là một function để xử lý cho sự kiện đó, lưu ý: callback function gán vào không có 2 dấu ().
- Trường hợp muốn truyền 1 callback function xử lý sự kiện có tham số : suKien={() => callbackfunction(param)} ta sẽ viết dưới dạng truyền 1 callbackfunction nặc danh và function đó sẽ trả về 1 function có tham số khi thực thi => Khi gọi function đó.
- Event Binding -> hay còn gọi là handle Event
- Những hàm xử lý sự kiện sử dụng arrow function.
==Lệnh điều kiện trong jsx==
- Kết hợp if else và hàm để xác định nội dung cần hiển thị trong react.
- Bằng cách xây dựng một hàm bên trong sử dụng lệnh if else để tùy biến nội dung jsx được render ra giao diện. Ngoài ra mình có thể sử dụng toán tử 3 ngôi để xá định phần nội dung hiển thị trực tiếp trên hàm render.
==Stage==
- State là một thuộc tính mặc định của class kế thừa từ class component để quản lý trạng thái của component. 
- Mỗi khi state thay đổi, thì hàm render sẽ được gọi chạy lại.
- không được gán giá trị trực tiếp = cho stage mà phải thực hiện thông qua phương thức this.setStage(newState) : phương thức của component thay đổi giá trị state hiện tại và render lại giao diện
- setStage là phương thức bất đồng bộ, có 2 tham số, tham số thứ 1 là thay đổi giá trị state, tham số 2 là call back thực hiện sau khi state mang giá trị mới.
- Những giá trị nào làm thay đổi giao diện thì đặt ở ngoài, thì đặt trong stage của component. Nếu sử dụng JS thuần thì phải dom lấy dữ liệu sau đó dom tới các phần thay đổi dữ liệu để gán giá trị mới. DOM JS thuần xử lý trên các dự án không xài React
==Render giao diện với mảng dữ liệu dùng vòng lặp==
- Để tạo ra các tag html (jsx trong react) thì ta có rất nhiều cách thực hiện, dùng các hàm như for, foreach, map... tạo nội dung. Viết 1 hàm render kết quả trả về là một mảng các tag jsx, tag được tạo ra từ vòng lặp luôn phải có 1 thuộc tính key không trùng nhau => sử dụng key={index}
- Gọi hàm tại thẻ body để giao diện render ra các thẻ mới tại đó.
- Ngoài ra chúng ta có thể viết phương thức render dưới dạng hàm map() hoặc viết trực tiếp trên giao diện code render trên giao diện.
==Truyền dữ liệu trong reactjs==
- Props (Truyền dữ liệu từ component cha sang con)
- Props là thuộc tính của thẻ (Ta có thể hiểu prop là property của thẻ). Ví dụ thẻ input bên dưới ta có các props ClassName, type, placeholder
- Props đối với component :
+ Props là thuộc tính mặc định của component để nhận dữ liệu từ các giá trị component cha truyền vào => để binding dữ liệu ra component con tại html tương ứng.
+ Props của component chỉ nhận các thuộc tính truyền vào từ component cha của nó và không thể bị chỉnh sửa bên trong component.
+ Đối với stateful và stateless component có các cách sử dụng props khác nhau. 
- Do stateless component là một function nên truyền props vào dưới dạng tham số, sử dụng bằng cách props.[thuộc tính của component cha] (nằm ngoài render) và export để có thể gọi ở các component khác.
- Đối với stateful component, thì props là thuộc tính mặc định của class, nên không cần truyền tham số. Chí cần gọi this.props
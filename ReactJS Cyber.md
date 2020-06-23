- React là một thư viện của JS, hỗ trợ SPAs, tăng hiệu suất load trang. VD: FB - react, Youtube - angular, do chỉ load nội dung mà không load lại toàn bộ trang
- React viết trên ngôn ngữ ES6
- create-react-app [tên dự án]
- node_modules:  Chứa các thư viện cài đặt cho ứng dụng
- Đầu tiên trình duyệt sẽ đọc index.html và index.js sau đó sẽ index.js điều hướng về App.js, ghi toàn bộ nội dung của App lên html.
- Những thẻ do react tạo ra gần giống như HTML. 
==Component==
- Là một thành phần của website, là một thẻ do mình định nghĩa.
- Có hai loại component là class và functional (React Hook - Đầu 2019 ra), cả hai loại đều có hiệu suất ngang nhau, sử dụng loại nào cũng được. Class viết nội dung trong phương thức render , còn function thì viết nội dung không trong phương thức nào hết, nằm trong lệnh return.
- Thẻ react bắt buộc phải viết hoa chữ đầu tiên
- Component không được trùng tên trong dự án
==Xử lý sự kiện trong REACT==
- Event Binding -> hay còn gọi là handle Event
- Những hàm xử lý sự kiện sử dụng arrow function.
==Stage==
- không được gán giá trị trực tiếp = cho stage mà phải thực hiện thông qua phương thức this.setStage(newState) : phương thức của component thay đổi giá trị state hiện tại và render lại giao diện
- setStage là phương thức bất đồng bộ, có 2 tham số, tham số thứ 1 là thay đổi giá trị state, tham số 2 là call back thực hiện sau khi state mang giá trị mới.
- Những giá trị nào làm thay đổi giao diện thì đặt ở ngoài, thì đặt trong stage của component. Nếu sử dụng JS thuần thì phải dom lấy dữ liệu sau đó dom tới các phần thay đổi dữ liệu để gán giá trị mới. DOM JS thuần xử lý trên các dự án không xài React
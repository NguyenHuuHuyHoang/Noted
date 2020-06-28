- Chuẩn ES6, các framework điều sử dụng ES6 này.
- Rã các tính năng của bài toán thành các đối tượng, VD các lớp đối tượng, chức năng của từng lớp.
==Xây dựng các lớp đối tượng nhân viên==
- Trong ES6 sẽ sử dụng class thay cho function 
- Nên tạo ra một mảng để chứa tất cả các thuộc tính để sau này duyệt qua các thuộc tính một cách dễ dàng hơn.
==Xây dựng tính năng thêm nhân viên==
- Tạo event khi người dùng click vào btnThem sẽ thực hiện việc XoaForm (Để các thông tin của lần thêm trước đó xóa, không hiển thị lại trên form) sau đó gọi Modal thêm người dùng ra.
- Xử lý sự kiện cho nút thêm nhân viên, trước khi thêm nhân viên phải thực hiện validation.
- Sau khi nhận value từ input và truyền vào obj nhanVienMoi, thêm nhanVienMoi vào congty, sử dụng thư viện sweetalert để thông báo thêm thành công.
==Sửa thông tin nhân viên==
- Sau khi click vào icon thì những thông tin từ input phải được lấy ra từ nhân viên trong danh sách nhân viên, khi click cập nhật thì những thông tin sửa sẽ được cập nhật và hiển thị ra màn hình.
- Trường hợp value là select box thì muốn gán lại giá trị phải sử dụng selectedIndex, và thay chức vụ của nhân viên = số theo thứ tự giá trị VD 1 - sếp, 2 - trưởng phòng, 3 - nhân viên
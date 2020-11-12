==Biến==
- Khai báo bằng var
- Đặt tên biến theo cú pháp lạc đà : firstName
- Lưu ý khi đặt tên: 
	- Tên biến không được trùng với các từ khóa
	- Tên phải có ý nghĩa: firstName, lastName,..
	- Không bắt đầu bằng số: 2name
	- Không chứa khoảng trắng hoặc gạch giữa ( - )
	- Không nên khai báo nhiều biến trên cùng một dòng.
	- Tên biến phân biệt chữ hoa, thường
- Gán giá trị bằng dấu =
- Loại dữ liệu:
	- String (chuỗi ký tự): var fullName = "Nguyen Van A";
	- Number (số): var age = 12;
	- Boolean (true/false): var isLogin = true;
	- Kiểm tra loại dữ liệu => typeof(biến hoặc dữ liệu cần kiểm tra);
- Hằng số (const): 
	- với cú pháp là const tên biến;
	- Đặt tên in hoa và gạch dưới giữa các tự VD: const SO_NGUYEN = 5;
	- Chỉ gán giá trị được một lần duy nhất.
==Chèn JS vào trang==
- Nên để JS ở cuối file HTML trước thẻ đóng </body>
- Chèn trực tiếp code vào HTML, <script>code</script>
- Chèn code js từ  js từ bên ngoài: <script src="đường dẫn tới file"></script>
==Toán tử==
- + | - | * | / : cộng - trừ - nhân - chia. Chú ý phép toán + khi xử lý giữa 1 chuỗi và 1 number thì JS sẽ ép kiểu number về kiểu string và thực hiện cộng chuỗi, các phép toán kia thì ép kiểu string về kiểu number.
- % : Lấy phần dư
- x++ => x + 1 | x-- =.> x - 1: Tăng 1 hay giảm 1;
- x+=1 => x = x + 1: Phép gán, có thể sử dụng với /= | %= | -= | ...
==Mô hình 3 khối==
- Đầu vào (Người dùng nhập vào)
- Các bước xử lý (Thuật toán, giải thuật)
- Đầu ra (Kết quả)
==Thêm sự kiện click==
- sử dụng thuộc tính onclick của object HTML, nếu thẻ HTML có sẵn sự kiện click, onclick sẽ ghi đè mất sự kiện có sẵn đó.
- sử dụng addEventListener, phương thức này nhận vào 2 tham số, tham số 1 là sự kiện, tham số 2 là một callback function, phương thức này không ghi đè mà chỉ thêm 1 sự kiện click cho thẻ đó, có thể add nhiều sự kiện click cho cùng 1 thẻ.
==Thêm CSS==
- Thêm css bằng thuộc tính class: sử dụng object.classList.add(class), không ghi đè thuộc tính css của thẻ
- Thêm css inline (thêm thuộc tính style):
	- object.style.property = value. Không ghi đè thuộc tính style có sẵn của thẻ, phải thêm nhiều thuộc tính css => tốn nhiều dòng code nếu thêm nhiều css.
	- object.style.cssText = string. Thêm được nhiều thuộc tính CSS trên cùng 1 dòng code, tuy nhiên khó theo dõi, maintain code.
==DOM thẻ HTML==
- Tìm thẻ HTML bằng ID: document.getElementById("id");
- Lấy các thuộc tính của thẻ: 
	- .value: giá trị của thẻ input
	- .classname: tên thuộc tính class của thẻ
	- .style: thuộc tính style của thẻ
	- .src: thuộc tính src của thẻ img
- Thay đổi nội dung bên trong thẻ: .innerHTML
==Thêm thuộc tính cho thẻ==
-	gọi trực tiếp tên thuộc tính và gán giá trị: element.disabled = true;
-	sử dụng setAttribute(): element.setAttribute("disabled", true);
==Ngăn load lại web khi click button của form==
- Sử dụng event.preventDefault();
- đổi type của button từ submit sang button
==Thêm thả con HTML vào thẻ cha==
- element.innerHTML = '<span style="vertical-align: super;">Thẻ con</span>'; (Nếu trong thẻ có sử dụng dấu nháy kép thì sử dụng dấu nháy đơn ở ngoài cùng để bọc thẻ).
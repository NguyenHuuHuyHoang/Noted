- HTML canvas drawImage(): Chuyển ảnh img thành canvas.
- biến argument trong function tạo theo cách không phải arrow function, nó là một mảng chứa toàn bộ các biến truyền vào function, có thể truy xuất vào index và  length như một mảng bình thường tuy nhiên nó không thể sử dụng các method của array.
- Infinity: là giá trị vô cực, thường được sử dụng làm flag đầu tiên để tìm giá trị lớn nhất hoặc giá trị nhỏ nhất trong mảng.
- phim.mota.length>100 ? phim.mota.substr(0,100) + '...': phim.mota - Nếu dài hơn 100 ký tự thì cắt chỉ chừa 100 ký tự và ...
- Dùng object lưu trữ dữ liệu sẽ nhanh hơn rất nhiều so với dùng mảng lưu trữ object, nếu lưu trữ mảng sẽ dài -> code dài hơn lưu trữ object, object lấy ra xài luôn, còn mảng phải truy xuất.
- Một số kỹ thuật đọc object sẽ nhanh hơn rất nhiều so với dùng mảng lưu trữ. VD for in duyệt object sẽ cho ra những cái key, ngoài ra còn có thể sử dụng hàm Object.entries () nó sẽ bóc tách đối tượng thành những mảng con, VD 1 object có 3 thuộc tính => 1 mảng lớn chứa 3 cái mảng con => sử dụng map để duyệt thành một array JSX. Chú ý nếu bóc tách thì sử dụng destructor array VD: Object.entries(burger).map(([propsBurger, value], index) => { console.log(propsBurger, value)})
==Alert=
- Dùng để hiển thị một thông báo và chờ người dùng nhấn nút OK. Cửa số nhỏ với thông điệp được gọi là modal window. Từ modal có nghĩa là khách truy cập không thể tương tác với phần còn lại của trang, nhấn các nút khác,... cho đến khi họ xử lý được cửa sổ.
- VD: alert("Hello")
==Prompt (lời nhắc)==
- Hiển thị một cửa sổ phương thức với một văn bản tin nhắn, trường nhập cho người dùng truy cập và các nút OK/Cancel.
- Hàm prompt nhận hai tham số. Tham số thứ nhất là nội dung để hiển thị ra cho người dùng. thuộc tính thứ hai là tùy chọn, đây là giá trị ban đầu cho trường hợp nhập vào.
- Trường hợp người dùng nhập nội dung nào đó và OK thì chúng ta có thể nhận được nội dung đó trong result. Trường hợp hủy bỏ bằng cách nhấn Cancel hoặc nhấn phím Esc thì chúng ta sẽ nhận được giá trị null trong result.
- VD: let age = prompt('How old are you?', 100);  alert(`You are ${age} years old!`); //You are 100 years old!
- Trong IE thì nếu không cung cấp tham số thứ 2 thì nó sẽ thêm giá trị undefined vào do đó chúng ta cần xử lý tham số 2 là 1 chuỗi rỗng.
==Confirm (xác nhận)==
- Chức năng confirm hiển thị một cửa sổ phương thức vơi một câu hỏi và có hai nút OK hoặc Cancel.
- Kết quả là true nếu OK và false là Cancel.
- VD let isBoss = confirm("Are you the boss ?"); alert(isBoss);
- Tất cả các hàm alert/prompt/confirm sẽ dừng thực thi tập lệnh và không cho phép người dùng tương tác với phần còn lại của trang cho đến khi cửa sổ bị loại bỏ.
- Vị trí chính xác của cửa sổ phương thức được xác định bởi trình duyệt. Thông thường sẽ ở trung tâm.
- Giao diện chính xác của cửa sổ cũng phụ thuộc vào trình duyệt, chúng ta không thể sửa đổi nó.
- Ưu điểm lớn nhất là sự đơn giản. Có nhiều cách khác để hiển thị các cửa sổ đẹp hơn và tương tác phong phú hơn với khách truy cập.
==Toán tử kết hợp ?? ==
- Toán tử hợp nhất nullish ?? là một cú pháp ngắn để chọn một biến đầu tiên được định nghĩa (có giá trị) từ danh sách.
- Kết quả a ?? b là :
	- Chọn a nếu nó không null hoặc undefined
	- Chon b cho trường hợp ngược lại.
- Do đó x = a ?? b <=> x = (a !== null || a !== undefined) ? a : b;
	==So sánh với || ==
	- Trên thực tế chúng ta có thể thay thế ?? bằng || và nhận được kết quả như nhau.
	- Sự khác biệt của 2 phép toán là || trả về kết quả đúng đầu tiên, còn ?? trả về giá trị được xác định đầu tiên. Điều này khác biệt khi ta xử lý null/undefined khác biệt với số 0
	- VD: height = height ?? 100; nếu nó không xác định thì giá trị 100, nếu nó có giá trị 0 thì vẫn là 0.
	==Quyền ưu tiên==
	- Mức độ ưu tiên của ?? là 7 trong bảng MDN.
	- Nó thấp hơn so với hầu hết các toán tử và cao hơn một chút so với = và ?
	- Vì vậy nếu cần sử dụng ?? trong các biểu thức phức tạp, thì nên sử dụng kèm theo dấu ngoặc đơn.
	- Ngoài ra khi sử dụng ?? thì không được sử dụng cùng với && và ||. Nếu sử dụng sẽ bị lỗi cú pháp. Trường hợp này cần sử dụng dấu ngoặc đơn rõ ràng để sửa nó. VD let x = 1 && 2 ?? 3 => let x = (1 && 2) ?? 3;
==Các kiểu dữ liệu trong JS==
- number : cho cả số nguyên nguyên và số thực.
- bigint: cho số nguyên có độ dài tùy ý.
- string: cho chuỗi
- boolean: cho các giá trị logic: true/false
- null: một loại có một giá trị duy nhất null, có ý nghĩa là trống rỗng, hoặc không tồn tại.
- undefined: một loại có một giá trị duy nhất undefined, nghĩa là không được chỉ định.
- object và symbol - đối với các cấu trúc dữ liệu phức tạp, chúng ta chưa tìm hiểu chúng.
- Các toán tử typeof trả về kiểu cho một giá trị với hai trường hợp ngoại lệ là null và function(){}
==Khai báo hàm==
- function sum(a,b) {};
- let sum = function(a,b) {};
- let sum = (a,b) => {};
- Các hàm có thể có các biến cục bộ: những biến được khai báo bên trong nó. Các biến như vậy chỉ được thấy bên trong hàm.
- Các tham số có thể có các giá trị mặc định: function sum(a=1, b=2) {}
- Hàm luôn trả lại một cái gì đó . Nếu không có return thì kết quả là undefined.
==Cấu trúc optional==
- Chuỗi ?. là một kiểu tùy chọn, nó là cách chống lỗi truy cập thuộc tính đối tượng lồng nhau, ngay cả khi thuộc tính trung gian đó không tồn tại.
- Trước khi toán tử ?. xuất hiện, toán tử && đã được sử dụng. VD alert( user && user.address && user.address.street).
- && toàn bộ đường dẫn đến thuộc tính đảm bảo rằng tất cả các thành phần tồn tại. Tuy nhiên cách này thì khá dài.
- Thay thế bằng ?. => alert(user?.address?.street);
- ?. chỉ được sử dụng trong trường hợp khi có một thứ gì đó không tồn tại, VD theo logic của đối tượng user thì luôn tồn tại nhưng address là tùy chọn (có hay không có cũng được), thì user.address?.street sẽ tốt hơn.
- Trong trường hợp nếu user không xác định được do nhầm lẫn gì đó, chúng ta sẽ biết về nó và sửa. Mặt khác lỗi code có thể bị không xuất hiện khi dùng ?. không đúng chỗ và nó làm cho việc gỡ lối trở nên khó hơn. Biến trước ?. phải tồn tại, nếu không có user thì user?.anything sẽ gây ra lỗi.
- Chuỗi tùy chọn ?. chỉ kiểm tra null/undefined, không can thiệp vào bất kỳ cơ chế nào khác của ngôn ngữ.
	==Đoản mạch==
		- ?. sẽ dừng ngay lập tức đánh giá nếu phần bên trái không tồn tịa. Vì vậy nếu có thêm bất kỳ lệnh gọi hàm hay ngoặc vuông nào thì chúng sẽ không xảy ra.
	==Các trường hợp khác: ?. (), ?.[]==
		- Chuỗi tùy chọn ?. không phải là một toán tử mà là một cấu trúc cú pháp đặc biệt, cũng hoạt động với các hàm và dấu ngoặc vuông.
		- Ví dụ ?.() được sử dụng để gọi một hàm có thể không tồn tại. Một số người dùng có hàm admin một số thì không.![[Pasted image 20201016210756.png]]
		- Trong hai dòng đầu tiên, chúng ta sử dụng dấu chấm để lấy thuộc tính admin, vì đối tượng người dùng phải tồn tại, do đó được đọc an toàn.
		- Sau đó, ?.() kiểm tra phần bên trái: nếu người dùng tồn tại, thì nó chạy (user1). Mặt khác với user2 thì đánh giá dừng lại mà không có lỗi.
		- Các cú pháp ?.[] cũng làm việc như vậy, nếu chúng ta muốn sử dụng dấu ngoặc [] để tính truy cập thay vì chấm . Tương tự như các trường hợp trước, nó cho phép đọc một thuộc tính một các an toàn từ một đối tượng có thể không tồn tại.
		- Ngoài ra chúng ta có thể sử dụng ?. với delele
		- delete user?.name; Chúng ta có thể sử dụng ?. để đọc và xóa an toàn, nhưng việc gán thì không dùng.
		- Chuỗi tùy chọn ?. không sử dụng ở phía bên trái của lệnh gán.
	==Coding Convention==
		==Quy tắc đặt tên (naming convention)==
		- Tên lớp đặt theo PascalCase.
		- Tên biến, tên hàm đặt theo camelCase hoặc snake_case
		- Hằng số đặt theo UPPER_CASE
		- Tên biến, tên lớp thường là danh từ, cụm danh từ hoặc tính từ: UserModel, userName, downloadCounter, isDownloaded.
		- Tên hàm thường bắt đầu bằng động từ: getUserName, setUserModel, increaseDownloadCouter.
		- Tên thìp hải có nghĩa, KHÔNG ĐƯỢC đặt tên theo kiểu viết tắt: dlCounter, uName, idl, a, a1, doFA.
		- Tránh đặt những tên quá chung chung, tối nghĩa: top, best, doIncrease, getAll
		==Quy tắc về số lượng==
		- Hàm không nên quá 30 dòng.
		- Lớp không nên vượt quá 500 dòng.
		- Một hàm không được vượt quá 5 tham số (tốt nhất nên giữ <= 3)
		- Một hàm chỉ làm duy nhất 1 việc, trong trường hợp chính đáng làm hai việc cũng được cho phép, tuy nheien tên hàm phải nói rõ điều này: increaseDownloadCounterAndSaveToDatabase.
		- Khi khai báo biến, một dòng chỉ chứa một biến.
		- Một dòng không nên dài quá 80 kí tự.
		- Các câu lệnh lồng nhau tối đa 4 cấp.
		==Quy tắc xuống hàng==
		- Nếu có dấu phẩy thì xuống hàng sau dấu phẩy.
		- Xuống hàn trước toán tử +,-,..
		- Nếu có nhiều cấp lồng nhau thì xuống hàng theo từng cấp.
		- Dòng xuống hàng mới thì nên bắt đầu ở cùng cột với đoạn lệnh cùng cấp ở trên.
		==Comment==
		- Hạn chế dùng comment để giải thích code, thay vào đó cải thiện đoạn code
		- Chỉ nên dùng comment trong trường hợp viết documentation cho thư viện, thông tin đính kèm cho class.
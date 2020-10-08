==1. Filter Unique Values==
Kiểu object Set đã được giới thiệu trong ES6 và kết hợp với 'spread' operator chúng ta có thể sử dụng nó để tạo một mảng mới với chỉ những giá trị duy nhất. Trick này chỉ làm việc với các mảng chứa kiểu dữ liệu nguyên thủy như : undefined, null, boolean, string và number. Trường hợp có một mảng chứa nhiều object, function hoặc những mảng khác, thì cần phải tiếp cận theo cách khác.
- const array = [1, 1, 2, 3, 5, 5, 1]
- const uniqueArray = [...new Set(array)]
- console.log(uniqueArray); //Result: [1, 2, 3, 5]
==2. Short-Circuit Evaluation==
- toán tử ba ngôi là một cách nhanh chóng để viết những đoạn điều kiện đơn giản. Nhưng đôi lúc kể cả toán tử ba ngôi thì vẫn phức tạp hơn cần thiết, thay vào đó chúng ta sử dụng && hoặc || để so sánh các biểu thức nhất định theo cách ngắn gọn hơn. Điều này thường được gọi là đoản mạch hoặc đánh giá ngắn mạch.
- Sử dụng && sẽ trả về giá trị false đầu tiên hoặc giá trị true cuối cùng nếu mọi biểu thức điều là true ![[Pasted image 20201008121710.png]]
- Sử dụng || sẽ trả về giá trị true đầu tiên, nếu mọi biểu thức điều false thì biểu thức cuối cùng sẽ được trả ra.![[Pasted image 20201008121804.png]]
- VD :
	- Chúng ta muốn trả về độ dài của một biến nhưng chúng ta không biết loại biến.
		- Bình thường chúng ta có thể sử dụng if/else để kiểm tra biến đó có kiểu được chấp nhận, nhưng nó có thể làm code dài. Đoản mạch có thể được sử dụng trong trường hợp này
		- return (foo || []).lenght; 
		- Nếu biến foo là truthy, nó sẽ được trả ra, nếu không chiều dài của một mảng rỗng sẽ là 0.
	- Khi truy cập thuộc tính đối tượng lồng nhau, chúng ta có thể không biết liệu đối tượng hoặc một trong các thuộc tính phụ có tồn tại hay không và điều này có thể gây ra lỗi khó chịu.
		- Đặt trường hợp chúng ta muốn truy cập một thuộc tính có tên là data trong this.state, nhưng dữ liệu không được xác định cho đến khi chương trình của chúng tôi trả lại kết quả fetch dữ liệu thành công.
		- Tùy thuộc vào vị trí chúng ta sử dụng nó. việc gọi this.state.data có thể ngăn chặn ứng dụng chạy, để giải quyết vấn đề này chúng ta có thể đặt nó trong một điều kiện.
		- if (this.state.data) {
			- return this.state.data;
		- } else {
			- return 'Fetching Data';
		- }
		- Nhưng làm như vậy thì có vẻ lặp đi lặp lại, trong trường hợp này sử dụng || sẽ ngắn gọn hơn
		- return (this.state.data || 'Fetching Data');
		- Chúng ta không thể chuyển đổi đoạn code trên thành &&. Đoạn 'Fetching Data' && this.state.data sẽ trả về this.state.data ngay cả khi nó undefined hoặc không. Điều này bởi vì 'Fetching data' mang giá trị truthy, and && sẽ luôn luôn chạy qua nó khi nó nằm ở đầu tiên.
==A New Proposed Feature: Optional Chaining==
	- Optional chaining hỗ trợ việc truy xuất thuộc tính nằm sâu trong cấu trúc dạng cây. Ký hiệu ? dùng để sử dụng để trích xuất một thuộc tính nếu nó không rỗng.
	- VD chúng ta có thể thay đổi ví dụ trên thành this.state.data?.(), do đó chỉ trả về dữ liệu nếu nó không phải là null. Hoặc nếu chúng ta chủ yếu quan tâm đến việc liệu trạng thái có được xác định hay không, chúng ta có thể trả về this.state?.Data.
==3. Convert to Boolean==
	- Bên cạnh giá trị logic thông dụng như true và false, JS cũng coi tất cả các giá trị khác là truthy hoặc falsy.
	- Trừ phi được định nghĩa khác, tất cả các giá trị trong JS đều là true, ngoại trừ 0, '', null, undefined, NaN và tất nhiên là false là falsy.
	- chúng ta có thể dễ dàng chuyển đổi giữa true và false bằng cách sử dụng toán tử phủ định !, cũng sẽ chuyển đổi kiểu thành boolean.
	- VD:
		- const isTrue = !0;
		- const isFalse = !1;
		- const alsoFalse = !!0;
	- Loại chuyển đổi kiểu này có thể hữu ích trong các câu lệnh có điều kiện.
==4. Convert to String==
- Để nhanh chóng chuyển một số thành một chuỗi, chúng ta có thể sử dụng toán tử + theo sau là một chuỗi rỗng ""
- VD: const val = 1 + "";
==5. Convert to Number==
- Chúng ta có thể chuyển từ chuỗi thành số nhanh chóng bằng việc sử dụng dấu + trước chuỗi.
- VD: let int = "15"; int = +int
- Điều này cũng có thể được sử dụng để chuyển đổi boolean thành số
- VD: console.log(+true); //Return: 1
- Có thể có những ngữ cảnh trong đó + sẽ được hiểu là toán tử nối hơn là toán tử cộng. Khi điều đó xảy ra (và chúng ta muốn trả ra một số nguyên, không phải là một số thực), thay vào đó, chúng ta có thể sử dụng hai dấu ngã : ~~
- Dấu ngã, được gọi là toán tử NOT bitwise, là một toán tử tương đương với -n-1. VD ~ 15 = -16.
- Việc sử dụng hai dấu ngã liên tiếp sẽ phủ định một cách hiệu quả phép toán, vì ~ - 16 = 15.
- VD: const int = ~~ "15"; console.log(int); //Result: 15.
- Ngoài ra toán tử NOT bitwise cũng có thể được sử dụng trên boolean: ~ true = -2 và ~ false = -1.
==6. Quick Powers==
- Kể từ ES7, nó đã có thể sử dụng toán tử lũy thừa ** như một cách viết tắt cho lũy thừa, nhanh hơn so với viết Math.pow(2,3). 
- console.log(2**3); //Result: 8
- Không nên nhầm lẫn ký hiệu này với ký hiệu ^, thường được sử dụng để biểu thị số mũ, nhưng trong JS là toán tử XOR bitwise.
- Trước ES7, viết tắt chỉ tồn tại cho các lũy thừa có cơ số a2, bằng cách sử dụng toán tử dịch chuyển trái bit <<:
- Các biểu thức sau là tương đương: Math.pow(2,n); 2 << (n-1); 2 ** n;
- Ví dụ: 2 << 3 = 16 tương đương với 2 ** 4 = 16.
==7. Quick Float to Interger==
- Nếu bạn muốn chuyển đổi một số thực thành một số nguyên, bạn có thể sử dụng Math.floor(), Math.ceil() hoặc Math.round(). Nhưng có một cách nhanh hơn cả là để biến float thành interger là sử dụng |, toán tử OR bitwise
- console.log(23.9 | 0); //23
- console.log(-23.9 | 0); //-23
- Hành vi của | khác nhau tùy thuộc vào việc chúng ta xử lý số dương hay số âm, vì vậy tốt nhất chỉ sử dụng khi biết chắc chắn.
- Nếu n dương thì n | 0 làm tròn hiệu quả. Nếu n là âm, nó có hiệu quả làm tròn. Nói một cách khác, thao tác này sẽ loại bỏ bất cứ thứ gì đứng sau thập phân, cắt bớt một số thực thành một số nguyên.
- Chúng ta có thể nhận được cùng kết quả làm tròn với cách sử dụng ~~ , như ở trên, và trên thực tế, bất kỳ toán tử bitwise nào cũng sẽ buộc một số float thành một số nguyên. Lý do khiến các phép toán cụ thể này hoạt động là - một khi bị buộc phải là số nguyê - giá trị không thay đổi.
==Remove Final Digits==
- Toán tử OR bitwise cũng có thể được sử dụng để loại bỏ bất kỳ số lượng chữ số nào ở cuối một số nguyên.
- Chúng ta sẽ không cần sử dụng code như sau: let str = "1553"; Số (str.substring(0,str.length - 1)); 
- Thay vào đó chúgn ta viết: console.log(1553/10 | 0) //155 ; console.log(1553/100 | 0) //15, console.log(1553/1000 | 0) // 1
==8. Automatic Binding in Classes==
- Chúng ta có thể sử dụng ký hiệu mũi tiên trên ES6 trong các phương thức lớp và bằng cách làm như vậy ràng buộc được ngụ ý. Điều này thường sẽ lưu một số dòng mã trong hàm tạo lớp, và chúng ta sẽ không cán phải sử dụng các biểu thức lặp lại như this.myMethod = this.myMethod.bind(this)
==9. Truncate an Array==
- Nếu bạn muốn bỏ một giá trị ở cuối mảng, có nhiều cách thay thế nhanh hơn sử dụng splice().
- Ví dụ, nếu bạn biết rõ đọn dài của mảng gốc, bạn có thể định nghĩa lại thuộc tính độ dài của nó:
	- let array = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];
	- array.length = 4;
	- console.log(array); //Result: [0, 1 , 2, 3];
- Đây là một giải pháp đặc biệt ngắn gọn, tuy nhiên thời gian chạy của phương thức slice() thậm chỉ còn nhanh hơn. Nếu tốc độ là mục tiêu chính thì có thể sử dụng slice.
	- let array = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];
	- array = array.slice(0,4);
	- console.log(array); //Result: [0, 1 , 2, 3];
==10. Get the Last Item(s) in an Array==
- Phương thức slice() của array có thể nhận lấy giá trị số nguyên âm. và nếu nó nhận vào thì nó sẽ lấy giá trị từ cuối cùng của mảng thay vì bắt đầu.
	- let array = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];
	- console.log(array.slice(-1)); //Result [9];
	- console.log(array.slice(-2)); //Result [8, 9];
	- console.log(array.slice(-3)); //Result [7, 8, 9];
==11. Format JSON Code==
- JSON.stringify có thể giúp thụt lề JSON.
- Phương thức stringify() nhận hai tham số tùy chọn: một hàm thay thế, bạn có thể sử dụng để lọc JSON được hiển thị và một giá trị khoảng trắng.
- Giá trị khoảng trắng nhận một số nguyên cho số khoảng cách mà bạn muốn hoặc chuỗi (VD '\t'  để chèn tab) và nó có thể giúp đọc dữ liệu JSON đã tìm nạp dễ dàng hơn rất nhiều.
- console.log(JSON.stringify({ alpha: 'A', beta: 'B' }, null, '\t'));// Result:
// '{
//     "alpha": A,
//     "beta": B
// }'

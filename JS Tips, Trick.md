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
==Tránh lỗi khi dùng default function==
- Các default array function của JS như map, forEach, filter,... sẽ bị lỗi nếu như array null hoặc undefined (VD: Nhận dữ liệu từ server), nó khá nguy hiểm nếu quên có thể gây ứng dụng đột tử. Nên kiểm tra trước khi gọi các function đó. 
- Có thể lồng vào scope của if để tránh trường hợp như vậy.
==Sử dụng toán tử Ternary Operator==
- Toán tử ba ngôi tùy từng trường hợp có thể không được khuyến khích, nhưng nếu cần giải pháp để code ngắn hơn thì có thể nghĩ đến nó.
==Dùng 3 dấu bằng thay cho 2 dấu bằng==
- Code == sẽ cố ép giá trị khi thực hiện chuyển đổi tự động.
- === sẽ không chuyển đổi mà cân bằng giá trị và kiểu của toán hạng, nhanh hơn nhiều so với ==
==Tận dụng những hàm có sẵn==
- Thay vì sử dụng forEach, Map, filter,.. kèm với jQuery. Tuy nhiên bản chất của JS đã có nhiều hàm để làm việc với Object, Array, String... Cho nên không cần phải sử dụng phần mềm thứ ba cho những vấn đề đó.
==Hạn chế sử dụng try-catch-finally trong vòng lặp==
- Lệnh try-catch-finally sẽ tạo biến mới trong phạm vi nhất định khi catch clause được áp dụng. Điều này sẽ gây caught exception object gán với một biến số.
- nên đặt vòng lặp trong try
==Các Array method cần biết==
+ push(), pop(), shift(), unshift():
	- Đây điều là các method giúp thêm hoặc xóa phần tử của mảng, tác dụng như sau: push() Thêm phần từ vào cuối mảng - unshift() Thêm phần tử vào đầu mảng - pop() Xóa phần tử cuối cùng trong mảng - shift() Xóa phần tử đầu tiên trong mảng.
+ every()
	- Method này sẽ có tham số là một hàm (tạm gọi là testMethod). Hàm testMethod sẽ có cấu trúc như sau function(el, index, arr) và luôn trả về giá trị true/false.
	- el: giá trị của phần tử hiện tại - index: vị trí của phần tử hiện tại trong mảng - arr: mảng chứa phần tử hiện tại.
	- Method every() sẽ kiểm tra xem toàn bộ phần tử trong mảng có thỏa mãn testMethod không.
	- ![[Pasted image 20201028091504.png]] testMethod ở đây chính là hàm kiểm tra xem phần tử có phải là số chẵn hay không.
+ some()
	- Tương tự, method này cũng nhận vào một tham số là testMethod. Method này sẽ trả về true nếu có ít nhất 1 phần tử trong mảng thỏa mãn testMethod, nếu không sẽ trả về false.
+ map()
	- Method này sẽ nhận vào tham số là một testMethod, tuy nhiên method này không nhất tiết phải trả về giá trị true/false, method này sẽ trả về một mảng mới, với giá trị được trả về từ testMethod của từng phần tử.
	- vd muốn bình phương tất cả phần tử trong mảng: arr.map(el => el*el).
+ find()(
	- Method này nhận vào một tham số là 1 testMethod và trả về phần tử đầu tiên thỏa mãn testMethod, nếu không có phần tử nào thì trả về undefined.
+ reduce()
	- Đây là method dùng để tính toán các phần tử của mảng (theo thứ tự từ trái sang phải).
	- Method này sẽ nhận vào 2 tham số: 
		- Tham số 1: function(total, el): Là một hàm tính toán, total chính là kết quả phép tính của phần tử trước, còn el chính là phần tử hiện tại.
		- Tham số 2: initValue: Giá trị ban đầu của phép tính, được sử dụng làm total cho phép tính của phần tử đầu tiên.
	- VD: arr.reduce((total, el) => total + el, 0) -> sẽ cộng tất cả các giá trị trong mảng.
+ splice()
	- Method này sử dụng để xóa các phần tử trong mảng và sẽ trả về các phần tử đã xóa. Method này nhận vào hai tham số:
		- index: vị trí của phần tử đầu tiên muốn xóa.
		- deleteCount: số phần tử muốn xóa từ vị trí index.
	- const remove = arr.splice(0,2) => ra mảng mới remove mang giá trị của mảng arr sau khi đã xóa 2 phần tử từ vị trí 0.
+ slice()
	- Method này tương tự với hàm substring() chỉ khác là sử dụng với mảng. Method này nhận 2 tham số:
		- Tham số 1: start vị trí phần tử đầu tiên.
		- Tham số 2: end vị trí của phần tử cuối cùng được tính là (n-1), nếu không truyền vào thì mặc định là độ lớn của mảng.
	- VD: const subArray = arr.slice(0,2) -> tạo ra mảng con subArray chứ phần tử 0 và 1 của mảng arr.
+ filter()
	- Method này nhận vào tham số là một testMethod và sẽ trả về mảng chứa các giá trị thỏa mãn testMethod.
	- VD: const filter = arr.filter(el => el % 2 == 0) -> tạo ra mảng mới filter chứa các số chẵn của mảng arr.
+ includes()
	- Method này nhận vào 1 tham số là el và sẽ trả về true, nếu mảng có chứa phần tử el, ngược lại sẽ trả về false.
	- VD: arr.includes(1): nếu arr chứ số 1 sẽ trả về true, còn không thì false.
+ forEach()
	- là phương thức có sẵn của array được JS cung cấp, nó giúp lặp qua các item trên array.
+ sort()
	- method này giúp sắp xếp số và ký tự. Cần lưu ý phương thức này làm mutate mảng gốc.
	- phương thức này nhận một hàm như một số. Nó sắp xếp các phần tử của một mảng.
	- ![[Pasted image 20201028103151.png]]
+ Array.from()
	- Giúp tạo 1 array từ một kiểu dữ liệu khác.
	- ![[Pasted image 20201028102138.png]]
+ Array.of()
	- Truyền vào phần tử khi tạo array.
	- VD. const nums = Array.of(1,2,3) => nums = [1, 2, 3].
+ flat()
	- Thường được sử dụng để tạo ra một mảng mới chứa các phần tử trong mảng (mà chứa các mảng con.)
	- ![[Pasted image 20201028102818.png]]
+ findIndex()
	- phương thức này sẽ nhận một hàm làm tham số và sẽ áp dụng nó cho mảng. Nó trả về chỉ mục của một phần tử được tìm thấy và thỏa mãn hàm kiểm tra được truyền dưới dạng đối số hoặc trả về -1 nếu không thỏa mãn nó.
+ concat()
	- phương thức này sẽ hợp nhất hai hoặc nhiều mảng / giá trị bằng cách ghép nó. Nó sẽ trả về một mảng mới.
+ fill()
	- phương thức này điền vào tất cả các phần tử của một mảng nhất định có cùng giá trị, từ chỉ mục bắt đầu (mặc định 0) đến chỉ mục kết thúc (mặc định array.length).
	- phương thức này làm thay đổi mảng gốc.
	- vd arr.fill(0, 1, 3) => đặt giá trị cho ô 1,2 của mảng arr giá trị 0
+ reverse()
	- Phương thức này sẽ đảo ngược một mảng. phương thức này sẽ làm thay đổi mảng gốc.
+ flatMap()
	- phương thức này áp dụng một hàm cho từng phần tử của mảng và sau đó làm phẳng kết quả thành một mảng. nó là sự kết hợp giữa hai phương thức flat() và map()
	- ![[Pasted image 20201028103738.png]]
+ entries()
	- phương thức này sẽ trả về một mảng iterator object chứa các cặp giá trị key/value cho mỗi index trong mảng.
	- ![[Pasted image 20201028105644.png]]
+ copyWithin()
	- phương thức này sẽ sao chép các phần tử trong mảng với vị trí bắt đầu và kết thúc việc sao chép được xác định.
	- Thực chất phương thức này không chỉ sao chép mà nó sẽ ghi đè các phần tử nó sao chép được lên các phần tử của mảng tính từ một vị trí xác định bởi người dùng.
	- phương thức này nhận vào 3 tham số:
		+ tham số đầu tiên là vị trí mà hàm sẽ bắt đầu ghi đè các phần tử sao chép được.
		+ tham số thứ 2 là vị trí bắt đầu sao chép.
		+ tham số thứ 3 là vị trí kết thúc sao chép. vị trí này được tính là n-1.
	- vd arr= [0,1,2,3,4,5] => arr.copyWithin(2,0,2) => [0,1,0,1,4,5].
==Intl.NumberFormat==
- Sử dụng dùng để format các đơn vị tiền tệ dựa theo language của hệ điều hành
==.blur()==
- Dùng để click ra ngoài, bỏ focus hiện tại.
==.focus()==
- Dùng để focus vào HTML Object
==.remove()==
- Xóa object HTML khỏi cây DOM.
==Tạo thanh navbar sticky khi scroll qua nó==
1.	DOM tới thanh navbar
2.	lấy giá trị top của thanh navbar thông qua .offsetTop.
3.	kiểm tra nếu window.pageYOffset >= giá trị top của navbar thì add class sticky cho nó, còn không thì remove thông qua classList.
4.	Trigger function bằng onscroll gắn vào body.

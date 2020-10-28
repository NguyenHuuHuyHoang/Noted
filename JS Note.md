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
		- Tên thì phải có nghĩa, KHÔNG ĐƯỢC đặt tên theo kiểu viết tắt: dlCounter, uName, idl, a, a1, doFA.
		- Tránh đặt những tên quá chung chung, tối nghĩa: top, best, doIncrease, getAll
		==Quy tắc về số lượng==
		- Hàm không nên quá 30 dòng.
		- Lớp không nên vượt quá 500 dòng.
		- Một hàm không được vượt quá 5 tham số (tốt nhất nên giữ <= 3)
		- Một hàm chỉ làm duy nhất 1 việc, trong trường hợp chính đáng làm hai việc cũng được cho phép, tuy nhiên tên hàm phải nói rõ điều này: increaseDownloadCounterAndSaveToDatabase.
		- Khi khai báo biến, một dòng chỉ chứa một biến.
		- Một dòng không nên dài quá 80 kí tự.
		- Các câu lệnh lồng nhau tối đa 4 cấp.
		==Quy tắc xuống hàng==
		- Nếu có dấu phẩy thì xuống hàng sau dấu phẩy.
		- Xuống hàng trước toán tử +,-,..
		- Nếu có nhiều cấp lồng nhau thì xuống hàng theo từng cấp.
		- Dòng xuống hàng mới thì nên bắt đầu ở cùng cột với đoạn lệnh cùng cấp ở trên.
		==Comment==
		- Hạn chế dùng comment để giải thích code, thay vào đó cải thiện đoạn code
		- Chỉ nên dùng comment trong trường hợp viết documentation cho thư viện, thông tin đính kèm cho class.
==Callback==
- Callback là một hàm sẽ được thực hiện sau khi một hàm khác đã thực hiện xong - vì thế nó có tên là Callback. Cụ thể hơn thì trong JS, hàm là đối tượng. Các hàm thực hiện điều này được gọi là higher - order function (Hàm bậc cao hơn). Bất kỳ hàm nào được truyền dưới dạng đối số được gọi là hàm callback.
- VD truyền 1 đoạn code (Hàm A) này vào một đoạn code khác (Hàm B). Tới một thời điểm nào đó, hàm A sẽ được Hàm B gọi lại (callback). 
- Tầm quan trọng của hàm Callback, JS là ngôn ngữ hướng sự kiện và bất đồng bộ nên Callback đóng vai trò rất quan trọng, chúng ta sẽ truyền một Callback function vào các sự kiệt và xử lý bất đồng bộ. Thay vì chờ phản hồi trước khi tiếp tục thì JS sẽ tiếp tục thực thi trong khi lắng nghe các sự kiện khác. Trình biên dịch đọc mã từ trên xuống dưới, từ trái qua phải. Hàm viết trước thì được thực hiện trước và hàm viết sau thì sẽ được thực hiện sau. Tuy nhiên trong trường hợp hàm trước là một hàm mà khi thực thi sẽ mất 1 khoảng thời gian để xử lý vd như gọi API hoặc đọc file thì chúng ta sẽ thấy hàm sau ra kết quả xong hàm trước mới trả ra kết quả => JS không thực hiện các hàm theo thứ tự mà chúng ta muốn => Callback là hàm đảm bảo code nhất định không được thực thi cho đến khi code khác thực thi xong. 
- Việc sử dụng Callback function phải hết sức cẩn thận, phải tuân thủ đúng nguyên tắc mà hàm đó đưa ra, có hàm sẽ truyền thêm tham số cho hàm Callback và có hàm thì không. VD hàm forEach, hàm này sẽ có tác dụng lặp một mảng và có hai tham số callback function. Mỗi vòng lặp sẽ truyền hai tham số vào hàm callback function, tham số thứ 1 là giá trị của phần tử đang lặp, tham số thứ 2 đó là vị trí index của phần tử đó.
- Khi chúng ta truyền hàm callback vào tương tư như tham số bình thường (chú ý không có dấu () sau tên hàm), đều này giúp cho hàm callback không được thực thi, mà chỉ được truyền vào như một tham số.
- Các nguyên tắc khi thực hiện Callback Function
	1. Tham số truyền vào phải là 1 function: Cần phải kiểm tra giá trị người dùng truyền vào là 1 function thì mới được thực thi thông qua typeof và giá trị function
	2. Cẩn thận với this khi hàm callback nằm trong object: Hàm được xây dựng trong Object là hàm được định nghĩa thông qua key của object và giá trị của key là một hàm. VD: hàm setName được xây dựng trong object personInfo. Theo nguyên tắc callback là một hàm đơn phương nên khi sử dụng từ khóa this trong hàm thì nó sẽ hiểu lúc này this chính là đối tượng Window Object, vì vậy cho dù định nghĩa hàm callback nằm trong object thì không thể truy cập đến dữ liệu của object thông qua từ khóa this.
	3. Khắc phục this khi hàm callback nằm trong object: Để tránh việc con trỏ this trong callback trỏ tới window object thì chúng ta sử dụng phương thức apply của function. khi này con trỏ this sẽ trỏ tới object của hàm callback.
	4. Callback Hell: hàm callback được thực thi trong một hàm khác, nếu ta tiếp tục có hàm callback bên trong 1 hàm callback khác có thể sẽ dẫn tới một vòng lặp vô tận => Callback Hell => logic xử lý của chương trình sẽ trở nên cực kỳ phức tạp và khó nắm bắt, khi có lỗi xảy ra ta rất khó để debug cũng như giải quyết, bên cạnh đó cũng làm giảm đi tính thẩm mỹ của code, khó đọc, khó maintain. Hiện nay để xử lý Callback Hell thì người ta sử dụng Promise và async/await.
==Promise==
- Promise là cơ chế trong JS giúp thực thi các tác vụ bất đồng bộ mà không rơi ào callback hell hay pyramid of doom, là tình trạng các hàm callback lồng vào nhau ở quá nhiều tầng. Các tác vụ bất đồng bộ có thể là gửi AJAX request, gọi hàm bên trong setTimeout, setInterval hoặc requestAnimationFrame, hay thao tác với WebSocket hoặc Worker,..
- Để tạo ra một promise object thì sử dụng class Promise có sẵn trong trình duyệt. const p = new Promise(tham số). tham số là 1 function gồm có 2 tham số, tham số thứ 1 là resolve hàm sẽ được gọi khi promise hoàn thành, tham số thứ 2 là reject là hàm sẽ được gọi khi có lỗi xảy ra.
- Truy xuất kết quả của promise object thông qua phương thức .then(onSuccess, onError). phương thức này nhận vào 2 hàm, onSuccess được gọi khi promise hoàn thành và onError được gọi khi có lỗi xảy ra. Bên trong tham số onSuccess có thể trả về một giá trị đồng bộ vd như giá trị số, chuỗi, null, undefined, arrray hoặc object hoặc một promise object khác. Các giá trị bất đồng bộ sẽ được bọc trong một Promise, cho phép kết nối (chaining) nhiều promises lại với nhau (promise chain).
- Phương thức catch() chỉ là cú pháp bọc đường (syntactic sugar) của .then(null, onError).
	==Tạo nhanh Promise==
	- Trường hợp chỉ cần bọc một giá trị vào promise hay tự động reject. Thay vì dùng cú pháp new Promise() dài dòng có thể sử dụng hai phương thức tĩnh là: Promise.resolve(result) và Promise.reject(err)
==Async / await==
- Được giới thiệu trong ES8, async/await là một cơ chế cho chúng ta thực hiện các thao tác bất đồng bộ một cách tuần tự hơn. Async/await vẫn sử dụng Promise ở bên dưới nhưng mã nguồn (theo một cách nào đó) vẫn trong sáng và dễ theo dõi.
- Để sử dụng, chúng ta phải khai báo hàm với từ khóa async, khi đó bên trong hạm có thể sử dụng await. Kết quả trả về của async function luôn là một promise. Async/await về cơ bản có thể sử dụng cho tất cả trình duyệt hiện đại trừ IE11 ra vì cần phải polyfill (một đoạn code dùng để cung cấp các tính năng của trình duyệt hiện đại cho trình duyệt cũ hơn)
==Các trường hợp cần lưu ý khi sử dụng Promise==
	+ "Kim tự tháp" Promise: nguyên nhân cơ bản là do không sử dụng tính chất liên kết của promise, cho phép bên trong hàm resolve có thể trả về một giá trị đồng bộ hoạc một promise khác. Việc hiểu và sử dụng thành thạo tính liên kết là một trong những điểm quan tọng nhất khi làm việc với promise. Khi promise lồng từ hai tầng trở lên thì cần phải refactor lại.
	+ Luôn đưa vào .then() một hàm: phương thức .then đòi hỏi tham số của nó phải là một hàm. Nếu đưa vào .then một giá trị, nó sẽ bị bỏ qua.
	+ Cẩn thận với this khi dùng tham chiếu hàm: Trong strict mode, biến ngữ cảnh this chỉ được xác định khi trực tiếp gọi phương thức của đối tượng đó, hoặc thông qua bind()
	+ Chạy các Promise tuần tự: Trường hợp muốn chạy các promise tuần tự (promise 1 chạy xong ra kq thì promise 2 sẽ chạy, ra kết quả xong chạy promise 3) thì chúng ta có thể sử dụng phương thức reduce của array. [promise1, promise2, promise3].reduce(function(currentPromise, promise) {return currentPromise.then(promise)}, Promise.resolve()). Ngoài ra còn có thể sử dụng Async/await: async function() {const res1 = await promise1(); const res2 = await promise2(res1); const res3 = await promise3(res2)}
	+ Chạy nhiều Promise cùng lúc với Promise.all(): Trường hợp muốn thực thi và lấy kết quả của nhiều promise cùng lúc. Phương thức Promise.all nhận vào một mảng các promises và chỉ resolve khi tất cả các promise này hoàn thành, hoặc reject khi một trong chúng xảy ra lỗi.
	+ Promise.race(): Ngoài hai kiểu chạy tuần tự và song song thì còn có Promise.race nhận vào là một mảng promises và sẽ resolve/reject  ngay khi một trong số các promises này hoàn thành/xảy ra lỗi.
	+ Cẩn thận với return không tường minh: trong JS nếu một hàm không công khai trả về một giá trị, undefined mặc định sẽ được trả về. Do đó cần lưu ý giá trị return khi làm việc với promise
	+ Phân biệt .then(resolve, reject) và .then(resolve).catch(reject): Hàm reject trong .then(resolve, reject) chỉ có thể chụp được lỗi từ những .then() phía trước nó, mà không thể bắt được lỗi xảy ra trong hàm resolve cùng cấp. Lưu ý là promise sẽ dừng quá trình thực thi khi bắt được lỗi.
	+ Truyền dữ liệu giữa các promise với nhau: Một trong những điểm yếu của Promise là không có cơ chế mặc định để truyền dữ liệu giữa các promise objectss với nhau. Có một cách là sử dụng Promise.all() kết hợp với kỹ thuật phân rã biến trong ES. Ngoài ra còn có thể dùng object hoặc async/await để truy xuất kết quả của các promise phía trước.
	+ Promise không lazy: Khi gọi promise thì hàm executor của Promise được thực thi ngay lập tức, trong trường hợp không muốn nó thực hiện ngay lập tức thì có thể đưa vào một hàm trả về promise.
	+ .finally() : bên cạnh .then() và .catch(), chúng ta còn có .finally(onFinally). Phương thức này nhận vào một hàm và sẽ được kích hoạt dù cho promise trước nó hoàn thành hay xảy ra lỗi. Phương thức này chỉ hỗ trợ firefox, chorme và opera.
	+ Tóm lại: Promise và async/await không hoàn toàn thay thế mà hỗ trợ lẫn nhau. Đa phần các trường hợp sẽ dùng async/await tuy nhiên promise vẫn là nền tảng cần thiết khi thực thi các tác vụ bất đồng bộ trong JS. Do đó nên cần phải xem xét và lựa chọn giải pháp phù hợp tùy vào tình hình thực tế.
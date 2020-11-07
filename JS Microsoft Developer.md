1. ==JS is a programming language==
	1. Được thiết kế để lập trình tương tác với các phần tử của một trang web VD như thêm 1 sự kiện click vào một nút mà nó sẽ show một alert hoặc thay đổi phong cách của một phần tử
	2. Mặc dù gọi là JavaScript nhưng nó không phải là Java, nó giống như ngôn ngữ C nhưng được thiết kế với tư tưởng gần giống như Java.
	3. Nó có kiểu dữ liệu động, chúng ta không cần phải khai báo kiểu dữ liệu của các biến, nó có thể tự nhận biết các biến thuộc kiểu dữ liệu gì.Vd nếu chúng ta cho x = 0 thì JS sẽ hiểu x có kiểu dữ liệu là number. 
	4. JS compiled JIT (Just in time), có nghĩa là chúng ta không cần phải compile hoặc build nó trước khi chạy nó, chúng ta cứ chạy nó và nó làm việc, code được biên dịch khi nó chạy
	5. Có nhiều ngôn ngữ lập trình ở ngoài vì vậy tại sao lại học JS. "bất cứ thứ gì được viết bằng JS cuối cùng sẽ được viết bằng JS" Jeff Atwood. JS có ở bất cứ nơi đâu:
		1. Client: Nó có trong trình duyệt web (browser) và những trình duyệt web đã đi một chặng đường dài trong năm năm qua trở thành một môi trường phát triển ứng dụng đầy đủ. Họ sử dụng để xem các văn bản trên web, bây giờ họ cũng sử dụng cho các ứng dụng. Bạn có thể xây dựng những ứng dụng phong phú, đa dạng, nhiều trải nghiệm trên trinh duyệt web mà điều đó nhìn giống như là các ứng dụng desktop. Trong 10 năm qua web đã phát triển một cách đáng kể để trở thành một môi trường đầy đủ khả năng cho các ứng dụng.
		2. Server: JS ở trên server với cái gì đó được gọi là Node.js, nó xử lý các đoạn mã JS trên server. Tất cả những gì mà chúng ta có thể làm với C# hoặc Java trên server bạn cũng có thể làm với JS, VD như đọc hoặc ghi file hoặc tương tác với một cơ sở dữ liệu. 
		3. Native: Xây dựng các ứng dụng gốc (native) cho desktop và mobile với electron, react native và native script. Những ứng dụng này mà chúng ta muốn cài đặt từ một cửa hàng ứng dụng trên điện thoại hoặc trên desktop, điều này được cho phép bởi các framework mã nguồn mở được bảo trì bởi các công ty, vd như Facebook hoặc ngay cả microsoft. Theo 1 khảo sát năm 2019 các lập trình viên của stackoverflow thì JS là ngôn ngữ lập trình sử dụng nhiều nhất trên thế giới.
		4. Chúng ta học JS bởi vì mọi người đang sử dụng nó. Ai đang sử dụng nó: Tất cả những trang web truyền thông xã hội hoặc thương mại điện tử mà bạn rất yêu thích tất cả điều đang sử dụng JS, các công ty lớn xây dựng các ứng dụng mà bạn đang sử dụng bằng JS, một số ứng dụng desktop mà bạn thích vd như VS Code và Slack được viết bởi JS.
		5. Tóm lại JS là một ngôn ngữ lập trình có thể được sử dụng ở mọi nơi để xây dựng mọi thứ.
2. ==JS on the Client vs JS on the Server==
	- JS on the Client: 
		+ Khi nói về JS ở trên Client chúng ta thường liên tưởng đến một trình duyệt web, bây giờ nó có thể là một ứng dụng native được viết bởi một thứ gì đó như React Native hoặc Electron. Nhưng phần lớn chúng ta cần một trình duyệt web. 
		+ Bây giờ khi viết JS cho trình duyệt web cần một script tag trong trình duyệt web. Sau đó chúng ta đặt code JS vào trong script tag đó.
		+ Tuy nhiên chúng ta thường không muốn để JS trực tiếp trong trang mà sẽ đặt nó trong những file tách rồi, vì thế nó dễ dàng hơn để bảo trì. Để làm việc đó, cần đặt nó vào một file có phần mở rộng .js, sau đó sử dụng thuộc tính src của script tag để link tới file .js đó. Nó được gọi là thuộc tính nguồn nó sẽ mang file script vào trang, khi trang load thì JS sẽ được chạy.
		+ JS được sử dụng trong một trình duyệt web thường được sử dụng để xây dựng một số giao diện người dùng, như vậy JS chạy ở trình duyệt web cũng truy cập đến một thứng được gọi là Document Object Model. Mọi người thường liên hệ điều này như DOM.
		+ DOM chỉ là các hàm và đối tượng mà JS truy cập vào trong trình duyệt web.
		+ VD như chúng ta có thể sử dụng một thứ gì đó được gọi là document object, nó là một đối tượng, điều kì diệu là nó tồn lại khi bạn chạy JS trong một trình duyệt web, thông qua phương thức getElementById, nó sẽ trả lại một phần tử HTML mà nó có cái id. Bạn có thể làm một điều gì đó với phần tử đó với JS chẳng hạn như thay đổi màu sắc.
	- JS on the Server:
		+ Khi viết JS ở phía server thì trò chơi thay đổi một chút xíu. Chúng ta thường không xây dựng một giao diện người dùng. 
		+ Bạn sẽ viết một số đại loại như một dịch vụ web hoặc dịch vụ thông thường, sau đó là những thứ đại loại như đọc và ghi các file hoặc tương tác với DB, đó là những nhiệm vụ của phần server.
		+ Để chạy JS trên server bạn cần một thứ gì đó gọi là Node.js. 
		+ kể từ lúc bạn không có bất kỳ trình duyệt web nào trên server hoặc các script tags. Bạn phải cài đặt thứ gọi là Node.js trên server, sau đso bạn có thể thực thi bất kỳ file JS thông qua gọi Node và sau đó trực tiếp tới file script của bạn từ terminal hoặc giao diện dòng lệnh. Nodejs không phải là web browser, nó không có components nhìn thấy được, DOM không tồn tại trên Nodejs, cái mà bạn nhận được thay thế là một thứ gì đó được là các gói (packages).
		+ Bây giờ một số package này đã được xây dựng ở trong chính Nodejs vd như được file (fs), đây là những thứ giống như có thể tương tác với file hệ thống.
		+ Có một kho của một đơn vị party thứ 3 được gọi là npm, mà nó chứa những gói cho bất cứ điều gì mà bạn có thể nghĩ ra.
	- Tóm tắt:
		+ Client: Chạy trên một trình duyệt web sử dụng script tags, nó chủ yếu được sử dụng để xây dựng các giao diện người dùng và tương tác với các phần tử của giao diện người dùng trong trang (DOM), có khả năng truy cập các hàm và đối tượng (DOM).
		+ Server: yêu cầu Node.js được cài đặt và có khả năng truy cập đến những gói được xây dựng trong node và bên thứ 3. Thường được sử dụng để xây dựng nhưng thứ đại loại như dịch vụ web.
3. ==Setting up your toolbox==
	- VS Code
		+ ESLint: tìm và sửa những vấn đề trong code JS trước khi nó được build
		+ Prettier: Tự động định dạng code, không cần phải quan tâm đến khoảng trắng thêm.
		+ JS (ES6) code snippets: Tránh gõ dư thừa với các lối tắt tới phần lớn mảng code được sử dụng thường xuyên.
	- Node.js
		+ Cài đặt Node.js bằng cách sử dụng NVM (Quản lý nâng cấp và nhiều môi trường). Sau khi cài nvm từ github, thì chạy thông qua lệnh nvm(node version manager) install node
4. ==Console.log==
	- Có hai cách để xuất dữ liệu từ một biến, là sử dụng template string hoặc sử dụng %s để đại diện cho biến truyền vào.
	- console.log(`${greeting}, ${place}`); => Hello, World
	- console.log('%s, %s', greeting, place); => Hello, World
5. ==Code Comment==
	- Nếu code của bạn cần một comment để giải thích nó làm gì, nó có lẽ quá phức tạp. Có thể bọc code trong một hàm với tên mô tả. VD thay vì comment: this code reverses a string, có thể đặt hàm tên reservedValue, làm như vậy thì bản thân code đã tự giải thích mục đích của nó rồi. Người lập trình tiếp theo chỉ cần đọc tên function là sẽ biết chức năng của nó mà không cần comment.
	- Single line: bắt đầu // ở đầu dòng, phần lớn các trình chỉnh sửa sẽ thay đổi màu sắc chữ của dòng thành màu xám. Chỉ áp dụng cho dòng hiện tại.
	- Multi line: Được thiết kế để comment nhiều dòng, /* ở đầu dòng bắt đầu và */ ở cuối dòng kết thúc. Không quan trọng bao nhiêu dòng.
	- Để giúp clean code thì hạn chế comment và thay vào đó làm cho code dễ dàng đọc hơn.
	- Khi nào thì cần comment, để giúp người đọc dễ dàng hiểu về code, hoặc là nhắc chính bản thân về nhiệm vụ của đoạn code vd: // TODO: Add in database connection string (Chúng ta có thể sử dụng chức năng tìm kiếm với key là TODO để duyệt nhanh các TODO trong code), để nhanh chóng ẩn các logic code mà chúng ta không muốn chạy, mà chúng ta không muốn xóa nó.
6. ==Delaring Varialbes==
	 - Trong JS có ba cách để khai báo một biến bằng ba từ khóa: var, let, const. Ba từ khóa này khác nhau một chút về cách hoạt động. Do đó thật tốt nếu chúng ta hiểu những cách khác nhau mà chúng ta có thể sử dụng những biến này và lý do chúng ta muốn sử dụng loại từ khóa để khai báo một biến.
	 - từ khóa var: Đây là từ khóa tồn tại lâu nhất, đó là cách ban đầu mà chúng ta khai báo một biến trong JS và var có phạm vi khai báo là một hàm. Điều đó có nghĩa là biến khi được khai báo bằng var sẽ tồn tại ở bất cứ nơi đâu trong hàm đó, thậm chí nó có sẵn trước khi chúng ta khai báo vì nó có sẵn trong toàn bộ hàm đó. Ví dụ khai báo biến ở dòng 10, nhưng thực tế nó đã có ở dòng 1. Một điều khác với biến kiểu var là biến có thể thay đổi trong scope, điều đó có nghĩa là no là một loại biến có thể thay đổi được (mutable), chúng ta có thể gán lại nó, có thể thay đổi kiểu dữ liệu của nó hoặc bất kỳ thứ gì mà chúng ta muốn làm, điều đó làm biến var là một biến rất linh hoạt nhưng nó cũng là một nguy hiểm tiềm ẩn trong việc khai báo các biến. => Function scoped, can be changed in scope, available before declaration.
	 - từ khóa let: let thì gần giống var, ngoại trừ nó có phạm vi block thay vì function, nó được biểu thị bằng cặp dấu ngoặc nhọn nơi mà chúng ta khai báo biến ở trong đó, nó cũng chỉ được sử dụng sau khi khai báo biến khác với var khi mà biến có thể sử dụng trong bất cứ đâu trong phạm vi mà nó được khai báo, vd nếu khai báo biến let ở dòng 10 thì chỉ có thể sử dụng nó từ dòng 10 trở đi, nó cũng là một loại biến có thể biến đổi (mutable), chúng ta có thể thay đổi giá trị, kiểu,.. trong khi nó bên trong phạm vi block của nó, nhưng một khi ở ngoài phạm vi block thì biến sẽ không còn tồn tại, chúng ta có thể tái sử dụng lại tên biến => block scoped, can be changed in scope, only available after declaration.
	 - từ khóa const: const thì gần giống như let, nhưng khác let ở chỗ nó chỉ được gán trị 1 lần và không thể gán lại (Hằng số),  => block scoped, like let, Cannot be changed, Only available after declaration.
	 - khi nào sử dụng các từ khóa:
		 - sử dụng biến const thường xuyên nhất nếu có thể (const by default), điều này sẽ giúp bạn khi bạn quay lại và nhìn vô code của bản thân mình hoặc giúp đỡ, những người khác khi họ nhìn vào code của bạn sẽ biết rằng biến đó chỉ được gán giá trị một lần duy nhất, không thể gán giá trị lại. Nó chỉ có là giá trị mà được khởi tạo ngay từ đầu và sẽ không thay đổi (immutable). Điều này hữu ích để đảm bảo rằng bạn sẽ có ít cơ hội cho bugs, nó thường xảy ra bởi vì một biến được gán lại giá trị mà chúng ta không nhận ra, mặc dù vậy let vẫn rất hữu ích.
		 - Chúng ta sẽ muốn sử dụng biến let bên trong một vòng lặp hoặc một block đặc biệt mà nó được sử dụng lại, bởi vì bên trong của một block scope, nơi bạn muốn tạo một biến mới mỗi lần lặp và gán 1 giá trị mới cho nó, nếu sử dụng const sẽ không thể gán lại giá trị và tái sử dụng tên biến. Không còn lý do cần thiết để sử dụng biến var nữa, bởi vì let và const đã cover tất cả các trường hợp sử dụng, và nó cũng loại bỏ một số vấn đề chúng ta có thể có với một biến var dựa vào sử khai báo biến.
7. ==String Concatenation (Nối chuỗi)==
	- Chuỗi là một loại dữ liệu mà nó đại diện có các yếu tố văn bản trên trang web. Điều này có thể là bất cứ thứ gì từ đầu ra console.log đến văn bản trên một trang web. Đôi khi chúng ta cần phải định dạng văn bản trước khi nó tới vị trí cuối cùng, đó là lúc cần sử dụng nối chuỗi.
	- Kết hợp hai hoặc nhiều chuỗi: để dễ dàng hơn cho việc định dạng văn bản, có thể gắn một biến và một chuỗi, gắn nhiều chuỗi với nhau sẽ tạo thành một chuỗi mới.
	- Sử dụng toán tử + để thực hiện nối chuỗi.
	- Cẩn thận với số, nếu nối một số với 1 chuỗi có giá trị là số thì nó sẽ biến đổi thành chuỗi ở kết quả đầu ra. VD 1 + "1" = "11".
8. ==Template Literals==
	- Flexible Formarting: Cú pháp để tạo chuỗi dễ dàng để định dạng và đọc hơn, sử dụng placeholders ${} cho các biến hoặc các biểu thức (VD: ${1+1} hoặc ${!bool1}), không cần phải "\n" để xuống dòng.
	- Uses backticks: Template literals chỉ yêu cầu sử dụng cặp ``
	- Đặt ở đầu và cuối một chuỗi.
9. ==Data types==
	- JS là một ngôn ngữ có kiểu dữ liệu yếu, nó không nhiều kiểu dữ liệu như các ngôn ngữ khác như C# hoặc Java. 
	- Simple type system: Number (float), String, Boolean, Date, Function, Array and Object.
	- Special Types: NaN, null, undefined.
	- Checking Type: typeof operator (Dùng cho dữ liệu kiểu nguyên thủy): Trả về một chuỗi của loại kiểu dữ liệu nguyên thủy, đôi khi nó trả về khác với kiểu dữ liệu vd typeof array => object. instanceof operator (Dùng cho dữ liệu tham chiếu): Trả về 1 boolean nếu giá trị khớp với loại constructor dùng để khởi tạo biến. vd (people instanceof Array) => kq là true or false;  Trong trường hợp x = 1 thì (x instanceof Number) => false, nhưng x = new Number(1) sẽ cho ra true;
	- Kiểu dữ liệu trong JS có thể thay đổi theo giá trị của dữ liệu.
	- Khi so sánh thì nên sử dụng === thay vì ==
10. ==Math==
	- Basic : + - * /
	- Addtional Mathematical Operations: % => phần còn lại VD: 100 % 1500 = 100, ++num1 => tăng 1, --num1 => giảm 1;
	==The Math Object==
		+ Tập hợp các hằng số và hàm. Thực hiện tính toán lượng giác, logaric,..
		+ VD: Math.PI, Math.sqrt(num1) (căn 2)
11. ==Number and strings==
	- Converting between numbers and strings:
		- parseInt() and parseFloat(): Chuyển đổi những chuỗi số thành số. Trường hợp chuỗi có những ký tự không phải là số có thể gây sai lệch kết quả (trừ hexadecimal number), nếu chứa chuỗi số thập phân thì phần thập phân sẽ bị bỏ qua. parseFloat() dành cho các số có dấu phẩy động, số có dấu thập phân.
		- toString(): chuyển đổi số thành chuỗi các ký tự số.
12. ==Handing errors with try/catch/finally==
	- Trong quá trình phát triển phần mềm, điều quan trọng là cân nhắc hoặc có sự chuẩn bị cho những lúc một cái gì đó sai. Chúng ta có thể làm việc đó trong code của chúng ta. 
	- Những hành vi ngoài ý muốn trong JS:
		+ Exception (Ngoại lệ): là sự gián đoạn trong quá trình thực thi code. Điều này thông thường nguyên nhân bởi các lỗi, và lỗi khi có những thứ sai trong code của chúng ta.
		+ Error (lỗi): Gián đoạn ngoài ý muốn trong quá trình thực thi code, thường hiển thị dưới dạng ngoại lệ, lỗi cú pháp là một lỗi xảy ra khi sử dụng sai cú pháp. VD nếu chúng ta viết sai cú pháp trong JS, đôi khi code không thực thi tất cả, chúng ta có thể nghĩ về một lỗi trong code, nó sẽ xảy ra khi nào và ở chỗ nào trong code => khi có lỗi xảy ra trong code, chúng ta sẽ biết nó nằm ở đâu và tại sao. Khi một ngoại lệ được quăng ra, nó mang theo một tin nhắn để bảo chúng ta cái gì đã sai trong code
		+ Throwing an Exception (Ném ra một ngoại lệ): Gửi một thông báo rằng có gì đó đã sai trong quá trình thực thi mã. Điều này có thể thực hiện bới JS hoặc bằng tay bởi người lập trình với từ khóa lỗi, có thể quăng ra 1 chuỗi hoặc một giá trị boolean. VD: throw 'myException' hoặc throw true, ví dụ này cho thấy 2 ngoại lệ được quăng ra bằng tay, khi quăng ra một ngoại lệ, chúng ta có thể gửi kèm theo một số thông tin với nó, thông tin có thể là bất cứ thứ gì từ một kiểu dữ liệu nguyên thủy cho đến một đối tượng phức tạp, điều này tùy thuộc vào người lập trình. Trong ví dụ thì ngoại lệ được quăng ra với một chuỗi hoặc một logic. Những ngoại lệ không bắt được có thể rất nghiêm trọng, nguy hiểm, hoặc những lỗi dừng chương trình một cách khó đoán. Điều quan trọng là chúng ta phải bảo code biết phải làm gì tiếp theo khi những tình huống này nảy sinh, việc này được thực hiện thông qua try,catch và finally.
	- Handing Errors in JavaScript:
		+ Uncaught Exceptions: Những ngoại lệ được quăng ra khi code không lập trình để xử lý các lỗi trong quá trình thực hiện, người dùng có thể thấy các thông báo lỗi tối nghĩa không hữu ích hoặc không tồn tại. Bắt lỗi với try..catch...finally.
		+ Try: Khối mã có thể trả ra một lỗi. Try sẽ giám sát những dòng code, do đó nó có thể quăng ra một ngoại lệ.
		+ Catch: Khối mã sẽ chạy nếu một lỗi được quăng ra. Catch sẽ xử lý những gì xảy ra khi có một ngoại lệ được quăng ra.
		+ Finally: Phần mã kèm theo tùy chọn sẽ chạy sau khối try hoặc sau khối catch. Finally sẽ điều khiển luồng chạy code một cách tùy ý, ngay cả khi không có một ngoại lệ nào được quăng ra.
		+ VD try {criticalCode()} catch (ex){console.log("Got an error"); logError(ex) ;} => Got an error, throwing an exception.
		+ Throwing in Try..Catch: try {throw "An exception that is thrown every time"} catch (ex){console.log("Got an error"); logError(ex);} => Got an error, An exception that is thrown every time
		+ Try..Catch..Finally: try {criticalCode()} catch (ex){console.log("Got an error"); logError(ex);} finally {console.log("Code that always will run")}; => Got an error, throwing an exception, Code that always will run. VD: chúng ta đang muốn lấy dữ liệu nhưng không nhận được thì chúng ta có thể quăng ra một ngoại lệ để thông báo.
		+ Cần chú ý khi sử dụng throw thì nó sẽ quăng ra một ngoại lệ và code sẽ dừng lại. Do đó code sẽ được hiển thị sau khi một ngoại lệ được quăng ra. Khi try bắt được 1 ngoại lệ thì code trong catch sẽ được chạy (catch nhận vào 1 tham số, đây là ngoại lệ mà try bắt được),
13. ==Date==
	- Time là một construct hoặc ít nhất, nó là một đối tượng trong JS.
	- Làm việc với ngày và giờ trong JS thì xung quanh một đối tượng là Date. Đối tượng Date chứa cả ngày và giờ. Thời gian nội bộ được lưu trữ dưới dạng số ms kể từ ngày 1/1/1970
	- Date có 3 loại constructor: Day(), Day(năm, tháng, ngày, giờ, phút, giây), Day(năm, tháng, ngày). Lưu ý, tháng được tính từ 0-11. giờ được tính 24H.
	- Date có các phương thức: setFullYear, setMonth, setDate, setHours, setMinutes, setSeconds, getMonth, getTime(kết quả là ms từ ngày 1/1/1970), getDay(chủ nhật sẽ là 0).
	- Khi in ra kết quả sẽ là giờ + thêm giờ UTC.
14. ==Boolean logic and if statements==
	- JS hỗ trợ những toán tử so sánh cơ bản: <, <=, >, >=
	- JS tự động chuyển đổi kiểu dữ liệu trong nhiều trường hợp, điều này có thể dẫn tới bug trong code. == | != => kiểu tra value, === | !=== => kiểm tra kiểu dữ liệu và value. best practice là sử dụng === và !==
	- if - else if - else => dùng để thực thi code theo điều kiện.
	- Trường hợp nếu chỉ thực hiện 1 dòng thì có thể viết thẳng mà không cần cặp móc nhọn: if (status === 200) console.log('OK!')
	- Có thể sử dụng toán tử 3 ngôi để thay thế cho if - else.
15. ==Switch statement and other Boolean syntax==
	- 
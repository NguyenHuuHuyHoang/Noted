==API==
- Application Programming Interface: là một tập các quy tắc và cơ chế mà theo đó, một ứng dụng/thành phần sẽ tương tác với một ứng dụng hay thành phần khác. API có thể trả về thông qua các kiểu dữ liệu phổ biến như XML hay JSON.
- API là giao diện lập trình ứng dụng hay nói cách khác nó là một ứng dụng được lập trình viên viết ra để thao tác với DB thông qua một phương thức nào đấy để trả về FE để hiển thị ra dữ liệu. Thường thì API sẽ trả về kiểu dữ liệu JSON.
==REST==
- REpresenttational State Transfer: là một dạng chuyển đổi cấu trúc dữ liệu, một kiểu kiến trúc để viết API. Nó sử dụng phương thức HTTP đơn giản để tạo cho giao tiếp giữa các máy. Vì vậy thay vì sử dụng một URL cho việc xử lý một số thông tin người dùng, REST gửi một yêu cầu HTTP như GET, POST, PUT, PATCH, DELETE đến một URL để xử lý dữ liệu.
- Là một chuẩn của API, là phương thức tạo API với nguyên lý tổ chức nhất định, các nguyên lý này nhằm hướng dẫn lập trình viên tạo môi trường xử lý API request được toàn diện. nếu không theo chuẩn thì mỗi người lập trình một API theo những cách khác nhau, gây khó khăn trong vấn đề sử dụng.
==RESTful API==
	- là một tiêu chuẩn dùng trong việc thiết kế các API cho các ứng dụng web để quản lý các resource. RESTful là một trong những kiểu thiết kế API được sử dụng phổ biến ngày nay để cho các ứng dụng (web, mobile,..) khác nhau giao tiếp với nhau.
	- Chức năng quan trọng nhất của REST là quy định cách sử dụng các HTTP method (như GET, PUT, POST, DELETE,..) và cách định dạng các URL cho ứng dụng web để quản lý các resource, RESTful không quy định logic code ứng dụng và không giới hạn bởi ngôn ngữ lập trình wúng dụng, bất kỳ ngôn ngữa hoặc framework nào cũng có thể sử dụng để thiết kế một RESTful API.
	- REST hoạt động chủ yếu dựa vào giao thức HTTP. Các hoạt động cơ bản nêu trên sẽ sử dụng những phương thức HTTP riêng.
		+ GET (SELECT): Trả về một resource hoặc một danh sách resource.
		+ POST (CREATE): Tạo mới một resource.
		+ PUT (UPDATE): Cập nhật thông tin cho Resource.
		+ DELETE (DELETE): Xóa một resource.
	- Những phương thức hay hoạt động này thường được gọi là CRUD tương ứng với Create, Read, Update, Delete.
	==Authencation và dữ liệu trả về==
	- RESTful API không sử dụng cookie và session. nó sử dụng một access_token với mỗi request.
	- Có 3 cơ chế Authorize chính, tùy thuộc vào service mà chọn loại phù hợp, cố gắng giữ càng đơn giản càng tốt.:
		+ HTTP Basic.
		+ JSON Web Token (JWT).
		+ OAuth2
	==CORS Policy==
	- CORS là một cơ chế cho phép nhiều tài nguyên khác nhau (fonts, JS,...) của một trang web có thể được truy vấn từ một domain khác với domain của trang đó. CORS là viết tắt của từ Cross-origin resource sharing.
	- CORS được sinh ra là vì same-origin policy, là một chính sách liên quan đến bảo mật được cài đặt vào toàn bộ các trình duyệt hiện nay. Chính sách này ngăn chặn việc truy cập tài nguyên của các domain khác một cách vô tội vạ.
	- VD: Nếu truy cập một trang web có mã độc, Trang web đó sử dụng JS để truy cập tin nhắn FB ở địa chỉ https://facebook.com/messages. Nếu đã đăng nhập fb từ trước rồi, nếu không có same-origin policy, trang web độc hại kia có thể thoải mái lấy dữ liệu và làm bất kỳ điều gì.
	- same-origin policy để bảo vệ kịch bản trên. Tuy nhiên trong thế giới web, lập trình viên thường xuyên phải thực hiện truy vấn đến các domain khác, đặc biệt là khi làm việc với các API. Đó là lúc cần CORS, nó sử dụng các HTTP header để thông báo cho trình duyệt rằng, một ứng dụng web chạy ở origin này (thường là domain này) có thể được truy cập các tài nguyên ở origin khác (domain khác).
	- Một ứng dụng web sẽ thực hiện truy vấn HTTP cross-origin nếu nó yêu cầu đến các tài nguyên ở các origin khác với origin nó đang chạy (khác giao thức, domain, port). Sự khác biệt về giao thức ở đây là khác biệt kiểu như HTTP với FTP chứ không phải HTTP và HTTPS (dù nhiều trình duyệt không cho phép trộn lẫn các tài nguyên truy cập bằng HTTP và HTTPS nhưng nó không liên quan đến CORS).
	- Các trường hợp cần đến CORS rất phổ biến trong thực tế. VD 1 ứng dụng web chạy ở domain foo.com và nó cần truy vấn đến bar.com để lấy một vài dữ liệu (thường được thông qua JS bằng cách sử dụng XMLHttpRequest).
	- Các trình duyệt đều cài đặt same-origin policy và tuân thủ nó rất chặt chẽ. Cài đặt XMLHttpRequest và kể cả Fetch API cũng điều tuân thủ chính sách này. Do đó những truy vấn như ở trên sẽ không thu được kết quả gì, trừ khi máy chủ trả về response có các header CORS phù hợp. Như vậy việc dùng CORS chúng ta có thể thúc đẩy việc giao tiếp trong ứng dụng web dễ dàng hơn rất nhiều.
	- CORS là công việc hoàn toàn của BE.
	==Các truy vấn dùng CORS==
		- Các truy vấn sau bắt buộc phải sử dụng CORS, theo chuẩn quốc tế:
			+ Các truy vấn bằng XMLHttpRequest hoặc Fetch API đến một domain khác.
			+ WebGL Texture.
			+ Ảnh, video được vẽ vào canvas sử dụng drawImage.
			+ Web fonts truy vấn đến domain khác qua @font-face của CSS, trong đó trang web chỉ có thể sử dụng font dạng True Type nếu được cho phép.
	==API Document==
	- API document là một phần tương tự như Unit Test - lấy ngắn nuôi dài. Nếu không được chăm sóc kỹ, đến lúc maintain hoặc thay đổi spec thì hậu quả sẽ rất thảm khốc. Một số lưu ý khi viết docs:
		+ Mô tả đầy đủ về params request: gồm những params nào, datatype, require hay optional.
		+ Nên đưa ra các ví dụ về HTTP requests và responses với data chuẩn.
		+ Cập nhật Docs thường xuyên, để sát nhất với API có bất cứ thay đổi gì.
		+ Format, cú pháp cần phải nhất quán, mô tả rõ ràng, chính xác.
	==Status code==
	- Khi chúng ta request một API thường có những status code sau:
		+ 200 OK - Trả về thành công cho những phương thức GET, PUT, PATCH hoặc DELETE.
		+ 201 Created - Trả về khi 1 resource được tạo thành công.
		+ 204 No content - Trả về khi resource xóa thành công
		+ 304 Not Modified - Client có thể sử dụng dữ liệu cache.
		+ 400 Bad request - Request không hợp lệ.
		+ 401 Unauthorized - Request cần có auth.
		+ 403 Forbidden - Bị từ chối không cho phép.
		+ 404 Not Found - Không tìm thấy resource từ URL.
		+ 405 Method Not Allowed - Phương thức không cho phép với user hiện tại.
		+ 410 Gone - Resource không còn tồn tại, version đã cũ không còn hỗ trợ.
		+ 415 Unsupported Media Type - Không hỗ trợ resouce này.
		+ 422 Unprocessable Entity - Dữ liệu không được xác thực.
		+ 429 Too Many Requests - Request bị từ chối do giới hạn.
	==Version==
	- Luôn sử dụng version để khi cần nâng cấp API mà vẫn hỗ trợ các API cũ.
	==HTTP Request==
	- Tổng cộng có 9 loại method, 2 loại được sử dụng phổ biến nhất là GET và POST.
		+ GET: được sử dụng để lấy thông tin từ server theo URL đã cung cấp.
		+ HEAD: giống với GET nhưng respone trả về không có body, chỉ có header.
		+ POST: gửi thông tin tới server thông qua các biểu mẫu http.
		+ PUT: ghi đè tất cả thông tin của đối tượng với nhwũng gì được gửi lên.
		+ PATCH: ghi đè các thông tin được thay đổi của đối tượng.
		+ DELETE: xóa tài nguyên trên server.
		+ CONNECT: thiết lập một liên kết nối tới server theo URL.
		+ OPTIONS: mô tả các tùy chọn giao tiếp cho resource.
		+ TRACE: thực hiện một bài test loop-back theo đường dẫn đến resource.
==Selenium Architecture==
- Selenium có kiến trúc là client - server, và bao gồm cả client và server components.
- Selenium Client bao gồm:
	- WebDriver API, với nó bạn sử dụng để phát triển các đoạn test script, nhằm mục đích giao tiếp với trang và các đối tượng của chương trình.
	- Lớp RemoteWebDriver, nó giao tiếp với một server Selenium từ xa.
- Selenium Server bao gồm:
	- Một server component, để nhận các request từ Selenium client's remoteWebDriver class
	- WebDriver API để chạy các bài kiểu tra đối với các trình duyệt web trên một máy server
	- Selenium Grid, thực hiện bởi Selenium server trong các tùy chọn dòng lệnh cho những chức năng lưới, bao gồm một hub trung tâm và các nodes cho nhiều môi trường khác nhau và khả năng của trình duyệt mong muốn.
==The seven basic steps of selenium tests==
- Có bảy yếu tố của một Selenium test script, nó áp dụng cho mọi trường hợp kiểm tra và mọi chương trình đang thử nghiệm.
	1. Tạo một ví dụ webdriver
	2. Điều hướng đến 1 trang web
	3. Định vị một phần tử HTML trên một trang web
	4. Thực hiện một hành động trong một HTML Element.
	5. Dự đoán phản hồi của trình duyệt đến hành động.
	6. Chạy các bài kiểm tra và thu lại kết quả kiểm tra bằng cách sử dụng một framework kiểm tra
	7. Kết luận bài kiểm tra.
==Example use case and web application==
- The login use case
	- Tưởng tượng rằng bạn muốn kiểm tra một cách rất cơ bản trường hợp sử dụng cho mọi website và ứng dụng web. Trong đó một người dùng đăng nhập và sau khi xác thực thành công, sẽ nhận được một thông báo. Có 2 quy trình cơ bản trong trường hợp sử dụng này, mỗi quy trình chúng ta cần kiểm tra là:
		- Quá trình đăng nhập, trong đó liên quan đến việc người dùng nhập tên người dùng và mật khẩu vào biểu mẫu và gửi.
		- Quá trình phản hồi sự đăng nhập, trong đó trang web hiển thị thông báo phản hồi đăng nhập.
- The Foo Web Application
	- The Foo Web Application, hosted at www.foo.com, thực hiện quá trình đăng nhập thôg qua một login form với các input HTML text cho tên đăng nhập, mật khẩu và các nút gửi và hủy. Tùy vào thành công hoặc thất bại của việc login mà foo sẽ hiện thị ra một thông báo. mục tiêu của Selenium Test của bạn chính là mô phỏng lại các hành động của một người dùng, người mà sẽ nhập các thông tin vào form và click nút gửi. và sau đó kiểm tra xem thông báo hiển thị có đúng với hành động hay không.
- Best Practices for identifying Elements in HTML Code
	- Khi bạn viết một Selenium test, bạn cần phải xác định các yếu tố mà bạn muốn bài kiểm tra tương tác, trong bài code example, mỗi một yếu tố mà bạn muốn kiểm tra điều được xác định dựa vào tên hoặc thuộc tính id, nó tuân theo các phương pháp viết code HTML là tốt nhất.
		- Trong trang đăng nhập, input đăng nhập và mật khẩu đã được xác định thông qua tên thuộc tính của chúng như username và password.
		- Các yếu tố của form đăng nhập thì đã được xác định bởi giá trị của nó như thuộc tính id="login".
		- Đoạn thông báo phản hồi đăng nhập có class="message" là class chung, nhưng nó có thuộc tính id là loginResponse.
==Creating an Instance of the WebDriver Interface==
-  Giao diện WebDriver là điểm khởi đầu cho mọi cách sử dụng của Selenium WebDriver API,  Khởi tạo giao diện WebDriver là bước đầu tiên để viết bài kiểm tra Selenium
-  Phải tạo một phiên bảo của giao diện WebDriver bằng cách sử dụng một hàm tạo cho một trình duyệt web cụ thể. Tên của các hàm khác nhau tùy theo trình duyệt web và việc gọi các hàm khác nhau tùy theo ngôn ngữ lập trình.
-  Sau khi đã tạo một phiên bản giao diện WebDriver, sử dụng các phiên bản này để gọi các phương thức và truy cập các giao diện khác được sử dụng trong các bước cơ bản. Để làm được như vậy thì cần gán các ví dụ cho một biến khi bạn tạo ra nó, và bằng cách sử dụng biến đó để gọi các phương thức.
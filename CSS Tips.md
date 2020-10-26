- Đặt tên font-face theo dạng main-font, title-font
- cho main-font vào font-family của *
- đặt class .title chứa font dành riêng cho title nếu có
- sử dụng [class*="col-"] {} để select tất cả class name col-
- muốn thẻ input và button cùng chiều cao thì nên set cho height = div chứa = 100%, set inline block cho cả 2 và set vertical-align giống nhau.
- vertical-align chỉ tác dụng lên thẻ inline block.
- đối với margin và padding của trong cùng 1 thẻ text nên xài em để nó ăn theo fz của thẻ text, còn đối với các div thì nên xài rem.
- Trường hợp nếu lấy hình từ api thì cần phải kiểm tra dữ liệu đổ về hết rồi mới render ra block HTML. Keyword search ContentLoaded.
- box-shadow có giá trị inset để đổ bóng vào bên trong.
- breadcum là đường dẫn cho phép user biết mình đang ở trang nào, vd Top products/Disk/Bach
- text wrap around image, thằng chữ float left, thằng hình float right.
- chỉ những thuộc tính bằng số mới bị tác động bởi transition
- Animation là chuyển động không cần tác động gì. Thường các keyframe sẽ được đặt ở cuối file css.
- Thuộc tính transform có thể áp dụng nhiều loại trên cùng một dòng.
==Các cách cơ bản để sử dụng CSS nhằm SEO tốt hơn==
	- Sắp xếp nội dung.
		+ Công cụ tìm kiếm nó không scan toàn bộ trang nhìn thấy nhưng nó dựa trên code. Web sẽ không được đọc như cách mà chúng ta muốn, công cụ tìm kiếm sẽ đọc mọi thứ trên trang từ phía trên bên trái đến phía dưới bên phải. VD nếu ta có một thanh điều hướng trước phần nội dung thực sự thì công cụ tìm kiếm sẽ đọc những phần này trước. Nó sẽ làm giảm thứ hạng tìm kiếm của trang vì trùng nội dung trên cùng của trang.
		+ Bằng cách sử dụng CSS, chúng ta có thể sắp xếp code của mình theo ý mình. Chúng ta có thể đặt những nội dung giá trị nhất và các nội dung giàu từ khóa trên cùng và đưa những khu vực ít quan trọng xuống phía dưới phần nội dung chính.
	- Nhấn mạnh từ khóa.
		+ Công cụ tìm kiếm cũng chú ý tới những tag khác như những tag nhấn mạnh (strong, em), công cụ tìm kiếm sẽ đánh giá giá trị của những từ trong các tag đó có giá trị hơn những từ xung quanh. Chúng ta có thể đã nhìn thấy những trang web có từ có vẻ ngẫu nhiên được in đậm. Các trang web này đang cố gắng cải thiện thứ hạng tìm kiếm của họ bằng cách giúp các công cụ tìm kiếm thấy từ khóa của họ.
		+ CSS giúp chúng ta có thể ẩn các thẻ đó khỏi trình đọc của mình. Giúp cho trải nghiệm người dùng tốt hơn, đọc không bị ngắt quãng bởi các key word được nhấn mạnh, song song đó vẫn giúp cho công cụ tìm kiếm dễ dàng nhận dạng các từ khóa quan trọng nhất.
		+ ở các tag em/strong chúng ta đặt class seo, trong phần css .seo chúng ta sẽ set fw và font style về normal.
	- Giảm tỷ lệ code / content
		+ Việc sử dụng CSS làm cho trang HTML nhẹ hơn, nó cũng giúp làm giảm tỷ lệ code / html, giúp tổ chức tốt hơn cho trang web, dễ dàng viết nội dung phong phú về mặt ngữ nghĩa.
		+ Việc lập chỉ mục tốt hơn làm cho nội dung dễ dàng hơn không chỉ cho người dùng mà còn cho các bot của công cụ tìm kiếm. Khi trang được tổ chức tốt, không có nhiều mã HTML, các bot tìm kiếm có thể nhanh chóng xác định nội dung trang web, giúp cải thiện thứ hạng tìm kiếm.
		+ Cần đảm bảo tất cả các code điều được đọc. Nếu HTML chứa quá nhiều nội dung thì bot sẽ khó khăn trong việc xác định nội dung trang web có liên quan đến một truy vấn tìm kiếm cụ thể hay không.
	- Đơn giản hóa các cập nhật.
		+ Với CSS nội dung dễ dàng truy cập hơn, như vậy nó cho mình các bản cập nhật thường xuyên, khi nội dung được cập nhật thường xuyên các trang web vẫn luôn mới. Độ tươi mới được các công cụ tìm kiếm đánh giá cao.
		+ Tiết kiệm thời gian khi cập nhật các nội dung nhỏ như thay đổi font chữ, trong CSS chỉ cần thay đổi một lần là đủ, còn trong HTML cần phải chỉnh sửa lại mọi trang. Giúp chúng ta tiết kiệm thời gian để cập nhật các phần quan trọng hơn như nội dung hoặc tiêu đề.
	- Sử dụng tốt hơn bộ nhớ trình duyệt.
		+ Các phần tử của trang như hình ảnh, phông chữ và màu sắc bằng CSS. Sau khi tạo file external  CSS và một người dùng tải về lần đầu tiên, file này sẽ được lưu vào bộ nhớ cache trình duyệt của người dùng. Các lần truy cập tiếp theo se load nhanh hơn do không phải tại lại file CSS.
	==Tóm tắt==
		- Sử dụng CSS trong thiết kế web có nhiều lợi ích. Ngoài việc dễ sử dụng, nó còn tốt hơn cho SEO so với chỉ sử dụng HTML. Với CSS chúng ta có thể cải thiện thứ hạng trên các trang kết quả tìm kiếm và thu hút các BOT tìm kiếm vào trang web.
		- Sự tách biệt giữa nội dung và style cho phép chúng ta viết code HTML phong phú, nhẹ nhàng và rõ ràng về mặt ngữ nghĩa được tối ưu hóa cho việc thu thập thông tin và lập chỉ mục của công cụ tìm kiếm. Đồng thời chúng ta vẫn giữ được kiểu dáng và bố cục hình ảnh.
==SEO==
	- Trong mã HTML bình thường, trình duyệt phải truy xuất, phân tích và hiển thị từng trang chuyên biệt. Nếu BOT cần phân tích thêm mã cho đến khi tìm thấy nội dung chính thì nó sẽ làm tăng tải máy chủ và làm giảm hiệu suất. BOT phân tích nhiều trang một lúc và việc làm chậm qua trình thu thập thông tin do hiệu suất thấp có thể làm ảnh hưởng đến số lượng trang được lập chỉ mục.
	- Ngoài CSS thì trong SEO cần chú ý đến nội dung thực tế. Giống như mã HTML phải sạch sẽ, nội dung cần phải được đánh bóng. Nội dung nổi bật phục vụ người sử dụng và cả BOT, giúp cải thiện thứ hạng tìm kiếm. Nếu nội dung có thể sử dụng một số cải tiến thì có rất nhiều công cụ và dịch vụ có sẵn như:
		+ Hemingway: trình chỉnh sửa trực tuyến quét nội dung và đưa ra các đề xuất để cải tiện khả năng đọc. Có khả năng phát hiện các giọng nói bị động và các cấu trúc câu khó khác có thể cản trở khả năng đọc.
		+ Readable: phần mềm cung cấp dịch vụ phân tích văn bản, phân tích mật độ từ khóa, phân tích URL, quét trang web và chấm điểm email. Kết quả sẽ cho ra điểm về khả năng đọc và các số liệu thống kê khác.
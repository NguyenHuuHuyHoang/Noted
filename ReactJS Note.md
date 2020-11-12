- Mỗi Component là một folder, ở trong file JS đặt tên là index để khi import không cần phải /index
- Dữ liệu get từ API thường đặt tên là payload, gán trong action dispatch lên store vd payload: res.data
- ![[Pasted image 13.png]] Trường hợp lần đầu tiên chưa có data thì set dữ liệu là rỗng để hiển thị hợp lý, không bị lỗi, đặc biệt trường hợp img tag không lấy được hình ảnh sẽ bị lỗi gây crash web.
- https://viblo.asia/p/reactjs-nang-cao-bai-1-tao-mot-hooks-dau-tien-usehover-Qbq5Qmo45D8
- https://viblo.asia/p/react-nang-cao-bai-2-render-component-layout-linh-hoat-hon-voi-grid-va-slots-ByEZk2mgKQ0
- decouple module
- ==Cấu trúc 1 dự án ReactJS để dễ scale và maintain==
	1. ==Global Structure==: Thư mục root sẽ có cấu trúc tương tự với các dự án khác, vì nó chứa config của dự án => tập trung vào cấu trúc thư mục ./src, cấu trúc thư mục src như hình ![[Pasted image 20201111204848.png]].
		1. Root
			- ./index.js : là file endpoint của dự án. Trong file này, sẽ dùng để khởi tạo các thư viện mà dự án sẽ sử dụng, ví dụ như theme provider (styled-components), store(Redux, Apollo hoặc các thư viện khác), material-ui, router(React Router) và component <App />.
			- ./App.js : chứa các containers của toàn bộ dự án và <Router />.
			- ./router.js : bao gồm <Switch /> và các <Route /> của dự án.
		2. ./assets
			- Thư mục này sẽ bao gồm các ảnh, icons, fonts và các file media khác. Nhưng để thư mục này không trở thành một thùng rác khi dự án ngày càng phát triển, thì thư mục này sẽ được sắp xếp theo ngữ cảnh. ![[Pasted image 20201111205506.png]]
			- Ví dụ, file logo.svg sẽ được sử dụng ở bất kỳ đâu trong ứng dụng nên sẽ đặt nó ở root của thư mục ./assets. Nhưng file avt-default.png chỉ được sử dụng trong container profile vì vậy sẽ được đặt trong thư mục ./assets/profile.
			- Do vậy có thể tìm kiếm dễ dàng các file asset và các file asset bị duplicate hoặc không dùng nữa.
		3. ./components
			- Theo tài liệu của React, để nhóm các components có thể sử dụng hai cách:
				+ Nhóm theo tính năng hoặc route
				+ Nhóm theo kiểu (CSS, components, tests,..)
			- Trong trường hợp chọn cách 2 thì khi số lượng component tăng lên nhiều, có thể gặp nhiều rủi ro, các file chồng chéo lên nhau, việc thay đổi có thể ảnh hưởng đến các file khác hoặc fix bug không triệt để.
			- Để một component đúng nghĩa cần thỏa mãn 2 quy tắc sau:
				+ Nó phải là một Presentational component, nghĩa là nó không kết nối trực tiếp với state của ứng dụng và chắc chắn không fetch hoặc post dữ liệu. Nó có thể tương tác với container cha bằng cách trigger các hàm được pass trong props.
				+ Nó phải được sử dụng trên container hoặc các components khác.
			- Tùy thuộc và mục đích của dự án mà component có thể là một trang hoặc là module của một trang.
		4. ./containers
			- Các file trong thư mục này có thể:
				+ Subcribe store
				+ Trigger side effects, tương tác với store, fetch hoặc post dữ liệu.
				+ Gửi các sự kiện phân tích.
				+ Cung cấp state, data và actions cho component thông qua props.
			- Với cách chia này thì có thể tách được thành phần logic và thành phần presentational của ứng dụng.
		5. ./core
			- Thư mục này cũng có thể đặt tên là commons hoặc shared. Nó chứa mọi thứ được tái sử dụng trong ứng dụng. ![[Pasted image 20201111211709.png]]
			- Thư mục ./store chứ các config của store và các middlewares. Nó cũng chứa tất cả reducers, actions, actionTypes, selectors.
			- Có hai cách để tổ chức reducer :
				+ nằm bên cạnh container mà nó được sử dụng chủ yếu.
				+ gộp tất cả các reducers vào một thư mục. Vì các state và actions sẽ được tái sử dụng nhiều trong dự án nên cần tổ chức reducer theo cách đầu tiên. Điều này sẽ giúp tìm kiếm dễ dàng hơn.
			- Thư mục ./themes chứa các styles global và các animations. Các biến dùng chung sẽ được lưu ở file index.js
	2. ==Container Structure==
		1. Root
			- ./index.js : định nghĩa và giá trị trả về của container
			- ./styled.js : chứa style của component (sử dụng với styled-componet), các components trong file này sẽ có cấu trúc <StyleAaa />.
			- index.test.js : for testing.
		2. ./components
			- Một container sẽ sử dụng những component riêng của nó. Thư mục này được sử dụng để gộp những sub-components tạo ra một component cha mà nó chỉ được sử dụng riêng ở chính container này. ở đây, <SubComponentB /> có thể là con của <SubComponentA />.
		3. ./service
			- service sẽ thực hiện nhiệm vụ gọi API của container cụ thể. Không phải tất cả container đều cần ./service vì nó có thể đã có sẵn trong thư mục ./core
			- Để cho container nhẹ nhất có thể nên ./service được đặt ngay trong container sử dụng chính service này. Có thể gộp tất cả các service vào một thư mục nếu cần thiết. Tuy nhiên, việc này có thể sẽ khiến cho những dev khác cảm thấy khó chịu khi không biết chính xác container đã sử dụng những service nào.
	3. ==Structure of the React Component==
			- Ví dụ về các có thể sử dụng để viết một component: ![[Pasted image 20201111212721.png]]
			- Khi mở một component lên thì sẽ biết ngay các props mà component sẽ nhận từ cha. Tiếp theo sẽ khởi tạo các hook mà component cần sử dụng . Sau khi biết được các props của component thì cần chú ý đến các globle state và local state mà component này nhận được và sử dụng.
			- Theo thứ tự quan trọng thì effect là phần cần xem tiếp sau state để có thể biết được component này hoạt động như thế nào. Cuối cùng là logic. Với cách bố cục như trên thì sẽ dễ dàng nắm được mục đích của component này để làm gì.
	4. ==Chú ý==
			- Để đảm bảo tính nhất quán của dự án cần đảm bảo các rules sau:
				+ Một file asset nếu chỉ được sử dụng trong một container cụ thể thì nó sẽ được đặt trong thư mục là tên của container đó.
				+ Component phải là một presentational component, có nghĩa là nó không kết nối trực tiếp tới state của ứng dụng và chắc chắn không fetch hoặc post dữ liệu. Nó có thể tương tác với container cha bằng cách trigger các hàm được pass trong props.
				+ Component phải được sử dụng trên container hoặc các components khác.
				+ service sẽ thực hiện nhiệm vụ gọi API của container cụ thể. Không phải tất cả container đều cần ./service vì nó có thể đã có sẵn trong thư mục ./core
	5. ==Tổng kết==
		- Có rất nhiều các cách tiếp cận khi tạo cấu trúc cho một dự án React. Với cách tiếp cận trên thì có thể giúp cho dự án scale nhanh hơn, hoạt động một cách hiệu quả, cho phép maintenance nhanh chóng mà không làm ảnh hưởng đến chất lượng của codebase.
		- Mỗi dự án sẽ có một cách cấu trúc khác nhau. Tuy nhiên, điều quan trọng nhất chính là duy trì được sự nhất quán trong toàn bộ dự án và các thành viên tuân thủ chính xác theo rules mà cấu trúc đặt ra.
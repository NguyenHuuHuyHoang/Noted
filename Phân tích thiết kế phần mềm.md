- Có nhiều quy trình cho việc phân tích thiết kế như:
	- Thác nước: khảo sát hiện trạng - xác định yêu cầu - phân tích - thiết kế - cài đặt - kiểm chứng - triển khai.
	- Xoắn ốc : Tiếp xúc khách hàng - lập kế hoạch - phân tích rủi ro - phân tích, thiết kế - xây dựng và triển khai - đánh giá của khách hàng. ![[Pasted image 20201124160736.png]]
==UML==
- Ngôn ngữ mô hình hóa thống nhất (Tiếng Anh: Unified Modeling Language, viết tắt thành UML) là một ngôn ngữ mô hình gồm các ký hiệu đồ họa mà các phương pháp hướng đối tượng sử dụng để thiết kế các hệ thống thông tin một cách nhanh chóng.
- Cách xây dựng các mô hình trong UML phù hợp mô tả các hệ thống thông tin cả về cấu trúc cũng như hoạt động, cách tiếp cận theo mô hình UML giúp ích rất nhiều cho những người thiết kế và thực hiện hệ thống thông tin cũng như những người sử dụng nó, tạo nên một cái nhìn bao quát và đầy đủ về hệ thống thông tin dự định xây dựng. Cách nhìn bao quát này giúp nắm bắt trọn vẹn các yêu cầu của người dùng, phục vụ từ giai đoạn phân tích đến việc thiết kế, thẩm định và kiểm tra sản phẩm ứng dụng công nghệ thông tin. Các mô hình hướng đối tượng được lập cũng là cơ sở cho việc ứng dụng các chương trình tự động sinh mã trong các ngôn ngữ lập trình hướng đối tượng, chẳng hạn như ngô ngữ C++, Java,... Phương pháp mô hình này rất hữu dụng trong lập trình hướng đối tượng. Các mô hình được sử dụng bao gồm Mô hình đối tượng (mô hình tĩnh) và mô hình động.
- UML sử dụng một hệ thống ký hiệu thống nhất biểu diễn các phần tử mô hình (model elements). Tập hợp các phần tử mô hình tạo thành các sơ đồ UML (UML diagrams). Có các loại sơ đồ UML chủ yếu sau:
	+ Sơ đồ lớp (Class Diagram)
	+ Sơ đồ đối tượng (Object Diagram).
	+ Sơ đồ tình huống sử dụng (Use Cases Diagram)
	+ Sơ đồ trình tự (Sequence Diagram)
	+ Sơ đồ cộng tác (Collaboration Diagram hay là Composite Structure Diagram)
	+ Sơ đồ trạng thái (State Machine Diagram)
	+ Sơ đồ thành phần (Component Diagram)
	+ Sơ đồ hoạt động (Activity Diagram)
	+ Sơ đồ triển khai (Deployment Diagram)
	+ Sơ đồ gói (Package Diagram)
	+ Sơ đồ liên lạc (Communication Diagram)
	+ Sơ đồ tương tác (Interaction Overview Diagram - UML 2.0)
	+ Sơ đồ phối hợp thời gian (Timing Diagram - UML 2.0)
==Use case diagram==
- Một biểu đồ Use case chỉ ra một số lượng các tác nhân ngoại cảnh và mối liên kết của chúng đối với Use case mà hệ thống cung cấp. Một Use case là một lời miêu tả của một chức năng mà hệ thống cung cấp. Lời miêu tả Use Case thường là một văn bản tài liệu, nhưng kèm theo đó cũng có thể làm một biểu đồ hoạt động. Các Use Case được miêu tả duy nhất theo hướng nhìn từ ngoài vào của các tác nhân (hành vi của hệ thống theo như sự mong đợi của người sử dụng), không miêu tả chức năng được cung cấp sẽ hoạt động nội bộ bên trong hệ thống ra sao. Các Use case định nghĩa các yêu cầu về mặt chức năng với hệ thống:
	+ Hệ thống: Với vai trò là thành phần của biểu đồ use case, hệ thống biểu diễn ranh giới giữa bên trong và bên ngoài của một chủ thể trong phần mềm chúng ta xây dựng. Một hệ thống ở trong biểu đồ use case không nhất thiết là một phần mềm, nó có thể là một chiếc máy, hoặc là một hệ thống thực như một doanh nghiệp, một trường đại học
	+ Tác nhân (actor): là người dùng của hệ thống, một tác nhân có thể là một người dùng thực hoặc các hệ thống máy tính khác có vai trò nào đó trong hoạt động của hệ thống. Như vậy, tác nhân thực hiện các use case. Một tác nhân có thể thực hiện nhiều use case và ngược lại một use case cũng có thể được thực hiện bởi nhiều tác nhân.
	+ Các use case: Đây là thành phần cơ bản của biểu đồ use case. Các use case được biểu diễn bởi các hình elip
- Use là gì:
	+ Use case là đối tượng người dùng muốn nhận được từ hệ thống. Nó được đặt tên giống động từ hoặc động từ + cụm danh từ. Tên use case thường ngắn gọn, rõ ràng, cụ thể và miêu tả đủ nghĩa của đối tượng người dùng. Những động từ như do, perform, các danh từ như data, information nên tránh nếu có thể
	+ Người dùng sử dụng use case để đại diện cho các nghiệp vụ trong hệ thống. VD hệ thống đặt khách sạn trực tuyến thì chức năng đặt phòng  là một use case rõ ràng nhất mà người dùng muốn nhận được từ hệ thống, chức năng tìm kiếm khách sạn trên bản đồ trực tuyến cũng có thể là chức năng mà người dùng cần, tuy nhiên nó không phải là một use case vì nó cũng chỉ là một phần của quá trình xử lý đặt phòng thay vì một đối tượng
	+ Một số chức năng có thể nhầm lẫn là use case như, look and feel, load in background, ready server, contruct database,... vì không giúp chúng ta xác định được đối tượng người dùng muốn nhận về.
- Các thành phần của user case:
	==Actor==
		- Actor được dùng để chỉ người sử dụng hoặc một đối tượng nào đó bên ngoài tương tác với hệ thống chúng ta đang xem xét. Lưu ý đôi khi có thể bỏ quên đối tượng tương tác với hệ thống ví dụ Bank
		- Để nhận diện Actor thì cần trả lời các câu hỏi sau:
			+ Ai sẽ sử dụng những chức năng chính của hệ thống (tác nhân chính) ?
			+ Ai sẽ cần sự hỗ trợ của hệ thống để thực hiện những tác vụ hằng ngày của họ ?
			+ Ai sẽ cần bảo trì, quản trị và bảo quản cho hệ thống hoạt động (tác nhân phụ) ?
			+ Hệ thống sẽ phải xử lý và làm việc với những trang thiết bị phần cứng nào?
			+ Hệ thống cần phải tương tác với các hệ thống khác nào ? Nhóm các hệ thống này được chia ra làm hai nhóm, nhóm kích hoạt cho mỗi quan hệ với hệ thống và nhóm mà hệ thống cần phải xây dựng của chúng ta sẽ thiết lập quan hệ. Khái niệm hệ thống bao gồm cả các hệ thống máy tính khác cũng như các ứng dụng khác trongchính chiếc máy tính mà hệ thống này sẽ hoạt động.
			+ Ai hay cái gì quan tâm đến kết quả (giá trị) mà hệ thống sẽ sản sinh ra ?
	==Use Case==
		- Use case là chức năng mà các Actor sẽ sử dụng
		- Để tìm các Use Case, bắt đầu với các Actor được xác định trước, trả lời các câu hỏi sau:
			+ Actor này cần những chức năng nào từ hệ thống ? Hành động chính của actor là gì
			+ Actor có cần phải đọc, phải tạo, phải hủy bỏ, phải sửa chữa, hay là lưu trữ một loại thông tin nào đó trong hệ thống ?
			+ Actor có cần phải báo cho hệ thống biết về những sự kiện nào đó ? Những sự kiện như thế sẽ đại diện cho những chức năng nào ?
			+ Hệ thống có cần phải thông báo cho Actor về những thay đổi bất ngờ trong nội bộ hệ thống ?
			+ Công việc hằng ngày của Actor có thể được đơn giản hóa hoặc hữu hiệu hóa qua các chức năng mới trong hệ thống (thường đây là những chức năng tiêu biểu chưa được tự động hóa trong hệ thống) ?
			+ Use Case có thể được gây ra bởi các sự kiện nào khác ?
			+ Hệ thống cần những thông tin đầu vào / đầu ra nào ? Những thông tin đầu vào / đầu ra đó từ đâu tới và sẽ đi đâu ?
			+ Khó khăn và thiếu hụt chính trong hệ thống hiện thời nằm ở đâu (thủ công / tự động hóa) ?
	==Các quan hệ trong Use Case==
		- Use Case include: Một Use Case (gọi là base Use Case) có thể chứa (include) chức năng của một Use Case khác (gọi là inclusion Use Case) như một phần xử lý của nó. Nói chung, nó giả sử rằng mọi Use Case include sẽ được gọi mỗi khi tuyến Use Case chính chạy. Quan hệ này còn gọi là quan hệ sử dụng uses. Ví dụ việc thực thi use case Card Identification là một phần của Use Case Withdraw, khi thực thi Use Case Withdraw, Use Case Card Indentification sẽ được gọi.
		- Use Case extend: một Use Case mở rộng (gọi là extension Use Case) có thể được mở rộng (extend) hành vi từ một Use Case khác (gọi là base Use Case); điều này thường dùng cho các trường hợp tùy chọn ngoại lệ chèn thêm vào... Ví dụ, nếu trước khi thay đổi một kiểu đặt hàng cụ thể, người dùng có thể phải nhận được sự đồng ý từ cấp phân quyền cao hơn, thì Use Case Get Approval có thể tùy chọn mở rộng (extend) Use Case Modify Order thông thường.
		- Use Case Generalizations: Một quan hệ generalization có giữa một Use Case cụ thể hơn đến với một Use Case tổng quát hơn. Một generalized có thể cụ thể hóa thành nhiều specifilized, một specifilized cũng có thể được cụ thể hóa từ nhiều generalized. Một quan hệ generalization giữa các Use Case trình bày thành một đường đặc từ specifilized đến generalized, với đầu mũi tên là một tam giác rỗng chỉ generalized. Tránh nhầm lẫn với quan hệ phụ thuộc
- Các giai đoạn xây dựng một Use Case Diagram:
	- Giai đoạn mô hình hóa:
		1. Thiết lập ngữ cảnh của hệ thống đích
		2. Chỉ định các Actor
		3. Chỉ định các Use Case
		4. Định nghĩa các quan hệ giữa các Actor và các Use Case
		5. Đánh giá các Actor và các Use Case để tìm cách chi tiết hóa.
	- Giai đoạn cấu trúc:
		6. Đánh giá các Use Case cho quan hệ phụ thuộc include
		7. Đánh giá các Use Case cho quan hệ phụ thuộc extend
		8. Đánh giá các Use Case cho quan hệ generalizations.
	- Giai đoạn review: Sau khi định nghĩa Use Case, cần tiến hành thử nghiệm Use Case:
		1. Kiểm tra (verification): đảm bảo là hệ thống đã được phát triển đúng đắn và phù hợp với các đặc tả đã được tạo ra.
		2. Phê chuẩn (validation): đảm bảo rằng hệ thống sẽ được phát triển chính là thứ mà khách hàng hoặc người dùng cuối thực sự cần đến.
		3. Một trong những kỹ thuật hữu dụng được dùng trong cả giai đoạn định nghĩa lẫn thử nghiệm Use Case gọi là walk-throughs with us-case storyboards (đi bộ dọc Use Case)
		
- Có nhiều quy trình cho việc phân tích thiết kế như:
	- Thác nước: khảo sát hiện trạng - xác định yêu cầu - phân tích - thiết kế - cài đặt - kiểm chứng - triển khai.
	- Xoắn ốc : Tiếp xúc khách hàng - lập kế hoạch - phân tích rủi ro - phân tích, thiết kế - xây dựng và triển khai - đánh giá của khách hàng. ![[Pasted image 20201124160736.png]]
==UML==
- Ngôn ngữ mô hình hóa thống nhất (Tiếng Anh: Unified Modeling Language, viết tắt thành UML) là một ngôn ngữ mô hình gồm các ký hiệu đồ họa mà các phương pháp hướng đối tượng sử dụng để thiết kế các hệ thống thông tin một cách nhanh chóng.
- Cách xây dựng các mô hình trong UML phù hợp mô tả các hệ thống thông tin cả về cấu trúc cũng như hoạt động, cách tiếp cận theo mô hình UML giúp ích rất nhiều cho những người thiết kế và thực hiện hệ thống thông tin cũng như những người sử dụng nó, tạo nên một cái nhìn bao quát và đầy đủ về hệ thống thông tin dự định xây dựng. Cách nhìn bao quát này giúp nắm bắt trọn vẹn các yêu cầu của người dùng, phục vụ từ giai đoạn phân tích đến việc thiết kế, thẩm định và kiểm tra sản phẩm ứng dụng công nghệ thông tin. Các mô hình hướng đối tượng được lập cũng là cơ sở cho việc ứng dụng các chương trình tự động sinh mã trong các ngôn ngữ lập trình hướng đối tượng, chẳng hạn như ngôn ngữ C++, Java,... Phương pháp mô hình này rất hữu dụng trong lập trình hướng đối tượng. Các mô hình được sử dụng bao gồm Mô hình đối tượng (mô hình tĩnh) và mô hình động.
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
- Trong phân tích thiết kế hệ thống, việc mấu chốt là phải hiểu rõ yêu cầu, để hiểu rõ yêu cầu thì phải đọc hiểu yêu cầu. Để thể hiện rằng mình đã hiểu yêu cầu đó, đồng thời có tài liệu phân tích về sau . Thì phải tạo ra sơ đồ Use-Case. Mô hình hóa yêu cầu: chỉ mô tả chủ yếu các thông tin liên quan đến việc thực hiện các nghiệp vụ trong thế giới thực, chưa thể hiện rõ nét việc thực hiện các nghiệp vụ trên máy tính. Mô tả thông qua các văn bản dễ gây ra nhầm lẫn và không trực quan.
- Use Case là kỹ thuật dùng để mô tả sự tương tác giữa người dùng và hệ thống với nhau, trong một môi trường cụ thể và vì một mục đích cụ thể. Sự tương tác ở đây có thể là: Người dùng tương tác với hệ thống như thế nào ? hoặc hệ thống tương tác với các hệ thống khác như thế nào ? Sự tương tác này phải nằm trong một môi trường cụ thể, tức là nằm trong một bối cảnh, phạm vi chức năng cụ thể, hoặc rộng hơn là trong một hệ thống / phần mềm cụ thể. Sau cùng thì việc mô tả sự tương tác này phải nhằm diễn đạt một mục đích cụ thể nào đó. Use Case phải diễn ra được Requirement theo góc nhìn cụ thể từ phía người dùng.
- Use Case Diagram gồm 5 thành phần chính:
	+ Actor: có thể là người dùng hoặc một hệ thống khác bất kỳ.
	+ Use Case: Tên các tương tác, format đúng là Verb + Noun
	+ Communication Link: Kết nối giữa Actor và Use Case, cho biết Actor đó có những sự tương tác nào với hệ thống.
	+ Boundary of System: Phạm vi của các sự tương tác (phạm vi mà Use Case xảy ra). Có thể là trong một hệ thống, một module, hoặc một tính năng bất kỳ. VD: trong hệ thống CRM, phạm vi có thể là từng cụm tính năng lớn như Quản lý khách hàng, Quản lý đơn hàng, hoặc cả một module lớn như Quản lý bán hàng.
	+ Relationship: Mối quan hệ giữa các use case với nhau.
- Một biểu đồ Use case chỉ ra một số lượng các tác nhân ngoại cảnh và mối liên kết của chúng đối với Use case mà hệ thống cung cấp. Một Use case là một lời miêu tả của một chức năng mà hệ thống cung cấp. Lời miêu tả Use Case thường là một văn bản tài liệu, nhưng kèm theo đó cũng có thể làm một biểu đồ hoạt động. Các Use Case được miêu tả duy nhất theo hướng nhìn từ ngoài vào của các tác nhân (hành vi của hệ thống theo như sự mong đợi của người sử dụng), không miêu tả chức năng được cung cấp sẽ hoạt động nội bộ bên trong hệ thống ra sao. Các Use case định nghĩa các yêu cầu về mặt chức năng với hệ thống:
	+ Hệ thống: Với vai trò là thành phần của biểu đồ use case, hệ thống biểu diễn ranh giới giữa bên trong và bên ngoài của một chủ thể trong phần mềm chúng ta xây dựng. Một hệ thống ở trong biểu đồ use case không nhất thiết là một phần mềm, nó có thể là một chiếc máy, hoặc là một hệ thống thực như một doanh nghiệp, một trường đại học
	+ Các use case: Đây là thành phần cơ bản của biểu đồ use case. Các use case được biểu diễn bởi các hình elips.
	+ VD: Sơ đồ Use-Case ![[Pasted image 20201126120719.png]]
- Use là gì:
	+ Use case là đối tượng người dùng muốn nhận được từ hệ thống. Nó được đặt tên giống động từ hoặc động từ + cụm danh từ. Tên use case thường ngắn gọn, rõ ràng, cụ thể và miêu tả đủ nghĩa của đối tượng người dùng. Những động từ như do, perform, các danh từ như data, information nên tránh nếu có thể
	+ Người dùng sử dụng use case để đại diện cho các nghiệp vụ trong hệ thống. VD hệ thống đặt khách sạn trực tuyến thì chức năng đặt phòng  là một use case rõ ràng nhất mà người dùng muốn nhận được từ hệ thống, chức năng tìm kiếm khách sạn trên bản đồ trực tuyến cũng có thể là chức năng mà người dùng cần, tuy nhiên nó không phải là một use case vì nó cũng chỉ là một phần của quá trình xử lý đặt phòng thay vì một đối tượng
	+ Một số chức năng có thể nhầm lẫn là use case như, look and feel, load in background, ready server, contruct database,... vì không giúp chúng ta xác định được đối tượng người dùng muốn nhận về.
- Các thành phần của user case:
	==Actor==
		- Tác nhân (actor): là người dùng của hệ thống, một tác nhân có thể là một người dùng thực hoặc các hệ thống máy tính khác có vai trò nào đó trong hoạt động của hệ thống. Như vậy, tác nhân thực hiện các use case. Một tác nhân có thể thực hiện nhiều use case và ngược lại một use case cũng có thể được thực hiện bởi nhiều tác nhân. Tác nhân được ký hiệu hình người và có tên ở dưới hoặc Actor.
		- Actor được dùng để chỉ người sử dụng hoặc một đối tượng nào đó bên ngoài tương tác với hệ thống chúng ta đang xem xét (Người dùng, thiết bị ngoại vi, phần mềm khác). Lưu ý đôi khi có thể bỏ quên đối tượng tương tác với hệ thống ví dụ Bank
		- Một nhóm người dùng tương ứng với một Actor.
		- Mỗi Actor được phép sử dụng một hay nhiều chức năng trong hệ thông như:
			- Nhân viên được phép thêm, sửa hóa đơn.
			- Admin được phép toàn quyền với hệ thống.
		- Một chức năng có thể cho phép nhiều Actor sử dụng như:
			- Nhân viên và quản lý đều được phép thông báo giờ làm của mình với hệ thống.
		- Nhiều Actor có thể có các quyền hạng giống nhau như: 
			- Admin và Quản lý đều có thể xem thống kê báo cáo của hệ thống.
		- Một hay nhiều Actor tùy vào ngữ cảnh: Với trường hợp nhân viên dùng phần mềm thì có thể có nhiều nhân viên, nhưng vẫn gọi chung actor đó là nhân viên. Máy quét mã vạch thì chỉ có một tương tác với phần mềm.
		- Để nhận diện Actor thì cần trả lời các câu hỏi sau:
			+ Ai sẽ sử dụng những chức năng chính của hệ thống (tác nhân chính) ?
			+ Ai sẽ cần sự hỗ trợ của hệ thống để thực hiện những tác vụ hằng ngày của họ ?
			+ Ai sẽ cần bảo trì, quản trị và bảo quản cho hệ thống hoạt động (tác nhân phụ) ?
			+ Hệ thống sẽ phải xử lý và làm việc với những trang thiết bị phần cứng nào?
			+ Hệ thống cần phải tương tác với các hệ thống khác nào ? Nhóm các hệ thống này được chia ra làm hai nhóm, nhóm kích hoạt cho mỗi quan hệ với hệ thống và nhóm mà hệ thống cần phải xây dựng của chúng ta sẽ thiết lập quan hệ. Khái niệm hệ thống bao gồm cả các hệ thống máy tính khác cũng như các ứng dụng khác trongchính chiếc máy tính mà hệ thống này sẽ hoạt động.
			+ Ai hay cái gì quan tâm đến kết quả (giá trị) mà hệ thống sẽ sản sinh ra ?
			+ Hệ thống lưu trữ dữ liệu, vậy ai là người input dữ liệu vào hệ thống ?
			+ Hệ thống lưu trữ dữ liệu, vậy ai là người cần những dữ liệu out ?
		==Phân loại Actor==
			- Nhóm người sử dụng: 
				- VD: Phần mềm quản lý học sinh cấp III ![[Pasted image 20201126115139.png]], Phần mềm quản lý thư viện ![[Pasted image 20201126115207.png]]
				- Có thể xác định các Actor qua các hình: ![[Pasted image 20201126115250.png]], Actor không chỉ là con người mà bất cứ thứ gì tương tác với hệ thống của chúng ta, nó là tác nhân bên ngoài của hệ thống, không phải là hệ thống.
				- Phân loại các Actor ra theo tác nhân: Như người dùng, hệ thống khác, phần cứng, phần mềm ![[Pasted image 20201126115308.png]] 
			- Nhóm phần cứng ngoại vi:
				- ![[Pasted image 20201126115328.png]]
				- Thiết bị ngoại vi rất nhiều, nên liệt kê ra để biết từng thiết bị ngoại vi tương ứng sẽ tác động tới hệ thống như thế nào từ đó nắm rõ được hệ thống sẽ xử lý ra sao từ đó xây dựng kiến trúc phù hợp nhất. Tóm lại, 1 thằng nào đó là thiết bị phần cứng truyền hoặc nhận thông tin từ hệ thống, thì được tính là actor.
			- Nhóm phần mềm khác:
				- ![[Pasted image 20201126115342.png]]
	==Use Case==
		- Use case là chức năng mà các Actor sẽ sử dụng, là một chuỗi các hành động mà hệ thống thực hiện MANG LẠI KẾT QUẢ QUAN SÁT ĐƯỢC ĐỐI VỚI ACTOR.
		- Có thể hiểu một Use-Case là một chức năng của hệ thống, mang một ý nghĩa nhất định đối với người dùng. VD ![[Pasted image 20201126115612.png]]
		- VD Về Use-Case: 
			- Yêu cầu: ![[Pasted image 20201126115808.png]]
			- Lập ra các Use-Case: ![[Pasted image 20201126115825.png]]
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
		- Use Case include: 
			- Một Use Case (gọi là base Use Case) có thể chứa (include) chức năng của một Use Case khác (gọi là inclusion Use Case) như một phần xử lý của nó. (bắt buộc).
			- Nói chung, nó giả sử rằng mọi Use Case include sẽ được gọi mỗi khi tuyến Use Case chính chạy. Quan hệ này còn gọi là quan hệ sử dụng uses. 
			- Xét về nghĩa, include nghĩa là bao gồm, tức nếu Use Case A có mối quan hệ include Use Case B, thì nghĩa là: Use Case A bao gồm Use Case B, để Use Case A xảy ra thì Use Case B phải đạt được.
			- Ví dụ việc thực thi use case Card Identification là một phần của Use Case Withdraw, khi thực thi Use Case Withdraw, Use Case Card Indentification sẽ được gọi.
			- Không có quy tắc nào rõ ràng cho việc khi nào cần tách Use Case ra thành các Use Case nhỏ và cho nó một mối quan hệ include cả. Tách hay không tách phụ thuộc vào người vẽ, lý do lớn nhất để mối quan hệ include ra đời là giúp cho các use case của chúng ta DỄ QUẢN LÝ hơn. Chỉ nên tách Use Case khi nó có độ phức tạp lớn và những thứ tách ra có thể được tận dụng ở các Use Case sau này. VD ![[Pasted image 20201126173345.png]]
			- Cách vẽ thì include tới thằng nào thì dấu mũi tên hướng tới thằng đó.
		- Use Case extend: 
			- một Use Case mở rộng (gọi là extension Use Case) có thể được mở rộng (extend) hành vi từ một Use Case khác (gọi là base Use Case); điều này thường dùng cho các trường hợp tùy chọn ngoại lệ chèn thêm vào... 
			- Nếu include là mối quan hệ bắt buộc, thì extend là một mối quan hệ không bắt buộc. Nó thể hiện mối quan hệ có thể có hoặc có thể không giữa các Use Case với nhau. Một Use Case B là extend của Use Case A thì có nghĩa Use Case B chỉ là một thứ optional, và chỉ xảy ra trong một hoàn cảnh cụ thể nào đó.
			- Có một thứ luôn đi kèm với Extend là Extension Point: là điều kiện mà Use Case có mối quan hệ Extend sẽ xảy ra. Sát nghĩa thì có thể hiểu Point là điểm dữu liệu thể hiện sự khác biệt, tứ là nếu dữ liệu này là A thì Use Case không xảy ra, nhưng nếu dữ liệu là B thì Use Case sẽ xảy ra. VD: ![[Pasted image 20201126174057.png]].
			- Extension Point không nhất thiết phải là một dữ liệu nào đó trên hệ thống, mà có thể là một "điều kiện" bất kỳ, miễn là nó thể hiện được trường hợp cụ thể mà Use Case sẽ xảy ra. VD: ![[Pasted image 20201126174253.png]] ![[Pasted image 20201126174316.png]]
			- Ví dụ, nếu trước khi thay đổi một kiểu đặt hàng cụ thể, người dùng có thể phải nhận được sự đồng ý từ cấp phân quyền cao hơn, thì Use Case Get Approval có thể tùy chọn mở rộng (extend) Use Case Modify Order thông thường.
		- Use Case Generalizations: 
			- Một quan hệ generalization có giữa một Use Case cụ thể hơn đến với một Use Case tổng quát hơn, ngắn gọn hơn là quan hệ cha con giữa các Use Case với nhau, nhưng khác biệt với include và extend là nó còn được dùng để thể hiện mỗi quan hệ giữa các Actor với nhau.
			- VD quan hệ cha-con giữa các Use Case: 
				+ Đăng nhập thì có thể đăng nhập qua số điện thoại, hoặc đăng nhập qua email.
				+ Đặt hàng thì có đặt hàng qua điện thoại hoặc đặt hàng qua website.
				+ Thanh toán thì thanh toán qua thẻ ATM, qua thẻ thanh toán quốc tế, hoặc qua ví điện tử
				+ Hoặc tìm kiếm thì có thể tìm kiếm bằng từ khóa, hoặc tìm kiếm theo nhóm sản phẩm.
			- VD quan hệ cha-con giữa các Actor:
				+ Khách hàng gồm khách hàng cũ và khách hàng mới
				+ Vendor thì có thể gồm Retailers hoặc Wholesalers ![[Pasted image 20201126174742.png]]
			- Một generalized có thể cụ thể hóa thành nhiều specifilized, một specifilized cũng có thể được cụ thể hóa từ nhiều generalized. Một quan hệ generalization giữa các Use Case trình bày thành một đường đặc từ specifilized đến generalized, với đầu mũi tên là một tam giác rỗng chỉ generalized. 
			- Nhìn chung generalization giúp thể hiện rõ hơn các yêu cầu bằng việc gom nhóm các Use Case lại theo quan hệ cha-con. Tùy style có thể vẽ theo kiểu này hoặc sử dụng include và extend là chính. Generalization có tính kế thừa. Tức là thằng cha có gì thì thằng con có đó, kể cả Use Case hay Actor dù không thể hiện trên hình.
			- Tránh nhầm lẫn với quan hệ phụ thuộc
	 + Mối quan hệ giữa các use case:
		+ Association: thường được dùng để mô tả mối quan hệ giữa Actor và Use Case và giữa các Use Case với nhau. (Đường thẳng nét liền).
		+ Include: là quan hệ giữa các Use Case với nhau, nó mô tả việc một Use Case lớn được chia ra thành các Use Case nhỏ để dễ cài đặt (module hóa) hoặc thể hiện sự dùng lại.. (Đường thẳng nét đứt có mũi tên, ở trên có chữ include). VD: login thì sẽ include verify password, khi thực hiện login thì sẽ luôn cần thực hiện việc xác thực mật khẩu, hoặc trong quá trình khách hàng mua hàng luôn luôn phải thực hiện bước thanh toán tiền cho chủ cửa hàng, hoặc khi khách hàng đăng nhập, luôn luôn phải thực hiện bước kiểm tra tài khoản tồn tại. Đăng nhập -> include Kiểm tra tài khoản tồn tại![[Pasted image 20201126120106.png]]. Tóm lại include là bắt buộc phải làm chức năng kế tiếp.
		+ Extend: dùng để mô tả quan hệ giữa 2 Use Case. Quan hệ extend được sử dụng khi có một Use Case được tạo ra để bổ sung chức năng cho một Use Case có sẵn và được sử dụng trong một điều kiện nhất định nào đó. (Đường thẳng nét đứt có mũi tên, ở trên có chữ extend , mũi tên sẽ ngược hướng với include) VD: Add Account Holder thì sẽ extend Open Account (Mũi trên trỏ hướng Account Holder -> Open Account) Trong một số trường hợp nếu Open Account sẽ thực hiện Account Holder, hoặc khi chủ cửa hàng thêm sản phầm vào dữ liệu có thể sử dụng chức năng đọc mã vạch sản phẩm nếu không muốn tự nhậm mã sản phẩm. Đăng sản phẩm <- extend đọc mã vạch sản phẩm ![[Pasted image 20201126120346.png]]. Tóm lại extend không bắt buộc phải làm.
		+ Generalization: Được sử dụng để thể hiện quan hệ thừa kế giữa các Actor hoặc giữa các Use Case với nhau, (đường thẳng nét liền, đầu mũi tên là hình tam giác) VD: User sẽ generalization Guest (Kế thừa các Use case của guest ngoài các use case có sẵn của user).
- ==Lưu ý==
	1. Đặt tên.
		- Trong mô hình hóa, chuyện đặt tên là rất quan trọng. Vì đã nói mô hình hóa tức là chúng ta dùng hình ảnh để nói chuyện, thì khi đó hàm lượng chữ chiếm rất ít, do đó nên những gì ghi trên diagram phải rất súc tích, cô đọng và có giá trị ngay tức thì.
		- Chỉ cần người đọc họ nhìn vô diagram mà thấy ngay 1 dòng chữ khó hiểu, thì không muống xem tiếp.
		- 1 số quy tắc đặt tên:
			- Actor thì phải đặt tên bằng danh từ, không dùng động từ, và cũng không mệnh đề quan hệ gì hết.
			- Tên Use Case thì phải ghi rõ ràng, rành mạch, đẹp nhất là dưới dạng format Verb + Noun. VD: Đổi điểm thành viên, Chuyển tiền nội địa, Chuyển tiền quốc tế, Duyệt nhận xét bài viết.
		- Chúng ta vẽ Use Case nhằm mục đích diễn tả yêu cầu cho stakeholders hiểu, do đó không được dùng những từ ngữ kỹ thuật, tránh đặt tên quá dài và không nên dùng kiểu bị động.
	2. Vẽ Use Case mà thành phân rã chức năng.
		- Đây là lỗi thường gặp, rất thường xuyên khi vẽ Use Case ![[Pasted image 20201126192627.png]], ở ví dụ này nếu nói Manage Gears, Manage Brakes hay Manage Air Conditioner thì quá tối nghĩa, chẳng ai hiểu mục đích sau cùng là làm gì.
		- Dấu hiệu nhận biết rõ ràng nhất là khi Use Case Diagram có nhiều chữ manage, chữ manager rất rộng nghĩa. Yêu cầu quản lý A gồm 5 việc, thì không có nghĩa yêu cầu quản lý B cũng gồm 5 việc. Use Case là diagram thể hiện yêu cầu của End-Users, nhằm đạt được mục đích nào đó.
		- Ngoài ra hình minh họa vẽ Use Case nhưng lại chưa mang lại được góc nhìn của End-Users, tức chưa cho thấy được End-Users muốn đạt được gì sau ngần ấy Use Case được liệt kê ra. Nguyên nhân có thể do người vẽ chưa nắm đủ thông tin về yêu cầu của End-Users, chưa hiểu rõ rốt cuộc người dùng muốn làm gì trên hệ thống hay hệ thống phải tương tác gì với hệ thống khác => Nhìn vô Use Case Diagram nhưng cảm thấy mông lung, do đó chỉ vẽ Use Case khi có đủ tất cả các thông tin:
			+ End-Users muốn làm gì ? Nhằm mục đích gì ? ==> tương tác giữa end-users và hệ thống.
			+ Hệ thống phải nhận / lấy data từ những nguồn nào ? => tương tác giữa hệ thống với những hệ thống bên ngoài khác.
		- Ngoài ra, khi đã có đủ thông tin nhưng Use Case vẫn bị confuse. Lý do có thể do các Use Case vẽ bị lệch các cấp độ Requirement với nhau. VD: ![[Pasted image 20201126204253.png]]
		- Tuy nhiên chữ Manage trong Use Case lại rất công dụng, đến mức không thể không dùng trong các document, nó sẽ giải quyết các vấn đề ở mục 4.
	3. Rối nùi Use Case
		- VD 1: ![[Pasted image 20201126204427.png]]
		- Nguyên nhân là do ôm đồm quá nhiều, dẫn đến quá nhiều Use Case xuất hiện trong cùng một Diagram, đã vậy cũng không có Boundary of Systerm rõ ràng.
		- Các điểm sai của Use Case ví dụ 1 ở các điểm sau:
			+ Xác định sai Use Case (nên mới nhiều UC như vậy): những thứ như single, double, num of guest ... rõ ràng không phải là một Use Case, không phải là một sự tương tác.
			+ Đặt tên Use Case sai: quá nhiều cụm danh từ cho Use Case.
			+ Không có Boundary of System
			+ Những Use Case có extend không ghi chú cụ thể điều kiện khi nào thì UC extend xảy ra.
		- Note nhỏ: Use Case Diagram sạch đẹp chỉ nên có dưới 10 Use Case trong đó. Các Use Case còn lại thì dùng Boundary of System để phân chia theo phân hệ một cách hợp lý nhất có thể.
		- VD 2: ![[Pasted image 20201126205140.png]]
		- Các điểm sai của Use Case ví dụ 2 ở các điểm sau:
			+ Một số Use Case đặt tên sai
			+ Chưa tận dụng các Relationship để thể hiện, khiến cho các Use Case quá rời rạc nhau, và trông rất không hợp logic
			+ Người vẽ không dùng Boundary of System để phân nhóm, giới hạn các Use Case.
			+ Người vẽ quá chú trọng đến các chức năng cơ bản nhất là: CRUD - Create/Read/Update/Delete
	4. Quá chi tiết các chức năng.
		- Như ở ví dụ trên, mỗi thực thể là một lần CRUD, như vậy quá tốn effort, trong khi ở bất kỳ phân hệ nào, hay dữ liệu nào đều cần phải CRUD dữ liệu hết.
		- Điều này tạo đi sự lặp đi lặp lại ở các Use Case Diagram, nhưng không thể hiện được gì nhiều cho người xem. Để giải quyết vấn đề này, có thể áp dụng một trong 2 cách sau:
			1. Thêm một dòng note trước đoạn mô tả Use Case trong tài liệu: "Toàn bộ dữ liệu đều có chức năng Thêm/Đọc/Sửa/Xóa và chịu tác động bởi sự phân quyền từ phía Quản trị hệ thống" hoặc đại loại vậy. Để cho các stakeholders biết được rằng hệ thống có chức năng CRUD các dữ liệu này.
				- Nên nhớ CRUD ở đây là đứng từ góc nhìn End-Users: hệ thống có cho phép End-Users CRUD dữ liệu hay không ?
				- Ví dụ hệ thống CRM lấy dữ liệu khuyến mãi từ hệ thống ERP. Thì về bản chất CRM phải có khả năng Create dữ liệu khuyến mãi, thì mới lấy dữ liệu khuyến mãi từ ERP về được.
				- Nhưng theo góc nhìn của End-Users, thì không một người dùng nào (kể cả System Admin), có thể tạo thủ công dữ liệu khuyến mãi trên CRM, mà End-Users chỉ Đọc/Sửa/Xóa dữ liệu được lấy về này thôi.
				- Do đó ở đây cần phải mô tả rõ là có phải tất cả dữ liệu đều cho phép End-Users CRUD được hay không (không tính phân quyền).
			2. Tạo hẳn một Use Case với tên là Manage "X", với X là một đối tượng bất kỳ. ![[Pasted image 20201126210912.png]]
				- Nếu không đầy đủ tính năng CRUD thì có thể làm một cái note nhỏ bên trên, nói rõ Manage là có những tính năng gì, không có những tính năng gì.
	5. Thẩm mỹ
		- Nguyên nhân việc Use Case mất thẩm mỹ đến từ lý do:
			+ Mắt thẩm mỹ kém
			+ Ẩu, cẩu thả
		- Một số điểm cần chú ý:
			+ Kích cỡ các Use Case trong Diagram là phải như nhau, kể cả cha-con, lẫn các mỗi quan hệ Include. Tuy nhiên Use Case có Extend sẽ được vẽ to hơn một chút.
			+ Nhớ phải đánh dấu Use Case ID trong hình vẽ.
			+ Các mối quan hệ không được chồng chéo lẫn nhau. Có thể vẽ 1 Actor ở 2 vị trí khác nhau để tránh các đường nối bắt chéo lên nhau.
			+ Khi vẽ Use Case Diagram, tập trung vào câu hỏi What để tìm ra Use Case, tránh câu hỏi How, vì khi đó rất dễ đi vào detail.
			+ Nếu được hãy tô màu lên Use Case để nhìn Diagram được rõ ràng, sáng sủa và mạch lạc.
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
	==Đặc tả Use-Case==
	1. Đặc tả Use Case là gì ?
		- Use Case Diagram khá là chung chung để các stakeholders có cái nhìn trực quan về những requirements được mô tả. Do đó, cần phải diễn đạt nó một cách chi tiết hơn nữa. Use Case Specification hay nói cách khác là đặc tả Use Case sẽ thực hiện việc này.
		- Sau khi mô hình hóa yêu cầu hệ thống, chúng ta cần đặc tả lại hệ thống theo phong cách chuyên ngành. Với mỗi Use-Case sẽ có một đặc tả riêng. 
	2. Các thành phần có trong Use Case Specification.
		- Đặc tả Use Case tồn tại dưới dạng một cái bảng ghi chú. Nó mô tả tất tần tật các thông tin về Use Case, giúp người khác đọc vào là hiểu ngay Use Case Diagram nó vẽ vậy nghĩ là gì.
		- Một Use Case Specification gồm có 3 thành phần chính: 
			1. Summary:
				+ Use Case Name: Tên Use Case
				+ Use Case ID: Mã Use Case
				+ Use Case Description: Tóm gọn nhanh sự tương tác được thể hiện trong Use Case là gì ? Chỉ cần mô tả ngắn gọn theo cú pháp của User Story: Là "Actor", muốn làm "Use Case Name", để đạt được mục đích - lý do gì đó. Đẹp là không quá 3 dòng cho phần tóm gọn Use Case này.
				+ Actor: Những đối tượng thực hiện sự tương tác trong Use Case.
				+ Priority: Mức độ ưu tiên của Use Case so với các Use Case còn lại trong dự án.
				+ Trigger: Điều kiện kích hoạt Use Case xảy ra.
				+ Pre-condition: Điều kiện cần để Use Case thực hiện thành công.
			2. Flow:
				+ Basic Flow: luồng tương tác CHÍNH giữa các Actor và System để Use Case thực hiện thành công.
				+ Alternative Flow: luông tương tác THAY THẾ giữa các Actor và System để Use Case thực hiện thành công.
				+ Exception Flow: luồng tương tác NGOẠI LỆ giữa các Actor và System mà Use Case thực hiện thất bại.
			3. Additional Information:
				+ Business Rule: các quy định về mặt Business mà hệ thống bắt buộc phải nghe theo, làm theo. Có thể hiểu là các quy định, hoặc các policy của khách hàng. Có sao ghi vậy, vì đây là giai đoạn tài liệu hóa yêu cầu thông qua Use Case nên cứ liệt kê hết có liên quan vào.
				+ Non-Functional Requirement: Vì Use Case chỉ dùng để thể hiện Functional Requirement (hành vi - chức năng của giải pháp), nên chúng ta phải bổ sung các yêu cầu về Non-Functional (không liên quan trực tiếp tới hành vi - chức năng của giải pháp nhưng lại là điều kiện giúp hệ thống chạy tốt và đảm bảo được chất lượng như yêu cầu => CHẤT LƯỢNG sản phẩm) ở đây luôn.
		- Template ![[Pasted image 20201126121055.png]]
			+ Sự kiện kích hoạt là khi nào mà use case hoạt động.
			+ Biến thể: VD trường hợp a, trường hợp b khi nào sẽ xảy ra (quay về nhánh chính)
			+ Túm lại là đưa ra nhiều trường hợp chi tiết hơn về Use-Case, càng chi tiết càng khỏe.
	3. Một số ví dụ đặc tả Use Case
		- VD 1: Use-Case Đăng nhập ![[Pasted image 20201126121147.png]]
		- VD 2: Use-Case Đăng nhập diễn đàn Medium. Use-Case: ![[Pasted image 20201126235507.png]]
		- Đặc tả Use Case: 
			+ ![[Pasted image 20201126235545.png]]
			+ ![[Pasted image 20201126235556.png]]
			+ ![[Pasted image 20201126235604.png]]
		- Một đặc tả Use Case cho một Use Case, ví dụ 2 là một sơ đồ Use Case Diagram gồm 5 Use Case thì sẽ ứng với 5 đặc tả Use Case.
	4. Một số nhầm lẫn hay gặp
		- thường dễ nhầm lẫn ở hai chỗ:
			1. Trigger và Pre-condition
			2. Alternative Flow và Exception Flow
		1. Trigger và pre-condition:
			- Trigger nghĩa là một thứ gì đó kích hoạt cho Use Case chạy, khởi xướng cho Use Case chạy. Còn Pre-Condition nghĩa là một thứ gì đó, mà phải có nó thì Use Case mới chạy được.
			- Use Case có thể có Pre-condition hoặc không, nhưng Trigger thì thường phải có. 
			- VD: ![[Pasted image 20201127000122.png]], Ở đây Use Case chỉ xảy ra khi khách hàng thực hiện lệnh rút tiền. Cụ thể là nhấn nút rút tiền trên màn hình. Đó là trigger Use Case xảy ra. Còn Pre-condition là các điều kiện cần phải có để ông này rút tiền thành công. Vì ổng không thể nào rút tiền được nếu trong tài khoản không còn tiền hoặc ổng chưa đút thẻ vô máy.
			- Hoặc Output (hoặc Post-condition) của Use Case này có thể là trigger của Use Case khác. Cũng ở ví dụ rút tiền tại máy ATM. post-condition có thể là khách hàng nhân được tiền mặt sau khi thực hiện rút tiền, số dư của khách hàng đã bị trừ đi khoản tiền đã rút. Nếu những post-condition này xảy ra thì Use Case: Rút tiền tại máy ATM đã được thực hiện xong và đồng thời nó cũng trigger cho Use Case tiếp theo là gửi tin nhắn SMS thông báo cho khách hàng.
			- Có thể trigger sẽ là bước đầu tiền của Basic Flow hoặc không. Trigger trong Use Case có thể là bất cứ thứ gì, có thể là tác động từ phía người dùng, hoặc tác động từ chính hệ thống, miễn nó thể hiện rõ là điều kiện để Use Case chạy là được.
		2. Alternative Flow và Exception Flow
			- Flow là các luồng tương tác giữa các Actor và hệ thống với nhau. Basic Flow là luồng tương tác chính, là happy case đơn giản nhất có thể xảy ra. Tuy nhiên thực tế còn có những luồng khác thì chúng ta sẽ quy nó thành Alternative Flow hoặc Exception Flow cụ thể:
				- Alternative Flow: những hướng khác dẫn tới kết quả cuối cùng
				- Exception Flow: những trường hợp mà ngăn chặn không dẫn tới kết quả cuối cùng.
			- ![[Pasted image 20201127001913.png]]
			- VD trong Mô hình quả lý e-Learning có Use Case là Hủy kích hoạt tài khoản học viên. Use Case này sẽ có các Flow như sau:
				+ Basic flow:
					1. Admin mở tài khoản học viên cần hủy kích hoạt
					2. Hệ thống hiển thị màn hình thông tin học viên
					3. Admin chọn lệnh hủy kích hoạt
					4. Hệ thống yêu cầu nhập mã OTP để xác nhận
					5. Admin nhập đúng mã OTP để xác nhận lệnh hủy kích hoạt
					6. Hệ thống kiểm tra mã OTP và tiến hành hủy kích hoạt
					7. Hệ thống hiển thị thông báo đã hủy kích hoạt.
				+ Alternative Flow:
					1a. Admin chọn học viên cần hủy kích hoạt ở lưới học viên. Use Case tiếp tục bước 3.
					4a. Admin chọn phương thức xác nhận khác: Xác nhận qua reCaptcha
					4a1. Hệ thống hiển thị mã reCaptcha và yêu cầu nhập mã reCaptcha để xác nhận
					5a. Admin nhập đúng mã reCaptcha để xác nhận lệnh hủy kích hoạt
					6a. Hệ thống kiểm tra mã reCaptcha và tiến hành hủy kích hoạt. Use Case tiếp tục bước 7.
				+ Exception flow:
					5b. Admin nhập sai mã reCaptcha
					5b1. Hệ thống báo lỗi và hủy bỏ lệnh hủy kích hoạt học viên. Use Case dừng lại.
					5c. Admin nhập sai mã OTP
					5c1. Hệ thống báo lỗi và hủy bỏ lệnh hủy kích hoạt học viên. Use Case dừng lại.
		- Ghi chú: Đối với luồng chính (Basic Flow) đánh số thứ tự theo số nguyên. Còn đối với Alternative hay Exception Flow, nên thêm các ký tự chữ cái bên cạnh để làm dấu cho dễ phân biệt.
	3. Mô tả Flow
		- Để mô tả Flow một cách logic thì nên sử dụng hình vẽ. Thể hiện Basic Flow, Alternative Flow và Exception Flow kèm theo hình vẽ như sau:
			+ Basic Flow:![[Pasted image 20201127003024.png]]
			+ Alternative Flow:![[Pasted image 20201127003033.png]]
			+ Exception Flow:![[Pasted image 20201127003040.png]]
		- Đây là cách mô tả flow một cách rõ ràng và sáng sủa nhất có thể.
		- Các step ở Basic Flow, Alternative Flow hay Exception Flow nó đều đối xứng với nhau, thể hiện rõ thằng nào là thay thế của thằng nào, và thằng nào là Exception của thằng nào.
		- Riêng luồng tương tác nào Exception nên sử dụng nét đứt cho dễ phân biệt.
		- Các step bắt đầu (có thể là Trigger hoặc không) và kết thúc nên tô màu đen, để các Stakeholder có thể nắm được độ phức tạp của Use Case một cách nhanh nhất.
		- Còn đối với các Exception Flow - những flow làm fail Use Case, thì tô màu đỏ các step cuối cùng mà Use Case xảy ra không thành công.
		- Tóm lại Đặc tả Use Case về bản chất mang ngôn ngữ tự nhiên của người dùng. Vấn đề chỉ nằm ở một số điểm hay nhầm lẫn và cách chúng ta tổ chức Use Case như thế nào cho logic và hiệu quả.
5. Chốt lại: làm Use Case được lợi ích gì?
	- Giúp thể hiện được Requirement theo góc nhìn của người dùng cuối (rất quan trọng vì nó giúp hiểu rõ bản chất vấn đề hơn).
	- Những gì thể hiện trong Use Case rất tự nhiên, ai đọc vô cũng hiểu
	- Use Case có thể chia nhỏ phạm vi theo nhiều phân hệ, hoặc cụm tính năng. Và nó cũng có thể nhìn dưới góc độ high-level. Do đó, dễ hơn cho mình rất nhiều để cover đủ các yêu cầu trong một dự án lớn.
	- Use case là bước đệm tuyệt vời giữa việc mô tả tổng quát và mô tả chi tiết sự tương tác thông qua Sequence Diagram 
	- Use Case được dùng để tạo các Epic và các User Stories trong dự án Scrum, làm mọi thứ được nhất quán và rất chặt chẽ
	- Use Case còn được dùng để tạo các Test Case sau này.
==Activity Diagram==
-	Thiết kế luồng đi của hệ thống - luồng đi của dữ liệu thông qua Activity Diagram.
-	Activity Diagram là một mô hình logic dùng để mô hình hóa các hoạt động trong một quy trình nghiệp vụ, tức là khi có đặc tả, đi tới được Use Case rồi, muốn mô hình hóa thành một quy trình nghiệp vụ để dev dễ code hơn. Hay có thể hiểu. Activity Diagram là sơ đồ luồng xử lý của hệ thống. Bao gồm luồng đi của dòng dữ liệu, dòng sự kiện
-	Dùng để mô thả các hoạt động trong một chức năng của hệ thống. Hay có thể hiểu là mô tả luồng xử lý của một Use Case
-	Mô tả hoạt động chính và mối quan hệ giữa các hoạt động này trong quy trình. Hay có thể hiểu là mô tả cả luồng xử lý chính của hệ thống bao gồm các luồng con, luồng xử lý của các Use Case gom lại mà thành.
-	Tóm lại Activity Diagram vẽ ra các luồng đi của hệ thống: luồng logic, luồng sự kiện.
-	==Các thành phần của Activity Diagram==
	-	==Start==
		-	Kí hiệu dấu chấm đen
		-	Đặc trưng: khởi tạo một hoạt động. 
		-	Một activity diagram có thể có nhiều trạng thái start. Hay có thể hiểu là điểm bắt đầu của một luồng xử lý. Một phần mềm có thể có nhiều luồng.
	-	==Activity==
		-	Kí hiệu hình vuông có tên của hoạt động trong.
		-	Đặc trưng: Mô tả hành vi của đối tượng trong quy trình. Tên hoạt động phải ngắn gọn - đủ nghĩa.
		-	Nên đặt tên là động từ, và mô tả đủ ý nghĩa tổng thể của hoạt động nhất có thể.
		-	VD: Nhấn button Đăng nhập, Gửi dữ liệu xuống server, nhận mã xác nhận.
	-	==Transition==
		-	Kí hiệu mũi tên
		-	Đặc trưng: Mô tả sự chuyển đổi trạng thái của các hoạt động
		-	Từ hoạt động này đến hoạt động khác cần có transition biểu thị đường đi. Lưu ý Transition có mũi tên biểu thị chiều của luồng xử lý.
	-	==Decision==
		-	Kí hiệu hình thoi
		-	Đặc trưng: Tập các điều kiện kích hoạt việc chuyển trạng thái
		-	Branch:
			+ Mô tả điền kiện rẽ nhánh
			+ Chỉ một dòng điều khiển đi vào
			+ Hai hoặc nhiều dòng điều khiển ra
			+ Chỉ một dòng điều khiển ra dẫn đến kết quả
			+ Mỗi dòng chứa một điều kiện (guard), guard phải liên quan đến điều kiện và loại trừ nhau.
		-	Merge:
			+ Có hai hoặc nhiều dòng điều khiển đi vào
			+ Chỉ một dòng điều khiển đi ra.
		-	Có thể hiểu đây là ký hiệu biểu thị nút điều kiện chuyển hướng. Tùy theo trường hợp đúng hay sai của kết quả biểu thức logic bên trong ký hiệu mà có hướng di chuyển theo tương ứng. Bên trong Decision là điều kiện.
	-	==Synchronization bar==
		-	Kí hiệu một đường gạch đậm.
		-	Đặc trưng: Mô tả các dòng điều khiển thực hiện song song
		-	Fork:
			+ Mô tả dòng điều khiển được tách ra thực hiện song song
			+ Chỉ một dòng điều khiển đi vào
			+ Có hai hoặc nhiều dòng điều khiển ra
			+ Dùng fork khi các hoạt động thực hiện không quan tâm thứ tự.
		-	Join:
			+ Kết hợp các dòng điều khiển song song (fork).
			+ Có hai hoặc nhiều dòng điều khiển vào, không nhất thiết phải fork mà có thể các luồng nào đó gộp lại.
			+ Chỉ một dòng điều khiển ra
			+ Dòng điều khiển ra được tạo ra khi tất cả các dòng điều khiển đã vào.
		-	fork và join không cần nhãn
		-	Có thể hiểu đơn giản. Có các trường hợp cần hội tụ đủ nhiều luồng điều khiển một lúc để gộp thành một luồng xử lý thì cần dùng join.
		-	Và đôi khi cần phải tách một luồng điều khiển ra hai hoặc nhiều luồng khác biệt nhau thì cần fork, và mỗi luồng fork hoàn toàn không lệ thuộc nhau.
	-	==End==
		-	Kí hiệu dấu chấm đen có vòng tròn bên ngoài
		-	Đặc trưng: Mô tả trạng thái kết thu quy trình.
		-	Một activity diagram có một hoặc nhiều trạng thái kết thúc.
		-	Điểm kết thúc của luồng xử lý.
-	==Cách ánh xạ từ sơ đồ Use Case qua Activity Diagram==
	-	Tham khảo sơ đồ : ![[Pasted image 20201128214135.png]]
	-	Cố gắng đưa ra tất cả các trường hợp có thể xảy ra. Phân tích kỹ code dễ hơn, khi code chỉ là hiện thực những cái đã có sẵn không cần phải phân tích thêm nữa.
	-	Ví dụ tham khảo: ![[Pasted image 20201128214947.png]]
==ER Diagram==
-	Để có thể hình dung được cấu hình tổng thể cũng như chi tiết của dữ liệu mà hệ thống sẽ sử dụng.
-	ER - Diagram hay Entity Relationship Diagram (ERD). Được giới thiệu bởi Chen, 1976. Phổ biến rộng rãi trong thiết kế quan niệm dữ liệu. ANSI công nhận mô hình chuẩn 1988.
-	ERD giúp cho chúng ta có cái nhìn tổng quát về sơ đồ dữ liệu lưu trữ dùng trong toàn bộ hệ thống.
-	Gồm : Mô hình nguyên thủy và mô hình mở rộng.
-	==Các thành phần của một ER - Diagram==
	-	==Thực thể==
		-	Biểu diễn một lớp khái niệm trong thế giới thực, thường là danh từ hoặc cụm danh từ, nếu nhìn thấy được thì là trực quan. Những đối tượng sẽ được lưu trữ trong hệ thống cơ sở dữ liệu.
		-	Trực quan:
			+ Con người: nhân viên, sinh viên, khách hàng,...
			+ Nơi chốn: phòng học, chi nhánh, văn phòng,..
			+ Đối tượng: sách, máy móc, sản phẩm, xe,...
			+ Sự kiện: đăng ký, bán hàng, đặt trước, yêu cầu,..
		-	Không trực quan:
			+ Tài khoản, thời gian, khóa học, khả năng, nguồn vốn,..
		- Ký hiệu: Ô vuông và tên thực thể.
	-	==Mối kết hợp==
		-	Biểu diễn sự kết hợp hệ ngữ nghĩa giữa 2 hay nhiều thực thể. Thường là động từ hoặc cụm từ mô tả mối quan hệ. ![[Pasted image 20201128222052.png]]
			+ Sự kiện nối kết
			+ Mối quan hệ vật lý
		-	Trực quan:
			+ Con người: nhân viên, sinh viên, khách hàng,...
			+ Nơi chốn: phòng học, chi nhánh, văn phòng,..
			+ Đối tượng: sách, máy móc, sản phẩm, xe,...
			+ Sự kiện: đăng ký, bán hàng, đặt trước, yêu cầu,..
		-	Không trực quan:
			+ Tài khoản, thời gian, khóa học, khả năng, nguồn vốn,..
		- Ký hiệu: Hình thoi và tên mối kết hợp
	-	==Vai trò==
		-	Biểu diễn ngữ nghĩa của một thực thể tham gia vào mối kết hợp, thường là động từ hoặc cụm động từ. ![[Pasted image 20201128222429.png]]. VD: nhân viên làm việc tại phòng ban, phòng ban gồm có nhân viên làm việc.
		-	Trường hợp tên quan hệ đã đặt đúng, tốt thì không cần tới tên vai trò. Thông thường tên mối kết hợp sẽ lấy 1 trong các tên vai trò (bỏ qua không đặt tên vai trò).
		-	Ký hiệu: tên vai trò trên đường nối giữa thực thể và mối kết hợp.
	-	==Bảng số==
		-	Ràng buộc về số lượng các thực thể tham gia vào mối kết hợp
		-	Ký hiệu bởi một cặp (min, max)
			-	Min: quy định giá trị tối thiểu các thực thể khi tham gia vào mối kết hợp. Giá trị đi từ 0, 1, 2,...đến k (k là hằng số)
			-	Max: quy định giá trị tối đa các thực thể khi tham gia vào mối kết hợp. Giá trị đi từ 1, 2,... đến n.
		-	Phân loại mối kết hợp dựa vào bảng số ![[Pasted image 20201128223429.png]]
	-	==Thể hiện==
		-	Thể hiện của thực thể
			+ Sự xuất hiện cụ thể của các phần tử![[Pasted image 20201128223615.png]], Mỗi khách hàng a, b, c là một thể hiện của thực thể. KH A khác KH B.
		-	Thể hiện của mối kết hợp
			+ Tổ hợp không trùng lắp các thực thể tham gia vào mối kết hợp. ![[Pasted image 20201128223851.png]].
		-	Tóm lại là chỉ có duy nhất một đối tượng thể hiện của thực thể.
	-	==Thuộc tính==
		-	Một thực thể có 1 hoặc nhiều thuộc tính. Thuộc tính phụ thuộc vào thực thể.
		-	Biểu diễn đặc trưng của :
			+ Thực thể
			+ Mối kết hợp
		-	Ký hiệu: một đường gạch và chấm tròn + tên thuộc tính.
		-	Sử dụng bảng số cho những thuộc tính đa trị. ![[Pasted image 20201128224658.png]] - học vị, thường những thuộc tính có nhiều giá trị sẽ kết nối để tạo ra một thực thể mới.
-	==ER - Diagram mở rộng==
	+ Bổ sung vào mô hình thực thể kết hợp:
		+ Thuộc tính kết hợp
		+ Định danh
		+ Tổng quát hóa
		+ Tập con
		+ Mối kết hợp mở rộng.
	-	==Cấu trúc phân cấp==
		-	Thiết lập cấu trúc cây phân cấp giữa các thực thể.
		-	E là một tổng quát hóa của một nhóm thực thể E1, E2, E3 khi mỗi đối tượng của lớp E1, E2, E3 cũng là một đối tượng của lớp E.![[Pasted image 20201128225202.png]]
		-	Ví dụ: ![[Pasted image 20201128225236.png]] ![[Pasted image 20201128225306.png]]
		-	Tóm lại là gom nhóm các đối tượng có chung các thuộc tính.
	-	==Tính kế thừa==
		-	Thực thể chuyên biệt kế thừa thuộc tính và mối kết hợp của thực thể tổng quát.![[Pasted image 20201128225439.png]]
		-	![[Pasted image 20201128225630.png]] 
		-	Nguyên tắc: 
			+ Xây dựng thực thể chuyên biệt khi xác định được đặc trưng riêng của nó
			+ Xây dựng thực thể tổng quá khi xác định được các đặc trưng chung của thực thể. 
			+ Mục đích tái sử dụng.
	-	==Tính bao phủ==
		-	Sự tương quan giữa thực thể tổng quát và thực thể chuyên biệt
		-	Gồm ![[Pasted image 20201128230625.png]]:
			+ Toàn phần (t-total: Tất cả các phần tử của các thực thể chuyên biệt phủ toàn bộ tập phần tử của thực thể tổng quát.
			+ Bán phần (p-partial): Các phần tử của các thực thể chuyên biệt không phủ toàn bộ tập phần tử của thực thể tổng quát.
			+ Riêng biệt (e-exclusive): Phần tử của thực thể chuyên biệt này không là phần tử của thực thể chuyên biệt khác.
			+ Chồng chéo (o-overlaping): Phần tử của thực thể chuyên biệt này có thể là phần tử của thực thể chuyên biệt khác.
		-	Ví dụ ![[Pasted image 20201128230814.png]]
	-	==Tập con==
		-	Là một trường hợp đặc biệt của tổng quát hóa, chỉ có một thực thể chuyên biệt. ![[Pasted image 20201128231026.png]]
		-	Sự tương quan luôn là bán phần và riêng biệt.
	-	==Thuộc tính kết hợp==
		-	Là một nhóm các thuộc tính có liên hệ ![[Pasted image 20201128231228.png]]
		-	Nếu tách các thuộc tính ra thì sau này filter dễ dàng hơn.
	-	==Định danh==
		-	Tập hợp các thuộc tính có tính chất đặc trưng duy nhất nhằm phân biệt tất cả các thể hiện của thực thể. Tóm lại là key dùng để phân biệt thực thể này với thực thể khác. VD mã số nhân viên.
		-	Kí hiệu: ![[Pasted image 20201128231618.png]]
		-	VD: ![[Pasted image 20201128231708.png]]
	-	==Mối kết hợp mở rộng==
		-	Là mối kết hợp được định nghĩa trên ít nhất 1 mối kết hợp khác, không có liên quan đến thực thể. ![[Pasted image 20201128232034.png]]
		-	Thường những đối tượng này sẽ biến đổi thành thực thể riêng biệt.
-	==Ví dụ minh họa==
	-	Yêu cầu: ![[Pasted image 20201128232133.png]]
	-	Mô hình: ![[Pasted image 20201128232155.png]]
-	==Chiến lượng phân tích ER Diagram==
	-	==Phương pháp phân tích dữ liệu==
		-	==Luật căn bản==
			-	Dùng để tinh chế lược đồ quan niệm. Tập hữu hạn các chuyển đổi cần áp dụng cho lược đồ ban đầu để tạo ra lược đồ cuối cùng.
			-	![[Pasted image 20201129201618.png]]
			-	Mục tiêu tạo ra lược đồ để tạo ra được cơ sở dữ liệu để lưu trên máy tính cho nên cần phải phân tích nó nhỏ ra. Giá trị lưu trữ càng nhỏ thì sau này làm sẽ dễ hơn. VD Nơi chốn và Nơi chốn bao gồm các thuộc tính số nhà, đường,... thì Nơi chốn càng rõ thì càng dễ dàng tìm kiếm => tăng tốc độ => trải nghiệm người dùng tốt hơn.
			-	Lược đồ ở mức quan niệm được tạo ra sau 1 quá trình xử lý lặp đi lặp lại:
				+ Bắt đầu bằng phiên bản chưa hoàn chỉnh
				+ Thực hiện các chuyển đổi
				+ Tạo ra phiên bản cuối cùng.
			-	Tính chất của chuyển đổi:
				+ Điều phải có một lược đồ khởi điểm, 1 lược đồ kết quả
				+ Ánh xạ tên giữa 2 lược đồ
				+ Các khái niệm trong lược đồ kết quả phải kế thừa tất cả các kết nối đã xác định trong lược đồ khởi điểm
			-	Tóm lại: từ lược đồ đơn giản nhất ta có thể nghĩa ra. Phân tích, đưa thêm thông tin vào. Sau đó lược đồ bị biến đổi. Chúng ta lại tiếp tục chỉnh lược đồ để hoàn chỉnh hơn. Đến khi có được lược đồ cuối cùng thỏa mãn các tính chất của phân tích thiết kế. Trong đó có tính đúng đắn, đủ và mở rộng.
			-	Được chia thành: Luật căn bản từ trên xuống và Luật căn bản từ dưới lên.
		-	==Luật căn bản trên xuống==
			-	Từ những thực thể phân tích chi tiết hơn.
			-	![[Pasted image 20201129202526.png]] Luật căn bản - Lược đồ khởi điểm - Lược đồ kết quả
			-	![[Pasted image 20201129202814.png]]
			-	![[Pasted image 20201129202931.png]]
			-	![[Pasted image 20201129202950.png]]
			-	![[Pasted image 20201129203036.png]]
		-	==Luật căn bản dưới lên==
			-	Từ những cái nhỏ phân tích ra cái lớn.
			-	![[Pasted image 20201129203117.png]]
			-	![[Pasted image 20201129203213.png]]
		-	==Chiến lược phân tích lược đồ==
			-	![[Pasted image 20201129203417.png]]
			-	Từ 1 cái ban đầu sau khi phân tích nhiều lần thì sẽ càng ngày to ra, càng ngày càng chi tiết hơn.
			-	Gồm có các chiến lược: Trên xuống - Dưới lên - Phối hợp - Trong ra ngoài.
			-	==Trên xuống==
				-	VD Ứng dụng quản lý nhân chủng học
				-	Tinh chế lần 1 ![[Pasted image 20201129203719.png]]
				-	Tinh chế lần 2 ![[Pasted image 20201129203744.png]]
				-	Tinh chế lần cuối ![[Pasted image 20201129203840.png]]
				-	Chúng ta có thể nhận thấy từ thông tin nhân chủng học. Phân tích ra được có con người và vị trí. Từ đó lại tiếp tục phân tích nhỏ hơn đến khi có sơ đồ hoàn chỉnh. Từ thực thể phân tích ra các thực thể khác rồi cuối cùng xuất hiện thuộc tính.
			-	==Dưới lên==
				-	VD Ứng dụng quản lý nhân chủng học
				-	Thu thập tất cả các đặc trưng của các thành phần trong hệ thống![[Pasted image 20201129204812.png]]
				-	Từ các đặc trưng (thuộc tính) phân tích ra các thực thể. ![[Pasted image 20201129204935.png]]
				-	Từ các thực thể nối lại nhau xem có liên hệ với nhau ra sao. Tổng quát hóa lên. ![[Pasted image 20201129205036.png]]
				-	Tiếp tục xác định mối kết hợp, bảng số và định danh ![[Pasted image 20201129205122.png]]
				-	Từ các thuộc tính sẽ gom ra thành thực thể rồi tinh chế cho đến hoàn chỉnh. Từ trên xuống và từ dưới có 2 hướng đi khác nhau nhưng đều cùng một kết quả nếu làm đúng.
				-	Sơ đồ không có đúng hay sai, chỉ có phù hợp với yêu cầu hay không, đáp ứng được yêu cầu là được, còn thêm vô hoặc bỏ ra là tùy thuộc vào ý định của người vẽ. Thêm vào nhiều dữ liệu phình ra, những tìm kiếm sẽ nhanh hơn. Hoặc là ở một phần nào đó xác định không cần tìm kiếm nhanh thì bỏ bớt ra.
			-	==Phối hợp==
				-	![[Pasted image 20201129205511.png]]
				-	![[Pasted image 20201129205535.png]]
				-	Kết quả lược đồ cuối cùng ![[Pasted image 20201129205711.png]]
				-	Từ lược đồ ban đầu, phân tích ra từng cụm sau đó tổng hợp lại. Giảm số lần tinh chế hơn. 
			-	==Trong ra ngoài==
				-	![[Pasted image 20201129205730.png]]
				-	Giống như theo vết dầu loang, thường dùng khi đã quen với việc vẽ ERD. Nếu không phương pháp phối hợp là đủ xài rồi.
				-	![[Pasted image 20201129205945.png]]
				-	Ví dụ: quản lý yêu cầu sách của nhà khoa học ![[Pasted image 20201129210108.png]]
				-	Kết quả Ví dụ: ![[Pasted image 20201129210156.png]]
				-	Chúng ta có thể nhận thấy. Từ một thực thể chúng ta xác định thuộc tính. Sau đó xác định các thực thể và thuộc tính liên quan. Loang ra đến khi hoàn chỉnh.
		-	==So sánh các chiến lược==
			-	Trên xuống - Dưới lên![[Pasted image 20201129210409.png]]
			-	Trong ra ngoài ![[Pasted image 20201129210534.png]]
			-	Phối hợp ![[Pasted image 20201129210554.png]]
	-	==Quy tắc mô hình hóa quan niệm dữ liệu==
		-	Mọi thuộc tính chỉ mô tả đặc trưng cho đúng thực thể mang thuộc tính ấy, tức là những thuộc tính chỉ nằm trên đúng thực thể của nó thôi ![[Pasted image 20201129210705.png]]
		-	Nếu có đặc trưng phụ thuộc vào nhiều thực thể thì đó là đặc trưng của mối kết hợp định nghĩa trên các thực thể đó. ![[Pasted image 20201129211100.png]]
		-	Các thực thể cùng liên quan đến 1 mối kết hợp thì một tổ hợp thể hiện của các thực thể đó phải là thể hiện duy nhất của mối kết hợp. ![[Pasted image 20201129211206.png]]
		-	Các nhánh nối với mối kết hợp phải là nhánh bắt buộc, nếu không phải ta nên tách thành nhiều mối kết hợp ![[Pasted image 20201129211313.png]]
		-	Nếu có 1 đặc trưng phụ thuộc vào 1 thuộc tính của thực thể thì tồn tại thực thể ẩn -> cần được định nghĩa bổ sung. ![[Pasted image 20201129211528.png]]
	-	==Tiêu chuẩn chọn lựa khái niệm==
		-	Trong 1 số trường hợp, các khái niệm cần biểu diễn chỉ có 1 thể hiện, nếu không có nhu cầu mở rộng về sau thì không nên xem là thực thể. ![[Pasted image 20201129211712.png]]
		-	Đối tượng quan tâm không có cấu trúc đặc trưng (chỉ có 1 thuộc tính) thì cẩn thận khi quyết định đó là 1 thực thể. ![[Pasted image 20201129211800.png]]
		-	Thực thể: xác định 1 số đặc trưng cơ bản như thuộc tính, mối kết hợp, tổng quát hóa.
		-	Thuộc tính: cấu trúc nguyên tố, đơn giản, không có các đặc trưng khác. ![[Pasted image 20201129211915.png]]
		-	Tổng quát hóa: một số đặc trưng sẽ được liên kết ở cấp thấp hơn.
		-	Thuộc tính: trường hợp ngược lại. ![[Pasted image 20201129212037.png]]
		-	Thuộc tính kết hợp: một số đặc trưng sẽ được liên kết ở cấp thấp hơn
		-	Thuộc tính đơn: trường hợp ngược lại ![[Pasted image 20201129212145.png]]
		-	Thực thể: khái niệm quan tâm có 1 số đặc trưng (mối kết hợp, định danh,...) ![[Pasted image 20201129212236.png]] => ![[Pasted image 20201129212308.png]]

- Sử dụng extension SCSS IntelliSense: Khi gõ tên biến thì sẽ gợi ý tên biến ra
- Trong mixin có thể thiết lập giá trị mặt định cho tham số, có thể sử dụng if để tăng logic cho mixin.
- Ngoài ra còn 1 số thứ nâng cao như function, vòng lặp.
==Cấu trúc 7-1 của SASS==
1. Helper (hoặc Abstract)
	- Dùng để chứa các file cần thiết cho dự án: 
		- _variables.scss
		- _extend.scss
		- _mixin.scss
2. Base
	- Dùng để chứa các file code giúp style css dùng chung cho cả dự án:
		- _reset.scss: xóa css mặc định của browser (margin, padding,...)
		- _customize.scss: ghi đè code mặc định của thư viện (ghi đè code thư việc cho toàn bộ dự án). Nếu chỉ muốn ghi đè code thư viện của một phần nội dung chính thì phải viết code trong file riêng của phần nội dung đó.
3. Components
	- Chứa các thành phần nhỏ nhưng được dùng nhiều chỗ trong dự án:
		- _button.scss
		- _link.scss
		- _card.scss
4. Layouts
	- Chứa các thành phần lớn dùng chung cho cả web:
		- _header.scss
		- _footer.scss
		- _sidebar.scss
5. Pages
	- Nếu dự án có nhiều trang web(homepage, )
6. Themes
	- Chứa các file giúp xây dựng các kiểu theme khác nhau, ví dụ: kiểu theme nền tối (dark), theme cho dịp lễ Halloween, theme cho sự kiện giật cô hồn
		- DarkTheme
		- Halloween
		- CoHon
7. Vendors
	- Chứa các file của thư viện khi tải về
		- Owl
		- LightBox
8. File main.scss
	- Khong có "_" phía trước tên, nếu có "_" trong tên file thì sẽ báo cho tool biên dịch là không biên dịch file này.
	- Không chứa code css chỉ chứa các đường dẫn đến các file scss trong 7 folders con
	- Thứ tự import
		1. @import files của Helpers:
			- _variables.scss : file biến luôn phải được import đầu tiên
			- _mixin.scss
			- _extend.scss
		2. @import files của Vendors:
			- Chỉ được import các file scss của thư viện, nếu thư viện chỉ có file css thì thêm css ở thẻ head của html
		3. @import files của Base:
			- _reset.scss_
			- _customize.scss
		4. @import files của Components:
		5. @import files của Layouts:
			- Layouts có thể import trước Components
		6. @import files của Pages:
		7. @import files của Themes:
==mixin==
@mixin flex($align: flex-start, $justify: flex-start, $warp: nowrap, $dir: row) {
	display: flex;
	align-items: $align;
	justify-content: $justify;
	flex-wrap: $wrap;
	flex-direction: $dir;
}
@mixin size ($width, $height: $width) {
	width: $width;
	height: $height;
}
==Setting live sass compiler==
- setting vị trí chứa của file css sau khi compiler
- "liveSassCompile.settings.formats":[
        // This is Default.
        {
            "format": "expanded",
            "extensionName": ".css",
            "savePath": "~/../css/"
        }        
    ]
	
==Dùng css để cho chữ chỉ hiện 2 dòng, phần còn lại chuyển thành ...==
.text-clamp {
	display: -webkit-box;
	-webkit-box-orient: vertical;
	overflow:hidden;
	text-overflow: ellipsis;
	&--2 {
		-webkit-line-clamp: 2;
	}
}
- Thẻ a lấy màu theo trình duyệt mặc định không lấy theo thẻ body nên cần set riêng thẻ a.
- Thẻ inline thì không thể set width, height. Chắc cú thì chuyển sang inline-block.
- Border 1px solid sẽ lấy theo màu mặc định của chữ hiện tại, nếu truyền màu vô thì nó sẽ lấy theo màu truyền vào.
- Những cái gì đè thư viện mà áp dụng ở toàn trang thì xử lý ở file customize nằm ở base để code. Còn áp dụng cho chỉ mỗi thư viện trong 1 section nào đó thì chỉ đè thư viện trong section đó. 
- Trường hợp mà sử dụng 1 giá trị, mà nó gần với biến đã khai báo 1-2 đơn vị thì có thể sử dụng toán tử + hoặc - trong scss để xử lý.
- Chú ý để tránh trường hợp khi live server load ok nhưng khi mở bình thường không load được thì cần phải sử dụng đường dẫn lấy vị trí file css làm chuẩn, chứ nếu để tự động thì sẽ lấy vị trí của file sass.
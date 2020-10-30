- Sử dụng extension SCSS IntelliSense: Khi gõ tên biến thì sẽ gợi ý tên biến ra
- Trong mixin có thể thiết lập giá trị mặt định cho tham số, có thể sử dụng if để tăng logic cho mixin.
- Ngoài ra còn 1 số thứ nâng cao như function, vòng lặp.
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
- 
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

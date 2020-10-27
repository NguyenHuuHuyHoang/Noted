- SCSS bản chất là SASS, SASS 3.0 chuyển từ đuôi file sass thành scss. Các cách chuyển scss thành css: Glup (thư viện mã lệnh, có thể viết mã lệnh bằng JS), koala, live sass. Angular với React đã có sẵn không cần phải sử dụng các chương trình chuyển đổi mà có thể import thẳng file scss.
==1 - Nested==
.parent {
	 .chill {
	 	.chill2 {
		}
	 }
}
==2 - Nested Property==
- Dùng để gộp các thuộc tính có cùng họ với nhau vd font-size, font-family => font : {size: 2px; family: tên font;}
==3 - Parent Selector==
.parent {
	&__text => .parent__text
	 &:hover {
	 }
}
- tùy vào vị trí đặt & ban đầu mà nó sẽ mang giá trị của thằng đó, nó sẽ copy cả dấu chấm và tên luôn.
==4 - Variable in SCSS==
- Biến dùng để chứa các giá trị. vd chứa giá trị mã màu: $bg-color: red. Ưu điểm là chỗ nào cần thì thay vì phải gõ mã màu thì sử dụng tên biến, dễ sử dụng, dễ nhớ do chính mình đặt tên. Sử dụng biến cho những giá trị hay thay đổi như màu sắc, hoặc những giá trị lặp đi lặp lại (từ 2 lần trở lên).
- $[tên biến] : giá trị;
==5 - Interpolation==
- sử dụng biến như một thuộc tính trong SCSS
- Khai báo `$[tên key]: width;`
- sử dụng `#{tên key}: giá trị của thuộc tính`
==6 - Mixin và include==
- khai báo @mixin [tên mixin] ($w , $h, $bg, $br) {}
- sử dụng @include [tên mixin] (các giá trị truyền vào)
==7 - @extend==
- Dùng để code gọn hơn, tái sử dụng code.
- @extend `<selector>`
- Extend được trả về sau khi phần còn lại của stylesheet đã được xử lý, Đặc biệt nó xảy ra sau khi parent selector đã được xử lý, có nghĩa là nếu @extend .error, nó sẽ không tác dụng đến những selector bên trong .error `{ &__icons{}}`. nó cũng có nghĩa là parent selectors trong SassScript không thấy được kết quả của extend
- Nguyên lý hoạt động @extend updates style rules that contain the extended selector so that they contain the extending selector as well
==Placeholder==
- placeholder được khai báo %[tên placeholder]
- Sass has a special kind of selector known as a “placeholder”. It looks and acts a lot like a class selector, but it starts with a % and it's not included in the CSS output. In fact, any complex selector (the ones between the commas) that even contains a placeholder selector isn't included in the CSS, nor is any style rule whose selectors all contain placeholders.
- Placeholder được sử dụng khi cần phải sử dụng đi lại giá trị nhiều lần mà không cần truyền vào tham số mới.
==8 - If Else trong SCSS==
- Thường được sử dụng trong mixin hoặc placeholder để điều chỉnh luồng các tham số vào, trường hợp quy định tham số truyền vào mixin cho if nhưng không truyền vào thì nó sẽ hiểu là false.
- @if điều kiện {} @else {}
==9 - List và @Each==
- LIST chứa một dãy các giá trị và ngăn cách với nhau bằng dấu phẩy
- @each gần giống với for in trong js về cú pháp, còn cách sử dụng gần giống như for of trong js
- khai báo $sizes : 20, 50, 100;
- @each  $size in $sizes {}
==10 - Maps trong SCSS==
- Maps gần giống như List nhưng chưa theo kiểu giá trị key : value
- $sizes: (
- 20:20 px,
- 50:50 px,
- 100:100 px,
- )
- Để sử dụng @each lặp qua map thì cần 2 biến ảo $key, $value in $sizes {
- mỗi lần lặp là một cặp key : value
- }
==11 - For & While loop==
- @for & @while
- @for $i from 1 to hoặc through 4 {
- .content:nth-child(#{$i}) {opacity: $i * 0.1;}
- } // to thì không lấy giá trị cuối, throught thì sẽ lây giá trị cuối
- tạo biến đếm bên ngoài  $i : 1;
- @while $i < 5 {
- `.content:nth-child(#{$i}) {opacity: $i * 0.1;};$i : $i + 1;}`
==12 - List Methods==
- append, nth, set-nth, length
- là những cái hàm được xây dựng sẵn trong scss mà ta có thể sử dụng mà không cần phải khai báo
- $list : 1px, 2px, 3px;
- khi sử dụng các method cần phải đặt biến để lưu trữ method vd `$newlist: append($list, 4px);` tạo ra một list mới và thêm phần tử vào đó, list cũ không bị thay đổi
- @debug $newlist /// @debug như console.log trong js.
- nth là một hàm lấy ra giá trị tại một vị trí bất kỳ nào đó
- cần phải gán 1 biến nếu muốn sử dụng nth:`$item: nth($list, 1)` đối với scss thì list sẽ bắt đầu từ số 1
- set-nth sẽ thay đổi một giá trị ở một vị trí nào đó bằng một giá trị khác, list cũ không bị thay đổi giá trị
- `$new-item: set-nth($list , 1, 3px)`;
- length trả về độ dài hay số phần tử của cái list: length($list), sử dụng trong @for @while
==13 - Map Methods==
+ map-get
+ map-remove
+ map-merge
+ map-values
- map-get sẽ lấy ra giá trị của key mà nhập vào
- map-get($map, key)
- map-remove sẽ xóa cặp key value nào đó trong map thông qua key, map ban đầu không bị thay đổi, giá trị trả ra map mới
- map-remove($map, key)
- map-merge
- map-merge($map, $map2) trả ra một map mới chứa tổng giá trị, map cũ không bị thay đổi giá trị, ngoài map thì có thể thêm cặp key: value vào
- map-values, thay vì sử dụng map-get để lấy ra từng value thì sử dụng map-values để lấy toàn bộ values của map và trả về ở dạng list
==14 - Compile từ SCSS sang CSS==
- glup sẽ giúp compile từ scss sang css, glup-sass
==15 - Làm việc với SCSS hiệu quả hơn==
- để code một SCSS hiệu quả thì cần 1 server chạy HTML và SCSS.
- npm browsersync + gulp.js tự động compile quá CSS
- chia nhỏ web ra nhiều component, mỗi component là một layout của web.


==Link game luyện selector==
https://flukeout.github.io
==font-face==
- cú pháp @font-face {font-family: tên đặt cho font; src: url(đường dẫn đến font)};
==setup file scss==
 html {
	 font-size: 62.5%;
 }
*,
*:before,
*:after {
	 box-sizing: border-box;
	-webkit-box-sizing: border-box;
}
img {
	 display: block;
	 max-width: 100%;
}
==Biến trong CSS==
:root {
	--primary: giá trị màu;
}
sử dụng 
var(--primary)
==Border-radius==
- border-radius: 4px 4px 0 0 => trên trái và phải có, ở dưới không có.
==Tạo tam giác==
- Thực chất tam giác là một phần của hình vuông, bốn cái tam giác tạo thành hình vuông
- tam giác đứng thì border left và right là transparent, border bottom sẽ có màu.
==em và rem==
- em phụ thuộc vào font-size của chính nó hoặc phần tử cha chứa nó
- rem phụ thuộc vào font-size của root (html)
==outline==
- none: dùng để khi click không hiển thị hình vuông bao quanh
==appearance==
- none: reset tất cả thuộc tính trở về dạng rỗng như một thẻ div
==user-select==
- none: ngăn người dùng dùng chuột quét trúng nội dung => gây giảm UX
==text-shadow==
- (.4px .4px 5px rgba(0,0,0,.2)): đổ bóng nhẹ font chữ khoảng 2px sẽ làm cho chữ cảm giác mượt mà khi nhìn vào chữ. 
==pointer-event==
- none: bỏ tất cả các sự kiện click lên đối tượng mang nó
==object-fit==
- cover: Cắt các cạnh của hình ảnh, giữ nguyên tỷ lệ ảnh và lấp đầy khoảng trống trong vùng chứa.
==cursor==
- cursor: url('images/my_cursor.png'), auto; -> Để thiết lập hình ảnh nào đó thành trỏ chuột sử dụng.
- Các loại cursor: auto, move, no-drop, col-resize, all-scroll, pointer, not-allowed, row-resize, crosshair, progress, e-resize, ne-resize, default, text, n-resize, nw-resize, help, vertical-text, s-resize, se-resize, inherit, wait, w-resize, sw-resize.
==saturate==
- filter: saturate(0) => màu đen trắng cho ảnh, 1 => màu bt
==user-select==
- user-select: none => không click tô chọn chữ được, không click đúp vào chữ và highlight được, không select text được.
==overflow==
- overflow: scroll: tạo thanh scroll khi nội dung tràn ra ngoài vùng chứa, sẽ hiện cả scroll ngang và dọc ngay cả khi tràn chỉ dọc hoặc ngang.
- overflow: hidden: ẩn nội dung, thường kết hợp với white-space: nowrap.
- overflow: auto: chỉ tạo thanh scroll ở vùng tràn ra ngoài.
- overflow: visible (default): phần tràn ra ngoài vùng chứa vẫn sẽ được hiển thị.
==resize==
- cho phép người dùng có thể thay đổi kích thước thẻ div cả chiều cao và chiều dọc.
- resize: both; overflow: auto;
==Thay doi hinh dang chuot ==
https://css-tricks.com/simulating-mouse-movement/
==flex-shrink==
- Mặc định giá trị trong flex-shrink là 1 nghĩa là cho phép các phần tử co lại khi độ rộng container giảm xuống. nếu 0 thì sẽ không co giãn và lúc này nó sẽ lấy giá trị của thuộc tính width.
- VD 1 phần tử có flex-shrink = 0. Khi co giãn tới ngưỡng độ rộng width của nó thì nó vẫn sẽ giữ độ rộng đó chứ không co lại, hơn nữa như các phần tử flex-shrink = 1.
- Cũng như flex-grow thì các phần tử cũng tỷ lệ với nhau. thằng nào lớn hơn sẽ mất nhiều px hơn khi container bị nhỏ lại.
==flex-grow==
- Cho phép các phần tử giãn theo độ rộng của container. Mặc định giá trị của flex-grow là 0, các phần tử sẽ không tự động co giãn kích thước khi chiều rộng của container bao ngoài thay đổi. Nếu set tất cả các phần tử con cùng 1 giá trị flex-grow thì khi container bao ngoài thay đổi thì các phần tử con sẽ bị co giãn giống nhau, nếu 1 phần tử set khác thì tỷ lệ co giãn sẽ khác.
- VD có 6 phần tử với giá trị flex-grow là 1 thì container sẽ chia điều cho 6. nếu tăng 1 ô lên 2 thì container sẽ chia cho 7, ô tăng lên 2 sẽ chiếm 2/7 width container.
- khi dùng với flex-column thì flex-grow sẽ co giãn theo chiều dọc và lúc này nó sẽ ăn theo height.
==flex-basis==
- Set chiều rộng hoặc chiều cao của phần tử dựa vào flex-direction row hoặc column. Mặc định là flex-direction row cho nên lúc này flex-basis sẽ tương ứng với thuộc tính width của phần tử và khi flex-direction column thì lúc này flex-basis sẽ là height của phần tử.
- Thuộc tính flex-basis sẽ đè lên thuộc tính width hoặc height của phần tử tùy thuộc vào giá trị của flex-direction.
==flex==
- là viết tắt của 3 thuộc tính flex-grow, flex-shrink và flex-basis. Nó như thế này: flex: flex-grow flex-shrink flex-basis. Mặc định grow-0, shrink-1 và basis-auto.
- khi giảm container sẽ tính theo flex-shrink, tăng thì tính theo flex-grow.
==flex-direction: column-reverse==
==flex-direction: row-reverse==
==flex-wrap==
- cho phép các items tự động xuống hàng hoặc vẫn luôn nằm trên cùng một hàng khi kích thước container thay đổi.
- Flex-wrap có 3 giá trị là wrap, nowrap và wrap-reverse
- mặc định là nowrap, khi resize trình duyệt lại thì các item sẽ tự động co lại chứ không xuống hàng, điều này dễ làm cho content bên trong (nếu có) bị ép lại có thể gây xấu giao diện.
- wrap thì ngược lại với nowrap. Khi kích thước container thay đổi và tổng chiều rộng các items cộng lại lớn hơn chiều rộng của container bọc ngoài thì nó sẽ rớt xuống.
- wrap-revese thì ngược lại wrap thay vì rớt xuống thì rớt lên.
- flex-flow:row wrap: thuộc tính này viết để gộp hai thuộc tính là flex-direction và flex-wrap. VD flex-flow: flex-direction flex-wrap. Ứng với flex-direction và flex-wrap là các giá trị tương ứng.
==justify-content==
- Thuộc tính này cho phép căn chỉnh các phần tử theo chiều ngang hoặc chiều dọc tùy thuộc vào thuộc tính flex-direction. 
- có 5 giá trị là flex-start (mặc định), flex-end, center, space-between và space-around.
- flex-start: sát lề trái (row), trên cùng (column)
- flex-end: sát lề phải (row), dưới cùng (column) khác với row-reverse là đổi hướng hiển thị.
- center: nằm giữa
- space-between: Tạo khoảng cách giữa các phần tử bằng nhau, phần tử đầu tiên sát lề trái, phần tử cuối cùng sát lề phải, container sẽ tự động canh khoảng cách giữa các phần tử với nhau sao cho luôn bằng nhau. column thì trên cùng và dưới cùng, những cái ở giữa sẽ bằng nhau.
- space-around: gần giống between nhưng khoảng cách 2 bên và giữa các phần tử bằng nhau. (Khoảng trống ở giữa các phần tử sẽ gấp đôi vì do 2 ô gộp lại), column cũng vậy nhưng theo chiều dọc.
=> justify-content là áp dụng cho content của container cụ thể là căn chỉnh các phần tử trong container.
==Order==
- Cho phép đổi vị trí hiển thị của các phần tử. VD khi xuống mobile muốn đưa hình lên trên nội dung hay đưa xuống dưới.
- Mặc định giá trị của thuộc tính order là 0.  VD có 3 thẻ mà thẻ thứ 2 order = 1, 2 thẻ khác vẫn default thì thẻ thứ 2 sẽ nhảy xuống hiển thị ở 3. Thẻ 3 sẽ nhảy lên 2.
==align-items==
- Ngược lại với thuộc tính justify-content thì mặc định align-items canh các phần tử theo chiều dọc thay vì chiều ngang như justify-content. Tuy nhiên nếu đổi flex-direction sang column thì align-items sẽ canh theo chiều ngang.
- align-items có 5 giá trị là flex-start, flex-end, center, stretch (mặc định thường dùng để canh các phần tử trong 1 div cao bằng nhau), baseline (typography)
- Mặc định trong align-items là stretch, nếu các phần tử height:auto thì sẽ cao full hết container chứa nó, nếu height cố định thì sẽ đè lên thuộc tính stretch này.
- baseline thì sẽ canh các phần tử với nhau dựa vào chữ bên trong (Dòng chữ đầu tiên)
- Baseline là định nghĩa trong typography.
- Trường hợp khi làm việc với column: các phần tử sẽ canh theo chiều ngang, riêng baseline không có tác dụng.
==align-self==
- tương tự align-items nhưng khác nhau ở chỗ là áp dụng riêng lẻ cho các phần tử.
- VD nếu các phần tử align-items: flex-start nhưng muốn 1 thẻ nằm ở giữa thì swr dụng align-self:center
==z-index==
- Giá trị mặc định là auto và z-index chỉ hoạt động khi đi kèm với thuộc tính position.
==Selector==
- :nth-child(even) hoặc :nth-child(odd) : chọn những div con chẵn hoặc lẻ.
- :before hoặc :after : 
	- Để sử dụng thì bắt buộc phải có thuộc tính content. Nếu để trống content thì có thể làm những việc như backgroudn phủ lên toàn bộ layer, hiệu ứng background chạy qua chạy lại(nhớ sử dụng z-index nếu không sẽ đè chữ),... Thường khi sử dụng before hoặc after thì phần tử đang làm nên sử dụng position relative hoặc absolute. Sau đó trong before hay after sử dụng absolute và các thuộc tính top, right, bottom, left để căn chỉnh vị trí.
	- Tạo ribbon hình tam giác: sử dụng 3 thuộc tính border-top: 10px solid #eee;, border-right và border-left. với right và left thì chỉnh transparent còn top thì chỉnh màu trùng với màu nền. các thông số còn lại giống nhau.
- .card:hover ~ .card: The sibling combinator . Chọn toàn bộ thẻ card khi thẻ card đang được hover. Ứng dụng trong việc hover 1 item, các item còn lại sẽ thay đổi. div ~ p: chọn tất cả các tag b được đặt sau tag div (cùng cấp)
- The element1+element2 selector is used to select elements that is placed immediately after (not inside) the first specified element. Chọn chỉ thằng element2 ngay sau thằng element1. div + p: chọn 1 tag nằm ngay sau tag div (cùng cấp).
- The element1>element2 selector is used to select elements with a specific parent. Chọn thằng element2 là thẻ con trực tiếp của element1.
- The element1 element2 selector is used to select elements2 inside elements1. là chọn những thằng element2 nằm trong element1.
- tag:first-child: chọn tag con đầu tiên của phần tử cha chứa nó.
- tag:last-child: chọn tag con cuối cùng của phần tử cha chứa nó.
- :nth-child(2): chọn thằng thứ 2 từ trên xuống.
- :nth-last-child(2): chọn thằng thứ 2 từ thằng cuối đếm lên.
- element[attribute="value"] vd div[class="demo"] chọn tất cả các thẻ div có thuộc tính class="demo".
- :active: chọn liên kết đang được kích hoạt.
- :link: chọn tất cả các liên kết chưa kích hoạt.
- :visited: chọn tất cả các liên kết đã kích hoạt.
- :hover: chọn tag đang được rê chuột vào
- :focus: chọn tag đang có trỏ chuột.
==Dark mode in one line==
- Áp dụng lên tag html khi thêm class dark mode vào.
1. filter: invert(1) hue-rotate(180deg); - tag html
2. chỉnh toàn bộ img : filter: invert(1) hue-rotate(180deg); - tag html img
3. chỉnh: transition: color 300ms, background-color 300ms; - tag html
==Button==
- Các thuộc tính cơ bản như con trỏ chuột, outline: none, background-color: transparent, border: none
==Cách chia căn điều các item trong flex==
- VD: có 4 item, mà muốn mỗi item có độ dài bằng nhau và cách nhau 30px (3 khoảng trống) => width = calc( 25% - 22.5px), 30px x 3 / 4 = 22.5px.
==white-space==
- white-space: nowrap để xử lý việc 1 trong các item cùng hàng có nhiều ký tự hơn 1 dòng => nhảy dòng so với các item còn lại làm bể design, nó giúp cho không nhảy dòng.
==text-overflow==
- text-overflow: ellipsis nếu dài quá mức thì sẽ hiển thị ... thường kết hợp với white-space và overflow: hidden nếu muốn 1 dòng.
==margin==
- margin-top: auto => sẽ đẩy content xuống dưới cùng, tránh trường hợp có khoảng trống ở dưới cùng item.
==Xử lý icon Font-awesome==
- Để chỉnh màu nền của icon trùng với màu của icon.
- Mặc định font awesome sử dụng thẻ before cho nên muốn xử lý gì thì chỉ có thể sử dụng after.
- setting after với thuộc tính height = width = 100%, background-color: currentColor, border-radius: inherit, position:absolute, top:0, left:0, opacity: 0.25.
==Lưu ý==
- Những giá trị trong form như: input, checkbox, button, select option, text-area sẽ lấy css theo trình duyệt chứ không lấy theo body vd: font-family, font-size,... , do đó phải set riêng
- input là dạng thẻ inline, thuộc tính for của label sẽ trỏ tới id của input tương ứng.
==a tag==
- nếu 1 div chứa nhiều thẻ a, muốn xuống dòng thì chỉnh display:block, cần xử lý thêm width: fit-content để tránh trường hợp click khoảng trắng mà vẫn dính thẻ a
==box-shadow==
- nhận vào 4 giá trị là x y blur scale và màu.
- x dương thì sẽ đổ sang phải, y dương sẽ đổ xuống dưới.
==Hướng dẫn code giao diện dropdown==
- fa fa-caret-down => icon
- .dropdown>.dropdown__select>span.dropdown__selected+i.fa.fa-caret-down^ul.dropdown__list>li.dropdown__item>dropdown__text+i.fa.fa-plus-circle.dropdown__icon
- dropdown: có w100% và max-width
- dropdown__select: có w100%
==Lưu ý khi sử dụng d-none==
- khi sử dụng d-none thì sẽ không sử dụng được thuộc tính transition được, do đó cần thay bằng visibility và opacity.
==Background-origin và background-position==
- background-position: là vị trí hình nền mình muốn hiện, ví dụ ưu tiên hiện center thì nó hiện center, nếu không xét thì mặc định sẽ ưu tiên top và left của hình nền.
- còn background-origin: là vùng phủ của hình nền. 1 thẻ HTML sẽ có các vùng content, padding, border, nếu cho bg-origin: padding-box thì nó sẽ chỉ phủ đến padding mà không thèm phủ border.
==font-size==
- Cùng 1 font size nhưng khác font-family sẽ tạo ra các phần tử có chiều cao khác nhau
- Cách font chữ hoạt động:
	- Một font định nghĩa em-square (units per em) của nó, một dạng ô chứa các ký tự được vẽ ra. Ô vuông này sử dụng các đơn vị tương đối và thông thường có giá trị 1000 đơn vị. Nhưng nó cũng có thể có các giá trị khác
	- Dựa trên đơn vị tương đối của nó, các chỉ số của font chữ (font metrics) sẽ được xác định (ascender, descender, capital height, x-height,...). Chú ý là một số giá trị có thể tràn ra ngoài em-square.
	- Trên trình duyệt, các đơn vị tương đối có thể được co giãn để vừa với font-size mong muốn.
	- VD :
		- font Catamaran trong FontForge có các chỉ số:
			- em-square là 1000
			- ascender là 1100 và descender là 540. Capital Height là 680 và X height là 485.
		- Điều đó có nghĩa là font catamaran sử dụng 1100 + 540 đơn vị trên 1000 đơn vị em-square, kết quả là 164px khi thiết lập giá trị fz100px. Chiều cao được tính toán (computed height) này định nghĩa content-area của một phần tử. Có thể xem content-area là vùng mà thuộc tính bg được áp dụng (không hoàn toàn chính xác lắm)
		- Chúng ta có thể dự đoán được độ cao của các chữ cái in hoa là 68px (680 đơn vị) và các chữ cái in thường (x-height) là 49px (485 đơn vị). kết quả là 1ex = 49px và 1em = 100px, không phải 164px (em là giá trị dựa trên fz, không phải chiều cao được tính toán).
		- Khi một phần tử p được hiển thị trên màn hình, nó có thể được tạo bởi nhiều dòng, dựa vào đột rộng của nó. Một dòng được tạo bởi một hay nhiều phần tử inline (thẻ HTML hay các phần tử inline vô danh như text) và mỗi dòng này được gọi là một line-box. Chiều cao của một line-box dựa trên chiều cao của các phần tử con của nó. Do đó trình duyệt sẽ tính toán chiều cao của mỗi phần tử inline, từ đó tính ra chiều cao của line-box (từ điểm cao nhất đến điểm thấp nhất của các phần tử con). Kết quả là một line-box luôn đủ cao để có thể chứa tất cả các phần tử con của nó. ![[Pasted image 20201006134134.png]]
		- *Mỗi phần tử HTML thực ra là một chồng các line-box. Nếu biết chiều cao của mỗi line-box, sẽ biết được chiều cao của phần tử đó.*
		- Trong 1 thẻ span, chứa 1 đoạn chữ, ở giữa đoạn chữ chứa 3 thẻ span. thì nó sẽ sinh ra 3 line-box. line-box đầu tiên và cuối cùng chứa một phần tử inline vô danh (text), line-box thứ 2 chứa 2 phần tử inline vô danh và 3 thẻ span.
		- ![[Pasted image 20201006134817.png]] Một thẻ p (đường viền đen) đường tạo thành từ các line-box (đường viền trắng) chứa các phần tử inline (đường viền trơn) và các phần tử inline vô danh (đường viền nét đứt).
		- Chúng ta thấy rõ ràng line-box thứ 2 cao hơn các line-box khác, do content-area của các phần tử con của nó, và chính xác hơn là phần tử sử dụng font Catamaran.
		- Phần khó trong việc tạo thành line-box là chúng ta không thực sự nhìn thấy hay kiểm soát được nó bằng CSS. Ngay cả việc áp dụng thuộc tính background vào ::first-line cũng không cho chúng ta một dấu hiệu trực quan về chiều cao của line-box đầu tiên.
==line-height==
- nên sử dụng line-height thay vì height vì nó có thể co dãn được, khi font chữ thay đổi thì nó sẽ không bị bể layout.
- Chiều cao của một line-box được tính toán dựa trên chiều cao của các phần tử con của nó chứ không được tính toán dựa trên chiều cao của content-area của các phần tử con của nó.
- Một phần tử inline có 2 chiều cao khác nhau: chiều cao content-area và chiều cao virtual-area (chiều cao mà chúng ta nhìn thấy được). ![[Pasted image 20201006135511.png]] Các phần tử inline có chiều cao khác nhau.
	- Chiều cao content-area được định nghĩa bởi các chỉ số của font.
	- Chiều cao virtual-area là line-height, nó là chiều cao được dùng để tính toán chiều cao của line-box.
- Quan niệm thông thường là line-height là khoảng cách giữa ác baseline. Trong CSS thì không như vậy.![[Pasted image 20201006135616.png]]
- Chiều cao khác nhau giữa virtual-area và content-area được gọi là leading. Một nửa leading được cộng thêm vào phía trên của content-area, nửa còn lại được cộng thêm vào phía dưới. Do đó content-area luôn ở giữa của virtual-area.
- Dựa trên các giá trị được tính toán, line-height (virtual-area) có thể bằng, cao hơn hoặc thấp hơn content-area. Trong trường hợp virtual-area thấp hơn, leading sẽ âm và một line-box trông sẽ thấp hơn các phần tử con của nó.
- Các loại phần tử inline khác:
	- Các phần tử inline thay thế (img, input, svg,...)
	- inline-block và tất cả các phần tử inline-*
	- các phần tử inline xuất hiện trong một bối cảnh định dạng riêng biệt (ví dụ như trong một phần tử flexbox, tất cả các flex item là blocksified).
- Với các phần tử inline riêng biệt này, chiều cao được tính dựa trên các thuộc tính height, margin và border của chúng. Nếu height là auto thì line-height được sử dụng và content-area sẽ bằng với line-height. ![[Pasted image 20201006140323.png]]
- Các phần tử inline thay thế, inline-block/inline-* và blocksified có content-area bằng với chiều cao, hay line-height, của chúng.
- Vấn đề đặt ra là giá trị normal của line-height là bao nhiêu ? Như việc tính toán chiều cao content-area, được tìm thấy trong các chỉ số của font.
- em-square của font Catamaran là 1000, nhưng chúng ta thấy nhiều giá trị ascender/descender khác nhau:
	- ascent/descent thông thường: ascender là 770 và descender là 230. Được sử dụng để vẽ ký tự (bảng "OS/2")
	- các chỉ số Ascent/Descent: ascender là 1100 và descender là 540. Được sử dụng để tính chiều cao content-area (bảng "hhea" và bảng "OS/2")
	- chỉ số Line Gap. Được sử dụng cho line-height: normal, bằng cách cộng thêm giá trị này vào các chỉ số ascent/descent (bảng "hhea")
- trong trường hợp font catamaran định nghĩa line gap với giá trị là 0, nên line-height: normal sẽ bằng với content-area, tức là 1640 đơn vị, hay 1.64
- để so sánh, font arial định nghĩa em-square với giá trị 2048 đơn vị, ascender = 1854, descender = 434 và line gap = 67. Nghĩa là với fz100px thì content-area sẽ là 112px (1117 đơn vị) và line-height: normal là 115px (1150 đơn vị hay 1.15). Tất cả các chỉ số này là của riêng font và được thiết lập bởi người thiết kế font.
- Do đó hiển nhiên việc đặt line-height: 1 là một cách làm xấu. Các giá trị không có đơn vị tính tương đối với fz, không tương đối với content-area, và trường hợp virtual-area thấp hơn content-area là nguồn gốc của rất nhiều vấn đề. ![[Pasted image 20201006145220.png]]
*Với các phần tử inline, padding và border làm tăng vùng background, nhưng không làm tăng chiều cao content-area (cũng như chiều cao của line-box). Do đó content-area không phải lúc nào cũng là thứ bạn nhìn thấy trên màn hình. margin-top và margin-bottom không có tác dụng*
*Với các phần tử inline thay thế, inline-block và blocksified: padding, margin và border làm tăng height nên làm tăng chiều cao content-area và line-box*
==Vertical-align==
- Vertical-align cũng là một nhân tố cần thiết để tính chiều cao của line-box. Thậm chí có thể nói rằng vertical-align có vai trò chủ đạo trong inline formatting context.
- Giá trị mặc định của vertical-align là baseline, các chỉ số ascender và descender của font xác định vị trí của baseline, cũng như tỉ lệ. Do tỉ lệ giữa ascender và descender hiếm khi nào là 50/50, nhiều vấn đề sẽ phát sinh ví dụ như các phần tử sibling.
- Xét trường hợp một tag p chứa 2 tag span cùng chứa 1 ký tự. 
	+ Trường hợp 2 thẻ span sibling kết thừa font-family, fz và line-height cố định, các baseline sẽ trùng với nhau và chiều cao của line-box sẽ bằng với line-height.
	+ Nếu ở phần tử thứ 2 có fz nhỏ hơn thì sao ?. Sự căn chỉnh baseline mặc định có thể sinh ra một line-box cao hơn ![[Pasted image 20201006185128.png]]. Chiều cao của line-box được tính toán từ điểm cao nhất tới điểm thấp nhất của các phần tử con của nó.
- Xét trường hợp một tag p với line-height: 200px, chứa một tag span kế thừa line-height.
	+ Chiều cao của line-box là bao nhiêu ? Chúng ta mong muốn một giá trị là 200px, nhưng không phải. Vấn đề ở đây là thẻ p có font-family riêng biệt (mặc định là serif). Các baseline của thẻ p và thẻ span có thể khác nhau, do vậy chiều cao của line-box sẽ cao hơn dự kiến. Điều này xảy ra do trình duyệt thực hiện việc tính toán với việc coi mỗi line-box bắt đầu với một ký tự có độ rộng bằng 0, đặc tả gọi ký tự đó là strut (Một ký tự vô hình nhưng tác động hữu hình)
	+ Chúng ta vẫn gặp vấn đề giống như với trường hợp các phần tử sibling. ![[Pasted image 20201006185825.png]]
- Việc căn chỉnh baseline đã bị rối loạn, vậy thì dùng vertical-align: middle để giải quyết thì sao ? Như đặc tả mô tả, middle căn chỉnh điểm giữa của chiều dọc của box với baseline của box cha cộng với 1 nửa x-height của phần tử cha. Tỉ lệ của các baseline khác nhau, cũng như tỷ lệ của x-height, do vậy căn chỉnh với middle cũng không ổn. Tệ nhất là, tỏng hầu hết các trường hợp, middle không thực sự là ở giữa. Có quá nhiều yếu tố tham gia vào việc tính toán mà không thể kiểm soát bằng CSS (x-height, tỷ lệ ascender , descender,..)
- Cần chú ý, có 4 giá trị khác ![[Pasted image 20201006191259.png]] có thể hữu ích trong một số trường hợp:
	- vertical-align: top/bottom: căn chỉnh về phía đỉnh hoặc đáy của line-box
	- vertical-align: text-top/text-bottom: căn chỉnh về phía đỉnh hoặc đáy của content-area.
- Tuy nhiên trong tất cả trường hợp việc căn chỉnh được thực hiện dựa trên virtual-area, tức là trên một chiều cao vô hình, do đó cần cẩn thận VD: ![[Pasted image 20201006192115.png]]
- vertical-align cũng nhận các giá trị số giúp nâng cao hay hạ thấp box theo baseline. Tùy chọn này có thể sẽ có ích trong một số trường hợp.
==font-metrics==
- liệu font-metrics có thể kiểm soát được bằng CSS ? Không. Font metrics là các hằng số nên có thể làm được gì đó.
- Sẽ ra sao nếu chúng ta muốn một đoạn văn bản sử dụng font cataraman và chiều cao của các chữ cái viết hoa đúng bằng 100px.
	- Đầu tiên chúng ta gán giá trị cho các font metrics bằng css, sau đó tính font-size để các chữ cái viết hoa có được chiều cao là 100px. ![[Pasted image 20201006193913.png]]
- Trường hợp chữ được hiển thị ở giữa để phần khoảng trống còn lại được chia đều ở phía trên và phía dưới chữ "B" thì sao ? để làm được điều đó cần phải tính vertical-align dựa trên tỉ lệ ascender/descender.
	-	Đầu tiên tính chiều cao của line-height: normal và content-area:
		-	p {--lineheightNormal: (var(--fm-ascender) + var(--fm-descender) + var(--fm-linegap)); --contentArea: (var(--lineheightNormal) * var(--computedFontSize)); }
	- Tiếp theo cần: khoảng cách từ đáy của chữ cái với cạnh dưới của box, khoảng cách từ đỉnh của chữ cái với cạnh trên của box.
		- p {--distanceBottom: (var(--fm-descender)); --distanceTop: (var(--fm-ascender) - var(--fm-capitalHeight));}
	- Giờ chúng ta có thể tính vertical-align bằng hiệu của các khoảng cách nhân với font-size được tính toán (chúng ta phải áp dụng giá trị này vào một phần tử con inline)
		- p {--valign: ((var(--distanceBottom) - var(distanceTop)) * var(--computedFontSize)) }
		- span {vertical-align: calc(var(--valign) * -1px)};
	- Cuối cùng, chúng ta gán giá trị line-height mong muốn và tính toán nó trong khi vẫn giữ được trạng thái căn chỉnh theo chiều dọc: ![[Pasted image 20201006201521.png]]
		- p {--line-height:3; line-height: calc(((var(--line-height) * var(--capital-height)) - var(--valign)) * 1px)};
	- Thêm một biểu tượng với chiều cao bằng với chữ cái "B" giờ khá dễ dàng: ![[Pasted image 20201006203452.png]]
		- span::before {
			+ content: '';
			+ display: inline-block;
			+ width: calc(1px * var(--capital-height));
			+ height: calc(1px * var(--capital-height));
			+ margin-right: 10px;
			+ background: url('https://cnd.pbrd.co/images/yBAKn5bbv.png');
			+ background-size: cover;
		- }
	- Ví dụ chỉ dùng cho mục đích diễn giải. Không nên phụ thuộc vào nó vì:
		- font metrics là các hằng số nhưng các tính toán trên trình duyệt thì không.
		- nếu font không tải được, font dự phòng được dùng nhưng có thể có font metrics khác, do vậy xử lý các giá trị font metrics của nhiều font sẽ trở nên rất khó khăn.
==Tổng kết==
+ inline formatting context rất khó hiểu
+ tất cả các phần tử inline đều có 2 chiều cao:
	+ content-area (dựa trên font metrics)
	+ virtual-area (line-height)
	+ cả 2 chiều cao này đều không được xác định một cách rõ ràng.
+ line-height: normal được tính dựa trên font metrics
+ line-height: n có thể tạo ra virtual-area nhỏ hơn content-area.
+ vertical-: không đáng tin cậy
+ chiều cao của một line-box được tính toán dựa trên các thuộc tính line-height và vertical-align của các phần tử con của nó.
+ chúng ta không thể lấy/gán font metrics một cách dễ dàng bằng CSS.
==Các phương pháp căn giữa bằng mẹo==
+ Sử dụng line-height:
	+ Chúng ta cần gán giá trị line-height của phần tử chứa chữ bằng với giá trị chiều cao của phần tử đó. Mặc định, khoảng trống phía trên và bên dưới chữ có chiều cao bằng nhau nên chữ sẽ được căn giữa theo chiều dọc. line-height = height = 120px.
	+ Hạn chế là chỉ tác dụng với một dòng chữ, với nhiều dòng thì không.
+ Sử dụng absolute bên trong relative position.
	+ Phương pháp này dựa trên thuộc tính margin:auto được dùng để căn giữa một phần tử bên trong phần tử cha của nó. Tuy nhiên độ rộng và chiều cao của phần tử con cần được xác định cụ thể.
	+ position: absolute, width: 64px, height: 64px; left: 0; top:0; right:0 ; bottom: 0; margin: auto;
	+ Phương pháp này có thể áp dụng cho các hộp thoại có độ rộng cố định.
+ Sử dụng padding và margin:
	+ Phương pháp này chỉ ổn với các nội dung tĩnh, có rất nhiều vấn đề với nội dung động. Hơn nữa, khai báo kích thước bằng pixel quá nhiều sẽ gây ra những vấn đề nghiêm trọng với thiết kế responsive do một pixel không phải một pixel trên các thiết bị di động.
+ Căn giữa sử dụng display table:
	+ Ở thời HTML4 thì phương pháp dàn trang chủ yếu là table. Chỉ có một thứ hoạt động tốt là: việc căn chỉnh theo chiều dọc. Khi thế giới cuối cùng cũng đã chuyển sang sử dụng HTML5, một việc được mong đợi từ lâu, và bắt đầu sử dụng các phương pháp dàn trang tốt hơn thì đột nhiên phát hiện tính năng căng chỉnh theo chiều dọc này bị thiếu mất. Tuy vậy, chúng ta có thể sử dụng ba thuộc tính display của CSS là table, table-row và table-cell, với 3 thuộc tính này thì bất kỳ phần tử HTML nào cũng có thể hoạt động như table, row, cell.
	+ Trên thực tế việc giả lập dàn trang bằng table trên HTML5 và CSS3 còn tốt hơn dàn trang bằng table gốc. Đầu tiên, không cần thiết phải phụ thuộc vào toàn bộ cấu trúc của table: table chứa các row, row chứa các cell. Bạn có thể dùng row nếu muốn, nhưng hoàn toàn có thể đặt table-cell trực tiếp bên trong table. Tuy nhiên vẫn cần tới table.
	+ do vậy để căn giữa nội dung bên trong div, chúng ta có thể hiển thị div đó như table và bao nội dung của div đó bên trong một phần tử nữa, vd span, và phần tử đó được hiển thị như là một table-cell
	+ div - display:table, span - display:table-cell - text-align: center - vertical-align: middle.
	+ Ưu điểm của phương pháp này khi so sánh với các mẹo bên trên là nó rõ ràng. Nó đơn giản, phổ biến và có thể sử dụng với bất cứ phần tử bao đóng và được bao đóng nào. Không cần biết trước nội dung, không cần phải xử lý với các kích thước cố định
	+ Nhược điểm: đầu tiên, cần phải chèn thêm một phần tử vào cấu trúc DOM. Trong một số trường hợp cụ thể, điều này sẽ khiến số lượng code tăng lên đáng kể. Thứ hai, ở mức khái niẹm thì chúng ta đang sử dụng mẫu dàn trang dựa vào table đã lỗi thời, điều này không được tốt lắm.
+ Căn giữa sử dụng Flexible box layout model
	+ Phương pháp căn chỉnh dựa trên table ở trên nhìn về quá khứ, trong khi phương pháp sử dụng flexible box thì hướng tới tương lai. Được phát minh vào năm 2009.
	+ Flexible box model cung cấp một khái niệm tự mô tả mới và đặc biệt là cung cấp những sự nhìn nhận mới về các khái niệm alignment và justification. thuộc tính justify-content định nghĩa cách các phần tử được đặt dọc theo trục cắt.
	+ Trục chính và trục cắt phụ thuộc vào giá trị của thuộc tính flex-direction, giá trị có thể là row (mặc định), reverse-row, column, hoặc reserve-column. Với hai giá trị đầu, trục chính nằm ngang và trục cắt nằm dọc, và ngược lại, với hai giá trị cuối thì ngược lại.
	+ Để sử dụng flexible box với mục đích căn giữa các phần tử, bạn có thể sử dụng quy tắc sau: justify horizontally, align vertically.
	+ Phương pháp này đơn giản, code rất ngắn và rõ ràng, không cần thêm phần tử và kết quả thậm chí chính xác hơn. Tuy nhiên cần phải tùy thuộc vào tính tương thích.
	+ Theo thông tin trên trang  Can I Use, display table được hỗ trợ đầy đủ bởi hầu hết các trình duyệt trên mọi nền tảng. Flex box thì thiếu đầy đủ hơn, IE10 chỉ hỗ trợ một phần và yêu cầu sử dụng vendor prefix, safari cũng yêu cầu dùng vendor prefix và cuối cùng opera mini vẫn chưa hỗ trợ.
+ Các trường hợp căn giữa thông thường: 
	+ Căn giữa textbox chứa ảnh được bao quanh bởi chữ:
		+ Chúng ta cần căn giữa một ô chứa chữ và ảnh nằm bên trong ô đó. Ô được hiển thị dạng inline-block với độ rộng cố định.
		+ Để căn giữa ô này bên trong một phần tử khác, ví dụ như một div, chúng ta có thể sử dụng cách căn chỉnh bằng table: hiển thị phần tử chứa như table cộng với một thẻ span hiển thị như một table-cell bên trong nó, thẻ span bọc toàn bộ nội dung hiển thị VD thẻ card
			+ thẻ cha d:table, thẻ span con bọc sử dụng d:table-cell, text-align: center, vertical-align: middle.
		+ Trường hợp căn giữa bằng flexible box model, chúng ta cần làm là gán giá trị flex cho thuộc tính display của phần tử chứa và giá trị center cho các thuộc tính justify-content và align-items.
	+ Nút với ảnh và chữ được căn giữa
		+ Để tạo ra một nút với chữ đẹp, 2 thành phần này cần phải được căn chỉnh một cách hợp lý so với nhau. Để đạt được mục tiêu này bằng cách sử dụng căn chỉnh bằng bảng, chúng ta phải tách chúng ra các ô riêng biệt. Do vậy HTML sẽ có dạng thẻ cha (a tag) chứa 2 span, mỗi span chứa 1 phần tử. 1 cái là hình 1 cái là chữ
			+ Trong CSS, gán giá trị d:table cho nút, sau đó thêm class cho các ô và ảnh, ảnh cần phải có thuộc tính float left
			+ thẻ span có thuộc tính d:table-cell và vertical-align: middle (để cân bằng 2 thẻ span với nhau)
			+ img có thuộc tính float left và mr để cách ra với chữ.
		+ Với flexible box thì cả ảnh và chữ đều có thể được đặt trực tiếp bên trong nút và không cần float vì cách căn giữa của flexible model đã tự căn chỉnh để cho ra kết quả đẹp. Do nút không có chiều cao cụ thể, thuộc tính display nên gán giá trị là inline-flex.
	+ Menu với ảnh và chữ được căn giữa:
		+ Menu được tạo nên bởi danh sách không sắp xếp thứ tự (ul). Ở đây chúng ta sẽ tạo ra một menu hiển thị theo chiều dọc chứa chữ và ảnh. Menu hiển thị theo chiều ngang thì cũng tương tự như chiều dọc.
			+ Sử dụng cách căn chỉnh bằng table, chúng ta sẽ căn giữa nội dung của các mục của menu theo cùng một cách mà chúng ta sử dụng để căn giữa nội dung của nút, tức là đặt ảnh và nhãn của các mục vào các ô riêng biệt.
			+ Sử dụng flexible model: 
				+ Trong ul: inline-block, list-style: none
				+ li : flex, align-items:center.
	+ Các thẻ input với nhãn được căn giữa.
		+ Trường hợp căn giữa nhãn của các input như checkbox, radio button, text box,...Nói chung thứ căn giữa là gì cũng không quan trọng, vậy nên checkbox hay radio button không khác so với ảnh.
			+ Sử dụng table ![[Pasted image 20201006183915.png]]
			+ Sử dụng flex ![[Pasted image 20201006184000.png]]
- Kết luận có 2 phương pháp tốt căn giữa các phần tử HTML là căn chỉnh bằng table và flex box, phương pháp đầu đáng tin cậy hơn ở khía cạnh tương thích, trong khi phương pháp thứ hai đơn giản hơn, chính xác hơn và cho phép viết code ngắn gọn hơn.
==Animation==
- cú pháp @keyframes. trong đây chúng ta sẽ khai báo 1 chu kỳ chuyển động thông qua các mốc như 0%,25%,50%,75%,100%. ở mức 0% nếu không có thay đổi gì thì để rỗng.
- Cách sử dụng thì cần khai báo ở phần css của các tag cần sử dụng thông qua từ khóa animation.
==Responsive==
- min-width: là mobile first, đây là cách tối ưu code nhất, bs đang sử dụng. code mobile, khi nào lên table có thêm không gian thì bổ sung thêm các component.
- max-width: là desktop first.
==Pseudo-class==
	==Hover==
	- Có thể sử dụng Hover với ~ để select nhiều yếu tố sau nó hoặc sử dụng kết hợp với after để tạo tooltip.
	==Checked==
	- Sử dụng để kiểm tra điều kiện đầu vào, có thể kết hợp + để kiểm tra nhiều check box liền kề nhau.
	==Target==
	- Sử dụng kèm với thẻ a, khi click vào thẻ a thì nó sẽ trigger đến class có id tương ứng kèm với #, nếu class đó có pseudo target thì nó sẽ kích hoạt css.
	==link | visited | hover | active (link stage)==
	- trường hợp sử dụng thì cần đặt đúng thứ tự link -> visited -> hover -> active.
	==focus==
	- kích hoạt css cho element sau khi nhấp hoặc sử dụng tab để focus vào element.
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
- rem phụ thuộc vào font-size của htmt
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
- .card:hover ~ .card: The sibling combinator. Chọn toàn bộ thẻ card khi thẻ card đang được hover. Ứng dụng trong việc hover 1 item, các item còn lại sẽ thay đổi.
- li + a: chọn a đầu tiên sau thẻ li
- :first-child: chọn thằng con đầu tiên
- :last-child: chọn thằng con cuối cùng
- :nth-child(2): chọn thằng thứ 2 từ trên xuống.
- :nth-last-child(2): chọn thằng thứ 2 từ thằng cuối đếm lên.
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
==a tag==
- nếu 1 div chứa nhiều thẻ a, muốn xuống dòng thì chỉnh display:block, cần xử lý thêm width: fit-content để tránh trường hợp click khoảng trắng mà vẫn dính thẻ a
==box-shadow==
- nhận vào 4 giá trị là x y blur scale và màu.
- x dương thì sẽ đổ sang phải, y dương sẽ đổ xuống dưới.

==Hướng dẫn code giao diện dropdown==
- fa fa-caret-down => icon
- 
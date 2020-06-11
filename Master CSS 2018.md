==1 - CSS Syntax==
- selecter(h1, p) attributes (được đặt bên trong {color:blue; font-size:12px})
- để dễ đọc thì các key:value trong attributes được viết xuống dòng, các attributes sẽ tô điểm cho selecter.
==2 - CSS selector (Part 1)==
- p {} select by HTML tag name
- #intro {} select by element ID, cách này không được khuyến khích, id thường dùng cho js hơn
- .center {} slelect by class name, cách này thông dụng nhất và khuyên dùng nhất vì tính reusability
- h1, h2, h3, .bold {} select group element
==3 - Colors in CSS==
- RGB Hex (#00FF00) nên viết hoa
- rgb(red, green, blue) (0 - 255)
- rgba(red, green, blue, alpha)
==4 - Styling text==
- Các thuộc tính hay dùng:
+ color: #DDD
+ text-align: center | left | right | justify(ít dùng trên web do canh đều cả trái cả phải bằng nhau rất xấu nên ít dùng)
+ text-decoration: none | underline | overline(ít dùng) | line-through(ít dùng)
+ text-transform: uppercase(được dùng nhiều nhất) | lowercase | capitalize
+ text-indent: 10px (Chữ đầu tiên sẽ được lùi vào)
+ letter-spacing: 5px (Khoảng cách của từng ký tự, thường không thay đổi nếu không cần thiết)
+ word-spacing: 10px (khoảng cách giữa các từ)
+ line-height: 1.2 //a Number (Khoảng cách giữa các dòng)
+ text-shadow: x y color blur  
==5 - 3 cách chèn CSS==
- Internal CSS là viết CSS ngay trong file html bằng thẻ style, thẻ style nằm tron tag head
- Inline CSS là viết CSS trong thẻ bằng thẻ style="attribute;"
- External CSS là viết CSS ở ngoài sau đó link vào file HTML
==6 - Custom fonts==
- Google font : có 2 cách dùng. 1 là copy link css google font và bỏ vào trong head HTML sau đó dùng tên font đó trong font-family, 2 là chọn @IMPORT và copy đường link @import paste vào trên cùng file css và sử dụng. Để biết dang sử dụng font gì thì sử dụng computed trong inspect element của chorme, kiểm tra xem font có hỗ trợ tiếng việt hay không trước khi sử dụng.
- Ngoài ra còn cách là tải font về xong sử dụng @font-face để import font vào (tránh dùng hoặc hạn chế dùng vì giữ cho design simple)
- Một số thuộc tính của CSS cho font :
+ font-family: font1, font2, font3 (Browser sẽ kiểm tra font đầu tiên có tồn tại hay không, nếu không tìm thấy sẽ thử font tiếp theo cho tới cuối cùng, nếu cuối cùng không thấy thì sẽ hiển thị font mặc định)
+ font-style: normal | italic
+ font-size : 18px
+ font-weight: normal | bold | 400 | 600 | 700 | 900
==7 - Live server (Giúp code CSS nhanh hơn)==
- npm install - g live-server
- giúp cho việc code css và html rất nhanh. cd đến thư mục chứa project , chạy live-server, tự động mở trên trình duyệt thư mục. Để thoát server thì ấn Ctrl + c
==8 - Padding==
- Các cú pháp padding:
+ padding-top
+ padding-right
+ padding-bottom
+ padding-left
+ padding: top right bottom left
+ padding: top left-right bottom
+ padding: top-bottom left-right
+ padding: all
- khoảng cách từ đường viền của container đến object trong đó.
==9 - Margin==
- Các cú pháp margin:
+ margin-top
+ margin-right
+ margin-bottom
+ margin-left
+ margin: top right bottom left
+ margin: top left-right bottom
+ margin: top-bottom left-right
+ margin: all
- Margin là khoảng cách bên ngoài, là khoảng cách giữa các component với nhau. Đa phần dùng margin bottom hơn top
==10 - Border==
- Syntax:
+ border-width: 1px
+ border-style: solid | dotted | dashed|....
+ border-color: red
`Short hand` border: 1px solid red
- Note:
+ border-width: top right bottom left
+ border-width: top left-right bottom
+ border-width: top-bottom left-right
+ border-top-width: 1px
+ border-right-width: 1px
+ border-radius: 5px
- border là lớp nằm ở giữa padding và margin
==11 - Background color==
+ background-color: color
+ background-color: transparent
+ background-color: gradient
google css color gradient, google cssgradient generator
- thường background gradient sẽ đi cùng 2 dòng để fallback nếu trình duyệt không hỗ trợ gradient thì sẽ sử dụng giá trị ở trên
- VD: background: rgb(2,0,36);background: linear-gradient(90deg, rgba(2,0,36,1) 0%, rgba(9,9,121,1) 35%, rgba(0,212,255,1) 100%);
==12 - Background image==
- background-image: url(...)
- background-repeat: repeat x (Từ một bức ảnh vuông, repeat thành một background)| repeat y  | no-repeat | repeat*(mặc định) | ...
- background-size: % | contain (làm cho ảnh fit vào khung của nó, làm thế nào đấy hiển thị 100%)| cover (sẽ làm cho ảnh bao trọn khung hình với điều kiện là ảnh to hơn khung hình) | auto* (mặc định) | ...
- background-position: x y | center (ảnh sẽ kéo lên trên và cái khung fit vào giữa cái ảnh)
- background-attachment: scroll*(mặc định) | fixed
- pattern là thuật ngữ chỉ những họa tiết có thể lặp đi lặp lại được, và sẽ tạo nên một cái hình khi lặp đi lặp lại theo chiều dọc hoặc chiều ngang, google abstract pattern.
==13 - Icons==
- vào trang fontawesome.com copy thẻ link file css fa cho vào head, có thể chỉnh sửa kích thước icon bằng các class chỉnh sửa vd fa-xs, fa-rotate-180 xoay icon, fa-spin sẽ làm icon chuyển động. fa là prefix class
- thường icon dùng thẻ i chứa class theo thư viện của font đó
- Material icon dùng tương tự font awesome, nên dùng 1 loại thư viện font trong một web cho có tính hệ thống
==14 - Styling links==
- States:
+ a:link
+ a:visited
+ a:hover
+ a:active (trỏ chuột lên click vào nhưng chưa thả tay ra)
- style cho một đường link cũng giống như style cho text.
- Chức năng force step trong chorme dev giúp chỉnh sửa thuộc tính dễ dàng hơn
==15 - Lists & Tables==
[LIST]
- list-style-type: none (áp dụng cho cả ol và ul), circle | square(ul), upper-roman(I,II,III) | lower-alpha(a,b,c)(ol)
- list-style-image: url('sqpurple.gif'); 
- list-style-position: outside (dấu chỉ mục sẽ nằm ngoài thẻ ul, ol)
- list-style-position: inside (dấu chỉ mục sẽ nằm trong thẻ ul, ol)
- để tô màu cho chỉ mục UL : ul {list-style: none} => li::before {content: "•"; color: red} => li::before {content: "•"; color: red;
  display: inline-block; width: 1em; margin-left: -1em}, có thể sử dụng các icon unicode như • = "\2022", ◦ = \25E6" and ▪ = "\25AA"
- để tô màu cho chỉ mục OL: ol {list-style: none; counter-reset: li} => li::before {content: counter(li); color: red;
  display: inline-block; width: 1em; margin-left: -1em} => li {counter-increment: li}
- `Short hand` list-style: square inside url('sqpurple.gif')
[TABLE]
- table, th, td {border: 1px solid black;} => tạo ra border double, 1 cái border của table, 1 cái của các element td, th trong table, muốn border single thì sử dụng thêm table {border-collapse: collapse;}
- nếu chỉ muốn border xung quanh table thì table {border: 1px solid black;}
- sử dụng width và height để thiết lập chiều dài và chiều cao table
- text-align: left | right | center
- vertical-align: top | bottom | middle ( chú ý chỉ sử dụng thuộc tính này khi set chiều cao của td để có đủ không gian di chuyển text)
- padding: trong các thẻ td với nội dung chứa
- th, td {border-bottom: 1px solid #ddd;} tạo horizontal dividers có dòng dưới các row để dễ xem
- tr:hover {background-color: #f5f5f5;} khi trỏ chuột vào dòng thì sẽ highlight dòng đó lên để dễ nhìn
- tr:nth-child(even) {background-color: #f2f2f2;} tạo màu sole  giữa các row table (zebra-striped tables)
- Responsive Table : container element (like `div`) with overflow-x:auto around the `table` element to make it responsive (tạo thanh scroll ngang của table để xem nội dung table chưa hiển thị hết màn hình)
- table-layout: auto | fixed 
- Display no borders on empty cells in a table: table {empty-cells: hide;}
- Thẻ caption dùng để ghi tên table: <caption>Table 1.1 Customers</caption>
- caption-side: top* | bottom là thuộc tính của table nhằm quy định vị trí của tên table
==16 - Inline vs. block==
- Các element inline (thẻ a) thì cùng nằm trên một hàng, block (thẻ p) thì chiếm một hàng và đẩy các element khác xuống dưới
- Có thể thay đổi bằng display: block | inline
- Thẻ inline không thể chỉnh kích thước được, còn block thì có thể chỉnh được chiều rộng content(width)
- Thẻ inline thì khi set margin all thì chỉ có trái phải không có trên dưới trái phải như block, padding thì inline vẫn có hiệu lực 4 phía
- tag img mang tính d:inline, nó như một ký tự nhưng mà to ra
==17 - CSS combinators==
- Là cách kết hợp các selector đơn giản như:
+ descendant selector (space) .list-1 .item - cha xong đến con, cháu
+ child selector (>) .list-1 >.item (chỉ tìm những thằng con thôi chứ không chọn cháu)
+ adjacent sibling selector (+) .list-1 .item-2 + .item tìm trong list-1 thằng item-2 và select thằng anh em tiếp theo của nó (chỉ select 1)
+ general sibling selector (~)  .list-1 .item-2 ~ .item tìm trong list1 thằng item-2 và select tất cả thằng anh em của nó có class là item
==18 - pseudo class & pseudo element==
`Pseudo-class`
- A pseudo-class is used to define a special state of an element:
+ Style an element when a user mouses over it
+ Style visited and unvisited links differently
+ Style an element when it gets focus
+ pseudo-classes: :checked, :active, `:disabled`, :empty, :enabled,` :first-child`,:first-of-type, `:focus`, :hover, :in-range, :invalid, :lang(language), :last-child, :last-of-type, :link, :not(selector), :nth-child(n), :nth-last-child(n), :nth-last-of-type(n), :nth-of-type(n), :only-of-type, :only-child, :optional, :out-of-range, :read-only, :read-write, :required,:root, :target, :valid, :visited 
- selector:pseudo-class {property: value;} VD: a:link , a:visited, a:hover, a:active
`a:hover MUST come after a:link and a:visited in the CSS definition in order to be effective! a:active MUST come after a:hover in the CSS definition in order to be effective! Pseudo-class names are not case-sensitive.`
- Pseudo-classes can be combined with CSS classes
- Hover over a `<div>` element to show a `<p>` element (like a tooltip) div:hover p {display: block;}
[The :first-child Pseudo-class]
The :first-child pseudo-class matches a specified element that is the first child of another element.
[The :lang Pseudo-class]
The :lang pseudo-class allows you to define special rules for different languages.
q:lang(no) {quotes: "~" "~";} thay "content" của tag q bằng ~content~
[The :focus Pseudo-class]
input:focus {background-color: yellow;}
`Pseudo-Elements`
- CSS pseudo-element is used to style specified parts of an element:
+ Style the first letter, or line, of an element
+ Insert content before, or after, the content of an element
`Syntax`
selector::pseudo-element {property: value;}
[The ::first-line Pseudo-element]
The ::first-line pseudo-element is used to add a special style to the first line of a text. The ::first-line pseudo-element can only be applied to block-level elements.
[The ::first-letter Pseudo-element]
The ::first-letter pseudo-element is used to add a special style to the first letter of a text. The ::first-letter pseudo-element can only be applied to block-level elements.
`pseudo-elements can also be combined`
[The ::before Pseudo-element]
The ::before pseudo-element can be used to insert some content before the content of an element.
h1::before {content: url(smiley.gif);}
[The ::after Pseudo-element]
The ::after pseudo-element can be used to insert some content after the content of an element.
h1::after {content: url(smiley.gif);}
[The ::selection Pseudo-element]
The ::selection pseudo-element matches the portion of an element that is selected by a user.The following CSS properties can be applied to `::selection`: color, background, cursor, and outline.
==19 - Flexbox (part 1)==
- flexbox để làm layout thuận tiện hơn, trước flexbox thì dùng float. 
- flexbox có những thuộc tính cho cha và cho con
[Thuộc tính cho cha]
- display: flex
- flex-direction: row* | column
==20 - Flexbox(part2)==
- justify-content (chia theo chiều flex): flex-start* | flex-end (dồn sang phải) | space-between(khoảng cách giữa các element sẽ được chia đều và không có khoảng cách ở đầu bên trái và cũng không có khoảng cách ở đầu bên phải) | space-around(khoảng cách giữa các element gấp đôi khoảng cách đầu và khoảng cách cuối) | center | space-evenly (chia đều khoảng cách đầu - giữa - cuối). Trường hợp direction column thì phải có khoảng cách thì mới sử dụng được justify-content
- align-items: (căn chỉnh item theo hướng vuông góc với chiều hiện tại của nó) flex-start | flex-end | center | baseline | stretch* (kéo dãn chiều cao của content = chiều cao của thằng cha)
==21 - Flexbox(part3)==
[thuộc tính cho con]
- flex-basics: auto* | `<length>` áp dụng item con bên trong dùng để thay đổi chiều rộng của các block item bên trong, vd flex-basics: 150px. Không phải lúc nào chiều rộng được như định nghĩa bên trong, nếu thằng cha rộng hơn chiều rộng các thằng con + lại thì ra được như định nghĩa trừ trường hợp content trong thằng con quá dài => dẫn tới thằng con đó sẽ bị kéo dãn ra do content. Trường hợp tổng 3 thằng to hơn thằng cha thì chiều dài sẽ không được như định nghĩa.
==22 - Flexbox(part4)==
- flex-grow: 0* | `<number>` có tác dụng là phân bổ khoảng trống còn lại của thằng cho cho các thằng con của nó, muốn chia đều cho mỗi thằng thì truyền cho mỗi thằng giá trị bằng nhau. Áp dụng vd: có 1 component có 3 div, muốn thằng ở giữa hiển thị nội dung chứa hết toàn bộ phần còn lại của thằng cha khi giãn ra, cung cấp khoảng trống còn lại cho thằng ở giữa.
==23 - Flexbox(part5)==
- flex-shrink: 1* | `<number>` nếu các thằng con bên trong có tổng chiều rộng vượt quá container thì nó sẽ cắt thằng con bên trong mỗi thằng một chút, mặc định là 1, nếu cho = 0 thì sẽ không bị cắt đi, mà phần phải cắt sẽ chia cho những thằng còn lại
==24 - Flexbox(part6)==
- order: 0* | `<number>` sẽ làm thay đổi thứ tự hiển thị trên trình duyệt của các thằng con, mặc định sẽ hiển thị từ trái sang phải
- thằng order nhỏ hơn sẽ hiển thị trước, ứng dụng vd có layout ảnh bên trái chữ bên phải, ở dưới thì chữ bên trái ảnh bên phải
==25 - Cùng code Zing MP3 (Part 1)==
- Phân tích -> đặt tên -> code
- Nên code từ trong ra ngoài
- Padding top-bottom sẽ canh theo div bự nhất trong component. Các div con thì padding trái phải.
==26 - Cùng code Zing MP3 (Part 2)==
- Để overlay phủ div cha thì sử dụng height: 100% hoặc kỹ thuật flex-warp,  (flex-column, flex-wrap)
- Để di chuyển có thể sử dụng d:flex, và align-items(flex direction: column) để căn chỉnh hoặc sử dụng position
- box-sizing: border-box thì padding sẽ không làm thay đổi cái size của thằng đang bọc nó.
- loremflickr để tạo ảnh ngẫu nhiên làm demo.
==27 - Cùng code Zing MP3 (Part 3)==
- cho icon vào giữa thì sử dụng d:flex, justify-content: center (cho vào giữa theo trục ngang), align-item: center (cho vào giữa theo trục dọc)
==28 - Position (Part 1)==
- position: static* | relative (nó sẽ không thay đổi nhưng sẽ thay đổi khi truyền vào thuộc tính top-bottom-left-right thì nó sẽ dịch chuyển so với vị trí ban đầu của chính nó mà nó không làm thay đổi những element chung quanh) | fixed | absolute | sticky
==29 - Position (Part 2)==
- giá trị fixed di chuyển tương đối so với cửa sổ trình duyệt, bị tách khỏi normal flow, thường được sử dụng để làm nút back to top
==30 - Position (Part 3)==
- giá trị absolute: thường được dùng để di chuyển vị trí của element hiện tại tương đối so với thằng thằng cha đầu tiên có position relative, thường dùng làm các menu sổ xuống, có thể làm những việc như justify-content hoặc align-item, muốn cho vào giữa thì cho left: 50%, top: 50%, margin-top: -50px; (biết được độ rộng độ cao của thằng con) margin-left:
==31 - Dropdown menu==
- là khi ta trỏ chuột vào sẽ hiện ra sub menu.
- sử dụng thẻ ul>li để tạo menu, trong li tạo 1 list ul>li để làm sub menu, dùng padding để các li item cách xa nhau.
- set position sub menu absolute và chỉnh vị trí đúng như mong muốn, top: 100% (của thằng li cha), sau đó set d:none, khi nào hover thằng li cha thì sẽ d:block ở thằng con
==32 - Float==
- float: left | right float bên trái hoặc bên phải
- clear: left | right | both không muốn thằng nào float bên trái - phải - cả hai bên
- Có 2 div, div trái cho width: 20% div phải cho margin-left: 20% thì lúc nào div phải cũng nằm gọn bên phần còn lại
- div cha sẽ có height bằng height của thằng con ở trong không float, để cho bằng content lớn nhất thì sử dụng kỹ thuật clear fix 
- .wrapper:after { content:''; d:b; clear:both;}
==33 - CSS Selector (Part 2)==
- attribute selector: 
+ a[target]{ } select những thằng có attribute target ở bên trong
+ input[type="text"]{} select những thằng có attribute có kiểu type="text"
- Google css selectors cheatset
==34 - CSS Specificity==
- Trong code CSS giả sử có nhiều selecter trỏ đến 1 thằng, thì trình duyệt sẽ trỏ đến thằng cụ thể nhất (Specificity).
- vd *{ color: green} p{color:red} => thằng p cụ thể hơn nên sẽ được trình duyệt pickup
- Thường khi code lộn xộn thì cần phải quan tâm còn nếu đã chia nhỏ ra thành nhiều component thì ít quan tâm hơn.
- CSS Specifity Caculator
- Cách tính:
+ * : 0 - 0 - 0
+ elements và pseudo-classes: 0 - 0 - 1 ( mỗi element sẽ tăng lên 1 ở trọng số 3)
+ classess - attributes and pseudo-classes: 0 - 1 - 0 (mỗi class sẽ tăng lên 1 ở trọng số 2)
+ IDs: 1 - 0 - 0 (mỗi id sẽ tăng lên 1 ở trọng số 1)
+ style="" : 1 - 0 - 0 - 0 (Trọng số lớn nhất chỉ thua !important)
+ !important: 1 - 0 - 0 - 0 - 0.
- Quy tắc trong css thì hạn chế sử dụng các selecter khác chỉ sử dụng class selecter, khi nào cần thiết lắm thì mới dùng những thằng khác. Tránh việc lỗi nhiều (sửa một chỗ mà chỗ khác hỏng)
==35 - 2D Transform==
- Translate: Dịch chuyển (Dùng nhiều)
- rotate: xoay element
- scale: phóng to thu nhỏ (Dùng nhiều)
- skew: làm biến dạng theo trục x hoặc trục y
- matrix
- Google tympanus.net CaptionHover effects
==36 - Transition==
- Dùng để làm cho các hiệu ứng mượt hơn.
- Có nhiều thuộc tính cần chuyển đổi thì chọn transition: all 0.5s [Short hand];
- google easing.net transition-timing-function
==37 - Media query==
- @media (min-width: 600px) {} Những thiết bị có chiều rộng tối thiểu là 600px => từ 600px trở lên
- @media (max-width: 480px) {} Những thiết bị có chiều rộng tối đa là 480px => từ 480px trở xuống
- Thiết kế theo mobile first là chuẩn hiện nay do số lượng người dùng mobile nhiều hơn desktop
==38 - Grid==
- Tạo ra một lưới, thường dùng để tạo layout tổng.
- đơn vị fr (fraction) là phần
- Google CSS trick css grid
==39 - px vs. em vs. rem==
- 1 em = font-size của cha element hiện tại.
- 1 rem = 2 lần kích thước của thằng root (kích thước trình duyệt). Nằm ở bất cứ ở đâu thì cũng là 32.
- Người dùng trên trình duyệt có thể thay đổi font-size của trình duyệt, khi người dùng thay đổi kích thước font thì px vẫn giữa nguyên nhưng rem thay đổi, khi người dùng thay đổi cỡ chỡ thì padding, margin cũng phải thay đổi theo để bảo toàn design. VD web boostrap. Thường border để px vì không muốn border rộng ra khi font-size của trình duyệt tăng lên.
==40 - Tổng kết và chốt hạ==
- Những kiến thức liên quan đến design điều liên quan đến CSS, mục đích của CSS là biến những Design để chạy trên trình duyệt.


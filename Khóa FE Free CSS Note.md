==Note== 
	- Đối với dạng icon thì nên để 46px
	- Những tag là duy nhất như body thì có thể sử dụng inline code để add bg-img. Tấm hình có nhiều kích thước, cần phải sử dụng các thuộc tính để điều chỉnh cho phù hợp. 
	- Thường sử dụng là bg-size:  mặc định là auto, nếu truyền giá trị vào theo kiểu x y thì sẽ set width và height của bg-image
	- Để ý thuộc tính nào cũng có 2 giá trị initial: giá trị mặc định ban đầu (điện thoại hoặc laptop thường sử dụng cái này), inherit: kế thừa.
	- Cover muốn sử dụng thì phải luôn luôn lớn hơn khu vực chứa, nếu nhỏ hơn khung thì sẽ bị bể, vd div 500px thì kiếm hình 600px-700px. Quan trọng ở khối bọc nó, cần phải xem xét tới tỷ lệ của hình gần tương đương với div bọc.
	- text-align: center, sẽ canh giữa item với thằng cha của nó, chỉ áp dụng với d:block, không áp dụng với img (thẻ inline) do thẻ inline là xài bao nhiêu chiếm bao nhiêu nên nó không biết được vị trí của nó nằm ở đâu mà canh center. trường hợp này thì xài cho thằng div cha thì nó sẽ ra ngoài giữa.
	- tái sử dụng code bằng cách sử dụng selector , selector { code css}
	- thẻ img nên đặt ở trong 1 div, để dễ canh chỉnh do mặc định thẻ img là inline, thẻ inline sẽ không thể set width và height. thẻ img nên set width và height 100%, display: block. để hình phủ đều tất cả các cạnh của div bọc, nhìn đẹp hơn.
- Có 2 hướng là làm web theo SEO, hoặc product
- Cần phân tích SEO cần dùng cái gì làm, product cần sử dụng cái gì để làm. VD SEO thì cần làm cho thằng google, mục tiêu là cho thằng google chấm điểm.
- test speed website trang web vừa tạo sau khoảng 1 tuần deploy web từ thằng google. điểm yêu cầu từ 90 - 100 điểm.
- SEO có nhiều mảng, tuy nhiên về lập trình thì cần: html, css, js , bstrap, jquery, về nguyên lý thì SEO là chơi theo luật chơi của google. google không thích mã nguồn JS chỉ đọc hoàn toàn HTML, cần lập trình thuần không dùng bất kỳ famerwork nào khác. Nhúng thẳng css vào file html luôn. Google có 2 craw là nhện đọc csdl và gấu trúc đọc code html
- Tối ưu code vd như cho các icon vào 1 file sau đó dùng thuộc tính để zoom ra làm thành icon bình thường.
- Product là những web app, SEO thường sử dụng cho mục đích thương mại điện tử, vào xong ra chứ không ở lâu như FB. Cùng lúc đó 1 lượng truy cập user lớn truy cập thì khi đó không thể nào làm thuần được vì không đấp ứng được yêu cầu của người dùng. đó các product không cần đánh vào SEO mà cần nâng cao trải nghiệm người dùng vd như reactjs, vuejs,.. Các framework sẽ gộp code vào 1 file trong khi thông thường truy cập trang nào thì chỉ load trang đó.
- product thường làm sẽ có API, làm web xong thì nhúng qua APP luôn.
==Về phương diện BE==
- backend, có rất nhiều ngôn ngữ, nhưng ở đây chuyên PHP và Laravel. PHP sinh ra để làm web, sử dụng nó vì nó có famerwork Laravel. JAVA thì chỉ có làm APP thôi, chưa có famework để làm web. Python thường sử dụng dữ liệu lớn, big DATA chứ ít ai dùng web vì nó có những thư viện.
- PHP và laravel chỉ là ngôn ngữ dùng để code chung với thằng SQL. PHP thì mình sử dụng mô hình MVC.
- BE là xử lý admin bên trong. BE là làm thuần xử lý dữ liệu.
- Khi làm FE cần phải biết luôn BE, để tổ chức xử lý code. Khi thiết kế FE cần phải biết BE cơ bản.
- Học xong BE sẽ quay về học các famework như VueJS, ReactJS. FS thì tầm từ năm đến sáu tháng, free hoàn toàn. yêu cầu mỗi người dùng 1 ly nước.
==Quản trị mạng==
- Quản lý hosting và server dùng để triển khai thực tế. 
==Điểm danh==
- Vắng 3 ngày nghỉ không lý do báo trước thì sẽ nghỉ luôn.
==Quản lý mạng==
- những web thương mại bình thường sử dụng hosting là đủ rồi, dự án lớn thì cần sử dụng server VPS.
==Cơ bản về website==
- Cơ bản xem web như một căn nhà, trước khi xây nhà phải có nền móng trước, nền móng là nền tảng ban đầu, nếu như không tổ chức không đúng thì sau này sẽ rất là khó làm. Khi xây khung sườn cứng là là HTML sau đó mình sẽ xử lý phần nội thất bên trong bằng CSS, và các sự kiện xử lý trong căn nhà, HTML + CSS + JS sẽ tạo thành một cái website.
==Quản lý mã nguồn==
- Người FE là người đầu tiên làm cho nên cần phải làm mã nguồn chuẩn nhất. Website là một tập hợp của nhiều page, VD: Trang chủ, đăng nhập, đăng ký,.... Trường hợp nào chỉ 1 page thì gọi là landing page hoặc one page. Tất cả page đều đặt cùng cấp ở ngoài hết.
- Đầu tiên phải tạo một folder rỗng, tất cả các file html điều nằm ở trong đây, tiếp tục sẽ là 1 folder img chứa hình ảnh, folder assets chứ những file hỗ trợ như font, các lib,...
- Tổ chức như thế thì khi lên hosting hoặc server thì sẽ không bị sai.
- HTML và CSS không phải là ngôn ngữ lập trình. 2 nguyên tắc khi dùng thẻ HTML, mặc định cơ bản trong HTML thì các thẻ có 2 kiểu hiển thị, 1 là d-block, 2 là kiểu inline là viết nhiêu lấy nhiêu, inline không sử dụng được với width. kiểu block khác với w100%.
- Những thẻ không có đóng là không hiển thị theo kiểu block hoặc inline luôn.
- HTML5 được tổ chức nhiều thẻ ngữ nghĩa hơn vd: nav, menu, footer,...
- thẻ h là thẻ tiêu đề, trong 1 page chỉ được sử dụng duy nhất 1 thẻ h1, còn các thẻ khác thì sử dụng nhiều không sao.
- thẻ a là thẻ link liên kết tới những đường dẫn ngoài trang web có thể sử dụng với các thuộc tính mailto, tel, ...
- p là thẻ đoạn văn.
- thuộc tính của một thẻ: Attribute: Đặc Tính, Property: Thuộc Tính. Định nghĩa chung thì 2 thằng này cũng tương đương là thuộc tính, attribute thực chất là đặc tính còn property là thuộc tính, chỉ có HTML mới có attribute còn mọi thứ trên đời điều là property hết. Về khác nhau thì property nghĩa rộng hơn attribute. vd 1 thẻ tạo có 2 attribute thì chỉ được xài 2 thôi không thể sử dụng hơn, còn property thì rộng hơn, một đối tượng có nhiều property, mình có quyền định nghĩa tạo thêm property. Tổng quát thì một cái có giới hạn còn một cái không có giới hạn
==CSS==
- CSS mà không sử dụng hai cặp thẻ div và thẻ span thì rất khó viết. Đặc tính của hai cặp thẻ này là thẻ vô nghĩa, nó rõng tất cả, thằng div là hiển thị kiểu block, thằng span hiển thị kiểu inline. Người ta tạo 2 thẻ này để chia component, vì nó không có css bên trong, các phần tử bên trong sẽ không bị ảnh hưởng. Thẻ span dùng để css các chi tiết nhỏ bên trong.
- CSS không phải là ngôn ngữ lập trình, có 3 cách viết:
	- Cách 1 là viết bằng attribute (inline style)
	- Cách 2 là viết bằng link (external css), tạo 1 file css nằm trong assets (tất cả các trang nằm ở ngoài còn bao nhiêu thứ điều đặt trong assets), sau đó link đặt trong HTML link tới style.css
	- Cách thứ 3 là style (cặp thẻ internal css)
- Độ ưu tiên của css :
	- ******* !important
	- ****** attr
	- ***** id
	- **** selector càng dài
	- *** last line
- id: trong một html chỉ có một id.
- class: có thể đặt nhiều class.
- Thẻ ul , li phân biệt cấp cha cấp con. ul luôn luôn đi với li. nếu trong li có 1 ul nữa thì nó phân biệt cấp 1 cấp 2.
- css selector: 
	- p : chọn tất cả các thẻ p trong web
	- p.intro: chọn tất cả thẻ p có tên class là intro.
	- p,div: chọn 2 tag
	- div p: 
	- div > p: nó lấy từng bậc, chỉ áp dụng với thẻ p con của div, chỉ lấy 1 cấp con trực tiếp, không ảnh hưởng các cấp con ở sau.
==margin, padding==
- margin là khoảng cách giữa các đối tượng với nhau, padding là khoảng cách từ border vào bên trong box. Tuy nhiên khi xài padding sẽ làm thay đổi độ lớn của box do vậy cần phải giải quyết bằng cách sử dụng box-sizing: border-box;
- box-sizing: border-box là thuộc tính hỗ trợ cho margin và padding.
- thuộc tính này nên áp dụng cho toàn bộ các element của HTML thông qua select refer: * (lấy hết tất cả của các phần tử HTML của mình).
- padding: 0, margin: 0 -> trả lại đồ thị về 0. Khi nào tạo file ra cần phải có sẵn 3 thằng này.
- trường hợp có scroll thì vẫn tính vào thằng body.
- margin: 0 auto, canh giữa đối tượng so với div cha
==Sidebar==
- nguyên tắc tổ chức là ul li và thẻ a.  những cái nào đặt chung các thẻ thì đặt, còn class là setting riêng vd ul li thì có list-type:none.
- Trường hợp cần dàn lên 1 hàng ngang thì sử dụng inline-block cho thẻ li.
- Nếu muốn đẹp thì nên đặt padding thằng a, khi ta chuyển thằng a thành d:block thì khi user click ở bất kỳ đâu điều click vào thẻ a được.
- Quan trọng nhất trong web là cần phải tổ chức, khi làm xong thì làm gì cũng được. 
==line-height==
- nên sử dụng line-height thay vì height vì nó có thể co dãn được, khi font chữ thay đổi thì nó sẽ không bị bể layout.
==Thuộc tính==
- Là cốt lõi bên trong website, những dự án lớn có từ lâu rồi thì đôi khi người ta không update css, chủ yếu sử dụng và update JS. Do đó cần nắm rõ thuộc tính để xử lý web.
	==Float==
		- thằng con float thì thằng cha phải float theo. khi đó thằng con nó mới nằm trên thằng cha, nếu không thằng con sẽ che thằng cha.
		- xem video how to float css, trên youtube.
		- web site chỉ nhìn trên màn hình máy tính là nó mặt phẳng nhưng thực tế browser là khối lập phương. Những gì mình làm sẽ nằm ở bên dưới mặt đáy.
		- khi sử dụng thuộc tính float thì item sẽ nổi lên trên cùng, có 2 thuộc tính là float left và float right, float left là chạy qua bên trái và chạy lên, right thì ngược lại.
		- khi một phần tử nổi lên, thì khi đó nó tạo khoảng trống những thằng phía sau sẽ bị dồn lên chỗ trống đó, do đó để tránh trình trạng vậy thì cần sử dụng thuộc tính clear để tạo ra 1 khoảng trống ảo, những thằng sau sẽ không chen vào chỗ trống đó được. thông thường người ta sử dụng clear:both.
		- Khi float mà không có width với height sẽ bị lỗi. Khi làm dự án không để height vô được. Để height thì web sẽ bị cứng. Tùy trường hợp scroll thì có thể height được do đã xử lý rồi. Còn nếu 4 sản phẩm thì không để height vào được, vì nếu admin thêm 2 dòng chữ sẽ bị bể layout.
	==Note==
	- Khi code web cần phải xác định layout, cần phải nhìn có những layout nào chính, VD trang tiki, có header => layout menu, sidebar left, main.
	- Phải làm được layout, mới code FE và BE được vì BE chia theo layout component.
	- Website hiện tại về phương diện làm thuần rất ít, hộ kinh doanh nhỏ, vừa, lớn hoặc các website nước ngoài thường làm bằng wordpress thì nó mạnh về SEO, muốn làm được thì phải nhìn được layout. Thiết kế thuần hầu như rất ít.
	- FE đưa cho BE layout, BE cắt ra từng file để chạy render theo mô hình MVC.
	==Position==
	- Nó tương tự với float, khi có thuộc tính position thì mặc định nó sẽ trôi nổi, nhưng nó không biết sẽ trôi về bên nào cho nên cần 4 thuộc tính top, left, right, bottom để điều chỉnh vị trí cho nó. 
	- position: relative là thuộc tính dành cho thằng cha. Thực tế ta có thể thấy ai cha ai con nhưng nguyên lý bên trong thì nó không biết ai là cha do đó cần thuộc tính position relative để bật chế độ cha lên cho box cha, box con thì sử dụng thuộc tính position: absolute.
	- Khi đó chúng ta chỉnh vị trí cho thằng con bằng các thuộc tính top, left, right, bottom
	- Mặc định thằng con có absolute sẽ theo thằng cha gần nhất có relative.
	- static thì trôi nổi nhưng không có gì xảy ra cả.
	- fixed: thì mặc định sẽ ổn định lại, xài top, left, right hay gì cũng được, có hoặc không.
	- sticky: ý nghĩa là miếng note dán vô tường, khi dán cần phải xác định vị trí dán ở đâu, nó cần phải thiết lập top, left, right, ..
	- thuộc tính đi chung với position là z-index
	- Thường absolute, sticky, fixed thường bị đè cho nên cần z-index để tránh bị đè.
	- Khi set absolute: sẽ bị mất width với height. Không có height thì một khối không hoàn chỉnh được. Cho nên khi làm cần phải kiểm tra code lại xem nó có ăn height không.
	- Display: block với display: none không sử dụng với position được.
		==Tạo navbar - submenu ==
			- Khi đụng vào text thì chuyển thành inline-block để dễ xử lý với thuộc tính position. Nếu không sẽ rất khó xử lý, inline-block sẽ khóa đứng vị trí, không bị trôi nổi, không ảnh hưởng tới các item khác, do đó rất dễ xử lý.
==Buổi 6: Chia lưới theo kiểu bootrap==
	- Chia cột theo công thức width cột ((100%/(số cột tối đa)*số cột chiếm) - 2%(padding))
	- sử dụng class col-số cột, mỗi cột sẽ có width được tính theo công thức, có float và padding theo tỷ lệ.
	- Col chỉ để nên để dàn layout chứ không để css trên đó.
==Buổi 7 Responsive==
	- Khi làm responsive thì dòng @media giống như if. max-width thì sẽ là responsive từ desktop xuống, min-width thì sẽ là responsive từ mobile lên. Tốt nhất thì nên xài max-width, vì khi code lập trình thì lúc nào cũng code từ desktop trước, do đó sử dụng max-width sẽ thuận tiện hơn. Khi làm việc trong công ty sẽ có màn hình dọc thì lúc đó code mobile first sẽ thuận tiện hơn.
	- 3 quy tắc responsive:
		+ Chỉ responsive theo trình duyệt nào mà google nó yêu cầu, nó có bao nhiêu màn hình thì test nhiêu đó (inspect) hay là test từng thiết bị hỗ trợ. VD Iphone6, ipad, ...
		+ Dòng code responsive luôn luôn lúc nào cũng đặt ở cuối cùng code CSS, để nó lấy được độ ưu tiên.
		+ Phải xác định desktop first hay mobile first. Xác định cột mốc responsive ở vị trí số mấy. Kinh nghiệm thường đặt một dòng max-width 768px.
	- Vẽ dấu cộng bằng before và after thay thế việc đặt tag, nhưng khi chúng ta sử dụng before after thì nó cần phải đi chung với position. Khi sử dụng before, after bắt buộc phải có một thuộc tính là content, chúng ta phải set width và height, nếu không se không hiện gì cả do tính chất của postition.
==Form==
-	những thẻ input, button phải đặt trong thẻ form. có thể dùng div bọc form rồi input và button trong đó. Dù thẻ form là thẻ block, nhưng để tránh vấn đề xử lý của BE đối với các thẻ form.
==Hover==
- Khi hover sẽ không xét tới độ ưu tiên.

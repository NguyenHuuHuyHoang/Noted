==Introduction==
- Cần biết những kiến thức design cơ bản để làm ra những sản phẩm đẹp
==1 - Công cụ và mục tiêu==
- Trong khóa học chỉ hướng dẫn những concept về design.
- Adobe XD, Figma, Google UI Design tools
- Để improve thì xem những web những app đẹp sau đó sẽ design sẽ đẹp hơn
==2 - Pixel==
- là đơn vị nhỏ nhất dùng để đo đạc tranh digital, màn hình thiết bị, máy tính
- Tranh vẽ được cấu tạo từ những thành phần phân tử của tờ giấy chứa màu sắc, vật dụng ngoài đời
- Tranh chụp bằng máy kỹ thuật số thì được cấu tạo từ những điểm ảnh. Pixel - điểm ảnh. Một bức ảnh bao nhiêu pixel sẽ được thể hiện bằng chiều rộng x chiều cao.
- Màn hình máy tính có kích thước thể hiện bằng chiều rộng x chiều cao, được tập hợp từ nhiều điểm ảnh, mỗi điểm ảnh có thể hiện 3 màu là đỏ, xanh lá, xanh dương
==3 - Canvas==
- Canvas ở ngoài đời là khung tranh,  digital canvas là 1 khung ảnh có chiều dài, chiều cao
- Khi design 1 UI thì phải tạo canvas đầu tiên
==4 - RGB colors==
- Màu sắc trong máy tính được mã hóa theo hệ màu RGB, mỗi màu có mức sáng từ 0 - 255 (256 mức 8bit), 0 = tắt, 255 là sáng nhất,  3 màu kết hợp (0,0,0) = đen, (255,255,255) = trắng
- Trong máy tính để viết gọn lại thì có thể viết theo Hex hoặc binary:
- `Hex` #D8D8D8 => 2 ký tự đầu là đỏ, 2 ký tự sau là xanh lá, 2 kí tự cuối cùng là xanh dương, thay vì mã hóa 6 giá trị có thể viết thành 3 giá trị trong trường hợp các kí tự trong cặp giống nhau.
- Nếu 3 giá trị RGB bằng nhau thì sẽ ra màu xám nào đó, sẽ càng đậm nếu giá trị càng nhỏ. 
- 000000 => đen, FFFFFF => trắng
- F00 hoặc FF0000 => đỏ
- 0F0 hoặc 00FF00 => xanh lá
- 00F hoặc 0000FF => xanh dương
==5 - Solid và Gradient fill==
- Solid : Tô một màu duy nhất
- Linear Gradient: Là sự chuyển đổi giữa hai màu khác nhau, tuyến tính theo đường thẳng.
- Radial Gradient: Là sự chuyển đổi giữa hai màu khác nhau từ tâm ra ngoài.
- Angular Gradient : Ít dùng
==6 - Color palettes==
- Cách chọn màu sao cho hợp lý trong design, cách chọn màu quyết định design, không bị chói mắt quá.
- Màu xanh lá cây, màu tím đi với xanh da trời không hợp.
- coolors.co có thể tạo ra các gam màu có thể kết hợp với nhau, sử dụng nút space để tạo
- Google color palette vd colourlovers
==7 - Fonts==
- Font chữ là kiểu hiển thị của một chữ. Có 2 họ font chữ khác nhau là Serif(kiểu cách như Time New Roman) và sans-serif (kiểu chữ đơn giản như Arial). 
- Có hai kiểu font là unicode và non-unicode (không hỗ trợ ký tự tiếng việt. Nhẹ hhơn khi cho trên web)
- dafont.com dùng để down font về và cài đặt lên máy tính và trong các phần mềm design
- google font
- Không nên dùng những font chữ màu mè quá.
==8 - Icons==
- là các biểu tượng hay gặp trong các ứng dụng hoặc trong các trang web mà hay gặp hằng ngày.
- có hai loại icon chính là font chữ và dạng ảnh.
- icon fonts : Font awesome, material design iconic font, icomoon.io, google icon fonts, google how to enter unicode charactes on windows.
- SVG icons: SVG là một kiểu ảnh trong máy tính, được tạo ra từ các phần mềm design : ionicons.com, flaticon.com, materialdesignnicons.com, google svg icons
==9 - Shapes==
- Trong design có nhiều hình khối khác nhau. 
- Hình chữ nhật có 2 dạng, hình chữ nhật vuông 4 góc và hình chữ nhất bo tròn 4 góc
- Hình oval có hình oval và hình tròn.
==10 - Border & Spacing, Margin ==
- Border là đường biên, biên giới. Trường hợp màu nền và màu object trùng nhau thì phải có đường biên để nhận biết được object đó, trường hợp khác nhau thì có thể không có đường biên cũng được. Border có 4 hướng.
- Padding là khoảng cách bên trong giữa vật thể a và vật thể b nào đấy, vd có một cái hộp và bên trong chứa hình tròn, thì lúc nào người ta cũng để một cái khoảng cách giữa hình tròn và border cái hộp thì gọi là padding của cái hộp. Padding có bốn hướng.
- Margin là khoảng cách bên ngoài đường biên của hai object với nhau hay có thể nói là khoảng cách giữa các object trong design.
- Nếu coi màn hình là 1 box thì khoảng cách bên trái và bên phải màn hình là padding của màn hình với các object bên trong
==11 - Layers==
- Layers là lớp trong thiết kế, trong UI design thì bao gồm nhiều layer nằm chồng lên nhau, cái trên sẽ che cái dưới,
==12 - Mask==
- Mask là một kỹ thuật thường dùng để lồng một ảnh vào trong một hình khối nào đó mà hình ảnh không tràn ra ngoài hình khối đó, vd thường sử dụng làm ảnh profile.
- Để làm Mask thì cần 2 layer là hình khối và ảnh, layer hình khối nằm trên ảnh.
==13 - Opacity==
- độ trong suốt hay còn gọi là Transparency, có thể áp dụng cho object hoặc màu, đối với màu thì nó còn có một tham số khác là alpha, hệ màu rgba.
- Chữ trắng nổi bật trên nền tối, chữ tối thì nổi bật trên nền sáng cho nên thường sẽ chèn 1 layer nằm giữa chữ và background sau đó set opacity để vừa đủ tối để dễ đọc chữ nhưng không quá tối để che mất hình nền ở bên dưới thường áp dụng trong trường hợp chữ và hình nền gần như cùng màu (trắng và hình nền sáng).
==14 - Shadow effect==
- cái bóng khi bạn chiếu nguồn sáng vào object nào đấy thì tạo một cái bóng trên cái nền. Tất cả các object trong design đều đổ bóng được.
- x => di chuyển theo trục x, y => di chuyển theo trục y, blur là độ tỏa , spread là độ cứng của bóng. color thì có thể chỉnh alpha thấp để tạo design mềm mại, tạo cảm giác hơi hơi đổ bóng.
==15 - Blur effect==
- Gaussian blur: kiểu bị nhòe
- Motion blur: kiểu chuyển động
- Sử dụng kỹ thuật mask và kĩ thuật blur để tạo float object blur trên nền background, blur chỉ nằm ở trong float object chứ không mờ toàn bộ background.
==16 - Consistency==
- Tính ổn định của hệ thống, trong design được thể hiện ở :
+ Border (color,size)
+ Spacing (padding, margin)
+ Font (size, family) thường sử dụng 1 hoặc 2 họ font chữ, các cỡ chữ trong design sẽ giới hạn ở khoảng 5  6 kích cỡ khác nhau, mỗi kích thước biểu thị 1 ý nghĩa nội dung khác nhau, vd nd không quan trọng thì sẽ chữ nhỏ.
+ Shadow (x,y,blur, spread) đã là shadow thì nên dùng thống nhất như nhau, trừ một số trường hợp đặc biệt, đừng tạo quá nhiều các kiểu shadow khác nhau
+ Color (primary, secondary) 
+ Alignment, các component phải đều thẳng như nhau.
+ Behavior (hover, animate) nên giống nhau.
==17 - Reusability==
- Khả năng tái sử dụng, bằng việc chia các component để tạo nên một design và sau đó tái sử dụng component cho các design khác có sử dụng component tương tự mà không phải tạo lại.
- Khi thay đổi thuộc tính của 1 component thì những component khác cũng thay đổi theo vd thay đổi màu chữ => giữ tính ổn định của design
==18 - Bitmap vs. Vector==
- Bitmap - JPEG , PNG , ảnh PNG thì không có background, còn JPEG thì có background
- Vector - SVG (Scalable vector graphic) là loại ảnh khi phóng to thu nhỏ đều không bị răng cưa.
- Khi zoom ảnh bitmap thì sẽ bị răng cưa, do dữ liệu ảnh lưu trong bộ nhớ ở dưới dạng pixel.
- Khi zoom ảnh vector thì không bị răng cưa, ảnh vẫn mượt do máy tính render lại ảnh, trong ảnh chứa nội dung như một file chứa thông tin để render các hình khối. Trước khi có màn hình retina của apple thì ảnh hiển thị ở tỷ lệ 1 : 1, sau khi có màn hình retina thì tất cả các trang web tạo trước màn hình retina hiển thị rất xấu.
==19 - 12 column grid layout==
- design layout là cách bố trí nội dung bên trong design như thế nào, cách thay đổi layout trong design sẽ làm cho design bớt nhạt. trong web design có kiểu thiết 12 cột cho desktop.
- những giao diện xây dựng trên nền boostrap thì sử dụng 12 cột grid layout. sử dụng plugin của chorme Boostrap gird overlay để hiển thị ra layout của trang web có sử dụng layout 12 cột.
- offset trong boostrap: theo mặc định các cột dính vào nhau mà không để lại bất kỳ khoảng trống nào về phía bên trái, và chúng ta vẫn thừa khoảng trống về phía bên phải. Để tạo ra lề về bên trái của cột chúng ta có thể sử dụng các class offset. Áp dụng một class .col-md-offset-Number cho bất kỳ cột sẽ di chuyển nó sang bên phải. Offset có thể sử dụng để canh giữa các cột
- Một design nhiều chữ quá thì giới hạn số chữ trên 1 dòng, khoảng 15 từ trở lại trên một dòng.
==20 - Responsive design==
- là thuật ngữ sinh ra khoảng trên dưới chục năm khi mà các thiết bị di động được sử dụng phổ biến, trước khi có responsive thì trên mobile muốn đọc nội dung trên các web thì phải zoom lên
- là viết code css, khi mở web trên đt hay ipad hay máy tính đều có thể xem rõ nội dung trên đó mà không phải zoom lên, để làm được việc đó thì phải có những thay đổi về nội dung và layout
- bootstrap được làm ra để viết code responsive dễ dàng hơn
==21 - Next Steps==
+ Share your designs: export design ra dưới dạng file design, ảnh jpeg hoặc png, khi làm việc trong team thì designer làm việc với cả dev, các làm việc theo nhiều cách khác nhau, một trong đó là sử dụng InvisionApp.com
+ For Sketch user: learn Craft plugin to update design to InvisionApp.com
+ Sync to InvisionApp
+ Follow good designers on Instagram #ui, Behance, Dribble
+ See real life examples at themeforest.net
+ Learn more at goodui.org
+ practice, practice, and practice
+ find a design that you live -> use design tools to make a copy
`Design is not just what it looks like and how it feels. Design is how it works`
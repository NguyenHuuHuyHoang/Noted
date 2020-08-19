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
- overflow: hidden: ẩn nội dung
- overflow: auto: chỉ tạo thanh scroll ở vùng tràn ra ngoài.
- overflow: visible (default): phần tràn ra ngoài vùng chứa vẫn sẽ được hiển thị.
==resize==
- cho phép người dùng có thể thay đổi kích thước thẻ div cả chiều cao và chiều dọc.
- resize: both; overflow: auto;
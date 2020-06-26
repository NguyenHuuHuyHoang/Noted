==0- Chuẩn bị==
- React dùng trong một số trường hợp nhất định không phải lúc nào cũng sử dụng react.
- Học xong làm được gì có thể dùng React để code front-end cho bất cứ web app nào.
- Có thể tự học React Native -> build app cho mobile
- Tự học được các SPA framework khác như Angular, Vue.
==1 - Single Page App==
- Trước khi SPA ra đời thì thường viết web như trong ExpressJS hoặc là dùng PHP, cách hoạt động là mỗi khi truy cập một trang web, hoặc chuyển từ page này sang page khác thì client sẽ gửi resquest lên server và server sẽ trả về toàn bộ code html cho client. Như thế việc xử lý chủ yếu bên server, mỗi lần resquest sever thì sẽ xóa dữ liệu và lấy dữ liệu mới từ server gửi về để hiển thị.
- Các đây khoảng chục năm thì có những framework được viết bằng JS giúp cho việc render ở client giúp tăng trải nghiệm người dùng vì load web rất là nhanh, tất cả các việc render xử lý ở client, theo cách truyền thống thì mạng chậm thì phải chờ một lúc, render ở client thì dữ liệu trả về ở server sẽ ít hơn (phần lớn, ở request đầu tiên sẽ mất thời gian). Mỗi lần click vào đường link thì đường link thay đổi nhưng dữ liệu không thay đổi.
- REACT là một tool giúp build SPA, REACT không phải là cái đầu tiên. Angular ra đời -> reactJS -> vue, trước angular còn có nhiều thằng khác như backbone, ember
- REACT được Facebook phát triển.
==2 - Cài đặt==
- Cách setup React bằng CDN Link. 
- tối thiểu cần phải có là 1 div id="root" trong thẻ body, copy 2 link cnd vào thẻ body.
- tạo script JS,  tạo element bằng React.createElement('div', null (không có thuộc tính), 'nội dung').
- dom tới root bằng documet.getElementById('root');
- render element mới vừa tạo vào root bằng ReactDOM.render(element cần render, root);
==3 - React.createElement==
- Khi lập trình thì code app thì chia nhỏ ra thành nhiều component.
- React.createElement dùng React API tạo ra các react Element.
- nhận vào 1, 2 hoặc nhiều tham số, tham số 1 là kiểu element HTML, tham số thứ 2 là một object chứa props (thuộc tính) vd className, src,... , nếu không có gì thì để null, tham số thứ 3 là children (các thằng con của nó), nếu không có con thì sẽ không ghi tham số thứ 3.
- React sẽ tạo ra các React component sau đó ReactDOM sẽ map 1 : 1 sang HTML DOM tương ứng. Xây dựng các thư viện component xong lắp ráp lại.
==4 - JSX==
- Babeljs.io : Chuyển code JSX thành JS, dùng để dịch các chuẩn JS mới hơn về chuẩn cũ hơn.
- Để sử dụng code JSX thì cần phải add link cdn của Babel vào html và  thêm type="text/babel" vào tag script chứa code.
- Babel sẽ không chạy đoạn code trong script mà sẽ biên dịch code thành code reactjs và bỏ vào một tag script do nó tạo đặt ở trên cùng thẻ HTML.
==5 - Create React App==
- công cụ create react app. Nếu đang sử dụng node 8 hoặc 10 -> npx create-react-app 3-create-react-app <- Tên project sẽ tạo

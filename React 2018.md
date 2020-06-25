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
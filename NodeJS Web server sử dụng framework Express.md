==1 - Introduce ==
- Express JS là một công cụ rất là mạnh để làm Web server, JS là ngôn ngữ làm trên framework này, framework này chỉ chạy trên nodejs. Là một dynamic webserver
- Static web server dễ dàng để xây dựng, rẻ để host, những nội dung fixed, là những file tĩnh nằm trên server. Server <=> client
- Dynamic web server trả về nhiều hơn một file, tương tác với DB, client có thể yêu cầu file thì nó có thể trả file được, nó nhận được các tham số đầu vào của client và trả về theo một logic nào đó, hơi khó để xây dựng, tốn chi phí hơn static để host, dễ dàng chỉnh sửa nội dung bởi người chủ. Sever <=> DB <=> client
- Setup Express server. npm install express --save
- express().get('/', callback function nhận vào hai tham số là request và response), request là những gì client gửi lên, response là server trả về.
==2 - Template engines==
- SPA (single page application): Nội dung được rendered ở phía client, không reloading trang, giao tiếp với data thông qua một số JSON API. Ở lần request đầu tiên thì server trả về file HTML kèm code JS trong đó (các file HTML rất là nhỏ, chỉ chứa thẻ div thôi, các AJAX sẽ render các thẻ div đó), trong JS đó chứa code AJAX, khi trình duyệt chạy sẽ kích hoạt AJAX request server lấy data về và render lên lại file HTML.
- MPA (multi pages application): Là kiểu truyền thống, code nhanh hơn giảm thời gian rất là nhiều.
- Nếu một app nhỏ mà không cần phải đòi hỏi người dùng cần trải nghiệm cực kỳ tốt, không cần dùng SPA. Tuy nhiên nếu app logic phức tạp ở phía FE nhiều thì sử dụng SPA
- Template engines gồm có các loại chính: Pug (jade) (popular), Mustache, ejs

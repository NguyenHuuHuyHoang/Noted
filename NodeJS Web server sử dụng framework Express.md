==1 - Introduce ==
- Express JS là một công cụ rất là mạnh để làm Web server, JS là ngôn ngữ làm trên framework này, framework này chỉ chạy trên nodejs. Là một dynamic webserver
- Static web server dễ dàng để xây dựng, rẻ để host, những nội dung fixed, là những file tĩnh nằm trên server. Server <=> client
- Dynamic web server trả về nhiều hơn một file, tương tác với DB, client có thể yêu cầu file thì nó có thể trả file được, nó nhận được các tham số đầu vào của client và trả về theo một logic nào đó, hơi khó để xây dựng, tốn chi phí hơn static để host, dễ dàng chỉnh sửa nội dung bởi người chủ. Sever <=> DB <=> client
- Setup Express server. npm install express --save
- express().get('/', callback function nhận vào hai tham số là request và response), request là những gì client gửi lên, response là server trả về. Thường kết hợp với res.render(view) để render pub thành page mà client yêu cầu rồi trả về client.
==2 - Template engines==
- Template Engines là công cụ giúp tách mã HTML thành các phần nhỏ hơn mà chúng ta có thể sử dụng lại trên nhiều tập tin HTML
- SPA (single page application): Nội dung được rendered ở phía client, không reloading trang, giao tiếp với data thông qua một số JSON API. Ở lần request đầu tiên thì server trả về file HTML kèm code JS trong đó (các file HTML rất là nhỏ, chỉ chứa thẻ div thôi, các AJAX sẽ render các thẻ div đó), trong JS đó chứa code AJAX, khi trình duyệt chạy sẽ kích hoạt AJAX request server lấy data về và render lên lại file HTML.
- MPA (multi pages application): Là kiểu truyền thống, code nhanh hơn giảm thời gian rất là nhiều.
- Nếu một app nhỏ mà không cần phải đòi hỏi người dùng cần trải nghiệm cực kỳ tốt, không cần dùng SPA. Tuy nhiên nếu app logic phức tạp ở phía FE nhiều thì sử dụng SPA
- Template engines gồm có các loại chính: Pug (jade) (popular), Mustache, ejs
- Pug là một ngôn ngữ tiền xử lý HTML như SCSS cho CSS, nó giúp tái sử dụng code HTML.
==3 - Query parameters==
- req.query của express(). https://zingmp3.vn/tim-kiem/index.html?q=lam%20truong  `?q=lam%20truong` là query được gửi lên server từ input có name = q, nếu có & thì nó là dữ liệu gửi kèm theo query nhằm thông báo những tùy chọn kèm theo kết quả trả về (filter)
- query là một phương thức của request nhằm bóc tách dữ liệu gửi từ client lên server để server xử lý.
==4 - POST Method==
- sử dụng app.post(view, callback function trả về res, req). trường hợp ở client sử dụng form có method POST để send req lên server theo view của app.post thì nó sẽ bắt lấy thông tin và trả về callback function.
- req.body là phương thức để get req body của client gửi lên. muốn sử dụng được phương thức này phải cài đặt, require body-parser và kèm theo các dòng code:
- `app.use(bodyParser.json());
app.use(bodyParser.urlencoded({ extended: true}));`
- res.redirect(view) sẽ chuyển trang về view.
==Bài 5 - nodemon==
- Dùng để restart server tự động, khi thấy code js trong project thay đổi.
- npm i --save-dev nodemon -> cài vào project, --save-dev là chỉ dùng khi đang phát triển dự án, chứ đưa lên server thì sẽ không sử dụng nữa
- npm i -g nodemon cài và sử dụng như một command.
- Thêm vào script package.json dòng "start": "nodemon index.js" => chạy bằng npm start, nếu có bất cứ sự thay đổi nào trong code js thì sẽ tự restart lại trình duyệt.
- Trường hợp muốn bỏ qua sự thay đổi file nào đó vd db.json thì tạo file nodemon.json, thêm vào {"ignore": ["db.json"]}
==Bài 6 - Tích hợp database (lowdb)==
- Khi gửi dữ liệu từ client lên server để lưu lại dữ liệu thì gặp vấn đề khi server khởi động lại thì sẽ mất hết dữ liệu, cho nên cần phải sử dụng một db nào đó để lưu trữ dữ liệu.
- DB có vô số loại, trong bài này sẽ sử dụng db được build từ js và làm việc được với file của máy tính, chủ yếu là dùng demo, test là chính.
- npm i lowdb --save. 
- var low = require('lowdb');
- var FileSync = require('lowdb/adapters/FileSync'); //Thường sử dụng ASync vì sẽ ảnh hưởng tới hiệu năng, blocking && non-blocking
- var adapter = new FileSync('db.json'); //Lưu dữ liệu trong file db.json trong cùng thư mục
- db = low(adapter); //Tạo một object mới có tên là db để truy xuất dữ liệu.
- db.defaults({ users: [] }) //Setting file mặc định trong trường hợp chưa có file nào.
    .write();
- users: db.get('users').value() //db.get(key) sẽ trả về value đã lưu của key đó
- db.get('users').push(req.body).write(); ghi dữ liệu nhận được từ client vào file
==7 - View user==
- Hiển thị thông tin của một user nào đấy trong db của mình. Trong bất kỳ db nào cũng có một id duy nhất để nhận dạng nó, chúng ta sẽ sử dụng id tạo link view user.
- ExpressJS ở phần routing có các kiểu pattern khác nhau để định nghĩa route của mình. VD app.get('/users/:id') => bất cứ khi nào có get request /users/[cái gì đó] thì sẽ chạy callback, [cái gì đó] sẽ được lưu vào một cái biến nằm trong req.params.id; (Route Parameter : khác với query parameter ?)
- Thông thường db sẽ tạo id, tuy nhiên trong một số trường hợp mình có thể tự tạo id cho riêng mình. shortid package tạo ra một chuỗi id ngẫu nhiên.
- Kết quả biết được dynamic routing và truyền params
==8 - Express Router==
- CRUD = Create(Tạo) Retrieve(Xem) Update(Cập nhật) Delete(Xóa) là những chức năng chính trong một cái app kiểu như app quản lý
- Điều hướng đường dẫn URL với Express Router, chia nhỏ chương trình ra.
- Định nghĩa 1 Folder routers, bên trong chứ user.router.js file này sẽ chứa toàn bộ những get, post bắt đầu bằng user, sau đó module.exports file router ra, trong file index.js chính sẽ require vào, sử dụng app.use('/users', userRoute); để tìm những đường link nào bắt đầu bằng users thì sẽ nhảy vào file router.js để tìm
==9 - Controller (MVC)==
- Thông thường trong các Routers chỉ chứ file route còn các logic xử lý sẽ tách riêng ra, những cái liên quan request người dùng, trả ra như thế nào thì xử lý riêng.
- Model - View(Là những file template) - Controller
- Những callback function của Router sẽ tách riêng ra thành riêng một file user.controller.js, sau đó sẽ export file đó ra thành một module, những function trong file là một key, bên route sẽ gọi vào để sử dụng.
==10 - Template layout==
- Thêm các thư viện css vào trang của mình để đẹp hơn. Thường thì thẻ link bs thường để ở thẻ HEAD.
- Trong pub có extends, chúng ta cần tạo file layout sẵn và extends ở các file cần thiết vd layout 2 cột, layout 3 cột, layout 1 cột.
- Trong 1 file chỉ được extends 1 lần và trong file được extends có thể chứa nhiều block khác nhau.
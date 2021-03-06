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
==11 - Static files==
- Thiết lập đường dẫn tĩnh cho files như: images, css files, fonts, js files, other documents
- Đầu tiên phải thiết lập route đến đường dẫn chứa file, sử dụng app.use(express.static('public')); //Khai báo sau app. Sau đó sử dụng đường dẫn tuyệt đối dưới dạng /folder con của public/file
- Bài tập là sử dụng express để quản lý cái gì đó.
==12 - Server-side validation (Login)==
- Khi cho lấy thông tin từ người dùng thì phải validate để tránh trường hợp người dùng thêm những dữ liệu không đúng.
- Kiểm tra tạo 1 array rỗng để chứa các error, sau khi check hết, nếu array.length > 0 thì render lại trang create, truyền vào array errors để hiện thông báo alert,   trả kèm theo req.body để không làm mất giá trị đã input, sau đó dùng toán tử 3 ngôi để kiểm tra, nếu biến không có thì đặt input rỗng
==13 - Middleware==
- Là một function nhận vào ba tham số, function(req, res, next), có thể dùng nhiều middleware cho một route
- Theo thứ tự thằng nào khai báo trước thì được dùng trước. Turờng hợp thằng middleware trước sử dụng res.send thì sẽ kết thúc luồng chạy những thằng ở sau sẽ không được chạy.
- Mục đích: tách riêng logic ra vd như: validation ra một file, không thực hiện validation trong controler chính. Đặt module.exports.postCreate (vì validation xong sẽ trả data về postCreate). Sau khi thực hiện hết logic nếu chưa trả res thì phải có next() nếu không trang sẽ reload mãi mãi tới khi hết timeout sẽ báo lỗi.
- Để sử dụng thì require vào trang route.
- Khi client gửi 1 req thì sẽ đi qua nhiều middleware khác nhau và cuối cùng sẽ tới thằng xử lý logic chính sau đó trả về thông qua res.render
- có thể sử dụng res.locals để chuyển giá trị từ middleware trước cho middleware sau.
==14 - Cookie==
- Là một khái niệm trong lập trình web nói chung, không riêng gì bất cứ ngôn ngữ gì.
- Cách thức hoạt động: Ở bất kỳ req mà client gửi lên, server có thể trả về cookie hoặc không (Set-cookie: giá trị mà mình muốn set). Client nhận được res có chứa set-cookie thì nó sẽ lưu lại ở trình duyệt, sau đấy từ các lần gửi tiếp theo nó sẽ gửi kèm theo cookie nằm trên trình duyệt, khi nào server bảo xóa đi thì nó xóa đi.
- Nếu client đã có cookie thì khi gửi req sẽ có kèm cookie, để bắt được thì sử dụng req.cookie, để đọc được cookie thì phải sử dụng một middleware là cookie-parser, sau đó require nó và sử dụng app.use(cookieParser()); 
- Ứng dụng khi login vào trang thì server sẽ gửi 1 cookie là session phiên làm việc của người dùng đó, khi logout sẽ gửi lệnh để xóa đi, thường server sẽ gửi cookie có một thời gian tồn tại xác định để tránh tình trạng bị hack. Có thể lưu cookie ở nhiều vị trí khác nhau như ổ đĩa, ram, db,.... thường thì sẽ lưu ở db để khi client gửi req lên những server khác nhau thì vẫn truy cập được.
==15 - Authentication (Login)==
- Tạo controller auth, page login, require route vào index.js, sử dụng app.use để link tới autoRoute đã require ở trên.
- Trong db sẽ chứa object có key là email và password, nếu đúng email và password sẽ trả về 1 cái gì đó thông qua POST req.
- Để người dùng truy cập bất cứ trang nào mà chưa login thì sẽ redirect sang trang login bằng cách tạo một middleware trước tất cả các middleware, nó làm nhiệm vụ kiểm tra req gửi lên có cookie hay không, cái cookie này sẽ do thằng postLogin thêm vào trước khi redirect về trang users.
- Trường hợp muốn đặt protect cho toàn bộ route users thì ở index.js require authMiddleware, sau đó đặt vào app.use('/users').
- Tất cả các thứ bên phía browser đều có thể sửa đổi bởi người dùng, trong trường hợp đoán được userId của người khác thì có thể sử dụng để đăng nhập vào.
- Không bao giờ lưu trữ mật khẩu trong db dưới dạng RAW, có thể đọc được, do không bảo mật.
==16- md5==
- Mã hóa password của người dùng thì chẳng may bị hack thì lộ db nhưng không lộ mật khẩu của người dùng.
- MD5 là một hàm mã hóa, nó biến đổi mật khẩu thành 1 chuỗi ký tự nào đấy (Hash).
- MD5 được dùng nhiều trong quá khứ giờ thì ít vì khi người dùng nhập mật khẩu vào thì tối đa khoảng 10 - 20 ký tự là max, giả sử có 1 hacker cho máy tính chạy tạo hash từ 0 -> FFFFFFFFFFF thì họ sẽ cho ra chuỗi rất nhiều mk khác nhau sau đó cho chạy md5 -> được tất cả mật khẩu, do hàm md5 tốc độ xử lý nhanh nên việc chạy như vậy là dễ dàng, do đó từ mk thì người ta có thể dịch ngược mã rất dễ dàng.
- MD5 rainbow table -> những người đã làm và lưu trữ vào db, từ db đó có thể check mk mạnh hay yếu
==17 - Signed Cookie==
- Khi server gửi cookie về thì sẽ gửi kèm 1 signature để kiểm tra tính hợp lệ của cookie. nếu cookie thay đổi thì signature sẽ thay đổi theo.
- res.cookie nhận vào tối đa 3 tham số, tham số thứ 3 có option signed để thêm signature vào trong cookie, để làm được việc này đòi hỏi cookie-parser phải chứ chuỗi secret. Khi sử dụng signed cookie thì ở đọc cookie phải chuyển thành signedCookies
==18 - Environment Variables==
- biến môi trường: trong thực tế thì khi dev trên máy hoặc deploy sử dụng những biến khác nhau vd đường dẫn lưu dữ liệu, db ... sẽ thay đổi giữa các môi trường làm việc vì vậy sử dụng environment variables. Trong app sẽ tham chiếu đến các biến đấy.
- trong nodejs thì biến môi trường được lưu vào process.env (là một obj chứa key:value, nếu chúng ta truyền vào cái gì thì key:value là cái đó), để thêm biến vào trước khi chạy thì ở teriminal:
- Cách 1: SESSION_SECRET=1223:123 APP_SECRET=dsadasfasdas npm start
- Cách 2: dùng dotenv npm, và tạo 1 file .env vào chương trình, không commit folder .env (SECRET KEY hoặc SECRET API) lên github. Trong file .env chứ các cặp Key=value
==19 - Debug nodejs app ==
- Nếu dùng nodemon thì có thể debug bằng cách sửa thông tin nodemon trong package.json bằng cách thêm --inspect ở  giữa nodemon và index.js sau đó npm start để chạy app, sử dụng chorme để debug
==20 - Pagination (Phân trang)==
- trong lập trình web sử dụng rất là nhiều hoặc ứng dụng show ra rất nhiều sản phẩm. Thường đường link có dạng /products?page=2, nếu có 1 array n sản phẩm, nếu muốn hiển thị x sản phẩm 1 trang thì begin = (n-1)*x, end=(n-1)*x + x, sử dụng method slice => items = array.slice(begin, end).
- Để tạo dữ liệu nhanh chóng sử dụng mockaroo.com
- lowdb được xây dựng trên thư viện lodash, do đó nó có phương thức drop(n) bỏ n phần tử của mảng, take(n) lấy ra n phần tử của mảng.
- tạo pagination: Trường hợp người dùng input vào nếu là trang 1 thì chạy lặp 1 -> max pages per pagination, nếu là trang maxPage thì sẽ lặp từ 0 -> 2 và dùng page - giá trị lặp. nếu khác 2 điều kiện trên sẽ lặp từ -1 -> 1 nếu 3 page per pagination.
==21 - File Upload==
- Data được gửi lên server dưới dạng test thông qua method POST, mặc định form không gửi dữ liệu lên server dưới dạng boudnary mà gửi theo dạng text, vì vậy input file sẽ có giá trị là tên của file đính kèm. Muốn upload file thì phải chuyển form sang một dạng encoding khác là enctype="multipart/form-data" (thuộc tính của form) điều này là bắt buộc, method bắt buộc phải là POST
- bodyParser không hỗ trợ multipart/form-data nên sẽ gặp lỗi nếu input file nằm chung với input text. Do đó cần sử dụng middleware multer.
- Trong route cần require multer sau đó tạo một biến chứa đường dẫn thư mục sẽ chứa file var upload = multer({dest: './public/uploads/'})
- Trong phần route post cần phải add middleware upload.single('name input file') trước các middleware khác. Dữ liệu về file sẽ được lưu trong req.file, còn các thông tin khác dạng text của form sẽ được lưu trong req.body
- req.file.path => trả về đường dẫn của file, reg.file.filename => trả  về tên file đã được lưu trong uploads.
==22 - Session==
- Session là một phiên làm việc của người dùng, nó dùng cookie.
- Trên thực tế, những app mua bán hàng thì người dùng không đăng nhập vẫn lưu dữ liệu mua hàng -> sử dụng session.
==23 - CSRF Attack==
- Cross-site request forgery.
- Thường tấn công vào trang chuyển tiền hay những trang mà thay đổi dữ liệu qua form hoặc đường link
- nạn nhân login vào tk khoản, trong app đó có chức năng chuyển tiền, attacker sẽ giả mạo cái form đấy ở trên trang web của nó và sẽ gửi cho nạn nhân link tới trang web của nó, khi ấn vào thì vô hình là không biết và submit cái form ẩn đó và attacker sẽ lợi dụng cookie trên máy nạn nhân để có thể submit form đó.
- Để tránh thì thêm vào form 1 token, nếu gửi đi phải có token nếu không có thì không cho gửi đi. Token dưới dạng signed, sử dụng phương thức để mã hóa xem token có hợp lệ hay không.
- sử dụng npm csurf, nó là một hàm trả về 1 middleware, khi sử dụng thì sẽ tạo một method mới cho req. là req.csfrToken() trả về một string nào đấy dùng để tạo token. Trong form post thêm 1 input type="hidden" name ="_csrf", value=csrfToken , cho phép sử dụng cookie để gửi token cùng. app.use(csurf({cookie: true})), phải đặt sau cookie-parser trong app.use
- Để chèn token vào form thì phải gửi token từ controller ra form
==24 - Install MongoDB==
- Cài MongoDB Server, bản community server là bản miễn phí
- show databases để xem trên terminal hoặc sử dụng robomongodb để xem trên giao diện
- Mặc định server nằm ở trên localhost:27017
- Trong mongoDB có các collection tương ứng với mỗi array , document tương ứng object
- Mongo không sử dụng id mà tự tạo 1 field _id ra
- terminal : mongo -> truy cập mongo, show databases -> xem tất cả db đang có, use [tên db] -> chuyển sang db, show collections -> xem tất cả collection đang có, db.[tên collections].find() -> lấy tất cả dữ liệu trong collection
==25 - Giới thiệu Mongoose==
- Tutorialspoint.com để học mongodb
- sử dụng mongoose npm để tương tác với mongodb dễ hơn.  var mongoose = require('mongoose') -> mongoose.connect('mongodb://[host]/[db]'). Địa chỉ mongodb nên đặt trong file .env để đảm bảo tính bảo mật của server db.
- mongoose là một thư viện dùng để object modeling, chuyển js object sang các collection, document trong db. Đó đó để sử dụng phải tạo một cái schema sau đó tạo model. tạo một thư mục models -> tạo file model vd user.model.js, phải require mongoose vào để dùng các class bên trong -> tạo schema: var userSchema = new mongoose.Schema(Object chứa các key và value vd email:String, password: String, name: String, avatar: String, phone: String), schema dùng để khai báo các field có trong object -> khai báo model var User = mongoose.model('User', userSchema, 'users') trường hợp muốn truyền vào collections nào thì truyền vào ở tham số thứ 3 -> module.exports = User.
- Sau đó có thể dùng User ở các chỗ khác. require module, sử dụng Model.find() để truy xuất dữ liệu, nó trả về 1 promise nên phải dùng .then hoặc đặt trong một async - await function.
- Model.find() trả về mảng tất cả các document của collection Model, nếu cần tìm kiếm thì cần phải truyền vào find() một object có giá trị { key (field cần tìm) : value (giá trị cần tìm)} => trả ra một mảng các object có giá trị phù hợp với giá trị cần tìm. Trường hợp cần tìm theo _id thì sử dụng findById(id cần tìm) sẽ trả ra 1 obj (do id là duy nhất)
- Để lưu giá trị vào mongoDB thì sử dụng new Model.save({object các giá trị cần ghi}) hoặc tạo một document mới var product = await Product.create(req.body);
==HTTP API==
- HTTP là một giao thức qua internet, API là Application programming interface là giao tiếp giữa ứng dụng với ứng dụng, GUI là Graphic User Interface - giao diện đồ họa người dùng, giao tiếp giữa người dùng với ứng dụng, CLI là Command line interface giao diện dòng lệnh.
- HTTP API sẽ cung cấp cho các ứng dụng khác một số endpoint, các endpoint này không trả về http mà trả về dữ liệu vì HTTP chỉ dùng cho browser còn các mobile app hay hệ thống IOT thì không quan tâm đến HTTP mà quan tâm đến dữ liệu mà thôi, có thể trả về 2 dạng chính XML và JSON (ajax)
- Công cụ postman giúp test các API.
- Về thiết lập thì tương tự như bt, nhưng thay về trả về res.render thì trả về res.json(object hoặc array) => trả về json của dữ liệu
==REST API==
- Cũng sử dụng giao thức http như http api, có một số quy chuẩn như:
+ GET /products -> Get all products []
+ GET /products/:id -> Get one product {}
+ POST /products -> Create product
+ PUT /products/:id -> Replace/Create product nếu không có
+ PATCH /products/:id -> Update product
+ DELETE /products/:id -> Delete a product
- REST API không phải là thư viện mà là một quy chuẩn. Khi viết một REST API thì sẽ không dùng cookie để authentication mà sẽ dùng một authentication header (JWT) nào đấy có cái name là authentication, tùy vào kiểu authentication mà có mã khác nhau.
- products được xem như là một Resource (thường là số nhiều), thường kèm theo các query parameter để phân trang, filter ...
==28 - Error Handling==
- Là kỹ thuật bắt lỗi, sử dụng throw new Error('Thông báo lỗi'), nếu gặp lỗi thì sẽ quăng thông báo lỗi ra và phần mềm sẽ dừng lại. sử dụng try {phương thức có thể xảy ra lỗi} - catch (error) {console.log(error)}để bắt lỗi nhưng phần mềm vẫn tiếp tục chạy, sau đó kết quả là vẫn nhận được lỗi để biết nhưng phần mềm không bị gián đoạn.
- Cách 2 thì sử dụng trong Promise(function(resolve, reject)) {reject(new Error('Promise error'))} reject().catch(function(error){console.log('Has error', error.message)});
- try { toàn bộ code nghi có lỗi } catch (error) { next(error)} thằng next sẽ gửi sang thằng middleware error handler (mặc định có) => khi chạy hết tới cuối chương trình thì sẽ hiển thị ra lỗi.
==29 - Deploy to Heroku==
- Trước khi deploy lên Heroku :
+ Sửa biến port sử dụng env
+ Kiểm tra lại package.json
+ Không lưu uploaded files trên Heroku (có thể dùng dịch vụ khác để up ảnh lên VD Cloudinary do cung cấp các API để chúng ta có thể upload lên và miễn phí nhiều)
+ Thay thế code khi sử dụng lowdb, dùng MongoDB
+ Heroku chỉ lưu source code
- firebase hosting chỉ lưu được các code tĩnh html, css , js còn code server side thì phải deploy lên các dịch vụ khác, heroku là một thằng miễn phí, không cần phải quản lý server.
- Để sử dụng heroku git thì phải cài heroku CLI => sau khi push project lên heroku
- heroku logs để xem tình trạng server, cần phải điều chỉnh một số thứ
- nodemon là khi sử dụng dev mới được cài đặt còn trên server sẽ không có nên phải chỉnh sửa lại "dev" -> chạy có nodemon, "start" -> chạy node index.js bình thường. sau này để chạy trên máy bản thân thì sử dụng npm run dev, start là câu lệnh đặc biệt, nên không cần phải run start
- trên server sẽ không có MONGO_URL -> vào mục resources -> thêm add-on mlab MongoDB (cần phải nhập tài khoản thẻ tín dụng vào > account settings)
- Vào settings -> config vars nó chính là env variables, tất cả cái biến ở trong đây sẽ được dùng trong process.env -> thêm biến SECRET, nên để khác với biến đặt trên local để không bị đoán.
- Khi start server ở trên heroku, thì heroku sẽ tạo ra một biến môi trường tên là PORT, var port = process.env.PORT || 3000 ; nếu trên local không có biến PORT thì sẽ sử dụng 3000
- Gói miễn phí của heroku chỉ cho một ngày chạy xx tiếng không chạy 24/24, nếu không có res nào lên server trong vòng bao nhiêu lâu thì nó sẽ chuyển sang trạng thái nghỉ, nếu trong trạng thái nghỉ mà nhận được res thì phải mất 1x giây để start server, do đó chỉ dùng thích hợp cho test thôi.
==NOTE==
- có thể học các framework của các ngôn ngữ khác như codeigniter hoặc laravel của PHP, Play framework của Java, Python thì có django
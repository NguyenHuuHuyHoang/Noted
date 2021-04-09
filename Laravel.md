==Nội dung==
- laravel, composer
- Để tạo project mới có 2 cách
	- nếu đã cài global laravel: composer global require laravel/installer thì chỉ cần tại thư mục cần chứa project sử dụng laravel new [tên project]
	- nếu chưa cài thì sử dụng lệnh composer create-project --prefer-dist laravel/laravel blog "5.8.*"
- vendor: là thư mục chứa toàn bộ code của thư viện.
- Quản lý DB: navicat, mysql workbench, emma, datagrip
- MVC:
	- Model: thể hiện của những vật thể, thực thể trong thực tế
	- View: hiển thị
	- Controller: Xử lý
- artisan: công cụ của laravel được viết bằng PHP
	+ php artisan  serve => start webserver, start app laravel lên
- Blade template
- Eloquent model
- Route
- Auth, middleware
-  Auth sử dụng lệnh : php artisan make:auth để cài đặt Auth (bản 5.8)
- Migration, seeder
- Migration
- Cach
- Schedule
- .env: environment là file cấu hình, bất cứ khi nào sửa .env thì cần phải chạy clear config => cache lại bằng lệnh php artisan config:cache
- php artisan preset react để sử dụng ui react với laravel
==Application key==
- Mỗi ứng dụng đều có 1 key, dùng để mã hóa, nó giúp cho app chúng ta là riêng biệt, khi deploy lên production thì sẽ sử dụng 1 key khác, server test là 1 key khác.
- 
==Route==
- Route là đường dẫn url, từ đường dẫn url sẽ thực hiện công việc tương ứng, hay nói cách khác là phân tích đường dẫn url và trỏ tới controller tương ứng.
- Route cấu trúc Route::get('home/laravel', function(){return view('welcome')});
- Route::get là phương thức
- 'home/laravel' là đường dẫn
- function là tham số truyền vào theo đường dẫn, ở đây nó sẽ trả về view home
- Ngoài ra còn 1 cách khác nữa là: Route::get('/home', 'HomeController@index')->name('home')
- Ở đây HomeController@index là trỏ vào phương thức index của Controller HomeController.
- Trường hợp trỏ tới resource controller thì chỉ cần sử dụng 1 route duy nhất thay vì phải viết nhiều route vd Route::resource('/baiviet', 'ArticleController') - Thay vì phải @từng hàm thì ta chỉ cần trỏ đến cả cục.
- Trong trườnghợp nếu muốn dùng một số action nhất định trong đó có thể khai báo: ![[Pasted image 20210409113027.png]]
- Mặc định laravel sẽ đặt tên cho các route, trường hợp muốn ghi đè tên route có thể sử dụng cách: ![[Pasted image 20210409113221.png]]
- Chạy php artisan route:list sẽ hiển thị danh sách tất cả các route hiện tại trên hệ thống. ![[Pasted image 20210405125201.png]]
- Route::get('/user', 'ApiUserController@userInfo')->middleware('auth:api') Để vào route này thì cần phải đăng nhập
==Controller==
- Route sẽ trỏ tới controller
- Để tạo controller chúng ta sử dụng php artisan make:controller tên-controller -> nó sẽ tạo ra 1 class
- Chúng ta tạo function trong controller để thực hiện các logic, trong function bắt buộc phải return để trả về view.
- Sau khi đã tạo model rồi, ở trong controller ta muốn sử dụng model nào thì khai báo use đường dẫn tới model (tính từ app) VD: use App/Models/Article sau đó ta có thể tạo ra một thể hiện của class đó
- Sau khi đã tạo thể hiện của model rồi, muốn lưu dữ liệu gì xuống database thì chúng ta sử dụng $tên-thể-hiện->cột của model = value
- VD: $article -> title = 'bai viet 1', $article->content = 'nội dung bài viet 1'. Ở đây ta có thể thấy cái này gồm 2 bước, bước 1 là khởi tạo 1 object và bước 2 là gán giá trị cho các thuộc tính của object đó.
- Để lưu xuống db thì sử dụng $article -> save(); sử dụng phương thức save.
- Để đọc lên thì chúng ta sử dụng phương thức find, chú ý đây là một phương thức static (sử dụng ::) VD: $article  = Article::find(1) => Ở đây nó sẽ lấy record của id = 1 từ db lên và gắn vào $article, lưu ý dữ liệu lấy dữ db lên sẽ là một object, các column là các thuộc tính của object
- Resource controller: cũng là một controller được tạo các hàm có sẵn, tự tạo sẵn tất cả các hàm controller bằng php artisan make:controller tên-controller --resource khi đó controller tạo ra sẽ khác controller tạo bình thường ở chỗ có sẵn các function rỗng.
- Để controller trả về giá trị cho view chúng ta sử dụng view('tên view'). VD: return view('article.list', ['articles' => $articles]) tương đương vào thư mục article tìm file list.blade.php, tham số thứ 2 của view là mảng các giá trị dữ liệu gửi sang view.
- Trường hợp trả nhiều thì chúng ta có thể sử dụng hàm compact($articles) sẽ tạo ra mảng ['articles' => $articles]
- VD return view('article.list', compact($articles) )
- hoặc chúng ta có thể sử dụng với with
- return view('article.list', ['articles' => $articles]) <=> return view('article.list') -> with ('articles' => $articles)
- Trong controller resource hàm store có params là request, thì request là một object, nó chứa toàn bộ dữ liệu từ client gửi lên. Chúng ta có thể lấy dữ liệu ra thông qua name của input form bằng cách $request -> name-input
- nếu sử dụng request->all() sẽ lấy ra toàn bộ dữ liệu gửi lên. 
- Sau khi lấy được dữ liệu lên thì để save dữ liệu xuống db chúng ta new 1 thực thể của model xong gán giá trị cho các thuộc tính của thực thể đó xong sử dụng save() để lưu xuống db
- Sau khi save dữ liệu thì ở return chúng ta sử dụng hàm redirect() -> route('baiviet.create') để quay lại cái form, chúng ta có thể kèm theo with với thông báo vd redirect() -> route('baiviet.create') -> with ('msg', 'dang bai thanh cong') ở phần form template chúng ta có thể sử dụng @if để bắt nếu có msg
- Tên-model::all() sẽ lấy hết tất cả dữ liệu của model đó dưới db lên, dữ liệu trả ra là collection dạng như mảng
- tên-model::paginate(10)  chỉ lấy 10 record, khi đó ở url sẽ truyền param số page để nó lấy dữ liệu của theo từng trang, ở trang view để hiển thị pagination chúng ta sử dụng {{$articles->links()}}, ở đây articles là dữ liệu đổ ra từ paginate của controller và truyền sang view -> khi đó nó sẽ tạo phân trang cho chúng ta
- hoặc tên-model::latest()->paginantion(10)
- Để tạo mới một user chúng ta sử dụng model sau đó tạo 1 biến user = new User, user -> fill($request) -> all(); là lấy toàn bộ dữ liệu gửi lên chuyển vào user.
==Model==
- php artisan make:model tên-model - nó sẽ tự tạo file model và để trong app, do đó chúng ta sử dụng php artisan make:model Models/tên-mode để nó tạo thư mục Model và bỏ file model mới tạo vào nhằm dễ quản lý các file model
- Model liên kết với migration, trong laravel chúng ta sử dụng eloquent model là model thường được liên kết với migration hay nói cách khác là liên kết với db, có thể được gọi là ORM (Object related mapping)
- ORM giúp cho dễ dàng lưu code xuống db, db đọc lên thành object trên code. 1 dòng dữ liệu là một object trên code.
- Khi tạo 1 model thì chúng ta có thể tạo migration luôn cho nó bằng lệnh php artisan make:model Models/tên-mode -m để tạo migration của model này luôn, chúng ta chỉ việc vào file migration để tạo ra các cột dữ liệu cho table nào.
- fillable:
	- Chỉ định các field sẽ được lưu xuống db
	- đặt biến protected $fillable là một array, trong đây sẽ khai báo các field sẽ được lưu. 
- Liên kết với DB ngoài ra Model còn liên kết với nhau
- Eloquent:Relationship
	- 1 - 1
	- 1 - n
	- 1 - n (Inverse) ngược lại
	- n - n

- Để tạo relationship thì chúng ta vào model, tạo 1 function có tên là column của cột muốn set relation ship với nó, trong đó sẽ trả về thiết lập relationship. VD role có nhiều users thì ta vào model role tạo function users, return là this->hasMany('App\User'), sau khi làm xong ở model Role rồi ta qua User thiết lập quan hệ 1 user chỉ có 1 role -> return this->belongsTo('App/Models/Role')
- 
==Migration==
 - php artisan migrate dùng để thực thi các migration trong thư mục migrations, VD tạo table, các cột,..
 - php artisan migrate:rollback : hủy bỏ lệnh migrate mới thực hiện
 - php artisan migrate:refesh : xóa hết db và tạo lại -> mất hết dữ liệu
 - $table -> bigIncrements('id') => cột tự động tăng
 - $table -> timestamps() => tự tạo 2 cột là thời gian tạo và thời gian update
 - $table -> string('title') => tạo cột title có kiểu string
 - $table -> text('content') => tạo cột content có kiểu text
 - $table->interger('role_id')->default(2); //mặc định là 2
 ==Blade template==
 - blade là một template engine, làm nhiệm vụ là chuyển các markup php trong blade thành code php, code php sẽ ký hiệu @ ở trước, nó giúp việc viết code php lồng trong html, để truy xuất giá trị các biến trong blade thì sử dụng {{tên biến}}
 - trong thư mục resources/views chúng ta tạo thư mục articles chứ file list.blade.php (nhớ phải có .blade)
 - Trong 1 file blade template nếu sử dụng @yield('content') thì tất cả các template khác điều có thể extend được. VD ở file home ở body chúng ta đặt @yield('content'), ở section khác muốn sử dụng lại code của home thì gọi @extends(layouts.home) - thư mục layouts file home, tiếp theo ta thêm @section('content'), ở cuối code thì đặt @endsectionthì khi đó ta sẽ có nội dung là code của home và ở chỗ đặt @yield là code của thằng extends, có nghĩa là code được tự động copy vào chỗ @yield\
 - ==Blade Directive==
	 - @auth - @endauth: Kiểm tra xem người dùng có được xác thực hay không. ![[Pasted image 20210409110205.png]]
	 - @guest - @else - @endguest: Kiểm tra xem người dùng có phải là khách hay không. ![[Pasted image 20210409110250.png]]
	 - @includeFirst(['first-view-name', 'second-view-name']); Xây dựng 1 trang web có nhiều theme, phải include file view nào đó nếu tồn tại, còn không thì dùng default => sử dụng first view nếu có không thì sử dụng second view
	 - @includeWhen($post->hasComments(), 'posts.comments'); Người dùng sẽ thấy giao diện ở các điều kiện khác nhau tùy mỗi điều kiện mà có thể add content cho phần hiển thị, VD nếu có comment trong bài viết thì sẽ hiện không thì thôi
	 - @includeIf('viewname'); include file view nếu nó tồn tại

- Giả method cho form
	- Trong HTML không có method PUT, PATCH, DELÊT nên cần dùng lệnh @method để gán các method này vào
	- @method('PUT') ![[Pasted image 20210409112846.png]]
	- 
 ==View==
 - Trong form ở phần action chúng ta gắn link action bằng action="{{ route('baiviet.store') }}" - đây là tên route chúng ta có được khi sử dụng route:list thay vì sử dụng url. thay vì ghi url ra. hàm route sẽ gọi ra địa chỉ của một route nào đấy thông qua params tên route truyền vào
 - Trong laravel để bảo vệ tấn công csrf thì chúng ta sử dụng @csrf trong blade template, nó sẽ tự tạo ra 1 input ẩn có chứa mã token, khi gửi lên server thì server sẽ check token này

==Seeder==
- là công cụ để tạo dữ liệu mẫu
- sử dụng php artisan make:seeder tên-seeder nó sẽ nằm trong thư mục database/seeds
- trong seeder chúng ta use model mà chúng ta muốn tạo dữ liệu mẫu
- phần function run chúng ta chạy 1 vòng lặp for với nội dung là tạo ra bài viết
- chúng ta có thể kết hợp với thư viện faker laravel để tạo dữ liệu random thay vì dữ liệu cứng
- để chạy seed thì chúng ta sử dụng php artisan db:seed -> nó sẽ chạy db seeder (databaseseeder) nó là 1 seeder chung nó sẽ gọi các seeder con bằng $this->call(tenseedercon::class, sau khi thêm code gọi seeder con vào db seeder chúng ta chạy composer dump-autoload
- Ngoài ra còn 1 cách chạy trực tiếp mà không đăng ký vào dbseed là php artisan db:seed --class=RoleTableSeeder
==Request==
- khi dữ liệu đổ lên chúng ta cần phải validate dữ liệu trước khi xử lý
- php artisan make:request tên-request khi đó trong http sẽ có folder requests trong đó sẽ có file mới trong file đó có sẵn 2 function là authorize và rules
- authorize returrn true thì tất cả thằng nào dù chưa đăng nhập cũng request được
- rules return một mảng trong đó chứa các cặp key value với giá trị là tên name input và giá trị yêu cầu
- VD: return [
	- 'title' => 'min: 10',
	- 'content' => 'min: 20'
- ] có nghĩa là biến title sẽ đi qua hàm min của laravel và kiểm tra có đủ 10 ký tự hay không. nếu muốn thêm điều kiện chúng ta sử dụng | VD: 'min: 10 | max: 1000', những cái rule này có thể xem ở laravel validation
- Sau khi đã tạo request và set rule thì chúng ta vào controller ở phần lấy resquest từ params chúng ta thêm đường dẫn tới request chứa rule hoặc có thể use ở trên cùng sau đó ở phần request chúng ta chỉ cần gọi thôi
- VD: public function store(App/Http/Requests/StoreArticRequest $request) =>use 'App/Http/Requests/StoreArticRequest' và public function store(StoreArticRequest $request)
- Client gửi dữ liệu qua route nó sẽ chuyển sang controller tương ứng, trong quá trình đi tới controller nó sẽ đi qua check dữ liệu, nếu không hợp lệ nó sẽ quay về lại trang ban đầu, để bắt lỗi thì chúng ta sử dụng @error('name-input') và @enderror, ở giữa chúng ta sẽ lấy ra value lỗi thông qua biến message, sẽ lấy ra lỗi của field nào đấy và thông báo ra ngoài
- 'email' => 'required | email | unique:users' : email bắt buộc phải có, phải là địa chỉ email và nó là duy nhất trong table user
- user->password = Hash::make(request->password) nhớ phải Use Hash ở trên 
- trong api, thì controller sẽ trả về json. return response()->json(user)
- 
==Laravel mix==
- để sử dụng các thư viện ngoài như bootstrap thì chúng ta cần phải build, nghĩa là laravel sẽ compile js, css => public sau khi build sẽ chỉ ra 1 file js và css duy nhất
- trong package.json chứa thư viện laravel-mix
- chúng ta sẽ chạy dòng lệnh

==Sử dụng bootstrap trong laravel==
- php artisan ui bootstrap
==Middleware==
- php artisan make:middleware tên-middleware
- Sau khi tạo xong middleware thì đăng ký nó trong kernel.php, kernel là file được load đầu tiên. Routemiddleware là apply cho cả web và api, cho nên chúng ta đăng ký rolemiddleware vào trong đây bằng cách thêm 'role' => /App/Http/Middleware/RoleMiddleware::class,
- Để sử dụng middleware chúng ta vào route, ở các route nào cần apply chúng ta sử dụng gọi ra: Route::get('/user', 'UserController@showInfo') -> middleware('auth') : đăng nhập mới được vào
- Route::get('/admin', 'AdminController@showImportantInfo') -> middleware('auth', 'role') : đăng nhập và có role mới được vào.
- Route::get('/admin', 'AdminController@showImportantInfo') -> middleware('auth', 'role:admin') : đăng nhập và có role là admin mới được vào, cần phải thêm biến để hứng data từ route truyền vào middleware, do route sẽ truyền admin vào middleware.
- Trong role middleware chúng ta thiết lập 
	- use Auth
	- if( !Auth::user() || Auth::user()->role->name != $role) { //Lấy dữ liệu đăng nhập xem trong đó có role là role truyền vào không, nếu không trả về trang login
		- return redirect()->route('login');
	- }
- Lập một hàng rào bảo vệ các thành phần của ứng dụng, 
- Dùng để phân quyền
- Tạo ra các roles (tạo model roles) php artisan make:model Models/Role -m
- Trong 1 role sẽ có cột name: Admin, user
==Athorization==
- Phân quyền chi tiết hơn vd, ai được sửa bài viết, ...
==Đăng nhập==
- Để đăng nhập bằng api được thì sử dụng passport
- composer require laravel/passport "-9.0"
- php artisan migrate
- php artisan passport:install
- Khi đó sẽ có 2 secret key, ngoài ra 2 key này được lưu trong oauth_clients table
- Thêm cái HasApiTokens vào trong App\User
- Thêm Passport::routes() vào function boot của AuthServiceProvider
- Vào config/auth sửa api driver => từ token sang passport
- Do sửa config nên cần cache config lại
- lấy token khi đăng nhập bằng api, xem ở managing personal access token trong laravel
	- if(Auth::attemp(['email' => request->email,'password'=>request->password])){
		- return 'ok' //Nó sẽ kiểm tra user name và password nếu đúng sẽ return
		- trong đây chúng ta có thể đặt logic là lấy cái thằng user ra và thêm token cho nó VD
			- user = User::whereEmail(request->email)->first()
			- user -> token = user->createToken('Token name')->accessToken;
			- return response()->json(user)
	- }
	- return response()->json(['error']=>'sai ten truy cap hoac mat khau', 401)
	- Token sẽ làm nhiệm vụ là cứ mỗi request sau này sẽ kiểm tra token, nếu đúng thì mới xử lý, nếu không thì thôi
	- Để gửi token lên thì trong post man cần phải có trường authorization, token dạng Bearer token ==> Bearer mã-token

- Viết một api mới bằng cách tạo controller tên userInfo(Request request) trong đây sẽ return response()-> json(request->user('api'))
==Docker==
- là môi trường ảo hóa để deploy dễ hơn
- docker-compose, đặt tên file là docker-compose.yml
- touch makefile, trong đây chúng ta sẽ khai báo các dòng lệnh hay sử dụng , nếu xài thì chỉ cần gõ tên lệnh sẽ tự động chạy ![[Pasted image 20210407224153.png]]
==Deploy== 
- vào console.cloud.google.com
- vào compute engine -> VM instances (tạo máy ảo)
- hệ điều hành sử dụng centos7
- ssh key:
	- hai máy tính bất kỳ có thể kết nối với nhau qua ssh key
	- Chúng ta phải copy ssh 
	- Vào metadata
	- chọn tab ssh keys và pass vào

- Chúng ta không up thẳng code lên server thì chúng ta up qua github, server sẽ pull code từ github về
- 
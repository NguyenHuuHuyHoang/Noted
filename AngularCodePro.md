==Giới thiệu về Angular ==
- Angular JS 2 hay gọi tắt là Angular 2 là 1 framework của JS được Google phát triển để phát triển ứng dụng web. Bản chất của nó vẫn là JS
- Angular 2 là 1 phiên bản tiếp theo của Angular JS (Angular 1) có thêm 1 số khái niệm mới. 
- Angular 2 hỗ trợ đa nền tảng web lẫn di động (dùng Ionic build ra các ứng dụng di động)
- Viết chủ yếu bằng code TS (gần với OOP hơn dễ tiếp cận).
- Hướng tiếp cận dựa trên component, module.
==Kiến trúc của Angular ==
- Sẽ có App module đại diện cho App, module là tập hợp các component để nó quản lý các component đó. Các componnent có thể tổ chức lẫn nhau để tạo nên từng thành phần của trang web. VD. App module chứa App component, trong App component chứa Trang chủ component, Trang chi tiết phim component, Trang đặt vé component. Component được tổ chức có dạng từ trên xuống như một cây đa cấp.
- App route là nơi sẽ quản lý, định nghĩa component đó là một phần của trang web hay chỉ là con của một component khác thôi.
==Một số khái niệm trong Angular==
- Module
- Components
- Phân tách module (Nhóm component)
- Templates
- Metadata
- Databinding
- BindingCustomer
- Directives
- Pipes
- Input, Output, ViewChild
- Form-Validation
- Service - Observable - Object - HTTP
- Routing
- Parameter
- Get Post Put Delete (HTTP service)
- Lưu trữ cục bộ - Redirect
==Cài đặt Angular CLI==
- Angular CLI là công cụ do google cung cấp để phát triển ứng dụng bằng angular, nó giưps tạo sẵn các cấu trúc thư mục ứng dụng và các tập tin cấu hình cần thiết.
- npm i - g @angular/cli => ng new tên-project, chạy bằng lệnh ng serve
- trong file main.ts, nó xác định module nào là module gốc khi khởi chạy. Mặc định là App module
==Component==
- Component biểu diễn giao diện UI (file.html)
- Nói 1 cách đơn giản, 1 component là một thẻ do mình định nghĩa trong thẻ đó chứa các nội dung html do mình biên soạn.
- để tạo component cú pháp là ng g c tên-component
- Một componnet bao gồm:
	+ Giao diện html
	+ Css của giao diện html đó
	+ selector (tên thẻ component do ta tự đặt) 
	+ ngoài ra còn chứa 1 class JS để xử lý cho component đó và export ra ngoài.
- trong file tên.component.ts chứa các thông tin:
	+ selector: tên của thẻ do ta tự đặt, các selector phải khác nhau giữa các component
==Phân tách module - Nhóm các component==
- Module là 1 nhóm chứa các component để thực hiện 1 chức năng nào đó của ứng dụng.
- Việc phân tích module giúp ta dễ quản lý ứng dụng, chia nhỏ công việc, dễ dàng bảo trì và nâng cấp.
- Phân tách module dựa trên nhóm các component phục vụ cho 1 chức năng nào đó.
- VD: module trang chủ chứa các component để hình thành nên trang chủ. hoặc module layout chứa các component tạo nên layout đó.
- Để tạo 1 module sử dụng lệnh ng g m tên-module
- Trường hợp muốn để cho component đang do module này quản lý ra ngoài để cho các component hay module khác sử dụng thì cần phải export trong file module.ts, tại App module cần sử dụng thì import module đó vào.
==Khái niệm về Template và Style==
- Template là một thành phần của component. Trong 1 component có 2 dạng định nghĩa template. Template được định nghĩa dưới selector.
- Template: Định nghĩa nội dung html của component đó trực tiếp
- TemplateUrl: Định nghĩa nội dung html của component đó thông qua url đến file.html. nên ưu tiên sử dụng Url để dễ dàng quản lý.
- Style cũng vậy, nên ưu tiên sử dụng Url hơn.
==Metadata==
- Thực chất 1 component chỉ là 1 class. Nó không phải là 1 component cho tới khi ta khai báo nó với angular.
- Để khai báo 1 class với angular rằng nó là 1 component, ta sẽ gắn thẻ metadata vào class này. Trong TS để gắn thẻ metadata ta dùng decorator (@component)
==Databinding==
- Data binding là một tính năng, đặc tính của framework hiện đại, chúng đồng bộ dữ liệu được hiển thị trên màn hình (template html) và model (class TS). Nói cách khác Databinding là sự giao tiếp giữa TS và HTML
- One-waybinding :
	+ Interpolation: {{data}} hoặc {{tenham()}}. Nếu dữ liệu model thay đổi => view thay đổi. 
	+ Property binding: [property]="data" //Gán giá trị data vào thuộc tính property nếu sử dụng Interpolation thì là property={{data}} thay đổi property (thuộc tính của object HTML Element) vd innerHTML,...
	+ Event binding: (event)="expression", để định nghĩa một sự kiện trong angular bằng cách đặt trong 2 dấu (click) = "ChangeName()". Trong phần model phải định nghĩa phương thức ChangeName để có thể gọi ra được.
- Two-waybinding: là một sự kết hợp giữa property binding và event binding. Model thay đổi => view thay đổi, view thay đổi => model thay đổi. Để sử dụng phải import {FormsModule} from '@angular/form' vào module chứa component cần sử dụng, ở phần imports, thêm FormsModule vào.
- ở trong component gọi ra bằng cách [(ngModel)]="biến chứa giá trị trong model" ở trong phần thuộc tính của thẻ. Khi mà giá trị ở component thay đổi thì biến chứa giá trị trong model sẽ tự cập nhật lại dữ liệu.
==Directive (Attribute directive)==
- Directives là một thành phần mở rộng HTML, hay nói cách khác là các thuộc tính (attribute) của các thẻ HTML mà Angular nó định nghĩa thêm. Vì nó của riêng Angular nên phải tuân thủ theo nguyên tắc của nó.
- Có 3 loại directive: Components - Structural - Atrtribute.
- Structural - directives: Dùng để thay đổi diện mạo của DOM ví dụ như ẩn hiện, load dữ liệu,.. :
	+ *ngIF: dùng để ẩn hiện theo điều kiện nào đó là true hoặc false
	+ *ngSwitch
	+ *ngFor
==ngIF==
- cách sử dụng ngIF: <div *ngIF='status'> cybersoft</div>. Nếu status false thì sẽ ẩn, nếu true thì sẽ hiện.
==ngIf else==
- *ngIf else: ở những phiên bản sau angular hỗ trợ ta thêm directive ng-template và ngIf else.
- ng-template: Về tính chất nó giống như một component (tái sử dụng) tuy nhiên phạm vi sử dụng chỉ được khai báo và sử dụng trong component chứa nó mà thôi.
- ng-IfElse: giống như các ngôn ngữ lập trình directive if else giúp ta làm nhiệm vụ khi điều kiện if không thỏa (thay vì phải sử dụng 2 lệnh if) từ phiên bản 4 trở đi có.
- cú pháp: ![[Pasted image 16.png]]
- Ứng dụng rất nhiều.
==ngSwitch==
- Dùng để ẩn hiện theo điều kiện, giá trị điều kiện. Thường sử dụng trong các lựa chọn. Hầu như ít sử dụng trong dự án, nếu không thích xài if else thì xài switch.
- Đặc trưng là không bắt đầu bằng dấu hoa thị mà bắt đầu bằng đấu ngoặc vuông. nó lấy giá trị xong rồi sử dụng ngSwitchCase để chuyển theo giá trị điều kiện.
- ![[Pasted image 17.png]]
==ngFor==
- Cấu trúc lặp dùng để duyệt mảng hoặc danh sách các phần tử trong mảng object. Thông thường duyệt mảng object.
- ![[Pasted image 18.png]]
- Cú pháp như for of của JS
- Ngoài ra để lấy được vị trí hay còn gọi là chỉ mục (index) của từng phần tử được duyệt ta có thể khai báo thêm beién để hứng lấy giá trị này.
- ![[Pasted image 19.png]]
==ngClass==
- Trong trường hợp áp dụng 1 hoặc 2 class trên 1 div là classA và classB thì ta sử dụng như sau: ![[Pasted image 20.png]]
==ngStyle==
- Ít sử dụng hơn, xem qua cho biết vì dùng ngClass cụ thể và tường minh hơn.
- VD: ![[Pasted image 21.png]]
==Attribute - Directive==
- ng g directive tên-directive.
- Attribute directive (tự định nghĩa): Để định nghĩa 1 attribute directive cũng giống như định nghĩa 1 component, tuy nhiên directive thì không có thành phần template hay css.
- ![[Pasted image 22.png]] từ angular 4 trở lên thì sử dụng renderer 2.
- Ví dụ trong trang web có rất nhiều nút, tất cả các nút có định dạng hover vào chuyển màu và thả ra thì chuyển màu khác, do ta chia tách component nên các class không thể sử dụng lại được => chúng ta tạo ra directive nhằm thay đổi attribute html, nó có thể sử dụng ở bất kỳ đâu của dự án.
- Renderer2: 1 tính năng của angular 4 dùng để DOM đến các thành phần của HTML thông qua các phương thức rõ ràng và cụ thể hơn.
- ![[Pasted image 23.png]] - elementRef.nativeElement đại diện cho tag được gắn atttribute.
- sử dụng HostListener của @angular/core để thực hiện các sự kiện đối với attribute directive ![[Pasted image 24.png]]
==Input==
- là lấy giá trị của cha truyền cho con, @Input đặt ở con. ở html cha truyền dữ liệu thông qua việc binding dữ liệu vào biến nằm ở model con. ![[Pasted image 27.png]]
- Ngoài ra ta có thể dùng input thông qua bí danh (Alias). ![[Pasted image 28.png]]
==Output==
- Là đẩy dữ liệu con ra ngoài component cho component cha xài thông qua sử dụng Output kết hợp với EventEmitter (được import từ @angular/core) tạo ra một event ảo. ![[Pasted image 29.png]] => khi đó ở bất kỳ component cha nào mà mình gắn cái component này thì có thể lấy dữ liệu ra thông qua event Binding với event là tên của cái emit event mà ta đã tạo và gọi function trong component cha với tham số truyền vào là $event (bắt buộc của angular).
- Mục đích của Output nhằm truyền dữ liệu từ component con sang component Cha. ![[Pasted image 30.png]]
==View Child==
- là kỹ thuật DOM.
- DOM đến component con => lấy ra được các thuộc tính và phương thức của nó![[Pasted image 31.png]] 
- ![[Pasted image 32.png]]
- DOM đến tag HTML thông qua local reference![[Pasted image 33.png]]
==Routing==
- Routing trong Angular 2 là cơ chế chuyển đổi qua lại giữa các component, đồng thời tạo ra các url cho component đó => Đây là 1 kỹ thuật giúp vừa load nhanh các thành phần của trang vừa đảm bảo được url (tốt cho SEO google có thể index được)
- import {Routes, RouterModule} from '@angular/router';
- ![[Pasted image 26.png]]
- nếu sử dụng children thì ở trong component cha, phải đặt router-outlet, nhớ trong file module quản lý của cha phải import RouterModule
==Parameter (tham số trên URL)==
- Parameter dùng để truyền nhận giá trị thông qua link (Url). Từ đó ta có thể dựa trên giá trị tham số đó để truy vấn trích xuất dữ liệu.
- Có 2 loại truyền nhận dữ liệu thông qua link (routerlink) và sự kiện:
	-  truyền 1 tham số.
	-  truyền nhiều tham số.
- Truyền 1 tham số : bằng cách sử dụng property binding dữ liệu vào thuộc tính routerLink với giá trị là mảng, tham số đầu tiên là path tham số tiếp theo là param, ở trang đặt Route chúng ta đặt path: 'đường dẫn/:param', để lấy tham số trên URL xuống cần thông qua phương thức params của 1 service là ActivetedRoute import từ @angular/router. Nó trả về 1 observable, giá trị trả ra là một object vì vậy cần truy xuất dữ liệu thông qua tên biến.
==Lifecycle trong Angular==
- thực chất là những hàm sẽ tự động chạy theo thời điểm, các hàm này muốn sử dụng thì phải implements.
- Thứ tự chạy: Constructor => ngOnInit => ngAfterViewInit => ngOnDestroy
- Ít khi nào code trong Contructor.
- ngOnInit(): Chạy sau khi component được gọi, trong đây sẽ viết những đoạn code sẽ được chạy ngay khi component load lên vd như việc lên server lấy danh sách về và hiển thị ra.
- ngAfterViewInit: Chạy sau khi toàn bộ view đã được khởi tạo (HTML của component đã được load). 
- ngOnDestroy: Lúc component bị hủy thì sẽ gọi VD đang ở component a mình chuyển hướng sang component b bằng route thì khi đó a sẽ bị hủy => chạy ngOnDestroy
- ngDoCheck: sẽ chạy lần đầu tiên sau init và trước afterviewinit sau đó mỗi khi thay đổi cái gì đó, vd giao diện, biến, thuộc tính nào đó trong class nó sẽ chạy lại.
- ngOnChange: sẽ chạy sẽ chạy lần đầu tiên khi giá trị input được truyền vào và sau đó khi giá trị Input thay đổi.
==Form==
- Trong angular hỗ trợ 1 module dành cho việc nhập liệu Form và kiểm tra giá trị đó là FormsModule. Khi nhấn submit dữ liệu đi thì angular sẽ làm việc và lấy ra giá trị form, dữ liệu người dùng nhập vào tạo ra 1 object.
- Import FormsModule từ @angular/form vào module quản lý component chứa form (Import ở trên lẫn ở dưới luôn)
- ở tag form chúng ta phải khai báo 1 local reference (thẻ #) = "ngForm". Dùng event binding cho form là (ngSubmit)="Phương thức (#form đã khai báo ở trên . value)".
- Trong form có những ô cần lấy dữ liệu những ô không cần, chúng ta cần phải cho angular biết cần phải lấy dữ liệu ở những input nào bằng cách thêm ngModel ở input cần lấy giá trị và thuộc tính name => object có dạng name:value
- ở trong file ts của component khai báo phương thức xử lý giá trị lấy được từ form.
==Form validation==
- Trạng thái của giá trị đầu vào thẻ input:
	- untouched: Trường này chưa được chạm vào.
	- touched: Trường này đã được chạm vào.
	- pristine: Trường này chưa được thay đổi
	- dirty: Trường này đã được thay đổi
	- invalid: Trường có nội dung không hợp lệ
	- valid: Trường có nội dung hợp lệ.
- Giá trị trả lại khi ta kiểm tra các trạng thái sẽ là true. Nếu ngược lại thì sẽ là false.
- Kiểm tra rỗng với required![[Pasted image 34.png]]
- Kiểm tra min-max length ![[Pasted image 35.png]]
- Kiểm tra họ tên tiếng việt ![[Pasted image 36.png]]
- Custom thông báo lỗi thông qua css ![[Pasted image 37.png]]
==Pipe==
- là một filter của angular giúp format định dạng dữ liệu hiển thị. ![[Pasted image 38.png]]
- DatePipe được xài rất là nhiều, để định dạng ngày tháng năm.
- DomSanitizer để khai báo với angular là đường dẫn an toàn thông qua phương thức bypassSecurityTrustResourceUrl(khi import link trailer youtube)
==Angular Material==
- Thư viện UI đã được xây dựng sẵn trong Angular
==Object Class==
- Object Class (TS đã học) là prototype
- cú pháp tạo class ng g class tên-class
==Observable==
- là 1 tính năng mới của ES7. Nó tương tự như promise trong ES6 nhưng promise nhận giá trị tại 1 thời điểm là thành công nhảy vào hàm thành công làm trả ra kết quả hoặc thất bại cũng vậy.
- Observable nó lấy nhiều giá trị tại nhiều thời điểm. Ngoài ra request được gửi đi ở observable thì có thể hủy được.
==Service - Observable - Object - HTTPService==
- Service là chứa các phương thức tương tác với BE để lấy hoặc upload dữ liệu từ BE về thông qua các phương thức như GET, POST, PUT, DELETE và thư viện hỗ trợ từ angular 2 gọi là Observable để đổ vào đối tượng (Object).
- Nói nôm na service chứa các hàm gọi ajax để lấy dữ liệu về.
- ng g service tên-service
==HTTP module==
- HTTP module cung cấp cho chúng ta service http dùng để giao tiếp với BE thông qua một số phương thức như get, post ,put ,delete,..
- Để dùng được HTTP service ta cần import httpModule vào toàn ứng dụng thông qua app module.
- 
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
- là lấy giá trị của cha truyền cho con, @Input đặt ở con. ở html cha truyền dữ liệu thông qua việc binding dữ liệu vào biến nằm ở model con.
==Routing==
- Routing trong Angular 2 là cơ chế chuyển đổi qua lại giữa các component, đồng thời tạo ra các url cho component đó => Đây là 1 kỹ thuật giúp vừa load nhanh các thành phần của trang vừa đảm bảo được url (tốt cho SEO google có thể index được)
- import {Routes, RouterModule} from '@angular/router';
- ![[Pasted image 26.png]]
- nếu sử dụng children thì ở trong component cha, phải đặt router-outlet, nhớ trong file module quản lý của cha phải import RouterModule
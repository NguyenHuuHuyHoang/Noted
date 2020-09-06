==Introduction==
- Angular khác với React ở hướng tiếp cận là componet, module trong khi React chỉ là component.
- App Module <=> App.js
- 1 Module có thể quản lý 1 module hoặc 1 component
- Gom những Component có cùng chức năng vào 1 module, component không thể tự đứng một mình mà phải có module quản lý.
- Các khái niệm trong Angular: 
+ Module
+ Components
+ Phân tách module (Nhóm component) - ShareModule
+ Databinding
+ Directives
+ Input, Output, ViewChild, View Children
+ Hướng dẫn angular Masterial
+ Template - Routing
+ Form - Validation
+ Pipes
+ Service - Observable - Object - HTTP
+ Get Post Put Delete (http service)
+ Hướng dẫn xây dựng dự án
+ Guard
+ RXJS DOM
+ Animation
==Cài đặt Angular==
- npm install -g @angular/cli
- Cách new 1 propject angular: ng new [tên project]
==Giới thiệu về cấu trúc thư mục và tập tin==
- package.json: Chứa thông tin của ứng dụng
- tsconfig.json: Dùng để cấu hình biên dịch cú pháp typescript => js
- e2e: Thư mục này dùng để chức các tập tin cho testing
- node_modules: Chức các module cần thiết cho ứng dụng
- src: Đây là thư mục sẽ chứa toàn bộ source code của ứng dụng.
- .editorconfig: Chức các cấu hình liên quan đến phần
- .gitignore: chứa thông tin những tập tin hoặc thư mục sẽ bị ignore không được commit lên git repo.
- angular.json: tập tin chứa cấu hình cho Angular CLI, giúp build ứng dụng Angular.
- browserslist: điều chỉnh CSS và JS để hỗ trợ cho nhiều trình duyệt đặc biệt (IE9-11, Edge 16..)
-  karma.conf.js: Tập tin cấu hình cho karma, liên quan nhiều đến phần testing
-  package-lock.json: Dùng để lock version cho các module dêpndencies.
-  README.md: hiển thị thông tin về Git repository
-  tslint.json: Tập tin cấu hình để kiểm tra lỗi cho các tập tin .ts (TypeScript) trong Angular project.
-  App: Đây là thư mục sẽ chứa toàn bộ code của ứng dụng Angular.
-  Assets: Thư mục này sẽ chứa các file ảnh, CSS, custom JavaScript của ứng dụng Angular.
-  Environments: Thư mục giúp chúng ta định nghĩa các tập tin cấu hình cho những môi trường khác nhau đó.
-  Index.html: Trang chủ của ứng dụng Angular
-  main.ts: Chứa code bootstrapping cho ứng dụng Angular.
-  polyfill.ts: định nghĩa các chuẩn giúp ứng dụng có thể chạy được trên mọi trình duyệt.
-  style.css: Định nghĩa style CSS cho ứng dụng Angular.
-  test.ts: Code để chạy test
-  tsconfig.json: Tập tin định nghĩa việc compile cho TypeScript.
==Cấu trúc project==
- tsconfig.base.json => baseUrl: Nguồn ứng dụng bắt đầu từ đâu
- angular có những thẻ <app-root> </app-root> =>div id ="root"
- Trong file main.ts => có bootstrapModule => cho biết Module nguồn của toàn bộ ứng dụng là cái nào.
- Module: Cấp cao nhất trong ứng dụng, dùng để đóng gói một chức năng cụ thể trong ứng dụng, 1 module có thể chứa nhiều module hoặc componet, có nhiều loại module: do dev tự định nghĩa, các module được angular định nghĩa sẵn.
- Trong angular 1 component bao gồm: HTML, css, selector (tên thẻ component để gắn vào html), class để xử lý logic. Component dùng để biểu diễn UI và logic.
- SCSS của component nào thì chỉ sử dụng cho mình component đó không sử dụng cho component khác.
- component luôn có tên app đăng trước vd demo => app-demo
- tạo component: ng g c [tên không dấu viết thường], nó sẽ tự import vào module gần nhất
- tạo module: ng g m [tên module] không tự import, phải tự import vào app module.
- Mặc định các component đang được quản lý trong module nào thì chỉ được sử dụng trong module đó. Để sử dụng ở những module khác thì cần phải exports: [Mảng các module] trong module quản lý.
- Mối quan hệ giữa module và component: module giống như 1 group của component quản lý các component. 1 Module có thể quản lý nhiều component và mỗi component phải được quản lý bởi module nào đó.
==Cài đặt bootstrap vào angular==
- cài npm i bootstrap jquery proper.js
- Trong angular.json, dòng gắn file bootstrap vào styles: "node_modules/bootstrap/dist/css/bootstrap.min.css", scripts gắn các file js thư viện ở ngoài. "node_modules/jquery/dist/jquery.min.js","node_modules/popper.js/dist/umd/popper.min.js","node_modules/bootstrap/dist/js/bootstrap.min.js"
==Binding==
- Oneway binding:
+ Interpolation: {{[tên biến]}} thường được sử dụng để binding dữ liệu vào các thẻ tag. Ngoài ra còn có thể {{tên hàm()}}. Nếu dữ liệu model thay đổi => view thay đổi.
+ Property binding: [property] = "[tên biến]" thuờng được dùng để binding dữ liệu cho các thuộc tính của tag. VD <input [value] = 'name' >
+ Event binding: dữ liệu được binding từ view về model thông qua các sự kiện. (event)="function()", event = click, change,..... VD <input type="text" #thamso index='12'> #thamso đại diện cho thẻ input, Muốn lấy giá trị value của thẻ thì .value tương tự muốn lấy các thuộc tính khác thì .thuộc tính khác. => thamso.value.
- Twoway binding: Là một sự kết hợp giữa property binding và event binding. Model thay đổi => view thay đổi, View thay đổi => model thay đổi. Để sử dụng thì phải import FormModule từ @angular/forms và gắn nó vào imports (ở module quản lý thằng component sử ) => gọi [(ngModel)]='tên biến' để set và lấy dữ liệu, kiểu thực hiện là input, nhập dữ liệu vào input thì sẽ binding ra liền. 
==Directives==
- Structural directives: 
+ 
+ tag ng-template mặc định sẽ không hiển thị ra, nếu muốn hiển thị thì phải gọi tới nó. <ng-template #loginTemplate>
+ ngFor đặt ở đâu thì tag đó sẽ lặp lại bao nhiêu lần. trong ngFor có let index = index, let total = count (tổng số phần tử có trong mảng).
+ Angular không cho 2 directive trong cùng một template, vì vậy cần sử dụng ng-container để chứa directives.
+ ngTemplateOutlet="templateA" Dùng để gọi template code được lặp đi lặp lại nhiều lần.
+ ng-content <=> children trong react.  Tuy nhiên trong react chỉ có 1 children, nhưng trong angualar có thể có nhiều children.
+ [ng-class] (phải bọc trong []) = "{key:value}" => key: tên class, value là điều kiện. nếu 
+ ng g d [hightlight]: tạo directives custom cho riêng mình, bên trong directive cần import thư viện ElementRef. Thuờng sử dụng trong truờng hợp logic xử lý lặp đi lặp lại nhiều lần.
==Giao tiếp giữa các component==
- @input: tương tự như việc truyền props trong react. Dùng để truyền dữ liệu từ cha sang con. Ở con để nhận dữ liệu từ cha truyền xuống thì cần phải import Input vào.
- @output dùng để đẩy dữ liệu ra cha. Cần import thư viện Output và EventEmitter để tạo ra giả lập sự kiện.
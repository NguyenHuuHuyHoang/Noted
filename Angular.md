- Cách new 1 propject angular: ng new [tên project]
- Angular khác với React ở hướng tiếp cận là componet, module trong khi React chỉ là component.
- App Module <=> App.js
- 1 Module có thể quản lý 1 module hoặc 1 component
- Gom những Component có cùng chức năng vào 1 module, component không thể tự đứng một mình mà phải có module quản lý.
==Cấu trúc project==
- tsconfig.base.json => baseUrl: Nguồn ứng dụng bắt đầu từ đâu
- angular có những thẻ <app-root> </app-root> =>div id ="root"
- Trong file main.ts => có bootstrapModule => cho biết Module nguồn của toàn bộ ứng dụng là cái nào.
- Module.
- Trong angular 1 component có 3 file: html, scss ,ts
- SCSS của component nào thì chỉ sử dụng cho mình component đó không sử dụng cho component khác.
- component luôn có tên app đăng trước vd demo => app-demo
- tạo component: ng g c [tên không dấu viết thường], nó sẽ tự import vào module gần nhất
- tạo module: ng g m [tên module] không tự import, phải tự import vào app module.
- Mặc định các component đang được quản lý trong module nào thì chỉ được sử dụng trong module đó. Để sử dụng ở những module khác thì cần phải exports: [Mảng các module] trong module quản lý.
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
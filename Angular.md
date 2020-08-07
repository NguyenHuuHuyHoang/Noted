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
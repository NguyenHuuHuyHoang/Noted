- Hiệu năng ở mức chấp nhận được chứ hiệu năng không bằng native được.
- Ưu điểm: Tốc độ phát triển ứng dụng nhanh, 1 codebase có thể build 1 ứng dụng chạy cả andriod và iOS => toàn bộ quá trình phát triển được tăng lên với số lượng lập trình viên 1 nửa, FE có thể qua làm cross platform.
- Nhược điểm: Hiệu năng với các ứng dụng đòi hỏi logic phức tạp can thiệp sau hoặc điều khiển phần cứng của hệ thống VD: bluetooth, camera,... , tốc độ update với các công nghệ, SDK của các platform thường chậm hơn so với Native, những tính năng mới cần phải đợi fb hoặc google đưa vào SDK mới sử dụng được. Bug khó xử lý hơn do framework đã che bớt đôi khi phải sử dụng *Xcode và VS studio * để debug
- Phỏng vấn thuyết phục tốt nhất là làm 1 demo sản phẩm, các câu hỏi phỏng vấn là kiến thức nền tảng, thể hiện điểm mạnh ở khả năng học hỏi, khả năng giao tiếp,..
- Kỹ năng cần có: Kiến thức cơ bản về lập trình (biến, hàm, câu lệnh điều kiện, vòng lặp, OOP,...), tư duy lập trình, giải quyết bài toán, sử dụng IDE lập trình (quan trọng để debug, để kết nối device, ....); GIT / Subversion, Debug, test là kỹ thuật hơi khó hơn trên web do phải test trên cả ios và andriod, đôi khi thư việc này chạy trên ios nhưng andriod bị lỗi hoặc chạy bt nhưng máy xiaomi bị lỗi,..., làm việc nhóm,....
- React Native: JS hoặc TS, VS Code
- Flutter: Dart, Andriod Studio hoặc VS Studio
- Debug, Analytics, Log
- Lập trình app làm việc với các thành phần mobile cơ bản: Camera,phải biết xin quyền(Vd để chụp hình thì phải xin những quyền nào), phải biết sử lý ảnh sau khi chụp từ camera về. photo, sound, video, backend vd như call api như thế nào, get api về như thế nào, database thường là local database, store những dữ liệu offline trong app, xử lý notification, multification như thế nào, nhận thông báo cho ứng dụng,.... build ra máy Andriod, IOS, đẩy ứng dụng lên store.
- Kiến thức nâng cao: Vẫn cần kết hợp làm việc với lập trình mobile native (Andriod Java tối cần thiết (Kotlin có thể có có thể không), IOS Swift sau này cần phải phát triển native module để tăng performen cho app, lv cấp thấp không cần, team leader sẽ phải biết làm), Animation/Gesture (xử lý được những animation, hành vi của người dùng), Hardware, Testing: Manual/Automation, unit test. Optimize code, chạy tốt trên nhiều hệ điều hành/ nhiều loại thiết bị mobile, App/Component Architecture vd: tìm hiểu sâu về kiến trúc andriod, các tầng như thế nào, tầng trên cùng là gì, tầng dưới là gì, đặc thù hệ điều hành thì mỗi tầng nó khác nhau, nếu hiểu thì khả năng code và tăng performen app, Build/publish app ra bản andriod, iOS.xin quyền chắc chắn 90% phải vào native để xin quyền, setup những giá trị như làm mờ code, bảo mật,...
- Y/c laptop Window: 8GB ram trở lên, ổ SSD, để cài Andriod Studio, hoặc VS Code (React Native), chạy máy ảo.
- Mac: sử dụng máy mac (ram 8GB trở lên, ổ ssd) để có thể debug và build bản release cho cả iOS và Andriod, đẩy app lên store phải mua tài khoản apple mỗi năm 100USD, muốn chạy trên máy thật thì phải có tài khoản apple developer. Hackintosh không stable.
 ==Lộ trình học React Native==
+ Lập trình JS, React Native cơ bản
+ Componet, Style - xây dựng giao diện ứng dụng
+ Sử dụng, quản lý props, state, hook
+ Navigation giữa các màn hình sử dụng React Navigation
+ Lưu trữ dữ liệu local với Async Storage
+ Redux, Redux thunk, Redux Saga.
+ Native modules
+ Tích hợp web service: HTTP/Socket
+ Đóng gói và publish app lên AppStore/Google Play Store
==Lộ trình học Flutter==
+ Lập trình Dart, Flutter cơ bản
+ Common UI Widget: Cheat sheet, container, table, image, Stack-xây dựng giao diện ứng dụng
+ Di chuyển và truyền dữ liệu giữa các màn hình
+ Lập trình theard: Future, Steam
+ Lưu trữ dữ liệu local với SQLite
+ Tích hợp web service: HTTP/Socket
+ BloC pattern, provider
+ Đóng gói và publish app lên AppStore/Google Play Store
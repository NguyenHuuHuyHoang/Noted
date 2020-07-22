==0- Chuẩn bị==
- React dùng trong một số trường hợp nhất định không phải lúc nào cũng sử dụng react.
- Học xong làm được gì có thể dùng React để code front-end cho bất cứ web app nào.
- Có thể tự học React Native -> build app cho mobile
- Tự học được các SPA framework khác như Angular, Vue.
==1 - Single Page App==
- Trước khi SPA ra đời thì thường viết web như trong ExpressJS hoặc là dùng PHP, cách hoạt động là mỗi khi truy cập một trang web, hoặc chuyển từ page này sang page khác thì client sẽ gửi resquest lên server và server sẽ trả về toàn bộ code html cho client. Như thế việc xử lý chủ yếu bên server, mỗi lần resquest sever thì sẽ xóa dữ liệu và lấy dữ liệu mới từ server gửi về để hiển thị.
- Các đây khoảng chục năm thì có những framework được viết bằng JS giúp cho việc render ở client giúp tăng trải nghiệm người dùng vì load web rất là nhanh, tất cả các việc render xử lý ở client, theo cách truyền thống thì mạng chậm thì phải chờ một lúc, render ở client thì dữ liệu trả về ở server sẽ ít hơn (phần lớn, ở request đầu tiên sẽ mất thời gian). Mỗi lần click vào đường link thì đường link thay đổi nhưng dữ liệu không thay đổi.
- REACT là một tool giúp build SPA, REACT không phải là cái đầu tiên. Angular ra đời -> reactJS -> vue, trước angular còn có nhiều thằng khác như backbone, ember
- REACT được Facebook phát triển.
==2 - Cài đặt==
- Cách setup React bằng CDN Link. 
- tối thiểu cần phải có là 1 div id="root" trong thẻ body, copy 2 link cnd vào thẻ body.
- tạo script JS,  tạo element bằng React.createElement('div', null (không có thuộc tính), 'nội dung').
- dom tới root bằng documet.getElementById('root');
- render element mới vừa tạo vào root bằng ReactDOM.render(element cần render, root);
==3 - React.createElement==
- Khi lập trình thì code app thì chia nhỏ ra thành nhiều component.
- React.createElement dùng React API tạo ra các react Element.
- nhận vào 1, 2 hoặc nhiều tham số, tham số 1 là kiểu element HTML, tham số thứ 2 là một object chứa props (thuộc tính) vd className, src,... , nếu không có gì thì để null, tham số thứ 3 là children (các thằng con của nó), nếu không có con thì sẽ không ghi tham số thứ 3.
- React sẽ tạo ra các React component sau đó ReactDOM sẽ map 1 : 1 sang HTML DOM tương ứng. Xây dựng các thư viện component xong lắp ráp lại.
==4 - JSX==
- Babeljs.io : Chuyển code JSX thành JS, dùng để dịch các chuẩn JS mới hơn về chuẩn cũ hơn.
- Để sử dụng code JSX thì cần phải add link cdn của Babel vào html và  thêm type="text/babel" vào tag script chứa code.
- Babel sẽ không chạy đoạn code trong script mà sẽ biên dịch code thành code reactjs và bỏ vào một tag script do nó tạo đặt ở trên cùng thẻ HTML.
==5 - Create React App==
- công cụ create react app. Nếu đang sử dụng node 8 hoặc 10 -> npx create-react-app 3-create-react-app <- Tên project sẽ tạo
==6 - Component==
- Cách tạo component trong react app. Component được sinh ra để viết UI kết hợp nhiều thẻ khác nhau.
- Để tạo 1 component thì phải tạo 1 folder component trong thư mục src. Trong thư mục component tạo file [tên component].js, trong file này chúng ta `import React, { Component } from 'react'`, sau đó tạo class [tên component] extends Component {}, tạo một method render() bên trong class, method này sẽ được gọi khi ta render component, render này sẽ return những element mà ta muốn sử dụng.
- Muốn dùng component trong app thì phải import component nó vào app, để import được thì component phải export, nên ở cuối component phải export default [tên component]
- Component hay ở cái là có thể nhóm nhiều thứ bên trong, có thể compound nhiều component lại với nhau thành component nhỏ, nhiều component nhỏ thành component lớn
- Component là một cách để tái sử dụng UI trong dự án.
==7 - Props==
- Các component có thể nhận vào các props khác nhau.  Các truyền props vào component <Tên component [biến]=[giá trị truyền] />, các giá trị truyền vào sẽ được lưu trong biến props, có thể truy xuất qua biến this.props.[tên biến đã truyền].
- Có thể truyền bất cứ giá trị gì cho props, nếu muốn truyền 1 object phải có {object muốn truyền vào}
==8 - Render a list==
- Lưu dữ liệu ở constructor function của component (trường hợp class component), trường hợp function component thì khai báo biến. Sử dụng map để biến 1 object thành một mảng các JSX component
- Khi sử dụng hàm map để render thì react yêu cầu phải có key để xác định đối tượng (sử dụng cho việc làm animation), callback function của map có thể nhận 1 tham số hoặc 2 tham số, nếu 2 tham số thì tham số thứ 2 là index của value => sử dụng key = {index} để thiết lập key cho object.
==9 - React Developer Tools==
- Giúp debug app react dễ dàng hơn, cài plugin React Developer Tools dành cho chorme, hoặc firefox
- Nó sẽ có thêm 1 tab react ở chorme develop tool
==10 - Dynamic class names==
- Thêm nhiều class một cách linh hoạt cho các component. Cách 1 đặt 1 biến tên className, nếu có sự thay đổi giá trị truyền vào thì biến đó sẽ + thêm string class tương ứng giá trị truyền vào.
- Ngoài ra còn có cách là sử dung classnames npm
==11 - Conditional rendering==
- Cách render các element dựa vào các điều kiện khác nhau.
- Sử dụng toán tử && để check điều kiện falsy && anything => false, truly && anything => anything.
==12 - State==
- State là trạng thái nội tại bên trong một component
- Khi state thay đổi thì render sẽ thay đổi cho nên cần chú ý.
==13 - Handling events==
- Trong HTML DOM để xử lý sự kiện thì sẽ thêm vào onClick, nó sẽ nhận vào một hàm, khi nào người dùng click vào ui thì những gì trong onClick sẽ được gọi như một hàm, onClick mặc định sẽ nhận một biến event.
- onClick={this.function} => báo lỗi do khi onClick chạy thì this.function sẽ chạy như một hàm => mất this. để xử lý thì sử dụng arrow function onClick= {()=> {this.function}} hoặc khai báo trong constructor () { this.function = this.function.bind(this)}. Không được truyền function() vì nó sẽ truyền vào giá trị trả về của hàm vào trong onClick
==14 - Immutability== 
- Immuatability : Bất biến - Trong lập trình thì là khả năng không thay đổi trạng thái của object nào đó. mutate (v) : thay đổi trạng thái bên trong VD a = {a : 1} => a = {a : 2} => a bị mutate. mutable object => nghĩa là object có thể thay đổi được. mutability => khả năng có thể thay đổi trạng thái bên trong, ngược lại immutability không có khả năng thay đổi trạng thái bên trong.
- Nắm vững thì sẽ điều khiển được app, tăng performance, vd có 2 function cùng nhận vào một biến a, 1 trong 2 function hoặc cả 2 làm mutate biến a => làm khó theo dõi kết quả, đôi khi bug không biết lỗi ở đâu.
- VD a = [2, 1, 3], a.sort => [1,2,3] = có thể nói a đã bị mutate thay đổi trạng thái bên trong
- Method thay đổi chính nó => làm cho chương trình khó đoán kết quả hơn.
- Để thay đổi các property trong 1 object và trả về một object khác object ban đầu. VD: Array thì có method như concat hoặc c = [...b, 4] hoặc [4,...b] hoặc c = b.slice(), chèn 4 vào giữa c = [...b.slice(0,2),4,...b.slice(2)]=> tạo ra một array mới
- Object thì sử dụng Object.assign({}, obj) hoặc c = {...obj} => vấn đề là cả 2 phương thức này chỉ là shallow copy. Để giải quyết vấn đề thì sử dụng 2 hoặc nhiều toán tử spread, mỗi toán tử phụ trách một obj vd obj cha, obj hoặc array con hoặc chuyển nguyên obj sang JSON xong chuyển ngược lại.
- Giá trị kiểu Primitive (String, boolean, number,...) bản thân là immutable rồi
==Thêm ảnh vào react== 
- sử dụng import [tên ảnh] from 'path'
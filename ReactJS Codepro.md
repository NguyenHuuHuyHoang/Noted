==Review==

1. Component thật ra là một thành phần UI + data: chia sao để tái sử dụng, bao gồm code HTML, bao gồm code JS có thể đan xen HTML, có file css cho component. Học tạo cách tạo component, chia component, tổ chức và cách sử dụng.
2. Có 2 loại: StateLess (Less không có) và Stateful. Stateful -> có state và component lifecycle (Vòng đời của một component)
3. Luồng đi: từ file HTML -> JS -> ReactDom -> Hàm render
4. App.js là component chính
5. Event Binding: 
- nghĩa là các phương thức trong lớp;
- Khi gọi sự kiện : 
+ Không tham số:
* Sử dụng con trỏ this. tên phương thức của lớp*
* Nếu phương thức có gọi this bên trong -> this. tên phương thức của lớp. bind(this)
+ Có tham số:
* this.tên phương thức của lớp. bind(this, tham số 1, ....).
- Chú ý phương thức render:
+ Đây là phương thức đặc biệt, có code gì trong đó thì nó hiển thị ra trình duyệt cả
+ Nó phụ thuộc thêm thứ nữa là state (Trạng thái, có nghĩa là sự thay đổi).
6. Xử lý If else, vòng lặp trong jsx
- Để xử lý nội dung có được render ra giao diện hay không ta sử dụng phép toán điều kiện 3 ngôi : Biểu thức ? Nội dung render ứng với đk đúng : Nội dung render ứng với điều kiện sai
- Để render nội dung jsx ra giao diện dưới dạng mảng ta dùng các hàm hỗ trợ của es6 như map, filter,....: cú pháp render: return Array.map ((item,index)=>{return Nội dung JSX})
7. Props
- Props là thuộc tính mặc định của component để chứa các dữ liệu được truyền vào từ component cha, tương tự kỹ thuật input ở Angular.
- Props của component chỉ nhận các thuộc tính được truyền vào từ component cha của nó và không thể bị chỉnh sửa bên trong component.
- Đối với stateful và stateless component có các cách sử dụng props khác nhau.
- Đối với stateful props nhận giá trị thông qua thuộc tính this.props của component. Đối với stateless component props sẽ nhậ nthông qua param truyền vào component.
- ở React để lấy giá trị từ 1 sự kiện bên trong component con ta sẽ truyền 1 callback qua props, component con sử dụng callback ấy gắn vào sự kiện để mỗi lần event thực thi tại component con sẽ gửi giá trị đến component cha nơi truyền callback.
8. React lifecycle
- React lifecycle mô tả vòng đời của 1 component trong ứng dụng. Bao gồm thứ tự các hàm chạy ở các mốc thời điểm của component.  Trong React, VueJS, Angular điều có lifecylce.
- Mounting:
+ componentWillMount
+ render
+ componentDidMount
- Updation:
*Props*
+ componentWillRecieveProps
+ shouldComponentUpdate
+ componentWillUpdate
+ render
+ componentDidUpdate
*States*
+ shouldComponentUpdate
+ componentWillUpdate
+ render
+ componentDidUpdate
- Unmounting:
+ componentWillUnmount
9. Redux
- Bản chất làm việc với React là việc truyền dữ liệu giữa các component và thay đổi state để re-render lại giao diện component.
- Redux là thư viện cung cấp cho ta một store trung tâm, lưu trữ tất cả các state, từ component muốn thay đổi state chỉ cần truy cập tới store thay đổi.
- Redux bao gồm 3 thành phần chính:
+ Action: là nơi mang các thông tin dùng để gửi từ ứng dụng đến Store. Nói dễ hiểu, từ 1 component muốn thay đổi state trên store, ta phải gửi action, là một object để miêu tả muốn làm gì.
+ Reducer: Nơi tiếp nhận action và thay đổi state.
+ Store: Nơi quản lý và lưu trữ state.
- 2 phương thức chính của Redux là:
+ mapStateToProps: phương thức lấy giá trị state từ store về tạo thành 1 thuộc tính của component.
+ mapDispatchToProps: phương thức tạo ra sự kiện để đưa giá trị từ component lên store thông qua action.
10. Routing (react-router-dom)
- Routing là cơ chế trong single page giúp ta chuyển đổi qua lại giữa các component, nhưng không làm cái trang load lại toàn bộ, nó chỉ load lại phần nội dung cần thiết thôi.
- Các thành phần trong routing:
+ BrowserRouter, Router, Swich: Các thành phần định nghĩa trong route.
+ NavLink, Link: Dùng để chuyển đổi link qua lại giữa các component (Giống thẻ a nhưng không reload lại trang)
+ History (push, replace): cung cấp các phương thức chuyển đổi route.
+ Match: Cung cấp một số thuộc tính hỗ trợ path hiện tại, trong đó bao gồm việc giúp lấy tham số từ url
+ Redirect: Giúp điều hướng từ path này đến path khác tương tự history nhưng có thể định nghĩa được trong phần render (JSX)
+ Prompt: Cho phép người dùng xác định trạng thái có được phép rời khỏi component đó hay không.
11. HOOK
- Hook là khái niệm dùng để thay thế react lifecycle trong react class component dành cho react functional component. Giúp code ngắn hơn clean nhanh hơn. Giảm bớt các khái niệm về hướng đối tượng, thuộc tính, phương thức,...
- Hook ra đời đầu năm 2019.
- Một số hook cơ bản:
+ UseState: Dùng thay thế state và setState react class component.
+ UseEffect: Hàm thay thế react lifecycle componentDidMount, DidUpdate, WillUnmount.
+ UseCallBack: Hàm tương tự lifecycle shouldComponentUpdate trong pureComponent trong react class component.
+ UseMemo: Tương tự useCallback nhưng kết quả trả về là một giá trị.
+ UseContext: Tương đương contextprovider.
==Cấu trúc dự án==
- quan trọng nhất là thư mục public: 
+ favicon.ico là logo của ứng dụng React.
+ index.html: là file html duy nhất.
+ logo192, logo512 : logo size 192x192 / 512 x 512
+ manifest.json: short_name: Tên của dự án, nếu đặt short name thì sẽ lấy short name không thì sẽ lấy name
- thư mục src: 
+ index.js: là file js chạy gắn liền với index.html khi ứng dụng được start, nhiệm vụ sẽ DOM tới thẻ root và đưa vào 1 tag component gốc của ứng dụng (App component)
==Luồng đi của ứng dụng==
- nên cái extension snippet React và HTML to JSX
- Browser sẽ đọc được trang index.html -> đọc file index.js, trong file này ReactDom được sử dụng để render nội dung của app component ra div root ở ngoài HTML. App.js chính là component gốc của toàn ứng dụng.
==Component==
- Component biểu diễn giao diện UI (file.html), nói một cách đơn giản 1 component là 1 thẻ do mình định nghĩa trong thẻ đó chứa các nội dung html do mình biên soạn.
- Cấu trúc của 1 component: là tập hợp những cái thẻ đế đóng gói thành 1 thẻ component, và sử dụng, tái sử dụng thẻ đó nhiều lần.
- Có 2 loại component: Stateless component (functional component) và Stateful component (class component)
==React functional component==
- rfc để tạo 1 functional component. Lưu ý khi tạo ra 1 component thì nó là 1 function, bên trong sẽ chứa lệnh return, nó không return về 1 tham số, biến đối tượng hoặc hàm mà return 1 dấu () bên trong chứa nhiều thẻ, nội dung bên trong luôn luôn chỉ được bao phủ bởi một thẻ duy nhất, muốn lồng bao nhiêu thẻ vào trong cũng được.
- Khi import thì chữ cái đầu tiên phải viết hoa để phân biệt được tag giữa HTML bình thường với tag là React component.
==React class component==
- rcc để tạo 1 class component. React class component là một lớp đối tượng, nó có 2 thành phần là thuộc tính và phương thức, trong khi function thì không có gì cả, nó cho phép định nghĩa các thuộc tính và phương thức. Và cái lớp này được xem là một React component.
- Nội dung thẻ được định nghĩa trong hàm render.
- Phạm vi của biến chỉ hoạt động trong hàm thôi, còn thuộc tính hoạt động trên tất cả các hàm của lớp đối tượng.
==Databinding React==
- JSX cho phép ta lồng JS vào HTML thông qua dấu { tên biến chứa giá trị cần truyền }, nó cho phép người dùng chèn các giá trị trực tiếp lvào các thẻ, thay vì phải DOM tới div đó rồi truyền giá trị. Để truy xuất thuộc tính của chính đối tượng đó thì sử dụng con trỏ this.tên thuộc tính.
- title, produceName, renderProduct,... jsx cho phép chúng ta có thể render biến chuỗi hàm,.. tại phần nội dung miễn kết quả trả về là 1 đoạn JSX (cách viết HTML và JSX kết hợp)
- JS sẽ được parse và hiển thị ra chung với html.
==Event React==
- Các sự kiện onClick, onChange, onSubmit... trong JS điều có thể sử dụng trong react. Tuy nhiên sẽ có khác biệt về cú pháp => Tham khảo ví dụ bên dưới
- Cú pháp: suKien= {callback function} => Sự kiện là các sự kiện nêu trên, callback function là 1 function để xử lý cho sự kiện đó, lưu ý callback function gán vào không có 2 dấu ().
- Trường hợp muốn truyền tham số thì sử dụng .bind(this, tham số truyền vào) - Tham số đầu tiên luôn luôn là con trỏ this.
- Arrow function thì suKien={()=>this.function(tham số truyền vào)}
==Khái niệm về closure function==
- Là kỹ thuật viết hàm lồng trong hàm. hàm cha sẽ nhận vào 1 tham số, return về hàm con sử dụng tham số của hàm cha để xử lý 1 logic nào đó,  kết quả nhận về sau khi goi hàm cha là 1 cái hàm, muốn kích hoạt cái hàm này thì sử dụng 2 dấu().
- Thông thường người ta sẽ tạo 1 biến để chứa cái hàm được trả ra từ hàm cha, sau đó mình gọi cái biến đó + ()
- Cách viết này sẽ giúp cho hàm bên trong sử dụng các tham số ở ngoài cùng hoặc của hàm chính hoặc là bên trong nó luôn. Mình có thể sử dụng phương pháp này để truyền callback đi và gửi dữ liệu vào bên trong cái hàm đó. Callback không được truyền tham số, tuy nhiên chúng ta có thể sử dụng kỹ thuật này bằng cách truyền tham số thông qua hàm con. ![[Pasted image 10.png]]
- Ứng dụng rất là nhiều trong React.
==Cấu trúc điều khiển If else==
- Kết hợp if else và hàm để xác định nội dung cần hiển thị trong react, bằng cách xây dựng một hàm bên trong sử dụng lệnh if else để tùy biến nội dung jsx được render ra giao diện, giá trị trả về khi thỏa điều kiện là return 1 chuỗi JSX để render ra giao diện.
- Ngoài ra mình cũng có thể sử dụng toán tử 3 ngôi để xác định phần nội dung hiển thị trực tiếp trên hàm render (chuỗi JSX)
==Làm việc với thuộc tính State, phương thức SetState và ReRender==
- State là một thuộc tính mặc định của class kế thừa từ component để quản lý trạng thái của component.
- Mỗi khi state thay đổi, thì hàm render sẽ được gọi chạy lại. Lưu ý: muốn component render lại ta phải thay đổi state thông qua phương thức setState chứ không được gán trực tiếp.
- Phương thức setState là 1 phương thức bất đồng bộ, có 2 tham số:
+ Tham số 1: giá trị state mới
+ Tham số 2: callback thực thi ngay sau khi state thay đổi.
Lưu ý: Không được set lại state theo cách: this.state.thuocTinh = giá trị. Ta set giá trị của state thông qua phương thức setState. this.setState({thuocTinh: giá trị mới}), sau khi setState thì component sẽ được render lại.
- Trong class component sẽ luôn có constructor(props) { super(props); this.state = {}} - Đây là thuộc tính có sẵn của component, nó chứa các thuộc tính có khả năng thay đổi bới một sự kiện nào đó của component, cái nào có khả năng thay đổi mới đưa vô. Truy cập bằng cách this.state.tên thuộc tính.
- setState là phương thức có được kế thừa từ class component, nó giúp thay đổi giá trị state và gọi hàm render lại giao diện. Đây là phương thức bất đồng bộ, khi gọi cái hàm sẽ mất một khoảng thời gian để xử lý.
==Render giao diện với mảng dữ liệu dùng vòng lặp==
- Để tạo ra các tag html (jsx trong react) thì ta có rất nhiều cách thực hiện, dùng các hàm như for, foreach, map.... tạo nội dung. Khi sử dụng cần phải return về một mảng hoặc đối tượng JSX thì mới render ra nội dung được.
- Khi tạo dữ liệu động dựa vào các tag JSX thì cần phải đặt key, để react quản lý các đối tượng JSX được tạo ra từ vòng lặp.
- Mục đích của vòng lặp là từ một mảng dữ liệu, tạo ra các thẻ JSX tương ứng để hiển thị ra giao diện.
- Hàm map trả về 1 mảng, do đó có thể sử dụng hàm map để tạo ra một mảng các JSX mang giá trị của mảng data cũ.
- Khi return nếu không có () thì phải đặt JSX ngay sau return không được xuống dòng, nếu return ( thì xuống dòng thoải mái)
- source bt: github.com/khaitruong1301/react_video
==React Props==
- một cái tag HTML là một object, vì vậy nó có thuộc tính và phương thức, thay đổi giá trị thuộc tính -> giao diện thay đổi.
- 1 component là một thẻ đặc biệt do mình tạo ra, nó cũng chứa thuộc tính và phương thức
- Props là thuộc tính của thẻ (Ta có thể hiểu prop là property của thẻ).
- Props là thuộc tính mặc định của component để nhận dữ liệu từ các giá trị component cha truyền vào => Để binding dữ liệu ra component con tại html tương ứng.
- Props của component chỉ nhận các thuộc tính được truyền vào từ component cha của nó và không thể bị chỉnh sửa bên trong component.
- Đối với stateful và stateless component có các cách sử dụng props khác nhau.
- truyền prop từ cha sang con bằng cách title={giá trị truyền}, ở con thì gọi ra bằng cách this.props.title để lấy giá trị được truyền từ cha, đổi với react functional thì nó sẽ nhận props thông qua tham số truyền vào, trường hợp nếu biết được tên thuộc tính truyền vào có thể sử dụng restParam vd function Phim_RFC({phim_input,...restParam}) => khi đó không cần đặt tên biến đế lấy dữ liệu từ props mà có thể sử dụng luôn.
- this.props là biến toàn cục cho nên gọi ở đâu cũng được.
==React Prop Callback Function==
- Thay vì truyền mảng hay object thì chúng ta truyền một function, nhằm mục đích truyền dữ liệu từ con sang cha.
- Xác định dữ liệu thay đổi + Dữ liệu đó sẽ thay đổi khi nào => Đặt dữ liệu đó ở đâu
==Redux==
- Bản chất làm việc với React là việc truyền dữ liệu giữa các component và thay đổi state để re-render lại giao diện component
- Redux là thư viện cung cấp cho ta một store trung tâm, lưu trữ tất cả các state, từ component muốn thay đổi state chỉ cần truy cập tới store để thay đổi.
- Cấu trúc của redux: 
+ Action: là nơi mang các thông tin dùng để gửi từ ứng dụng đến store. Các thông tin này là một object mô tả những gì đã xảy ra. Nói dễ hiểu, từ 1 component, ta muốn thay đổi state trên store, ta phải gửi action, là một object để miêu tả muốn làm gì.
+ Reducer: Nơi tiếp nhận action và thay đổi state gồm 2 loại:
	+ Root Reducer: là Boss, quản lý tất cả reducer con
	+ Child Reducer: như đã biết về state, state là một object có nhiều thuộc tính, mỗi child reducer chịu trách nhiệm thay đổi 1 thuộc tính trong state.
+ Store: Nơi quản lý và lưu trữ state (Chính là Big Boss).
==Setup Redux==
- npm i redux 
- npm i react-redux - dùng để kết nối redux store với react
- src -> redux -> reducers -> rootReducer.jsx :
+ import {combineReducers} from 'redux';
+ export const rootReducer = combineReducer ({
+  nơi sẽ chứa các reducer cho nghiệp vụ (store con)
+ })
- index.js :
+ import {Provider} from 'react-redux'
+ import {createStore} from 'redux'
+ import {rootReducer} from './redux/reducers/rootReducer'
+ const store = createStore(rootReducer)
+ Bọc App component trong Provider component, trong Provider component có thuộc tính store={store}
- tạo reducer con:
+ const stateGioHang = {
+ giá trị ban đầu theo dạng key: value
+ }
+ export const GioHangReducer = (state=stateGioHang, action) => {
+ return {...state}
+ }
+ ở rootReducer import và khai báo vào trong thân GioHangReducer:GioHangReducer
- Trong component cần lấy dữ liệu từ redux:
+ import {connect} from 'react-redux'
+ Xóa export default của component
+ const mapStateToProps = (state) => { //state: là store tổng => truy xuất đến GioHangReducer => biến state trên GioHangReducer
+ return {  
+ gioHang: state.GioHangReducer.gioHang
+ }
+ }
+ export default connect(mapStateToProps, null)(Tên component hiện tại)
+ Như vậy trong component sẽ có thuộc tính this.props.gioHang là thuộc tính nhận từ redux
- Để thay đổi dữ liệu trên store:
+ import {connect} from 'react-redux'
+ Xóa export default của component
+ const mapDispatchToProps = (dispatch) => {
	+ return {
		+ themGioHang: (sanPham) => { // Tạo ra props component là function để đưa dữ liệu lên store
			+ const spGioHang = {
				+ maSP: sanPham.maSP,
			+ }
			+ const action = { //Tạo action đưa dữ liệu lên reducer
				+ type: 'THEM_GIO_HANG, //bắt buộc đặt type
				+ spGioHang: spGioHang //Nội dung gửi lên reducer
			+ }
			+ dispatch(action) //Dùng hàm dispatch đưa dữ liệu action lên reducer.
		+ }
	+ }
+ }
+ export default connect(null, mapDispatchToProps)(tên component)
+ Để sử dụng ta gán this.props.themGioHang vào nút thêm giỏ hàng
+ Action sẽ được dispatch lên toàn bộ reducer trên store tổng.
+ Trong file reducer GioHang xử lý switch dựa trên loại action dispatch lên, trong case xử lý xong phải return về một state mới 
==Redux Dev Tools==
- phải cài addon redux dev tool trên chorme hoặc firefox để xem
- window.__REDUX_DEVTOOLS_EXTENSION__ && window.__REDUX_DEVTOOLS_EXTENSION__()
- copy đoạn trên vào createStore thành
- const store = createStore(rootReducer,  window.__REDUX_DEVTOOLS_EXTENSION__ && window.__REDUX_DEVTOOLS_EXTENSION__())

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
==React Form - validation==
- Khác với JS ta thường sử dụng đế lấy giá trị thông qua 1 tag input ta phải thực hiện DOM qua các selector sau đó truy xuất đến thuộc tính value để lấy giá trị... mất khá nhiều thao tác. Tuy nhiên: trong react chúng ta sẽ sử dụng thuộc tính state của component kết hợp cùng các sự kiện của control input để thực hiện việc lấy dữ liệu từ form dễ dàng hơn.
- Trong Component Form tạo 1 state chứa các thuộc tính với key là tên input và value là rỗng, mỗi khi người nhập nhập input sẽ kích hoạt onChange nhận một sự kiện event từ đó sẽ gán giá trị nhập vào object đó thông event.target, input sẽ lấy dữ liệu binding từ this.state về.
- input trong form đặt tên thuộc tính name trùng với tên thuộc tính của đối tượng, ở value thì lấy từ state xuống. khi sử dụng name thì chúng ta có thể set object động thông qua *name* đặt trong ngoặc vuông : value (name và value chúng ta bóc tách ra từ event.target)
- form có 2 cách submit: 1. đặt thuộc tính của form onSubmit và ở button đặt type là submit thì người dùng nhập xong enter thì browser sẽ tự kích hoạt nút Submit, 2. đặt onSubmit ở button ở form để trống, thì phải click vào nút button, enter nó không chạy.
- thẻ form thường có tình trạng sẽ reload lại trang khi submit thông qua form, do đó chúng ta cần phải bắt sự kiện event.preventDefault() nhằm cản sự kiện submit reload trang của browser. Các hàm xử lý logic khi submit sẽ nằm ở bên dưới.
- Trong state ở component thêm 1 object errors để lưu trữ những lỗi, tận dụng name chung với object lưu dữ liệu input. Trong khi handleChange input thì kiểm tra giá trị nhập vào, nếu lỗi thì push lỗi vào 1 biến chứa lỗi, kiểm tra hết thì cập nhật lỗi vào object errors để hiển thị ra màn hình. Chú ý sử dụng deep copy. Sau đó setState lại cho values và errors để render lại.
- Để kiểm tra bằng regex chúng ta sử dụng theo cú pháp. (regex.test(value)) => trả về true hoặc false. Chuỗi regex phải đặt giữa 2 dấu / /
- Trong HTML5 hỗ trợ thuộc tính pattern, những chuỗi regex sẽ đưa vào thuộc tính này, sau đó khi input ta sẽ bóc tách pattern lấy giá trị regex xong sử dụng new RegExp(pattern) để convert giá trị string thành chuỗi regex rồi so sánh.
- Trong trường hợp 1 trong các thuộc tính của errors có giá trị, chỉ cần 1 thằng bị lỗi thì nút submit sẽ ở trạng thái disabled hoặc ở lần đầu tiên chưa nhập gì hết. Sử dụng 1 flag trong state để điều khiển, mặc định = false. khi input xong thì sẽ quét tất cả các giá trị xem có lỗi không , có thì thay đổi biến flag để render lại nút submit. Chú ý cần phải kiểm tra dữ liệu của tất cả ô input , tránh trường hợp người dùng nhập 1 ô những ô còn lại chưa nhập nhưng nút submit vẫn hiện.
==LifeCycle getDerivedStateFromProps==
- là mỗi lần component nó render lại thì getDerivedStateFromProps sẽ được chạy lại, nó sẽ so sánh props truyền xuống và state trước đó nếu giá trị thay đổi thì đặt state = props truyền xuống, nếu giá trị truyền không thay đổi thì vẫn giữ nguyên state cũ. Thường sử dụng trong việc props thay đổi thì state thay đổi.
- trong react component được render lần đầu khi được gọi và chỉ render lại khi thay đổi state và khi thay đổi dữ liệu trên store.
==LifeCycle==
- Trong React có tổng cộng 16-17 lifecycle, chỉ những class component mới có component, functional thì không có. Chúng ta phải quản lý khi nào component được render lại để tăng vấn đề hiệu suất.
- 2 Loại lifecycle chính là creation và update. creation là những hàm tự động khởi chạy khi component được xây dựng lên. update là những hàm tự động chạy mỗi khi component được cập nhật lại.
- Creation: constructor(), componentWillMount(), render(), componentDidMount() sẽ tự động chạy theo thứ tự trên. 
- componentDidMount(): Khi muốn vừa load trang lên fetch dữ liệu từ server về hiển thị trên màn hình, hoặc muốn viết 1 logic thực hiện khi component được khởi tạo. Tại sao không viết hàm còn lại vì muốn tăng hiệu suất trang web lên, nó chạy sau render vì vậy sau khi giao diện đã render xong nó chạy thì sẽ không ảnh hưởng đến việc render -> làm cho trang web có cảm giác load nhanh hơn vì giao diện đã có sẵn rồi, sau đó nó mới chạy logic. Cấm kị việc fetch data trong render vì sẽ gây ra lặp vô tận. ở phiên bản 17++ thì những lifecycle có chữ will sẽ bị bỏ hết và nếu bỏ trong will mount thì giao diện sẽ bị giật, do đang fetch dữ liệu trả về trong khi render đang chạy được giữa chừng sẽ bị force render lại
- Update: componentWillRecieveProps(), shouldComponentUpdate(), componentWillUpdate(), render(), componentDidUpdate().
- componentWillRecieveProps(nextProps): để so sánh props cũ và props mới để xử lý vấn đề gì đó, nếu thay đổi thì làm gì đó.
- shouldComponentUpdate(nextProps): nếu trả về false thì component sẽ không render lại, nó sẽ quyết định khi nào component sẽ được update khi nào không. VD thằng child nó không có state thì khả năng nó render lại phụ thuộc vào cha, cha render lại thì con render theo => check this.props với nextProps nếu khác thì true, nếu không thì false. Trường hợp có khoảng 15 cái props, chục cái state => nếu không muốn code quá dài thì sử dụng PureComponent, child sẽ extends PureComponent thay vì Component, nó tự động check khi nào child thay đổi thì nó sẽ tự động render lại không thì nó sẽ không render -> PureComponent bị vấn đề giống redux là sử dụng shallow comparison, nếu props truyền vào là 1 số hay chuỗi thì check rất dễ, nếu truyền vào 1 object thì nó sẽ không nhận biết được sự thay đổi, do đó khi xử lý với object và array thì phải cẩn thận.
- componentWillUpdate(nextProps, nextState)
- componentDidUpdate(prevProps): nó chạy sau render, sau khi mọi thứ đã update rồi thì nó mới chạy, nếu gọi this.props trong nó thì là props mới, nếu muốn lấy props cũ check gì đó thì có thể gọi prevProps để check.
==React HOOK==
- Tại sao sử dụng class mà không dùng function vì class có State, function không có, class có lifecycle, function không có.
- Công dụng chính của React HOOK là cho chúng ta sử dụng lifecycle và state trong functional component. Toàn bộ dự án hiện giờ có xu hướng chuyển sang function component chứ không sử dụng class nữa, vì khái nhiệm class, OOP, con trỏ chuột, this hơi khó đối với một số lập trình viên.
==UseState==
- import {useState} from 'react'
- const [ count, setCount] = useState( giá trị mặc định ban đầu)  //Do useState sẽ trả về 1 cái array, count là biến state, mỗi lần count thay đổi giao diện sẽ load lại (tên tự đặt), setCount là một hàm dùng để set lại giá trị cho biến count.
- khai báo function trong functioncal component phải có từ khóa khai báo biến vì nó là hàm chứ không phải phương thức.
- trong một component có nhiều state thì tạo ra nhiều useState.
==UseEffect==
- Công dụng là sử dụng lifecycle trong function component,  import {useEffect} from 'react'
- để sử dụng useEffect thì gọi nó ra và truyền vào nó một function, code ở bên trong cái hàm này sẽ được chạy khi component được tạo, cập nhật và bị hủy. Nó đại diện cho 3 cái lifecycle là didMount, didUpdate, willUnmount.
- lần đầu tiên thì tất cả useEffect điều chạy dù có truyền tham số mảng vào hay không.
- Một component có thể có nhiều useEffect, thứ tự chạy là từ trên xuống dưới. Để component chỉ chạy 1 lần đầu tiên thôi thì truyền thêm 1 tham số là array rỗng === componentDidMount
- Trường hợp truyền mảng chứa các giá trị vào useEffect thì khi nào các giá trị đó thay đổi thì useEffect mới chạy lại. Nó sẽ có công dụng vào việc lần đầu tiên đăng nhập vào thì xuống local lấy token lên để kiểm tra có đăng nhập hay chưa, có token rồi thì mới fetch data. Khi nào token thay đổi thì mới tiến hành fetch data. Hoặc trường hợp location, yêu cầu user phải có location (geolocation.getCurrentPosition() - đây là một hàm bất đồng bộ) lên sau đó mình mới fetch về những cửa hàng gần user đó. Trường hợp sử dụng class thì phải sử dụng cả didMount để fetch localtion và khi localtion về rồi thì dùng didUpdate để hứng nó và gọi tiếp.
==memo==
- Để sử dụng shouldComponentUpdate hoặc PureComponent thì sử dụng memo thay thế, import {memo} from 'react'
- ở phần export default bọc component trong memo(tên component)
- memo đảm bảo component chỉ render lại trong trường hợp props thay đổi.
==useCallback==
- Trường hợp truyền một function cho child, theo lý thuyết, function không thay đổi nhưng thực tế nó lại render lại lý do vì khi component chứa function render lại thì toàn bộ các hàm điều được tạo mới 1 lần nữa do đó child render lại => ảnh hưởng đến performance của trang web => sử dụng useCallback
-  import {useCallback} from 'react'
- useCallback nhận vào 1 cái hàm và trả ra một bản sao của cái hàm đó
- vd const increaseCountCallback = useCallback( () => increaseCount, *array rỗng thì nó chỉ sao chép 1 lần đầu tiên*) | increaseCountCallback tương đương increaseCount. increaseCountCallback sẽ không thay đổi trong suốt quá trình dù component có render lại hay không, vì nó chỉ sao lần đầu tiên thôi.
- Đối với 1 số trường hợp logic trong function có sự thay đổi giá trị thì nếu cho sao chép lần đầu tiên thì giá trị của các logic đó sẽ bị đứng lại, nếu chúng ta sử dụng thì vẫn ra giá trị khi copy, do đó cần phải truyền các tham số cần theo dõi vào mảng để khi các tham số đó thay đổi thì function sẽ được copy lại theo giá trị mới.
==BT-Redux==
game đổ xúc xắc: https://drive.google.com/drive/folders/1cFlPw51YzVfUa-c4FDQoEz6QL4V3O_Xx  ![[Pasted image 11.png]]
game oẵn tù xì: https://drive.google.com/drive/folders/1RWZN4o2NFiBIxMIdPbS_j-f_hsQX7_Oq ![[Pasted image 12.png]]
Font sử dụng: Pony
==Axios==
- npm i axios --save => import Axios from 'axios';
- Gọi axios trong componentDidMount. mà componentDidMount là hàm chạy sau render -> sau khi render xong rồi mới lấy dữ liệu về, dữ liệu lấy về cũng không sử dụng được do đã render xong -> xử lý cho component render lại.
- hàm axios nhận vào 1 object chứa, method: 'GET' và url: đường dẫn do BE cung cấp. Trả ra 1 promise giống như Ajax trong jquery để chúng ta handle khi nào dữ liệu trả về. 
- .then khi server trả về dữ liệu thành công, hàm .catch trả về khi server trả về thất bại. cả 2 cái này điều nhận vào 1 hàm.
- các loại method là: 
	+ GET: lấy dữ liệu về
	+ POST: tạo dữ liệu mới
	+ PUT: ghi đè dữ liệu đã có
	+ PATCH: cập nhật từng phần của dữ liệu
	+ DELETE: xóa phần tử.
- axios được xây dựng theo kiểu bất đồng bộ, cho nên trong khi gọi lên server thì code vẫn tiếp tục chạy phòng trường hợp server đứng hay chết thì code bị block tại chỗ đó.
==Phần đăng ký==
- Muốn thêm 1 người dùng mới vào hệ thống chúng ta phải tạo 1 user chứa những thông tin mà BE cần, sau đó gửi cho BE để tạo user mới.
- Đăng ký thì chỉ là user thôi còn admin thì sẽ được cung cấp nên phần loại người dùng sẽ đặt mặc định là người dùng.
==Xử lý form với thư viện Formik==
- npm i formik --save, import {Formik, Form, Field} from 'formik'
- Gọi Formik, trong đó nó sẽ có 1 phương thức là render là 1 cái hàm nó nhận vào 1 cái formikProps, trong formikProps thì Formik đã xây dựng sẵn một số hàm để chúng ta xử lý form như hàm onChange, toàn bộ cái giao diện sẽ return trong đó (paste toàn bộ form vào trong đó bao gồm tag form). Trong cái Formik có 1 cái props là initialValues là 1 object, nó nhận giá trị ban đầu, mình muốn object trả ra từ form sẽ có những dữ liệu gì sẽ được định nghĩa trong đây.
- gắn onSubmit vào Formik, khi ta submit muốn làm gì thì gắn vào. hàm onSubmit nhận vào 1 function do ta tự định nghĩa, giá trị nhận vào mặc định là values của cái form.
- các input trong form phải có cái name trùng với các key đã khai báo trong initialValues, và gắn formikProps.handleChange vào onChange của từng input. Thay các input bằng Field component
- thay vì dùng tag form sẽ dùng Form component của formik.
- trường hợp sử dụng select thì cần phải có thuộc tính component="select"
==Validation với thư viện Yup==
- Trước khi gửi dữ liệu lên server phải validation dữ liệu. Yup sẽ giúp chúng ta tạo ra một cái object mẫu, khi formik trả dữ liệu ra thì mình lấy object đó so sánh với bản mẫu mà yup tạo ra nếu nó khớp từng thuộc tính một đúng hết mọi thứ thì chúng ta cho submit.
- npm i yup --save, import * as yup from 'yup';
- Tạo bản mẫu: const signupUserSchema= yup.object().shape({
	taiKhoan: yup.string().required('*Field is required !'),
	matKhau: yup.string().required('*Field is required !'),
	hoTen: yup.string().required('*Field is required !'),
	email: yup.string().required('*Field is required !').email('* Email is invalid!'),
	soDT: yup.string().required('*Field is required !').matches(/^[0-9]+$/), (^ : bắt đầu, 0 - 9 chỉ nhận từ 0-9 và kết thúc phải là số)
	maNhom:yup.string.required('*Field is required !')
})
	- trong formik cũng cấp 1 cái thuộc tính là validationSchema={signupUserSchema}, trước khi chạy submit nó sẽ check cái validationSchema này trước, nó hợp lệ nó mới gọi hàm chạy.
	- Để show message ra màn hình thì formik cung cấp 1 component là ErrorMessage. Mình sẽ đặt nó ở dưới cái Field, khi Field bị lỗi thì cái ErrorMessage component có tên tương ứng với tên Field sẽ in ra lỗi, nó cũng sẽ check nếu người dùng đụng vào input mà bị lỗi mới hiện. Ngoài ra ErrorMessage còn nhận vào một thuộc tính là component, mình tự config 1 component lỗi rồi truyền cho nó. Hoặc nếu muốn config giao diện thì ở giữa đóng mở component viết 1 function và truyền vô, với giá trị nhận vào là msg là biến hiện lỗi.
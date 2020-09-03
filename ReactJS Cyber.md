- React là một thư viện của JS, hỗ trợ SPAs, tăng hiệu suất load trang. VD: FB - react, Youtube - angular, do chỉ load nội dung mà không load lại toàn bộ trang
- React viết trên ngôn ngữ ES6
- create-react-app [tên dự án]
- node_modules:  Chứa các thư viện cài đặt cho ứng dụng
- Đầu tiên trình duyệt sẽ đọc index.html và index.js sau đó sẽ index.js, trong file nãy ReactDOM sẽ được sử dụng để render nội dung của app component ra div root ở ngoài HTML thông qua điều hướng về App.js, ghi toàn bộ nội dung của App lên html.
- App.js chính la component gốc của toàn ứng dụng.
- Những thẻ do react tạo ra gần giống như HTML. 
==Cấu trúc dự án==
- node_modules: chứa những thư viện mà dự án sẽ đóng gói
- package.json: chứa những thư viện mà cài đặt trong dự án
- Quan trọng nhất là thư mục public: chứa các file như sau: favicon.ico chứa logo react, index.html - trong ứng dụng react chỉ duy nhất một file index.html (body chỉ chứa duy nhất 1 thẻ div#root), không còn 1 file html nào khác (SPA), load trang, chuyển trang đều xử lý bằng react, manifest.json chứa các thông tin định nghĩa của dự án vd: short name, name,.. thường được dùng để config trên app vì react có thể được chạy trên app (react native). 
- index.js là 1 file chạy gắn liền với file index.html, làm nhiệm vụ là DOM đến #root, nó sẽ đưa vào 1 tag App (component gốc của ứng dụng, toàn bộ nội dung của html sẽ được load ra từ tag đó, nó là tập hợp nhiều tag div để tạo nên 1 component), nó sử dụng bộ thư viện của react là reactDOM.render để đưa nội dung App vào thẻ div#root
- App.js chính là component gốc của toàn ứng dụng
==Component==
- Là tập hợp các thẻ div, input,.... để đóng gói thành một thẻ component, muốn đặt tên gì cũng được và tái sử dụng thẻ nhiều lần.
- Component thật ra là một thành phần UI + data:
+ Chia sao để tái sử dụng
+ Bao gồm code HTML
+ Bao gồm code JS có thể đan xen HTML
+ Có file css cho component
- Luồng đi: Từ file HTML => JS => ReactDom => Hàm render
- App.js là component chính
- Component biểu diễn giao diện UI (file.html)
- Là một thành phần của website, là một thẻ do mình định nghĩa, trong thẻ đó chứa các nội dung html do mình biên soạn
- Có hai loại component là class (stateful component) và functional  - stateless component(React Hook - Đầu 2019 ra), cả hai loại đều có hiệu suất ngang nhau, sử dụng loại nào cũng được. Class viết nội dung trong phương thức render , còn function thì viết nội dung không trong phương thức nào hết, nằm trong lệnh return.
- stateless component thực chất chỉ là một function, return về một đoạn mã HTML để hiển thị ra giao diện, không thể sử dụng được state và component lifecycle.
- stateful component (class component) thực chất chỉ là một class, kế thừa từ lớp component, có phương thức là render(), khi component được gọi, render() sẽ chạy và trả về đoạn mã HTML, có thể sử dụng được state và component lifecycle. 
- Thẻ react bắt buộc phải viết hoa chữ đầu tiên
- Component không được trùng tên trong dự án
==React Functional Component==
- snippet rfc
- là một function bình thường return về 1 đoạn nội dung bao gồm rất nhiều thẻ, nội dung luôn luôn được bao phủ trong 1 thẻ, nếu có 2 thẻ đồng cấp trở lên sẽ báo lỗi.
- Muốn sử dụng thẻ component thì chèn vô App.js, do component export default nên khi import sẽ không có {}, dù bên component export là gì nhưng khi Import thì phải viết hoa chữ cái đầu tiên để phân biệt với các tag html
==React Class Component==
- sinppet rcc
- Là một lớp đối tượng do đó có 2 thành phần là thuộc tính và phương thức, có thể định nghĩa thêm nhiều thuộc tính và phương thức, còn functional chỉ có biến.
- nó có phương thức render() để render giao diện, nội dung sẽ chứa trong return của render(). 
- Sử dụng thì giống như functional.
==React lifecycle==
- React lifecycle mô tả vòng đời của một component. Bào gồm thứ tự các hàm chạy ở các mốc thời điểm của component
==Cấu trúc JSX==
- Đoạn mã được return trong component tương đố giống HTML nhưng thực chất đó là jsx cho phép chúng ta kết hợp HTML và JS trên một source.
- class -> className, các thẻ khuyết đóng phải đúng cú pháp, bắt buộc phải có "/" VD: <img />
- For -> htmlFor. VD: <label htmlFor="dangnhap"></label>
- Khi lấy source code HTML từ nguồn khác, để sử dụng với react, ta cần convert ra thành jsx. https://transform.now.sh/html-to-jsx/ hoặc sử dụng extention html to jsx.
==Các tổ chức thư mục==
- Thư mục hình sẽ bỏ trong folder public
- Ở folder src sẽ chứa: 
+ Components: để chứa các component nhỏ lẻ cấu hình nên 1 trang: header, footer,...
+ Containers: chứa các component ở mức độ trang.
==Event Binding==
- Nghĩa là các phương thức trong lớp
- Khi gọi sự kiện :
+ Không có tham số : 
1. Sử dụng con trỏ this.<Tên phương thức của lớp>
2. Nếu sử dụng phương thức có gọi this bên trong -> this.<tên phương thức của lớp>.bind(this)
+ Không có tham số -> this.<tên phương thức của lớp>.bind(this, <tham số 1>,...)
- Chú ý phương thức render:
+ Đây là phương thức đặc biệt, có code gì trong đó thì nó hiển thị ra trình duyệt cả
+ Nó phụ thuộc thêm thứ nữa là state (Trạng thái, có nghĩa là có sự thay đổi)
- Các sự kiện onClick, onChange, onSubmit... trong js đều có thể sử dụng trong react. Tuy nhiên sẽ có những khác biệt về cú pháp.
- Cú pháp suKien={callbackfunction} => sự kiện là các sự kiện nêu trên, callback function là một function để xử lý cho sự kiện đó, lưu ý: callback function gán vào không có 2 dấu ().
- Trường hợp muốn truyền 1 callback function xử lý sự kiện có tham số : suKien={() => callbackfunction(param)} ta sẽ viết dưới dạng truyền 1 callbackfunction  và function đó sẽ trả về 1 function có tham số khi thực thi => Khi gọi function đó.
- Event Binding -> hay còn gọi là handle Event
- Những hàm xử lý sự kiện sử dụng arrow function.
==Xử lý if else, vòng lặp trong jsx==
- Để xử lý nội dung được render ra giao diện hay không ta sử dụng phép toán điều kiện 3 ngôi.
- Để render nội dung jsx ra giao diện dưới dạng mảng ta dùng các hàm hỗ trợ của es như map, filter,...
==Databinding reactjs==
- JSX là những đối tượng HTML, khi react biên dịch đến các đối tượng này thì sẽ tạo ra các thẻ HTML
- JSX cho phép ta lồng js trực tiếp vào HTML thông qua dấu { a }
- Để truy xuất thuộc tính trong phạm vi class thì sử dụng con trỏ this
- jsx cho phép chúng ta có thể render biến chuỗi hàm,... tại phần nội dung miễn kết quả trả về là một đoạn jsx
- js sẽ được parse và hiển thị chung với html.
- Nếu khai báo 1 thuộc tính thì phạm vi hoạt động trên tất cả các hàm trong class, nếu khai báo như một biến trong render() thì phạm vi hoạt động trong function
==Lệnh điều kiện trong jsx==
- Kết hợp if else và hàm để xác định nội dung cần hiển thị trong react.
- Bằng cách xây dựng một hàm bên trong sử dụng lệnh if else để tùy biến nội dung jsx được render ra giao diện. Ngoài ra mình có thể sử dụng toán tử 3 ngôi để xá định phần nội dung hiển thị trực tiếp trên hàm render.
==Stage==
- State là một thuộc tính mặc định của class kế thừa từ class component để quản lý trạng thái của component. 
- Mỗi khi state thay đổi, thì hàm render sẽ được gọi chạy lại.
- không được gán giá trị trực tiếp = cho stage mà phải thực hiện thông qua phương thức this.setStage(newState) : phương thức của component thay đổi giá trị state hiện tại và render lại giao diện
- setStage là phương thức bất đồng bộ, có 2 tham số, tham số thứ 1 là thay đổi giá trị state, tham số 2 là call back thực hiện sau khi state mang giá trị mới.
- Những giá trị nào làm thay đổi giao diện thì đặt ở ngoài, thì đặt trong stage của component. Nếu sử dụng JS thuần thì phải dom lấy dữ liệu sau đó dom tới các phần thay đổi dữ liệu để gán giá trị mới. DOM JS thuần xử lý trên các dự án không xài React
==Render giao diện với mảng dữ liệu dùng vòng lặp==
- Để tạo ra các tag html (jsx trong react) thì ta có rất nhiều cách thực hiện, dùng các hàm như for, foreach, map... tạo nội dung. Viết 1 hàm render kết quả trả về là một mảng các tag jsx, tag được tạo ra từ vòng lặp luôn phải có 1 thuộc tính key không trùng nhau => sử dụng key={index}
- Gọi hàm tại thẻ body để giao diện render ra các thẻ mới tại đó.
- Ngoài ra chúng ta có thể viết phương thức render dưới dạng hàm map() hoặc viết trực tiếp trên giao diện code render trên giao diện.
==Truyền dữ liệu trong reactjs==
- Props là viết tắt của property (thuộc tính của đối tượng)
- Props (Truyền dữ liệu từ component cha sang con)
- Props là thuộc tính của thẻ (Ta có thể hiểu prop là property của thẻ). Ví dụ thẻ input bên dưới ta có các props ClassName, type, placeholder
- Props đối với component :
+ Props là thuộc tính mặc định của component để nhận dữ liệu từ các giá trị component cha truyền vào => để binding dữ liệu ra component con tại html tương ứng.
+ Props của component chỉ nhận các thuộc tính truyền vào từ component cha của nó và không thể bị chỉnh sửa bên trong component.
+ Đối với stateful và stateless component có các cách sử dụng props khác nhau. 
- Do stateless component là một function nên truyền props vào dưới dạng tham số, sử dụng bằng cách props.[thuộc tính của component cha] (nằm ngoài render) và export để có thể gọi ở các component khác.
- Đối với stateful component, thì props là thuộc tính mặc định của class, nên không cần truyền tham số. Chí cần gọi this.props
- Ở react để lấy giá trị từ một sự kiện bên trong component con ta sẽ truyền 1 call back qua props, component con sử dụng callback ấy gắn vào sự kiện để mỗi lần event thực thi tại component con sẽ gửi giá tri đến component cha nơi truyền callback
- Ngoài ra còn có thể truyền function qua props.
- Sau khi xây dựng layout xong => xác định những nguồn dữ liệu nào khi người dùng thao tác sẽ thay đổi và nguồn dữ liệu nào thay đổi, nếu thay đổi thì để trong state (Trường hợp đặt ngoài state thì code vẫn chạy nhưng sai converstion, khó quản lý do đó quy định thay đổi mới đặt trong state), nếu không thay đổi thì để ngoài state => cuối cùng sẽ xử lý chức năng liên quan đến người (event vd: click, hover,...)
- Khi nào truyền props function: Xác định state đặt ở component nào ? Nguyên tắc đặt state chứa  là ở giao diện binding ra trực tiếp hoặc gián tiếp, chứa nút xử lý trực tiếp hoặc gián tiếp. VD: Đặt ở App.js => PhoneList.js thông qua props => PhoneItem.js thông qua props. Các function tác động đến giá trị state thì lưu tại state, nút xử lý ở đâu thì truyền props tới đó.
- Những giá trị nào mà tính toán được sẽ không đưa vào lưu trữ
- Trường hợp truyền function là truyền props từ con lên cha nghĩa là khi con gọi function sẽ truyền dữ liệu lên cha và tác động vào function đã được khai báo ở cha.
==Redux==
- Bản chất làm việc với React là việc truyền dữ liệu giữa các component và thay đổi state để re-render lại giao diện component
- Redux là thư viện cung cấp cho ta một store trung tâm, lưu trữ tất cả các state, từ component muốn thay đổi state chỉ cần truy cập tới store để thay đổi.
- Redux gồm 3 thành phần chính :
1. Action: Là nơi mang các thông tin dùng để gửi từ ứng dụng đến Store. Nói dễ hiểu, từ 1 component, ta muốn thay đổi state trên store, ta phải gửi action, là một object để miêu tả muốn làm gì.
2. Reducer: Nơi tiếp nhận action và thay đổi state
3. Store: Nơi quản lý và lưu trữ state.
- Phương thức chính của Redux:
+ mapStateToProps: phương thức lấy giá trị state từ store về tạo thành 1 thuộc tính của component
+ mapDispatchToPróp: phương thức tạo ra sự kiện để đưa giá trị từ component lên store thông qua action.
- Tạo store ở file index.js. import {Provider} from 'react-redux'; import {createStore} from 'redux'  ,import {Provider} from 'react-redux', const store = createStore(rootReducer)
<Provider store={store}>
    <App />
  </Provider>, => tạo thư mục reducer ở trong src => Tạo file rootReducer.js `Đây là thằng sẽ quản lý những reducer nhỏ` => trong rootReducer.js sẽ import combineReduces từ redux
- Trong một hàm reducer có 2 cái, 1 là default state chứa giá trị mặc định và function để xử lý nó, 1 hàm reducer nhận vào 2 tham số, tham số 1 là default state, tham số thứ 2 là action (trong action có một type, sử dụng switch case để so sánh type truyền tới so sánh trong đó có hay không). Cuối cùng là export default function reducer => Sau đó quay lại rootReducer để import nó vào.
- Để componet connect được redux phải import thư viện react-redux, nó có nhiệm vụ kết nối tới store và lấy dữ liệu về cho component. Khai báo mapStateToProps fucntion, hàm này return một object chứa key value, key là tên của biến chứa dữ liệu, value là state.todosReducer.todoList.
- thay thế export default cũ (export default TodoApp) bằng export default connect(mapStateToProps) (TodoApp)
- Các action bản chất là một function và trả về một object, trong action sẽ có type, thường sẽ viết hoa toàn bộ vì nó là một const
- Redux quy định khi return 1 state mới thì phải là một object mới hoàn toàn, do trong hàm redux có một hàm  sẽ phát hiện sự thay đổi giữa state cũ và state mới. => return {...state, todoList} thay vì return state. Do nó so sánh địa chỉ vùng nhớ, có thay đổi địa chỉ vùng nhớ thì nó mới thay đổi => tăng tốc độ xử lý. default return state để khi có một action nào đó không dính vào case thì vẫn không render lại.
- Khi làm việc với obj hoặc array thì mình phải clone nó.
- Để sử dụng action cần phải sử dụng môt connect khác là mapDispatchToProps (khai báo trong TodoApp)
- Trong file action phải export action ra để reducer truy cập vào
==Routing (react-router-dom)==
- Routing là cơ chế trong SPA giúp ta chuyển đổi qua lại các trang mà không làm các trang đó load lại tòa
- Các thành phần trong routing:
+ BrowserRouter, Route, Switch: Các thành phần định nghĩa route
+ NavLink, Link: Dùng để chuyển đổi link qua lại giữa các component (giống thẻ a nhưng không reload lại trang)
+ History (push, replace): cung cấp các phương thức chuyển đổi route
+ Match: Cung cấp một số thuộc tính hỗ trợ path hiện tại, trong đó bao gồm việc giúp lấy tham số từ url
+ Redirect: Giúp điều hướng từ path này đến path khác tương tự history nhưng có thể định nghĩa được trong phần render(JSX)
+ Prompt: Cho phép người dùng xác định trạng thái có được phép rời khỏi component đó hay không
==Hook==
- là khá niệm dùng để thay thế react lifecycle trong react class component dành cho react functional component. Giúp code ngắn hơn clean nhanh hơn. Giảm bớt các khái niệm về hướng đối tượng, thuộc tính, phương thức.
- Một số hook cơ bản:
+ UseState: Dùng thay thế state và setState react class component
+ UseEffect: Hàm thay thế react lifecycle componentDidmount, Didupdate, WillUnmount
+ UseCallBack: Hàm tương tự lifecycle shouldComponentUpdate trong pureComponent trong react class component
+ UseMemo: Tương tự useCallBack nhưng kết quả trả về là 1 giá trị
+ UseContext: Tương đương contextprovider
==Thư mục selector==
- chứa các file js chứa logic lặp đi lặp lại của dự án nhằm tái sử dụng code trong dự án. Chú ý phải export cho các function trong file js để import vào component
==React Form - validation==
- Luồng là state thay đổi thì view thay đổi
- Có 4 input thì tạo 1 state gồm 4 thuộc tính. 
- input chứa value = this.state.[key tương ứng], và onChange={evt=>this.state({[key] : evt.target.value})} nếu không có thì sẽ không nhập được vào ô input.
- [evt.target.name] nếu đặt trong ngoặc vuông thì sẽ hiểu ở trong là một biến và lấy giá trị biến thành key thay vì kiểu string. (ES6)
- Chặn submit khi chưa điền đầy đủ các ô hoặc focus vào 1 input mà không điền vào gì hết mà nhảy ra sẽ báo lỗi.
- Do this.setState là hàm chạy bất đồng bộ nên sẽ xảy ra lỗi khi chạy nhiều lần do vậy sử dụng function trong this.setState(state => {}) khi truyền state vậy thì state luôn luôn là mới nhất, nếu đặt ở ngoài thì không đảm bảo state là mới nhất => sai lệch dữ liệu
==Life cycle getDerivedStateFromProps==
- Mỗi lần component được render lại thì hàm getDerivedStateFromProps sẽ chạy lại, nó nhận lại 2 tham số là nextProps và prevState, trong đó nextProps là props và prevState là state
- Hàm return trả về một state mới. Dùng khi muốn props thay đổi thì cập nhập lại state tương ứng. 
- dùng điều kiện if để điều khiển việc cập nhật, vd khi nào thay đổi user name thì mới set lại state còn nếu không thay đổi thì chạy tiếp.
==Life cycle component==
- componentDidMount(): được chạy duy nhất một lần sau khi render chạy xong, thường trong đây sẽ thực hiện các tác vụ như gọi API, tương tác DOM, setTimeOut, setInterval,... (Nói chung những hoạt động liên quan đến site effect)
- componentWillMount(): được chạy một lần trước khi hàm render được gọi (react 16.4++ sẽ không sử dụng) nếu được sử dụng sẽ có UNSAFE_componentWillMount(). Ngày xưa được dùng để setState trước khi render sẽ tiết kiệm 1 lần render, cũng ít được sử dụng
- khi state thay đổi => render chạy lại => chạy componentDidUpdate(), trong đây cũng làm những việc như setState, gọi API,... tương tự như DidMount khi nhận được prop mới, khác với DidMount chạy một lần thì DidUpdate chạy nhiều lần. *Chú ý* cần có điều kiện dừng nếu không sẽ lặp đi lặp lại do state thay đổi, điều kiện dừng là if, nếu thỏa mãn điều gì đó thì mới setState cho nó.
- UNSAFE_componentWillUpdate(): được chạy sau khi state hoặc props thay đổi nhưng chạy trước render, được bỏ đi từ phiên bản react 17
- shouldComponentUpdate(): dùng để tăng performent, nó nhận vào 2 tham số nextProps, nextState. Trường hợp hàm trả về giá trị true thì hàm render sẽ được chạy, nếu trả false thì render sẽ không được chạy. Chạy sau khi state hoặc props thay đổi và chạy trước render. Nếu chạy sai sẽ block hàm render.
- UNSAFE_componentWillReceiveProps(nextProps): Chạy lại sau khi props thay đổi và chạy trước shouldComponentUpdate, trước khi sử dụng để khi nhận được props mới sẽ setState trong này.
- static getDerivedStateFromProps(nextProps, prevState): Nếu return về null thì không thay đổi gì hết, nếu return 1 object thì state của nó sẽ mang giá trị object đó, tương đương như setState. Phải có điều kiện if nếu không sẽ chạy lặp lại liên tục. Nó thay thế cho componentWillReceiveProps, chạy sau khi props thay đổi và chạy trước shouldComponentUpdate. Ít sử dụng. Case Study: Trong todoApp khi nhận được props mới thì dùng filter để props todolist và props user để return về state mới
- componentWillUnmount(): Chạy trước khi component bị hủy đi, thường sẽ sử dụng để clearTimeoue, clearInterval, removeAddEventListener,.. dùng để giải phóng vùng nhớ - rò rỉ vùng nhớ.
- forceUpdate(): render lại khi gọi, hiếm khi xài, thường được sử dụng để vẽ canvas, vẽ chart
- Extends PureComponent, tác dụng của nó là tự handle shouldComponentUpdate (không gọi nó trong PureComponent được vì bản thân nó đã có). Sẽ sử dụng shallow compare các giá trị primitive (string,number, boolean), nó tự so sánh props cũ, props mới nếu khác sẽ chạy render nếu không khác sẽ không chạy lại render, không nên lạm dụng sử dụng PureComponent vì khi nó handle shouldComponentUpdate thì sẽ tốn thời gian xử lý, nếu props là Array, Object thì không nên sử dụng, chỉ sử dụng khi props truyền vào là Primitive
==File constants==
- Trong cấu trúc redux có file constants. Khi sử dụng những biến const ở nhiều nơi thì sử dụng file để có sửa thì chỉ cần sửa ở một nơi mà thôi.
==Middlewares==
- Để giải quyết vấn đề nhiều component cùng gọi 1 API, tránh phải viết nhiều lần code API ở từng component thì chúng ta sử dụng middleware.
- Middleware có thể xem như là lớp ngăn cách giữa component và reducer
- Action được dispatch lên reducer phải đi qua middleware.
- Ta có thể sử dụng middleware để đảm bảo rằng khi tới được reducer, response từ server đã được trả về.
- có 3 thư viện middleware thông dụng là redux-thunk, redux-saga và redux observable
- setup redux-thunk:  index.js => import thunk from redux-thunk , import {createStore, applyMiddleware} from redux. trong createStore nhận vào 2 tham số, tham số 1 là store, tham số 2 là applyMiddleware, const store = createStore(rootReducer, applyMiddleware(thunk))
- thư viện compose của redux gom tất cả các thư viện vào thành một cục để vừa sử dụng middleware vừa sử dụng redux dev tool. 
==Routing==
- cần sử dụng thư viện react-router-dom
- import { BrowserRouter, Switch, Route, Link } from "react-router-dom";
- Dùng tag BrowserRouter để bọc các component trong App.js
- Sử dụng Switch - Route để điều khiển luồng, trường hợp trang home thì sử dụng exact path = "/"
- <Route exact path="/" component={Home}/> Component trong 1 Route sẽ tự động có 3 props là history, match, location
- History: Quay lại componet Link, ta sử dụng nó để khi click vào thẻ có thể chuyển route hiện component tương ứng. Trong trường hợp ta có một chức năng đăng nhập, ta chờ sau khi đăng nhập thành công, mới chuyển component Đăng nhập sang component Trang chủ, tả khôgn thể dùng Link được vì đây là code js => đối tượng history được thêm vào để giải quyết điều này, nó cung cấp các phương thức để chuyển đổi route.
- Có 2 cách chuyển trang. Sử dụng Link to và this.props.history.push=("/"). Chú ý history.push sẽ giữ lại lịch sử điều hướng, khác với push thằng replace thì lịch sử của trang đó sẽ thay thế bằng trang replace. Thông thường sẽ sử dụng push là chủ yếu, replace trong một số trường hợp đặc biệt.
- Match: đối tượng match cung cấp một số thuộc tính hỗ trợ: path hiện tại, tham số được truyền qua url (params)
- Redirect: Component Redirect được cung cấp bởi react-router-dom hỗ trợ ta điều hướng từ path này tới path khác.
- Trường hợp sử dụng render={(routerProps) => {return <SignUp {...routerProps} />;}} thì không có props phải gắn bằng tay, trường hợp vừa khai báo component vừa render thì sẽ nhận component
- Khi sử dụng component chỉ được nhét tên của component còn sử dụng render thì có thể chứa các component => root không cần layout thì sử dụng component, root nào cần layout thì sử dụng render
- Trong react tất cả các component sẽ có 1 props là children. this.props.children
- Cơ chế Guard (bảo vệ route trong React): Để bảo vệ route tránh cho sinh viên truy cập vào trong trường hợp không đủ điều kiện. VD: khi tài khoản là sinh viên nhưng muốn truy cập vào route admin,... hoặc sinh viên chưa có tài khoản,chưa đăng nhập thì không được truy cập vào một số route. Guard bằng cách sử dụng một component Auth HOC để bọc Route.
==Cấu trúc một app cơ bản==
- components: chứa các component nhỏ thường sử dụng như navbar, header, loading,...
- pages: chứa các trang của app
- actions, constants, reducer (nễu sử dụng redux)
- utils: những function chung chung dành cho toàn ứng dụng
==HOC - Higher Order Component==
- là 1 function nhận vào 1 component và return 1 component mới.
- Dùng để tái sử dụng logic trong Component.
- file HOC bắt đầu bằng with VD withForm.js
==HOOK trong Function Component==
- Muốn dùng state phải  import React, {useState} from 'react'
- useState trả về 2 tham số: const [count, setCount] = useState()
- useEffect nhận vào 2 tham số, tham số 1 là 1 callback function, tham số 2 nếu [] rỗng thì sẽ chạy 1 lần duy nhất sau khi render tương đương với componentDidMount. Trong function component có thể sử dụng n useEffect. nếu để [count] thì sẽ chạy mỗi khi biến count thay đổi và chạy sau render tương đương componentDidUpdate nhưng khác DidUpdate xíu là lần đầu tiên vẫn chạy chứ không phải chỉ chạy khi state với props thay đổi, không chạy lần đầu tiên.
- Trường hợp không truyền tham số 2 thì sẽ tự động chạy lại mỗi khi props hoặc state thay đổi => không nên xài. 
- Không thể sử dụng so sánh Array và Object
- memo dùng để khắc phục tình trạng componet cha thay đổi props thì thằng con tự thay đổi theo khi thằng con sử dụng useEffect mà không có tham số 2. Tương tự PureComponent, tuy nhiên memo chỉ kiểm tra được sự thay đổi props chứ không được state. Trường hợp props là một function thì sẽ luôn luôn render lại do không kiểm tra được object.
- sử dụng dùng memo bọc function memo(Hello (){}) hoặc sử dụng export default memo(Hello)
- useMemo, nhận vào tham số 1 là callback function , tham số 2 là array set khi nào chạy như useEffect. Catched lại giá trị cũ, khi nào thay đổi state thì mới sử chạy vào. Nếu phép tính phức tạp hơn useMemo thì sử dụng còn không phức tạp thì không nên sử dụng do tốn bộ nhớ để chứa function, lưu giá trị cũ, thời gian xử lý do đó cần phải cân nhắc khi sử dụng.
- useCallback dùng để ngăn chặn việc render lại khi truyền vào 1 function do dùng memo ở component con không thể so sánh props là function, khi component bị render lại hàm handleShowMessage sẽ bị chạy lại => component con sẽ bị render lại, dùng useCallback để đảm bảo khi state message thay đổi thì hàm handleShowMessage mới chạy lại, các state khác thay đổi sẽ không làm render lại component Hello, sử dụng như useMemo.
- useMemo và useCallback dùng để tăng performance của app
- Custom HOOK tương đương với HOC. Khi đặt tên cho custom HOOK thì bắt đầu bằng use. Thông thường HOOK sẽ trả về giao diện, còn custom HOOK thì trả về array các giá trị. trong file cần sử dụng chỉ cần import và sử dụng thông qua các biến.import useCounter from './useCounter' => const [count1, increase, decrease] = useCounter(0); . Nếu return về array thì cái tên biến không cần trùng với tên nhưng cần phải để ý vị trí, khai báo bằng const [], nếu return về object phải khai báo biến giống tên và khai báo bằng const {}, không cần quan tâm vị trí.
- sử dụng HOOK để lấy dữ liệu từ store redux bằng useSelector, import {useSelector} from 'react-redux' => const {danhSachKhoaHoc} = useSelector(state => state.khoaHocReducer)
==Note==
- React.Fragment để trả về 2 thẻ div mà không cần phải bọc trong 1 thẻ div. ngoài ra có thể viết tắt <> div div </>. 

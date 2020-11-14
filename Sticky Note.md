==BOOTSTRAP==

IE9 trở xuống không support boostrap 4, nên sử dụng bootstrap 3
Bootstrap là một framework chứa các thẻ đã được tạo sẵn nhằm mục đích tạo responsive web
------------
TEXT CLASS 
tag small => text note, class="text-muted"
tag h6 class ="h1" => set size h6 = size h1
class = "text-danger" =>set color red
class= "text-primary" => set color blue
class = "text-success" => set color green
h5 class="display-1" 
h5 class="display-2"=> h5 dưới sẽ có size nhỏ hơn display 1
class="lead" => font chữ to hơn và nhìn nổi bật hơn
class="font-weight-bold" => in đậm
class="font-weight-normal" => bình thường
class="font-italic" => nghiêng
class="text-lowercase" => toan bo chu viet thuong
class="text-uppercase" => viet hoa toan bo
class="text-capitalize" => in hoa chu dau 
tien
class="list-unstyled" => bo dau cham cua list
class="list-inline" => cac the nam tren mot hang dung de tao nav bar
ALIGNMENT AND DISPLAY
class="text-right" => text nam ben phai 
class="text-justify" => text can bang nhau
class="text-lg-right" => nhung man hinh > 992px => text nam ben phai nho hon thi nam ben trai
class="align-top" => vi tri chu o tren cung cua dong
class="align-bottom" => vi tri chu nam o duoi cung cua dong
clsss="align-text-top"
class="align-middle" => vi tri chu nam o giua dong.
class="bg-success" => backgound mau xanh la
class="d-inline" => display inline
class="bg-primary"=> background mau xanh duong
class="d-block" => display block
FLOAT AND FIXED
class="clear:both" => clear float 
class="float-right" => float right
class="float-left" => float-left
class="float-none" => khong float ben nao ca
class="float-lg-right" => nhung man hinh > 992px thi se float right, nho hon se float left
class="float-sm-right" => lon 576px thi ben phai nho hon thi ve mac dinh
class="clearfix" => cong dung nhu clear:both
class="fixed-top" => co dinh vi tri tren cung
class="fixed-bottom" => co dinh vi tri cuoi cung
class="sticky-top" => khi chua lan toi thi no se nam o vi tri no khi lan qua roi thi vi tri no se nam o tren cung
COLOR CLASSES
text-info => xanh da troi
text-warning => vang cam
text-light => gan bang mau trang
text-dark => no gan giong mau den
text-white => trang
text-primary => xanh duong
text-secondary => mau xam
text-success => mau xanh la
bg-primary text-white => nen xanh duong chu mau trang
invisible => an di
PADDING AND MARGIN CLASSES
ml-5 => margin left muc do 5 (3rem)
mr-5 => margin right muc do 5
mt => margin top
mb => margin bottom
my => margin tren duoi
mx => margin trai phai
m-5=> margin 4 phia muc do 5

pl => padding left
pr => padding right
pt => padding top
pb => padding bottom
py => padding tren duoi
px => padding trai phai
p => padding bon phia

SIZING AND BORDER
w-25 => width 25%
w-50 => width 50%
w-75 => width 75%
w-100=> width 100%
h-25 => height 25%
h-50 => height 50%
h-75 => height 75%
h-100 => height 100%
border => tao border
border-primary => border mau xanh duong
rounded => tao border radius 4 canh
rounded-top => border radius o tren thoi
border-bottom-0 => khong co border bottom
BUTTON
btn => set button the bootstrap 4
btn-primary => chinh mau button xanh duong
btn-link => co mot button hover vao se co gach chan nhu the link
a class="btn btn-primary" => the a bt chuyen thanh nut
input class="btn btn-warning" type="button" => chuyen thanh button
btn-outline-primary => button co chu va vien mau xanh duong nen trang, hover vao thi chu thanh trang va nen thanh xanh duong
btn-lg => button lon
btn-sm => button nho
active => dieu chinh trang thai cua button
disabled => mau nhat co ve nhu khong cho phep nguoi dung click vao
data-toggle="button" => click vao thi active click lai thi mat mau active
~Dropdown menu~
div class="dropdown"
button class="btn btn-primary dropdown-toggle" data-toggle="dropdown"
div menu class="dropdown-menu
nhung phan tu con thi : a class="dropdown-item"
~button group~
div class="btn-group"
nhung bottom bt se cach ra khi gom nhom lai thi no se sat nhau theo chieu ngang
neu btn-group-vertical thi no se xep theo hang doc
NAVIGATION BAR
nav class="navbar navbar-expand-sm navbar-light bg-light" => expand-sm thi navbar se thu gon lai khi kich thuong man hinh nho, neu navbar-light thi mac dinh nhung the a trong no se la mau toi nen can phai chon bg-light de chinh mau sang cho de nhin chu

div class="container" => de set do dai cua cua navbar
a class="navbar-brand" => nhan hieu vd ben trai se co logo hoac nhan hieu cua web ben phai la navbar
ul class="navbar-nav" 
li class="nav-item"
a class="nav-link"

NAV with BTN COLLAPSE
tao mot buttun tren ul
button class="navbar-toggler" data-toggle="collapse" data-target="#menuNav"
trong the button tao the mot the span class="navbar-toggler-icon" de tao icon
tao mot div bao toan bo menu : div class"collapse navbar-collapse" id="menuNav"

~~ NAV WITH FORM ~~
them form sau ket thuc ul
form class="form-inline"
input class="form-control" placeholder="tim kiem"
button class="btn btn-outline-primary"

~~ NAV with dropdown menu ~~
them li class="nav-item dropdown" vao trong the ul
a class="nav-link dropdown-toggle" data-toggle="dropdown" 
div class="dropdown-menu"
a class="dropdown-item"
TABLE
table class="table" => trang tri table the dinh dang boostrap
table class="table table-dark" => table mau toi
~~
table class="table"
thead class="thead-dark" =>head table mau dank body mau sang

table class="table table-striped" => table co nhung dong xen ke nhau la mau sang va toi

table class="table table-hover" => khi dua chuot vao dong nao thi no se thay doi

table class="table table-sm" => kich thuoc bang nho lai

tr class="table-success" => dong co mau xanh la

PAGINATION
nav
ul class="pagination"
li class="page-item disabled">< a class="page-link"> 
li class="page-item active"><a class="page-link">1</a></li>

INPUT GROUP => nham gom nhom input voi nhung ki tu dac biet, input voi voi text hoac input voi button
gom @ voi input => cac ki hieu hoac text can input group thi phai dat trong the span va the span phai chua class input-group-addon
div class="input-group"
span class="input-group-addon">@</span>
input class="form-control" type="text" placeholder="text..." => form-control de input dep hon

gom input va btn thi o o button khong xai addon ma xai input-group-button, btn phai dat trong the span va the span chua class input-group-button

LIST GROUP AND BADGES
list group dung de group cac item lai co the su dung voi the ul>li hoac div>a
ul hoac div chua class="list-group"
li hoac a chua class="list-group-item"

them mau thi them class="list-group-item-primary"

tao LIST GROUP NHAP VAO SE EXPAND RA
div class="list-group" id="tab-nav" role="tablist"
a class="list-group-item" data-toggle="list" href="#link-home"
a class="list-group-item" data-toggle="list" href="#link-about"
// tao tab chua noi dung
div class="tab-content"
div class="tab-pane fade show active" id="link-home" => fade la cach hien thi, show active la luon sang nut dau tien, id dung de tro noi dung sang tag co href

div class="tab-pane fade" id="link-about"

BADGE
the bagde thuong dung de the hien so luong noi dung chua trong the vd 30 tin nhan chua doc

gan vao the span mot class="badge badge-warning">30</span>

BREADCRUMB dung de the hien duong di cua trang web giup cho nguoi dung biet dang o dau
ol class="breadcrumb"
li class="breadcrumb-item">Home
li class="breadcrumb-item">Library
li class="breadcrumb-item active">Data => active the hien nguoi dung dang o data 

ALERT AND PROGRESSBAR
div class="alert bg-primary"

div class=progress
div class=progress-bar bg-dark progress-bar-striped progress-bar-animated" style="width: 70%">70%</div> => progress-bar-striped lam cho thanh tien trinh co soc, progress-bar-animated tao hieu ung dang lam viec cho thanh tien trinh

CARD
card thay the cho well
div class="card"
div class="card-body"
p class="card-text"


card don giann
div class="card"
div class="card-body"
h4 class="card-title"
h6 class="card-subtitle"
p class="card-text"

card with image
div class="card"
img class="card-image-top" => do hinh tren card-body
div class="card-body"
h4 class="card-title"
h6 class="card-subtitle"
p class="card-text"

card voi header, footer
div class="card text-center" => text-center => noi dung nam o giua
div class="card-header"
div class="card-body"
p class="card-text"
div class="card-footer"

card voi nav
div class="card"
div class="card-header"
ul class="nav nav-tabs card-header-tabs"
li class="nav-item"
a class="nav-link">Home
li class="nav-item"
a class="nav-link">Product
div class="card-body"
h4 class="card-title"
h6 class="card-subtitle"
p class="card-text"

card voi image overlay
div class="card"
img class=card-image"
div class="card-img-overlay"

card group
div class="card-group"
div class="card"
div class="card-body"
div class="card-text"
div class="card"
div class="card-body"
div class="card-text"


card deck => gan giong nhu card group nhung thay vi card sat vao nhau thi no cach nhau mot khoang
div class="card-deck"
div class="card"
div class="card-body"
div class="card-text"
div class="card"
div class="card-body"
div class="card-text"

MEADIA OBJECT tao ra cac binh luan
div class="media"
img class="d-flex"
div class=media-body

media object long vao mot media object khac nhau la mot binh luan tra loi mot binh luan bang cach tha mot media object vao trong media-body cua cai truoc
div class="media"
img class="d-flex"
div class=media-body
         div class="media"
         img class="d-flex"
         div class=media-body


lam cho hinh nam giua dong binh luan khong nam o tren cung
div class="media"
img class="d-flex align-self-center"
div class=media-body

hinh nam o duoi cung
div class="media"
img class="d-flex align-self-end"
div class=media-body

tren cung thi khong de cap hoac su dung start
div class="media"
img class="d-flex align-self-start"
div class=media-body

list binh luan, moi the li la mot media object
ul class="list-unstyled" => khong co ki hieu dac biet
li class="media"
img class="d-flex align-self-start"
div class=media-body
GRID
co 2 dang class la container va container-fluid (100% do rong man hinh)
bootstrap chia trang web thanh 12 cot
neu khong su dung rieng le cac cot co the gom cac cot thanh mot cot co kich thuoc lon hon
co 5 class chinh
.col- : extra small devices man hinh nho hon 576px - portrait phones
.col-sm: small devices nho hon hoac bang 576px - landscape phones
.col-md: medium devices lon hon hoac bang 768px - tablets
.col-lg: large devices man hinh lon hon hoac bang 992px - laptops
.col-xl: xlarge devices: man hinh lon hon hoac bang 1200px - laptops and desktops
=> neu muon xet sm va md giong nhau chi can xet sm la duoc

cau truc cua grid
bao ben ngoai la mot contrainer, trong div co nhieu row, trong row co nhieu cot nhung toi da la 12 cot. 
col-*-*, *1st la loai man hinh, *2nd la so cot muon gom lai
vd col-lg-4 => man hinh lon thi se chiem 4 cot neu man hinh nho thi se 100%

quy tac cua GRID
row phai duoc dat trong container
neu khong co row thi cac col se nam tren cung mot hang theo chieu doc, neu co row se nam theo chieu ngang
noi dung nen nam trong col bang the div
co the chen them cac row vao cac cot
grid systeem da bao gom gutter va padding
gutter la padding cua container so voi noi dung ben trong no
noi tai cac column cung da co padding
--RESPONSIVE GRID--
neu muon man hinh lon va man hinh nho giong nhau chi can chinh man hinh nho
neu khong chinh thang lon thi mac dinh se lay thang nho ap dung len thang lon
extra small : col- < 576px
small grid: col-sm la bootstrap chia tu dong, muon set ty le phai la col-sm-* so luong cot chua >= 576px
medium grid: col-md
large grid: col-lg
extra large grid: col-xl
ALIGNMENT GRID
align-item-center: nhung cot nam o giua
align-item-end: nhung cot nam o duoi cung
align-item-start: nhung cot nam o tren cung (mac dinh)
justify-content-center: can ngang giua
justify-content-end:  nam ben phai
justify-content-start: nam ben trai (mac dinh)
justify-content-around: cac cot tu dong cach deu
justify-content-between: cai dau cai cuoi nam ben trai va ben phai o giua cach deu
---FLEX BOX--
flex-container
d-flex: display flex
flex-item
flex-row: flex direction row
flex-column: flex direction column
flex-row-reverse: doi chieu tu trai sang phai sang phai sang trai, neu column thi tren xuong duoi se thanh tu duoi len tren
FLEX WRAP
neu khong co flex wrap thi them nhieu phan tu se bi tran ra ngoai (khi khong du cho), neu co flex wrap thi se xuong dong
flex-warp
flex-nowrap(mac dinh)
ALIGN SELF chinh tung item con dung cho responsive. vd align-self-md-end : khi nao kich thuoc medium thi no moi ap dung va thay doi vi tri item
align-self-center
align-self- end
align-self-baseline
JS WIDGETS
CAROUSEL 
set hinh d-block va img-fluid de hinh khong tran ra khoi carousel
set div chua hinh .carousel slide va data-ride="carousel" de hinh tu dong chuyen doi
trong div .carousel slide se chua div .carousel-inner role="listbox"
moi div chua img se set .carousel-item, phai active 1 img neu khong co thi cac tam hinh se nam len nhau, khong co nut

tao nut de dieu khien carousel
nut prev
duoi div carousel-inner se tao mot the a href="#slider-2" data-slider="prev" class="carousel-control-prev" 
ben trong the a dat span class="carousel-control-prev-icon"
nut next
a href="#slider-2" data-slider="next" class="carousel-control-next" 
ben trong the a dat span class="carousel-control-next-icon"

indicators la nhung nut dieu khien click vao nut nao se chuyen qua hinh do
the div carousel slide phai chua them id="slider-3"
truoc div carousel-inner them the ol
su dung the ol thay cho div
ol class="carousel-indicators"
li class="active"(de kich hoat hinh dau tien) data-target="#slider-3" data-slide-to="0"(de biet di chuyen toi hinh nao)

li data-target="#slider-3" data-slide-to="1"
li data-target="#slider-3" data-slide-to="2"

CAROUSEL WITH CAPTION
duoi moi cai hinh chung ta them div .carousel-caption trong div nay chung ta them noi dung vao thi doan text se nam ben trong hinh

chinh sua option carousel bang js 
$('.carousel').carousel({
interval: thoi gian tu dong chuyen hinh
pause:'hover' hover vao thi se dung lai khong chuyen
warp: true -> tu thay doi toi hinh thu 3 se toi hinh thu nhat, neu false thi tam thu 3 se dung lai
})

COLLAPSE AND ACCORDION
khi click vao btn thi no se hien ra, click lai thi no se an
button .btn.btn-primary.d-block.my-5.ml-3 data-toggle="collapse" data-target="#demoCollapse"
div id="demoCollapse" .collapse p-3
.card
.cardbody

ACCORDION MENU
div cha chua ben ngoai cho id ="accordion" role="tablist"(de screen reader hieu la mot tablist"
div card con o ben trong thi o the a chua data-parent = id cua cha "#accordion" data-toggle="collapse" data-target="#menu1"(id cua the div chua card body tuong ung voi card header chua the a
div id="menu1" class="collapse" neu muon mac dinh la hien thi class="collapse show"
div .card-body

FORM AND VALIDATION
form
div .form-group
lable for="name"
input .form-control type="text" id="name"
form-control-sm nho
form-control-lg lon
small .form-text.text-warning => chu nho

check box
div .form-check
label .form-check-label
input .form-check-input type="checkbox" id"check"

input file
div .form-group
label
input class="form-control" type="file" id="getFile"

submit
button type="submit" .btn.btn-primary

inline form cung nam tren mot dong
form .form-inline
div .form-group
input .form-control
div .form-group
input .form-control

form row co the dung thay form-group
form
div .form-row

VALIDATION
viec kiem tra phai dung js hoac sever side nen o day chi chuyen ve mau xanh hoac do de nguoi dung biet dung hoac sai

form
div .form-group
input .form-control.is-valid (neu dung se co mau xanh bao quanh)
input .form-control.is-invalid(neu nguoi dung nhap sai)
div .invalid-feedback se thong bao o duoi form neu nguoi dung nhap sai (van nam trong div form group)


MODAL
co mot btn khi click vao se hien ra mot popup
button data-toggle="modal" data-target="#myModal" class="btn btn-primary"
div .modal.fade id="myModal  (fade de tao hieu ung muot ma)
div .modal-dialog
div .modal-content
{ div .modal-header
- h5> My modal
- button .close data-dismiss="modal">$times (dau nhan);
div .modal-body
- p>Ban da dang ky thanh cong
div .modal-footer
button data-dismiss="modal" .btn.btn-secondary> close
}

TOOLTIP
khi hover vao btn se hien ra o bat ki vi tri nao xung quanh btn noi dung

btn data-toggle="tooltip" data-placement="top"(vi tri hien tooltip co the thay left-right-bottom) title="Hello"(noi dung ben trong)

phai co doan js de chay tooltip
$('[data-toggle="tooltip"]').tooltip();

TOOLTIP VOI HTML thi them data-html="true" va them title="<h3>Tooltip</h3>" thi se hien neu khong co data-html="true" thi se khong hieu cac the html

POPOVER giong nhu toottip nhung thay vi hover thi phai click vao thi moi hien

button .btn.btn-primary data-toggle="popover" data-placement="top"(co the thay bang bottom-left-right) title="Popover"(chi la tieu de thoi) data-content="Noi dung show"

phai co js moi chay
$('[data-toggle="popover"]').popover();

click vao hien ra, click vao cho khac thi se mat
them thuoc tinh data-trigger="focus"

SCROLLSPY
khi cuon chuot toi section nao thi nav bar se thay doi theo, neu nhay section nao thi no se nhay toi do
phai co mot navbar de click
nav
div class=navbar navbar-expand-sm(de thu lai khi man hinh nho) bg-dark navbar-dark fixed-top(luon nam tren cung man hinh) id="myNav"
ul .navbar-nav
li .nav-item
a href="#section1" class=nav-link
li .nav-item
a href="#section2" class=nav-link
li .nav-item dropdown
a href="#section5" class="dropdown-togle nav-link" data-toggle="dropdown
div class=dropdown-menu
a href="#section4.1" class="dropdown-item"
a href="#section4.2"  class="dropdown-item"
ta gan position relative cho tab body

o the body ta them data-spy="scroll" data-target="#myNav"(truyen id cua navbar) data-offset="50"

==FORM==
FORM 
form có thuộc tính name, action, method
name là tên của form
action là địa chỉ trang web xử lý form
method chỉ phương thức gửi dữ liệu khi nhấn nút submit
TEXT VIEW
input gồm có
type: kiểu dữ liệu , text là kiểu dữ liệu text
name: tên của input
value: là giá trị của trường dữ liệu này
size: kích thước bao nhiêu ký tự, độ dài của text field
maxlenght là số ký tự tối đa được phép nhập
PASSWORD FIELD
input
type = "Password" dùng để che dấu kí tự nhập vào
còn lại giống như text
HIDDEN FIELD
dùng để truyền 1 giá trị của thuộc tính value khi form được submit
không hiển thị trên màn hình
input 
type "HIDDEN"
các thuộc tính khác vẫn không thay đổi
CHECKBOX FIELD
input type="checkbox"
name ="text"
value="text"
checked : mặc định chọn.
RADIO BUTTON FIELD
input type ="radio"
name = "text", các radio button cùng name thì chỉ có một lựa chọn
value = "text"
checked
FILE UPLOAD CONTROL
<form action=".." method="post" enctype="multipart/form-data" name="..">
input type="file" name=".."
</form>
enctype: kiểu mã hóa dữ liệu
SUBMIT BUTTON
nút phát lệnh và gửi dữ liệu của form đến trang xử lý
mỗi form chỉ có một nút submit và nút này được viền đậm
input type="submit name =".." value=".."
RESET BUTTON
dùng để trả lại giá trị mặc đinh cho các control khác trong form
input type="reset" name=".." value =".."
BUTTON TỔNG QUÁT
bao nhiêu nút button trong một form cũng được
cú pháp input type="button" name=".." value=".." onclick="script"
MUTILINE TEXTFIELD
Dùng để nhập văn bản nhiều dòng thường dùng nhập nội dung liên hệ, hoặc cần nhiều không gian, văn bản nhiều dòng.
textarea 
col: số cột
row: số dòng
disabled ẩn 
name: tên
readonly: chỉ được xem không được nhập
tabindex là thứ tự tab
wrap xuống dòng hay không xuống dòng
COMBOBOX - DROPDOWN BOX
select name=".."
có thể có nhiều group hoặc không có group (optgroup)
vd optgroup label ="multimedia"
option value="wm10> window media 10
hoặc không nhóm
option selected value="office07">Office 2007
PHƯƠNG THỨC GET/POST TRONG FORM
get và post điều gửi dữ diệu trong form đến server xử lý
phương thức GET:các đối số trong form được ghi chèn thêm vào đường dẫn url của thuộc tính action trong tag form nghĩa là người dùng thấy được những đối số này. khối lượng dữ liệu đối số được truyền đi của form bị giới hạn bởi chiều dài tối đa của mọt url trên address bar. hữu ích khi xài ở một số nơi không cần đến bảo mật thì có thể lấy dữ liệu một cách nhanh chóng.
phương thức POST những cái đối số của form được truyền ngầm bên dưới, khối lượng dữ liệu đối số được truyền đi của form không phụ thuộc vào url->không bị giới hạn.
chỉ sử dụng được phương thức truyền post khi action chỉ định đến trang web thuộc dạng trang web có mã lệnh xử lý trên server.
Phân biệt value và name
VALUE sẽ xác định giá trị của thẻ input
nó được sử dụng trong những loại thẻ input khác nhau
đối với type là button, reset, submit thì nó xác định là text hiển thị trên button
đối với type là text, password và hidden thì nó xác định giá trị khởi tạo hay là giá trị mặc định ban đầu của trường input này
đối với type là checkbox, radio, image nó sẽ xác định giá trị tương ứng cho các thẻ input và các giá trị này cũng sẽ được gửi khi nhấn submit
NAME dùng để chỉ định tên cho thẻ input, được sử dụng trong việc xử lý javascript và dùng để tham chiếu nhận dữ liệu trong form sau khi submit


==Khong biet==
client side script là script được thực thi tại client side trình duyệt thực hiện các tương tác với người dùng (tạo menu chuyển động,...) kiểm tra dữ liệu nhập, không gửi dữ liệu gì về server cả
server side script là những đoạn mã script được sử lý tại server side nhằm tạo các trang web có khả năng phát sinh nội dung động. một số xử lý chính: kết nối csdl, truy cập hệ thống file trên server, phát sinh nội dung html trả về người dùng.
javascript là ngôn ngữ client side script hoạt động trên trình duyệt của người dùng
chia sẻ xử lý trong ứng dụng web. giảm các xử lý không cần thiết trên server
giúp tạo hiệu ứng , tương tác cho web

Kiểu dữ liệu object : vd mảng var listBooks = new Array(10); trước khi sử dụng phải cấp phát bằng từ khóa new.

có thể cộng hai biến khác kiểu dữ liệu, ưu tiên kiểu dữ liệu của biến đầu tiên vd "12" + 34.5 = "1234.5"

hàm parseInt(), parseFloat() đổi kiểu dữ liệu từ chuỗi sang số

dạng phương thức khai báo hàm chung
function tên_hàm (thamso1, thamso2,...) {
...
}
vd function sum(x,y)
{
tong=x+y;
return tong;
}

hàm có giá trị trả về thì sẽ có return (value); 

các sự kiện thông dụng
onclick
onfocus: khi đang click vào
onchange: bắt sự kiện thay đổi dropdown
onblur: khi đưa chuột khỏi thẻ
onmouseover: rê chuột vào (hover)
onmouseout: rê chuột ra
onmousedown: đè chuột xuống
onmouseup: thả chuột ra
onload: khi đang load thông tin
onsubmit: khi gửi dữ liệu đi
Đối tượng DOM
dom là Document Object Model
là tập hợp các đối tượng HTML chuẩn được dùng để truy xuất và thay đổi thành phần HTML trong trang web(thay đổi nội dung tài liệu trang)
Một số đối tượng của DOM:windown, document, history, link, form frame, location, event,...
ĐỐI TƯỢNG WINDOW
là thể hiện của đối tượng cửa sổ trìn hduyệt
tồn tại khi mở một tài liệu HTML
sử dụng để truy cập thông tin của các đối tượng trên cửa sổ trình duyệt(tên trình duyệt, phiên bản trình duyệt, thanh tiêu đề, thanh trang thái.....)
dùng để kiểm tra user xài trình duyệt gì
các thuộc tính
document
event
history
location
name
navigator
screen
status
Các phương thức
Alert thông báo
confirm 
prompt
blur không click vào trình duyệt
close đóng trình duyệt
focus focus vào trình duyệt
open

Đối tượng document
biểu diễn nội dung trang HTML đang được hiển thị trên trình duyệt, dùng để lấy thông tin về tài liệu, các thành phần HTML và xử lý sự kiện
Đối tượng document có các thuộc tính
aLinkColor
bgColor
body
fgColor
linkColor
title
URL
vlinkColor
forms[]
images[]
childNodes[]
documentElement
cookie
Methods
close
open
createTextNode("text")
createElement("HTMLtag")
getElementById("id")
Tìm phần tử thẻ trong HTML
document.getElementById(id) tìm thẻ thông qua Id của thẻ
document.getElementByTagName(name) tìm tất cả các thẻ thông qua tên thẻ
document.getElementByClassName(name) tìm tất cả các thẻ thông quá css class


==NOTE linh tinh==
hàm để nhân trong css 1fr 1fr 1fr
grid-auto-rows: minmax

*---*NOTES*---*
Không thể lồng thẻ Block vào trong thẻ Inline được (VD dùng thẻ a bao block) vì vậy cần chuyển thẻ a > display:block

css in js

==JS==
input newTask
btn addItem
ul  todo
ul  completed


Them, xoa, check

<i class="fa fa-check-circle"></i>
<i class="fa fa-check"></i>
<i class="fa fa-trash-alt"></i>
<i class="fa fa-undo"></i>

obj toDo - name, check,

xoa obj bang splice khoi array todo va completed, khi xoa phai biet xoa cua list nao

check se add completed sau do xoa bang splice

add thi set li style display flex
justify content space between.

// function xoa, tao ui, check, add

function plus : localStorge and get localStorge

//toDoList[0] = array toDo
//toDoList[1] = array toDoCompled

var ToDo = function (){
  maToDo= 0;
    dataToDo = '';
    toDoCompleTed = 'false';
}

validation chi nhap chu khong nhap so

checkToDo: push obj sang mang completed, xoa obj cu, chuyen completed sang true

==Thu tu CSS==
display: ;
visibility: ;
float: ;
clear: ;

position: ;
top: ;
right: ;
bottom: ;
left: ;
z-index: ;

width: ;
min-width: ;
max-width: ;
height: ;
min-height: ;
max-height: ;
overflow: ;

margin: ;
margin-top: ;
margin-right: ;
margin-bottom: ;
margin-left: ;

padding: ;
padding-top: ;
padding-right: ;
padding-bottom: ;
padding-left: ;

border: ;
border-top: ;
border-right: ;
border-bottom: ;
border-left: ;

border-width: ;
border-top-width: ;
border-right-width: ;
border-bottom-width: ;
border-left-width: ;

border-style: ;
border-top-style: ;
border-right-style: ;
border-bottom-style: ;
border-left-style: ;

border-color: ;
border-top-color: ;
border-right-color: ;
border-bottom-color: ;
border-left-color: ;

outline: ;

list-style: ;

table-layout: ;
caption-side: ;
border-collapse: ;
border-spacing: ;
empty-cells: ;

font: ;
font-family: ;
font-size: ;
line-height: ;
font-weight: ;
text-align: ;
text-indent: ;
text-transform: ;
text-decoration: ;
letter-spacing: ;
word-spacing: ;
white-space: ;
vertical-align: ;
color: ;

background: ;
background-color: ;
background-image: ;
background-repeat: ;
background-position: ;

opacity: ;

cursor: ;

content: ;
quotes: ;
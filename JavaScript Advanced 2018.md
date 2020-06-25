==0 - Introduction ==
- Các kiến thức chưa học về JS
- Các tính năng mới của ES6+
- Bước đệm cho khóa học React
==1 - Hoisting trong JavaScript==
- trường hợp sử dụng biến trước khi khai báo biến bằng var thì nó mang giá trị undefined.
- khi JS chạy thì tìm tất cả các biến được khai báo là var thì sẽ mang lên trên cùng scope, khi tới dòng gán giá trị thì sẽ mang giá trị đó.
- Để tránh trường hợp như vậy thì khai báo biến ở đầu chương trình hoặc đầu hàm tránh khai báo biến ở bên dưới vì dễ gây ra lỗi.
==2 - var, let, const==
- khai báo var , let , const. Nếu dùng var thì có thể khai báo var lại được, dùng let không được khai báo lại nếu không sẽ gặp lỗi, const không thể khai báo lại được. Có thể khai báo biến mà không gán giá trị cho nó được cho var hoặc let nhưng const thì sẽ gặp lỗi, phải gán giá trị cho nó.
- hoisting: nếu sử dụng khai báo let hoặc const mà sử dụng biến trước khi khai báo sẽ bị lỗi.
- let và const có block scope {} trừ trường hợp khai báo object, var thì không có block scope mà chỉ có function scope, nó không tuân thủ block scope (khai báo var trong scope nhưng ở ngoài vẫn sử dụng được)
- Thông thường khi lập trình sẽ muốn cho giới hạn scope càng nhỏ càng tốt thì sẽ tối ưu hóa, giảm sử dụng bộ nhớ do vòng đời của biến ngắn.
==3 - Function context & bind==
- global context - function context
- function context là nội dung trong biến đó, vd object gọi phương thức của object đó thì khi đó phương thức sử dụng context của object. nếu phương thức của object được gọi từ một biến khác thì khi đó phương thức không lấy được giá trị của function context mà lấy giá trị global context.
- phương thức bind là gán context vào function, do đó function sẽ không sử dụng global context.
==4 - Arrow function expression==
- hay còn được gọi là fat arrow, không phải lúc nào cũng dùng arrow function thay thế cho function bình thường.
- Dùng arrow function để truyền context từ function cha vào function con, nếu không dùng thì function con sẽ lấy giá trị global context.
==6 - Template string==
- Tạo ra string mà không cần phải sử dụng dấu +, điều kiện thì phải sử dụng ` ${biến hoặc các biểu thức + - * / hoặc gọi hàm} có thể xuống bao nhiêu dòng cũng được, có thể truyền nhiều biến vào`
==7 - arguments==
- Là biến nằm trong tất cả các hàm trừ arrow function ra. Nó là một object và có dạng như array (array-like object)
- Array-like object là các object có các thuộc tính giống như array (các index là các key của object) và có thêm thuộc tính length nhưng nó không có các method của array.
-  arguments là biến tồn tại bên trong scope của hàm (hàm thông thường không phải arrow function). nó có các key là index và value là các parameter truyền vào, và nó có method .length => trả về độ dài => nó là một array-like object.
-  có thể biến arguments thành một array và sử dụng các method array bằng Array.from(arguments)
==8 - Default parameters==
- là tham số mặc định truyền vào, nếu truyền vào tham số thì sẽ sử dụng tham số truyền vào nếu không sẽ sử dụng tham số mặc định function(name = "friend") => nếu không truyền tham số vào thì sẽ sử dụng value 'friend cho biến name'
==9 - call==
- method call dùng để gọi hàm vd greeting.call() <=> greeting(), call() có thể nhận vào nhiều tham số, tham số đầu tiên sẽ đại diện cho this, trường hợp function được gọi không có sử dụng this thì truyền bất cứ gì vào cũng không có tác dụng gì cả -> truyền null vào. Từ tham số thứ 2 trở đi là tham số của hàm được gọi.
- Trường hợp không truyền đầu vào thì sẽ mang giá trị undefined.
- call khác bind ở chỗ bind trả về một hàm và phải sử dụng () để chạy. Còn call thì gọi hàm đấy và trả về giá trị của hàm trả về.
==10- apply==
- cách hoạt động giống call nhưng tham số 2 là một array hoặc array-like object chứa các tham số truyền vào. dùng để lấy giá trị truyền vào của 1 function mà ta không biết nó nhận vào bao nhiêu tham số.
==11 - Enhanced object literals==
- object literals: bình thường có 2 các khởi tạo 1 object là tạo 1 constructor function sau đó sử dụng từ khóa new để tạo ra một object, cách 2 là khai báo 1 object ra chứa key : value trong đó, cách 2 được gọi là object literals
- tính năng mới của es6 là enhanced object literals, khi khai báo biến the object literals thì key của object trùng với biến truyền giá trị value thì ta chỉ cần ghi tên key, thay vì key = key,. Trường hợp phương thức thì thay  vì run: function() {} => run() {}
==12 - class==
- Ngôn ngữ JS không phải là một ngôn ngữ OOP, cú pháp class được sinh ra để viết constructor function ngắn gọn hơn và giống ngôn ngữ OOP hơn.
- Bản chất của class cũng là prototype.
==13 - class inheritance==
- Sự thừa kế class, dùng từ khóa extends để chỉ sự thừa kế của class con khởi tạo với class cha. class con sẽ có các method của class cha và có thể thêm các method mới ngoài method của lớp cha đã có.
- Có thể kế thừa rất nhiều lần vd parrot extends bird, bird extends animal.
- Có thể kế thừa ở contructor function bằng việc sử dụng .call hoặc .apply(this, arguments)
==14 - method overriding==
- Ghi đè lại một method, vd class con ghi đè lại method của lớp cha được kế thừa, thay đổi cách hoạt động của phương thức của lớp cha.
==15 - super==
- dùng để gọi lại constructor của class cha, method của class cha.
- class RangedHero extends Hero{
    constructor (name, hp, damage, range) {
        super(name, hp, damage);
        this.range = range;
    }
    attack(enemy) {
        super.attack(enemy);
        this.hp += this.damage;
    }
}
==16 - static==
- instance là một object được tạo ra từ class nào đấy. người ta gọi object đó là instance của class đó.
- trong class khai báo method với key static thì sẽ gọi được mà không cần new method, còn những method nào tạo trong class mà không có từ khóa static thì sẽ phải new object rồi mới sử dụng được method đó, tương ứng với việc sử dụng constructor function và tạo method bằng prototype. Bắt buộc phải gọi từ khóa new rồi mới gọi được method đó.
- Ngoài ra còn có thể dùng static để tạo ra các biến chỉ được truy cập từ class thôi mà không được truy cập từ các instance của class đấy.
==17 - rest==
- Trường hợp function nhận 1 tham số nhưng truyền vào 4 tham số thì từ tham số 2 - > 4 sẽ bị bỏ qua, các tham số 2->4 được gọi là rest. (Số lượng tham số có thể thay đổi).
- cách sử dụng function (biến đầu, ...tên rest) => rest được đặt ở cuối cùng để hứng tham số có thể truyền vào vượt quá số quy định, rest trả về một mảng các tham số truyền vào, rest khác arguments ở chỗ là arguments chứa tất cả tham số truyền vào và nó trả về là một object chứ không phải array. Trường hợp sử dụng rest mà không truyền vào tham số đầu tiên thì nó sẽ chứa toàn bộ tham số truyền vào function(...tên rest).
- Hay dùng trong trường hợp là không biết tham số đầu vào là như thế nào.
==18 - spread==
- spread gần giống rest ở chỗ bắt đầu ... nhưng khác nhau ở chỗ rest gom các giá trị thành một array, spread thì trải các giá trị của một array ra các phần tử
- Có thể kết hợp giữa rest và speard để có thể giá trị vào là một mảng mà vẫn nhận được là các giá trị riêng lẻ.
==19 - Value types vs Reference types==
- reference types gồm: object, array, function
- Kiểu object nó phức tạp khi tạo ra trong bộ nhớ thì cái biến lưu giá trị tham chiếu đến giá trị thực tế của object đấy. Khi khai báo là 1 obj thì tạo 1 object ở đâu đó và nó lưu giá trị tham chiếu đến biến, nên so sánh thì sẽ ra kết quả khác nhau.
- khi khai báo value thì nó lưu giá trị vào biến nên khi so sánh === thì nó sẽ giống nhau.
- Khi tạo một biến a3 = a2, thay đổi a3 thì a2 không thay đổi. nếu tạo obj3 = obj2, thay đổi giá trị obj3 thì obj2 cũng bị thay đổi, khi gán 1 biến = 1 reference thì đang tham chiếu đến object đấy cho nên khi chỉnh sửa 1 thì thằng kia cũng thay đổi luôn.
- Trường hợp function nhận 1 object vào và xử lý thay đổi giá trị object đó thì object ở ngoài cũng bị thay đổi giá trị theo. Nếu có nhiều function thay đổi giá trị của cùng 1 obj thì rất khó theo dõi sự thay đổi giá trị của obj.
==20 - spread Part 2==
- shallow-cloning: clone là copy, shallow là clone 1 level , deep clone là clone toàn bộ object.
- Shallow-cloning là quá trình tạo object copy mà trong đó nếu object đó chứa object khác thì quá trình copy chi copy reference (địa chỉ vùng nhớ) của object chứa trong đó. Điều đó có nghĩa là cả 2 object sẽ cùng trỏ tới 1 giá trị của object chứa trong nó. Khi thay đổi giá trị obj thì sẽ thay đổi trên cả 2 obj.
- Deep Copy sẽ tạo ra object mới với reference độc lập với object gốc, mọi thay đổi object chứa trong sẽ không ảnh hưởng đến nhau.
==21 - Closure==
- Bình thường khi khai báo 1 biến trong 1 function thì sau khi sử dụng xong biến thì biến đó sẽ bị xóa tuy nhiên trong trường hợp trong function đó có chứa 1 function khác và nó sử dụng biến đó thì nó vẫn truy cập được mặc dù biến đó nằm ngoài scope của function. -> gọi là closure. Hàm con có thể truy cập và thay đổi các biến bên ngoài
- Ứng dụng dùng để làm các function factory (design patterns có cái gọi là factory method), function trả về 1 fucntion làm gì đấy.
- Closures hữu dụng vì nó cho phép chúng ta gắn một vài dữ liệu (bên trong lexical environment) với một function sẽ tương tác với dữ liệu. Tương tự như trong object-oriented programming, các object cho phép chúng ta gắn một vài dữ liệu với một hoặc nhiều phương thức bên trong
- Trên nền web, hầu hết code được viết bằng JavaScript là event-based — chúng ta định nghĩa một xử lý, sau đó gắn nó vào event sẽ được gọi bởi user (ví dụ như click hay keypress). Đoạn code của chúng ta sẽ là callback: 1 function chạy khi có một sự kiện xảy ra.
 ==22 - Higer order functions==
 - là hàm có thứ tự order cao hơn, là hàm có thể nhận vào 1 function làm tham số hoặc trả về 1 function là higher order function.
 - Ứng dụng chia nhỏ chương trình, thường chương trình chia nhỏ thành nhiều hàm để dễ dàng debug và test. Các hàm nhỏ thì khi chạy xong sẽ giải phóng bộ nhớ giúp chương trình hiệu quả hơn
==23 - Destructuring==
- Destructuring là tháo dỡ cấu trúc, áp dụng cho array hoặc cho object.
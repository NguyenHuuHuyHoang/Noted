==Var, let và const==
- Var là biến toàn cục có tác dụng với tất cả scope
- let là biến chỉ có tác dụng trong scope chứa nó, nó có thể gán giá trị lại
- const là khai báo biến Hằng số, không thể gán giá trị lại, trường hợp tạo biến const là object thì không thể trỏ vào object khác nhưng có thể thay đổi giá trị trong object đó
==Arrow function==
- let showMessage = () => {}
- Khác với ES5 ở việc thay function bằng mũi tên
- trường hợp trong function chỉ duy nhất 1 return thì có thể bỏ return VD: let tinhDiemTrungBinh = (dToan,dLy,dHoa) => (dToan + dLy + dHoa) / 3; 
- Arrrow function không được coi là phương thức.
==Khác biệt về ngữ cảnh trong con trỏ this==
- Trường hợp xử lý function trong một phương thức của một object thì sử dụng arrow function sẽ không thay đổi con trỏ this truyền vào từ object, nếu sử dụng khai báo function của es5 thì sẽ bị đứt do không truyền giá trị của object vào trong hàm
- Prototype function là lớp đối tượng.
==Rest Params==
- Toán tử ba chấm. Nếu khai báo function với toán tử ba chấm thì có thể truyền bao nhiêu tham số cũng được, bên trong hàm phải kèm theo switch case check số lượng tham số truyền vào để cho từng trường hợp xử lý, nếu quá số lượng thì trả ra không hợp lệ
- 
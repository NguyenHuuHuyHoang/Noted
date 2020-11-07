1. Nếu cộng số lượng sản phẩm thì giá tiền sẽ thay đổi theo. Công việc chính của FE là lập trình các sự kiện.
2. JS là ngôn ngữ mạnh nhất thế giới, cũng là chậm nhất thế giới. Do các ngôn ngữ khác có kiểu dữ liệu cho biến, biến không phải tạo ra để chơi, khi 1 kiểu dữ liệu được sinh ra, thì nó sẽ tạo 1 biến trên vùng nhớ, đảm bộ sự ràng buộc của kiểu dữ liệu, mỗi kiểu dữ liệu chỉ chứa được tối đa 1 giá trị do dựa vào vùng nhớ. Trong DB thì có thể giới hạn số lượng dữ liệu vd tạo trường chỉ chứa 10 số điện thoại số int, nếu nhập nhiều hơn sẽ lỗi. JS hoặc PHP thì sẽ không có kiểu dữ liệu của biến vì nó sẽ chậm. Khi khai báo 1 biến nó sẽ chứa toàn bộ kiểu dữ liệu.
3. Cách nhúng JS, Nhúng ở cuối cùng HTML (sau đóng tag html). Biến ở đây dưới dạng JS thuần thì khai báo bằng từ khóa var. Khai báo biến là lưu lại kiểu dữ liệu, trường hợp khai báo a = 1 thì nó sẽ được lưu trong quere, Nó lưu trữ không quan tâm là var hay let hay const. BT thường ngôn ngữ sẽ dịch trực tiếp, nhưng JS thì dịch phải qua quere rồi mới dịch về mã máy bằng C++ rồi browser mới đọc.
4. hậu tố + tổng, tiền tố + tăng. ++x = tăng, x++ = tổng.
5. !(!), !().
6. Khi xử lý JS thuần thì lúc nào cũng sử dụng for để duyệt phần tử. 
7. OOP Trong JS:
	1. Đối tượng là gì ? đối tượng có 2 thứ là thuộc tính dùng để phân biệt giữa đối tượng này với đối tượng kia và phương thức là hành động của một đối tượng. Nguyên lý lập trình hướng đối tượng là đem những gì ở ngoài đời vào trong lập trình.
	2. Có nhiều cách tạo ra đối tượng, tuy nhiên cách được sử dung nhiều trong plugin là:
		1. this.car = function () {
			- var id = 250; // biến là private, không lấy được phải lấy thông qua 1 phương thức trả về id (không có this).
			- this.name = "Merc";
			- this.edition = 2018; 
			- this.run = function() { //Không nên khai báo phương thức kiểu này
				- return this.edition;
			- }
			- //Cách khác
			- this.run = run;
			- function run() {
				- return this.edition;
			- }
			- function getPrivate() {
				- return id //Trả về giá trị biến private.
			- }
		2. }
		3. var obj = new car();
		4. console.log(obj.name);
		5. Kết thừa thông qua phương thức call
		6. this.bmw = function() {
			1. var color
			2. car.call(this) 
		7. }
8. DOM
	1. Mỗi thẻ điều là một đối tượng, DOM đơn giản là thay đổi nội dung website. Muốn thay đổi node con thì phải DOM từ node cha vào. (Theo cây DOM)
	2. document.getElementById => đối tượng document có method getElementById.
	3. DOM lấy thằng cha ra sau đó lấy thằng cha.children để lấy thằng con. 
	4. 

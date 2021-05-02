- undraw.co
- behance
- drippble
==Component, Module==
- Module dùng để quản lý component hoặc module khác
- Để một module này sử dụng một component đang được quản lý bởi 1 module khác thì tại module khác phải export component quản lý và module này phải import module khác vào
==One way binding==
==Interpolation==
	- {{ tên biến }} được gọi là interpolation, binding dữ liệu đang có trong biến vào code html
	- Interpalation thường được sử dụng để hiển thị và thực hiện các đánh giá các chuỗi vào trong đoạn chữ giữa các thẻ HTML và trong phép gán thuộc tính ![[Pasted image 20210502211653.png]]
	- Ngoài ra Interpolation còn được sử dụng để đánh giá các phép toán trong cặp ngoặc nhọn. ![[Pasted image 20210502211755.png]]
	- Thực hiện các phương thức và trả về các giá trị thông qua việc call các phương thức trên component ![[Pasted image 20210502211934.png]]
	- Hiển thị các mảng phần tử bằng việc kết hợp với ngFor directive để hiển thị một mảng các phần tử ![[Pasted image 20210502212136.png]]
==Property==
	- [tên thuộc tính] = "tên biến chứa dữ liệu" được gọi là property binding
	- Khi gán giá trị cho một thuộc tính của một phần tử mà không phải dạng chuỗi (VD: true/false) thì bắt buộc phải sử dụng property. ![[Pasted image 20210502212811.png]] Nút cancel sẽ luôn là disabled bất kể là giá trị gì.
==One way event binding==
	- Sử dụng (target event name) = "template statement" ![[Pasted image 20210502214659.png]]
	- (size) = "increaseSize()"
==Two way event binding==
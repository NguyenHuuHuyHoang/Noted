- Master Data
- Transaction data
- symmetric
- Về cơ bản trong ERD có 3 loại quan hệ là:
	-  1 - 1
	-  1 - n 
	-  n - n
- Từ 3 loại trên có 6 mối quan hệ:
	- 1 : đơn thuần chỉ là một
	- 1 và bắt buột phải có một: Required (chỉ được một, và bắt buộc có một dữ liệu)
	- không hoặc 1 : Optional (không có dữ liệu cũng được)
	- Nhiều: Đơn thuần là nhiều
	- Một hoặc nhiều: Required (ít nhất phải có một dữ liệu)
	- Không hoặc nhiều: Optional (không có dữ liệu cũng được)
- QH 1 - 0 hoặc nhiều
	- Các bệnh nhân chỉ được chăm sóc bởi một và chỉ một y tá
	- 1 y tá có thể chăm sóc nhiều bệnh nhân hoặc không chăm sóc bất kỳ bệnh nhân nào
- QH nhiều - nhiều
	- Các bệnh nhân được chăm sóc bởi nhiều y tá
	- nhiều y tá chăm sóc nhiều bệnh nhân, hoặc nhiều y tá không chăm sóc bất kỳ bệnh nhân nào
- QH 1 - 1
	- 1 bệnh nhân được chăm sóc bởi 1 y tá
	- 1 y tá chăm sóc 1 bệnh nhân
- QH 1 - 1 và chỉ một
	- 1 bệnh nhân được chăm sóc bởi 1 y tá
	- 1 y tá bắt buộc phải chăm sóc 1 bệnh nhân và chỉ được 1 bệnh nhân duy nhất
 - QH 1 - 0 hoặc 1
	 - 1 bệnh nhân được chăm sóc bởi 1 y tá
	 - 1 y tá có thể chăm sóc 1 bệnh nhân hoặc không chăm sóc bệnh nhân nào (không bắt buộc)
- QH  1 - 1 hoặc nhiều
	- 1 hoặc nhiều bệnh nhân được chăm sóc bởi duy nhất 1 y tá
	- 1 y tá bắt buộc chăm sóc 1 bệnh nhân hoặc nhiều bệnh nhân (ít nhất phải có một bệnh nhân).
 - QH 1 - nhiều
	 - Nhiều bệnh nhân được chăm sóc bởi một y tá
	 - 1 y tá chăm sóc nhiều bệnh nhân
==Note==
- Xác định FK cho nhanh : Nếu 2 table quan hệ 1 - nhiều với nhau, thì chỉ cần lấy PK của table ở đâu quan hệ 1 bỏ vào FK của table ở đầu quan hệ nhiều
- Bản chất quan hệ 1 - nhiều : nghĩa là 1 record A bao gồm rất nhiều record B, hoặc nhiều record B cùng liên kết đến 1 record A. Cũng có thể hiểu rằng A có một cái lưới hoặc bảng chứa các dòng dữ liệu của B
- Trong QH nhiều - nhiều, thực tế sẽ không quan hệ nhiều nhiều trực tiếp với nhua mà cần thông qua một entity trung gian, 2 Entity sẽ quan hệ 1 - nhiều với entity trung gian. Trong entity trung gian chứa khóa ngoại là 2 khóa của entity quan hệ nhiều nhiều.
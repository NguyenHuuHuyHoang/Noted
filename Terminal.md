Những thủ thuật để làm việc trên linux, ubuntu: 
+ `<C-w>` xóa từng từ trong dòng lệnh
+ để di chuyển mũi tên nhanh thì giữ ctrl + di chuyển mũi tên
+ history cho xem tất cả câu lệnh đã gõ trong quá khứ
+ C-l xóa toàn bộ lệnh trên màn hình
+ C-r gõ từ khóa cần tìm sẽ cho ra câu lệnh đã gõ trong quá khứ, ấn C-c để bỏ đi
+ mở tab mới bằng C-t
+ chuyển giữa các tab bằng A-1/2/3
+ C-S-w để đóng tab
+ C-d đóng tab
+ pwd: print working directory cho biết thư mục hiện tại đang làm việc là thư mục nào, mỗi khi mở terminal thì sẽ tự động vào thư mục của user hiện tại
+ ls: list , ls -a hiện thị tất cả file ẩn. những file có dấu . ở đầu sẽ ẩn
+ ls -al tên_foler cho thấy quyền sở hữu
+ sudo chown -R tenUser tenThuMuc: cấp quyền cho user đối với thư mục
+ man sẽ ra thông số của các công cụ, để thoát ra thì ấn q
+ / là thư mục root vd cd /
+ /tmp là thư mục khi tắt máy tính thì sẽ xóa những file trong thư mục này đi
+ touch [file] để tạo file
+ echo hello > [file] => ghi thông tin hello vào file, nếu sử dụng tiếp echo thì sẽ ghi đè lên cũ muốn tránh ghi đè thì echo world>> [file]
+ cat [file] in nội dung của file ra màn hình
+ mkdir [tên thư mục] => tạo thư mục mới
+ mv [file] `[tên mới]` thì sẽ đổi tên file hoặc thư mục thành tên mới
+ cp [file] `[tên file mới]` thì sẽ copy file
+ cp -r [thư mục] `[tên thư mục mới]` copy thư mục
+ vim: khi làm việc với server không có ui thì bắt buộc phải xài vim để xem các file log trên server
+ ifconfig để xem địa chỉ pip
+ curl để gửi get, post, các lệnh http request
+ whoami để cho biết đang xài user nào
+ top để xem những process đang chạy, kill bằng PID, thoát ra bằng <C-c>
+ kill -9 [PID]
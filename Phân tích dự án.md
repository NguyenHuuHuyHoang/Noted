- Trước hết phải làm xong phần home - trang chủ, lấy danh sách phim, trang chi tiết phim, trang đặt vé, phần carousel nhanh nhất thì sử dụng react slick để phân trang. (Nhược điểm bắt buộc phải gọi API lấy toàn bộ danh sách phim về, Nếu sử dụng thì phải kiểm tra có data mới render ra slick)
- Phần sử dụng lấy thông tin hệ thống rạp => Lấy thông tin cụm rạp theo hệ thống => lấy thông tin lịch 
- admin thêm xoá sửa user, thêm xoá sửa phim, có thể thêm dashboard, các api thêm xoá sửa thì phải gọi api lấy danh sách lại để lấy data mới.
- Nếu link trailer lấy về có watch thì cần thay watch bằng embed
==Codepro==
- 3 loại người dùng : khách vãng lai, người dùng bt, quản trị viên

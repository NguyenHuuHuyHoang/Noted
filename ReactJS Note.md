- Mỗi Component là một folder, ở trong file JS đặt tên là index để khi import không cần phải /index
- Dữ liệu get từ API thường đặt tên là payload, gán trong action dispatch lên store vd payload: res.data
- ![[Pasted image 13.png]] Trường hợp lần đầu tiên chưa có data thì set dữ liệu là rỗng để hiển thị hợp lý, không bị lỗi, đặc biệt trường hợp img tag không lấy được hình ảnh sẽ bị lỗi gây crash web.
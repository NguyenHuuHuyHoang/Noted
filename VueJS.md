Data = State
VueX = Redux
Vue Router = router
Component = Component
Props = Props
NPM
==Khởi tạo project==
- Vue CLI cli.vuejs.org
- npm install -g @vue/cli
- sau khi đã cài vue ở global xong thì chúng ta sử dụng vue create tên-project
- Sau khi tạo project xong thì để chạy sử dụng npm run serve
- Stable hiện tại là 2.6.12
- npm install vue
==Cấu trúc thư mục==
- src: source code
	- main.js là file gốc của hệ thống
	- App.vue là component gốc
	- components chứa các component
	- Assets: chứa các hình ảnh
- Component có 3 thành phần:
		- Template: HTML -> hiển thị
		- Script: js -> xử lý
		- Style: css -> làm đẹp
			- Hỗ trợ SCSS
			- Scoped style: là style dành riêng cho component

- Tạo component:
	- Tạo file .vue
	- Ở trong file vue nào sử dụng component thì import nó vào và khai báo trong danh sách components
	- Trong mỗi component chỉ được bọc trong 1 thẻ div, người ta gọi là root element bắt buộc

- 2 way binding
	- bind dữ liệu hai chiều ![[Pasted image 20210407184208.png]]
	- dữ liệu được khai báo trong export defaultdata() {
		- return {
			- name: value;
		- }
	- }
	- Để lấy dữ liệu vào input ta sử dụng thuộc tính v-model="tên-biến" còn nếu bind thẳng vào thì sử dụng {{ tên biến }}, nếu input thay dổi giá trị thì ở data sẽ tự động thay đổi giá trị, do liên kết với input rồi
	- Phụ thuộc vào kiểu element
	- 


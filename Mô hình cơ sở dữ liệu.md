==Key - Value==
- Nên dùng cho caching, pub/sub, leaderboards vì nó nhanh. Tiêu biểu là redis
==Wide - column==
- Trade-off: 
	- Positive: Schema-less
	- Negative: Without Joins
- mỗi một row sẽ có 1 row key tương ứng với N columns value, cột đầu tiên trong columns sẽ có giá trị tương ứng với row key. VD row key giá trị là bob thì cột đầu tiên của nó cũng sẽ có giá trị là bob
- Ưu điểm là dễ scale, nên dùng cho lưu time-series, historical records, high-write, low-read.
==Document==
- Trade-off:
	- Positives: schema-less (noSQL), relational-ish queries
	- Negative: without joins
- 1 collection sẽ gồm nhiều doc dưới định dạng json, mỗi doc là 1 sub-collection chứa n doc con
- Tiêu biểu sử dụng định dạng kiểu này là mongoDB và firestone.
- Best for: Most apps, Games, IoT
- Not ideal for: Graphs
==Relational==
- Một bảng sẽ có 1 primary key, từ primary key đó ta sẽ liên kết với 1 bảng con join_table
- Tiêu biểu là MySQL
- Yêu cầu phải có schema.
- Best for: Most Apps
- Not ideal for: Unstructured Data.
==Graph==
- Các data sẽ được lưu dưới dạng node, các node được liên kết với nhau bởi edge (relationship). Các node có thể được phân thành các group để dễ quản lý nhờ vào label, nó không có key - value như relational.
- Best For: Graphs, knowledge graphs, recommentdation engines.
- Ứng dụng tiêu biểu: Airbnb
==Search==
- Gồm có các documents được đánh id, và các inverted index (chỉ mục đảo ngược)
- Khi truy xuất dữ liệu nó sẽ tìm trên các inverted index (rất nhanh do dữ liệu đã được sắp xếp) sau đó sẽ trả về ID của các tài liệu tương ứng.
- Ứng dụng tiêu biểu Elastic
- Best for: search engines, typeahead
==Multi-model==
- Ứng dụng tiêu biểu: Fauna
- Là sự kết hợp giữa graphql schema và document relational graph
- Best for: honorable mentions, data warehouse, time-series.
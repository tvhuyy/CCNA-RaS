## Transport Layer, UDP and TCP

## Transport Layer

- Lớp Transport sẽ thực hiện các cơ chế phù hợp để đảm bảo cho quá trình truyền thông
- Lớp Transport có 5 **chức năng** :

	- *Session multiplexing* : Giúp cho các phiên làm việc hoạt động một cách đồng thời và bình đẳng với nhau.
	- *Segmentation* : Giúp phân mảnh gói tin thành nhiều segmen tránh việc truyền một gói tin chiếm hết tài nguyên của các phiên làm việc khác.
	- *Flow control* : theo dõi điều khiển để báo cho server làm chậm quá trình truyền hoặc dừng hẳn khi máy trạm không đủ tài nguyên bộ nhớ đệm.
	- *Connection-oriented* : Quá trình bắt tay ba bước đảm bảo 2 bên máy trạm và server đủ tài nguyên để truyền và nhận dữ liệu.
	- *Reliability* : Đảm bảo độ tin cậy trong suốt quá trình truyền thông.

- Lớp Transport sử dụng khá nhiều các giao thức nhưng chủ yếu sử dụng 2 giao thức là TCP và UDP.

## Giao thức TCP (giao thức truyền thông tin cậy)

- Sử dụng quá trình bắt tay ba bước để truyền nhận dữ liệu :

	-	Bước 1 : Máy truyền sẽ gửi cờ SYN để kiểm tra xem máy nhận có đủ tài nguyên RAM và CPU để nhận dữ liệu hay không.
	-	Bước 2 : Nếu đủ tài nguyên thì máy nhận sẽ gửi cờ SYN để hỏi lại máy truyền có đủ tài nguyên không và cờ ACK để báo nhận.
	-	Bước 3 : Nếu máy truyền cũng đủ tài nguyên thì sẽ gửi lại cờ ACK để xác nhận. Quá trình truyền thông bắt đầu.

- Trước khi gói tin được truyền đi thì nó sẽ được phân mảnh thành các segment khác nhau có đánh số thứ tự.
- Đầu tiên máy truyền sẽ gửi gói tin 1 đi, nếu máy nhận nhận được gói tin thì gửi lại cờ ACK1 để xác nhận đã nhận được gói 1. Sau đó máy truyền sẽ truyền tiếp các gói sau và máy nhận cũng gửi các cờ ACK theo đúng thứ tự.
- Nếu sau một khoảng thời gian nhất định mà máy nhận không được cờ ACK của gói tin thì nó sẽ gửi lại gói tin đó.
- Nhờ quá trình trên mà giao thức TCP có thể đảm bảo quá trình truyền thông tin cậy.
- Để khắc phục nhược điểm truyền tin chậm của TCP thì người ta sử dụng tham số Window size.

## Giao thức UDP (giao thức chuyển phát nhanh)

- Không sử dụng quá trình bắt tay ba bước.
- Khi cần gửi gói tin thì sẽ lập tức chuyển luôn gói tin đến máy nhận. Nhưng trước khi truyền thông thì nó cũng chia nhỏ gói tin thành các segment và sau đó gửi ồ ạt các gói tin qua máy nhận.
- Tốc độ truyền thông nhanh hơn hẳn so với TCP. Tuy nhiên nó có nhược điểm là nguy cơ mất mát dữ liệu trong quá trình truyền thông.

### So sánh 2 giao thức TCP và UDP

- Trong thực tế có một số kiểu truyền dữ liệu cần sự kết hợp của cả 2 giao thức. Ví dụ như VoIP, đầu tiên nó sẽ sử dụng TCP để bắt đầu cuộc gọi, sau khi đã kết nối thành công thì nó sẽ gửi 2 luồng UDP trao đổi giữa 2 thiết bị.
- **Sự khác biệt** : 

	- UDP có tốc độ truyền phát nhanh hơn nhiều so với TCP.
	- TCP đảm bảo sự toàn vẹn của gói tin còn UDP thì không.

## Các trường trong TCP Header

![a](https://i.imgur.com/ihWDQKY.png)

### TCP Acknowledgment

- **Window Size = 1**

	Với window size bằng 1 thì mỗi lần sender chỉ có thể gửi duy nhất 1 segment cho đến khi được hồi đáp ack thành công.

![a](https://i.imgur.com/7fKNIdb.png)

### Fixed Windowing

- **Window Size = 3**

	Để cải thiện tốc độ của TCP thì window size sẽ được đặt = 3. Lúc này Sender sẽ gửi liên tiếp 3 segment 123 và đợi hồi đáp ACK 4 khi receiver nhận được cả 3 segment. Trong quá trình truyền thông, nếu một segment bị lỗi thì receiver sẽ gửi lại ack với số thự tự của segment đó, máy sender sẽ gửi lại 3 segment theo thứ tự từ segment bị lỗi trở đi.

![a](https://i.imgur.com/2KzRAdB.png)

### Sliding Windowing

- Cơ chế hoạt động : 
	Hệ điều hành sẽ ước lượng tài nguyên máy đang còn bao nhiêu (CPU, RAM) rồi quyết định giá trị của Window size.
- Khi máy truyền có window size = 3, nó sẽ gửi đi 3 segment, trường hợp máy nhận chỉ có window size = 2 thì nó sẽ gửi lại gói ACK 3 và báo window size =2. Sau đó máy sender nhận được ACK này sẽ gửi lại gói segment 3 và chỉ gửi liên tiếp 2 segment, nhưng nó vẫn gửi window size = 3 để khi nào máy nhận có giải phóng được tài nguyên thì sẽ tự động nâng window size lên.

![a](https://i.imgur.com/zEAQfe2.png)

### Sequence và ACK

- **Tham số Sequence** : bản tin đầu tiên được truyền đi sẽ có số sequence = với số bytes data được gửi đi. Bản tin thứ 2 sẽ có số sequence = với số bytes gửi đi của bản tin 2 + với số bytes gửi của bản tin đầu.
- **Tham số ACK** : Khi máy nhận nhận được bản tin đầu tiên thì nó gửi lại bản tin có số ACK = số Sequence nhận được + với 1.

![a](https://i.imgur.com/BFLgo2y.png)

## UDP Header

![a](https://i.imgur.com/CK2iPDs.png)

### S.Port và D.Port

- Theo quy ước thế giới thì các port từ 1 đến 1023 là chỉ các dịch vụ được quy ước sẵn gán cho các port
- S.Port khi được gửi đi sẽ được định danh bằng các số port bắt đầu bằng Port 1024 rồi liên tiếp các phiên sau sẽ theo thứ tự tăng dần.
- Khi máy nhận nhận được bản tin và hồi đáp thì sẽ đảo ngược S.port và D.port rồi gửi lại máy gửi.

### Mapping Layer 4 to Application Layer.

- Một số Application thường dùng và Port Number của App đó :

![a](https://i.imgur.com/BJslsIM.png)


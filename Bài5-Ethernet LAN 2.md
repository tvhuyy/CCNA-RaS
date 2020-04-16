## Ethernet LAN : Xác định số lượng Broadcast và collision domain

### Communication Type

- *Unicast* : 1 thiết bị gửi đến 1 thiết bị bằng cách gửi Frame có gắn định danh MAC của máy cần nhận.
- *Broadcast* : 1 thiết bị gửi đến toàn bộ thiết bị trong mạng bằng cách gửi Frame có MAC đi kèm là địa chỉ có toàn bộ kí tự là **F** 
- *Multicast* : 1 thiết bị gửi đến một nhóm thiết bị.

### Switching

- Khi một máy cần gửi gói tin đến một máy khác thì nó sẽ soạn Frame có cấu trúc S.MAC là chính nó và D.MAC là mac của máy đích. Còn khi nó muốn gửi đến toàn bộ máy trong mạng thì nó sẽ soạn Frame có cấu trúc S.MAC là mac chính nó và D.MAC là FFFF:FFFF:FFFF:FFFF

### Broadcast Domain

- Là một vùng mạng mà trong đó khi có một máy gửi gói tin Broadcast thì tất cả các máy trong vùng mạng đó đều nhận được. 
- Các máy trong Broadcast Domain nằm trong cùng một lớp mạng.
- Nếu Broadcast Domain quá lớn sẽ ảnh hưởng đến hiệu suất mạng. Nên cần phải chia nó thành nhiều Broadcast Domain nhỏ bằng thiết bị Router.

- **Sự khác biệt giữa Hub và Switch** :

	- Switch được coi là thiết bị lớp 3. Khi nhận được Frame, có khả năng đọc thông tin layer 2 header (S.MAC-D.MAC) rồi đẩy ra chính xác port cần đến.
	- Hub được coi là thiết bị lớp 1. không có khả năng đọc layer 2 header. Nó sẽ nhận tín hiệu có dạng nhị phân rồi khuếch đại và gửi đến tất cả các thiết bị kết nối.

- **Full Duplex on Switch** : Khi các thiết bị mạng kết nối với nhau qua sw, thì chúng có khả năng hoạt động ở chế độ Full Duplex. Chế độ này cho phép thiết bị gửi và nhận thông tin một cách đồng thời.

- **Half Duplex on Hub** : Khi các thiết bị kết nối với nhau thông qua hub thì nó chỉ chạy ở chế độ half duplex. Chế độ Half duplex nghĩa là tại 1 thời điểm thì thiết bị chỉ có thể gửi hoặc nhận dữ liệu.

### Collision Domain

- Là một vùng mạng mà trong đó 2 thiết bị bất kì trong vùng mạng gửi dữ liệu ra mà có khả năng xảy ra đụng độ.
- Collision Domain chỉ xảy ra khi sử dụng thiết bị Hub.
- Có thể chia nhỏ một Collision Domain thành nhiều CD nhỏ bằng cách sử dụng SW.
- Một Collision domain cũng được coi là một Broadcast Domain.

- **CSMA/CD** : Để tránh đụng độ trong Coliision domain thì ta nên sử dụng cơ chê CSMA/CD.

	- CSMA/CD được kích hoạt trên card mạng của PC.
	- Trước khi PC truyền dữ liệu thì nó sẽ lắng nghe xem có ai truyền dữ liệu hay không. Nếu không có ai truyền dữ liệu thì nó mới bắt đầu truyền tín hiệu đi.
	- Khi các thiết bị trong mạng phát hiện ra xung đột thì nó sẽ gửi ra tín hiệu xung báo nghẽn gọi là tín hiệu *JAM*. Khi xung báo nghẽn được phát ra thì thuật toán *Backoff Algorithm* trong cơ chế chống đụng độ CSMA/CD mới được kích hoạt lên.
	- Thuật toán này sẽ phân cho các PC cần giao tiếp một khoảng thời gian trên từng máy. Khi một máy cần truyền thì nó sẽ không truyền ngay mà phải đợi hết khoảng thời gian được phân cho rồi mới truyền.

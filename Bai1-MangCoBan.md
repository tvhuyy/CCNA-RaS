## Mạng Cơ Bản
### 1. Thế nào là hệ thống mạng :
- Một hệ thống mạng bao gồm từ 2 thiết bị trở lên được kết nối thông qua cáp dây hoặc không dây qua wifi,bluetooth với nhau và có khả năng truyền thông với nhau.
- Ví dụ một hệ thống mạng cơ bản :

![a](https://i.imgur.com/Bxov5b1.png)

### 2. Switch Function
- Switch giúp các thiết bị trong hệ thống mang như các PC kết nối với nhau dễ dàng hơn

![a](https://i.imgur.com/iHyU66H.png)
### 3. Router Function
- Router có chức năng kết nối nhiều hệ thống mạng LAN lại với nhau, hoặc từ các site lại với nhau.

![a](https://i.imgur.com/0O2MTbE.png)

### 4. Các đặc điểm của hệ thống mạng tiêu chuẩn
- Tốc độ (Speed)
- Chi phí (Cost)
- Bảo mật (Security)
- Độ sẵn sàng (Availability)
- Độ mở rộng (Scalability)
- Độ tin cậy trong quá trình truyền thông (Reliability)
- Các thiết bị kết nối với nhau như nào (Topology)


![a](https://i.imgur.com/cyC8PUT.png)


#### Speed
- Tốc độ bên trong hệ thống mạng :
	* Các thiết bị LAN cắm cáp cần có cổng mạng tốc độ tối đa như nhau để dùng tối đa được đường truyền.
	* Các thiết bị wifi thì cần có AP (access point). Cần chú ý đến tốc độ của các chuẩn wifi như sau : 802.11 b/g/a/n/ac tương ứng tốc độ 2/54/300/1300 Mbps. Cần chú ý thêm tốc độ tối đa đạt được sẽ chia đều cho các thiết bị sử dụng đồng thời.

- Tốc độ bên ngoài hệ thống mạng :

	* Tốc độ tải từ bên ngoài phụ thuộc vào gói mạng thuê từ nhà mạng. Ngoài ra còn bị giới hạn từ server của trang web hoặc ứng dụng đang sử dụng.

#### Cost (chi phí)

- Chi phí đầu tư ban đầu : Các PC, Switch, Router, hệ thống Server.
- Chi phí duy trì hệ thống, thuê IT, Admin, chi phí điện, mạng.
- Chi phí cho các hệ thống UPS để đảm bảo luôn cung cấp nguồn điện cho server

#### Security (Bảo mật)

- Hệ thống cần trang bị Firewall (firewall cứng hoặc software firewall).
- Cần trang bị các loại Switch có chức năng PortSecurity, DHCP snooping,...

#### Availability (Độ sẵn sàng)

- Cần ít nhất 2 kết nối đi Internet (khác nhà cung cấp)

#### Scalability (Khả năng mở rộng)

- Cần trang bị các router, switch có khả năng cân tải, phục vụ lớn hơn so với lúc triển khai để có thể dễ dàng mở rộng mô hình cho sau này.

#### Reliability (Độ tin cậy)

- Cần sử dụng các tool để mã hóa dữ liệu, tránh bị rò rỉ thông tin.

#### Topology

- Cách lắp đặt các thiết bị theo mô hình để sử dụng tối ưu nhất.
- Có 3 mô hình cơ bản :
	* *Bus Topology* : Các PC, thiết bị mạng được kết nối với nhau thông qua 1 trục bus. Khi 1 thiết bị gửi tín hiệu đi thì nó sẽ gửi đi tất cả các thiết bị còn lại -> tốn băng thông đường truyền và không bảo mật.

	![a](https://i.imgur.com/nypxl5Z.png)
	
	* *Ring Topology* : Các thiết bị được kết nối với nhau theo vòng ring. Khi một thiết bị gửi tín hiệu, thiết bị sẽ đi theo dạng vòng cho đến khi tìm được đích -> không tối ưu.

	![a](https://i.imgur.com/VmwXWlk.png)

	* *Star Topology* : Các thiết bị mạng được kết nối thông qua một thiết bị tập trung như switch hoặc router. Khi một thiết bị muốn gửi tín hiệu đến thiết bị khác, thì nó chỉ cần gửi đến thiết bị tập trung, rồi sẽ được gửi đến chính xác thiết bị nhận -> tối ưu, được sử dụng nhiều nhất.

	![a](https://i.imgur.com/QUV4j9k.png)

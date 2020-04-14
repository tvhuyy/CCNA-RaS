## Ethernet LAN : Local Area Network

### Mạng LAN :

- Local Area Network (Mạng cục bộ). Mạng LAN là sự kết hợp của nhiều thiết bị được kết nối lại với nhau trong một hệ thống mạng tại một khu vực nhất định.
- Đặc thù của mạng LAN là khi các thiết bị muốn gửi nhận cho nhau thì chúng sẽ soạn một Frame gồm S.MAC và D.MAC.

### LAN Components (thành phần)
	
Các thành phần của mạng LAN bao gồm

- **Computers**

	-	PCs
	-	Servers
- **Interconnections**

	-	NICs (Network Interface Card)
	-	Media
- **Network devices**

	-	Hubs
	-	Switches
	-	Routers
- **Protocols**

	-	Ethernet
	-	IP
	-	ARP
	-	DHCP

### Switching

- Trên môi trường Ethernet LAN, các thiết bị muốn gửi và nhận dữ liệu với nhau sẽ chúng sẽ soạn các Frame với thông tin MAC nguồn, MAC đích rồi sau đó được trung chuyển trong mạng LAN nhờ cơ chế chuyển mạch của Switch.
- Để Switch có thể hoạt động chuyển mạch được thì nó sẽ căn cứ vào bảng chuyển mạch là MAC Address Table.

### Frame Structure

- Frame là đơn vị thuộc lớp 2 - Data link. Frame gồm có 2 phần : header và data.
- Header gồm có :

	- *Destination MAC* - dài 48 bit, gồm 24 bit đầu định danh cho hãng sản xuất(OUI) và 24 bit sau định danh cho từng card mạng (Vendor Assigned).
	- *Source MAC*, 
	- *Type* - thông báo cho card mạng biết được nội dung của Data chưa bản tin gì.
	- *FCS* (trường kiểm tra lỗi)

-	Phần Data chứa các dữ liệu thuộc các kiểu bản tin khác nhau.

### ARP - Address Resolution Protocol (giao thức phân giải địa chỉ IP,MAC)

- Là giao thức phân giải địa chỉ động giữa địa chỉ lớp network và địa chỉ lớp datalink.
- Quá trình thực hiện bằng cách : một thiết bị IP trong mạng gửi một gói tin local broadcard đến toàn bộ mạng yêu cầu thiết bị khác gửi trả lại địa chỉ MAC.
- Quá trình thực hiện ARP được bắt đầu khi một thiết bị nguồn trong một mạng IP có nhu cầu gửi một gói tin IP. Đầu tiên nó cần xác định IP đích có nằm cùng lớp mạng không. Nếu cùng trong lớp mạng thì nó sẽ gửi luôn gói tin đến thiết bị đích, nếu không nó gửi gói tin đến một trong các router và để router này forward gói tin.
- ARP về cơ bản là một quá trình 2 chiều request/response giữa các thiết bị trong cùng mạng nội bộ. Máy nguồn gửi broadcast trên toàn mạng, máy đích gửi trả bằng unicast đến máy nguồn.
- Có 2 dạng bản tin trong ARP :

	-	Request : Khởi tạo quá trình, gói tin được gửi từ thiết bị nguồn đến thiết bị đích.
	-	Reply : Là quá trình đáp trả gói tin ARP request, được gửi từ máy đích đến máy nguồn.

- Có 4 loại địa chỉ trong một bản tin ARP : sender MAC, sender IP, target MAC, target IP.
- *ARP Caching* : Quá trình gửi và nhận gói tin sẽ tiêu tốn băng thông mạng. Chính vì vậy sau mỗi lần phân giải thì địa chỉ sẽ được lưu vào cache.
- *Proxy ARP* : Để các máy không cùng lớp mạng có thể giao tiếp và phân giải địa chỉ của nhau thì nó cần router forward gói tin. Vì vậy proxy giúp các máy nhận được MAC table của Router từ đó có thể giao tiếp khác lớp mạng.

## Mô Hình OSI và TCP/IP

### 1. OSI Model (Open Systems Interconnection)

- Là mô hình giúp chuẩn hóa để các thiết bị mạng từ nhiều nhà cung cấp khác nhau có thể giao tiếp đồng nhất với nhau.
- Được thiết kế dựa vào nguyên lý tầng cấp. Được chia thành 7 lớp. Lớp 1-4 thực hiện việc di chuyển dữ liệu, lớp 5-7 chứa các dữ liệu ở cấp độ ứng dụng.
- Có 2 ứng dụng chính : 
	- Giúp cho quá trình nghiên cứu và học tập.
	- Giúp cho quá trình nghiên cứu khắc phục sự cố.

![a](https://i.imgur.com/QsylkhS.png)

### 1.1 Tổng quan về các tầng trong mô hình OSI

- **Lớp Physical** : Là lớp phần cứng giúp chuyển các tín hiệu Binary (0,1). Chuẩn hóa một số đặc tả liên quan như các loại cáp, các loại đầu kết nối, chuẩn kết nối có dây, không dây.
- **Lớp Data Link** : Là lớp quy định cấu trúc đơn vị dữ liệu phù hợp với từng môi trường truyền thông. Định nghĩa cơ chế kiểm tra lỗi trong quá trình truyền thông.
- **Lớp Network** : Có các chức năng như định tuyến gói tin, chọn đường đi tối ưu, quy định cấu trúc của từng loại địa chỉ IP trên từng môi trường khác nhau.
- **Lớp Transport** : Đảm bảo quá trình truyền thông không bị mất mát dữ liệu.
- **Lớp Session** : Điều phối quá trình truy cập mạng bằng cách thiết lập, quản lý, chấm dứt phiên làm việc. Đảm bảo các quá trình truy cập bình đẳng, đồng thời trong 1 thời điểm.
- **Lớp Presentation** : Đảm bảo các thiết bị từ đầu cuối đến đầu cuối trong quá trình truyền thông có thể đọc hiểu được.
- **Lớp Application** : Cung cấp các ứng dụng sử dụng các giao thức để người dùng có thể tương tác và sử dụng được hạ tầng mạng

### 2. TCP/IP Model

- Chỉ gồm có 4 lớp.
- Các nhà cung cấp thiết bị mạng thường chủ yếu dựa vào mô hình này

![a](https://i.imgur.com/554Y8rt.png)


### 2.1 Tổng quan các lớp

- **Lớp Application** : Gộp cả 3 lớp Application, Presentation, Session của OSI thành một lớp. Các nhà sản xuất thiết bị và lập trình thường sẽ làm cả 3 công đoạn này nên gộp chung vào thành 1 lớp.
- **Lớp Transport** : Vẫn giữ nguyên như bên OSI.
- **Lớp Internet** : Đổi tên từ lớp Network của OSI thành lps Internet còn chức năng thì không có gì khác biệt.
- **Lớp Network Access** : Gộp 2 phân lớp Data Link và Physical của mô hình OSI thành một. Các nhà sản xuất thiết bị switch hay card mạng thường làm cả 2 lớp nên sẽ gộp thành 1 luôn.

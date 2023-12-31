# SIP2TEST

SIP2TEST là server xử lý dữ liệu đầu ra/ vào từ thiết bị sử dụng giao thức SIP2 ([Docs](https://developers.exlibrisgroup.com/wp-content/uploads/2020/01/3M-Standard-Interchange-Protocol-Version-2.00.pdf)). 

Thiết bị được giả lập qua công cụ [SIP Testing Tool](https://clcohio.org/sip-testing-tool/)


## Installation

1. Clone repo.

```bash
git clone https://github.com/nna2k2/SIP2TEST.git
```

2. Cài đặt docker. Build image và chạy container.
```bash
docker-compose up -d
```

3. Cài đặt [SIP Testing Tool](https://clcohio.org/sip-testing-tool/)


## Usage
*Chưa sử dụng được Docker do bị lỗi cổng*

1. Sau khi chạy container/ xampp, truy cập http://localhost:8080 (docker) hoặc http://localhost (xampp).

2. Nhập IP và port sau đó nhấn Start để chạy Server.

3. Vào SIP Testing Tool, nhập IP và port tương ứng sau đó nhấn Connect. 

4. Sau khi kết nối thành công với thiết bị SIP Testing Tool, tuỳ chọn các chức năng và thông báo sẽ được hiển thị ở phần Logs bên server. 

5. Để tắt server nhấn Stop.

## Example
Nếu xử lý nhận dữ liệu và gọi API thành công
![Hình minh hoạ](minhhoa.png)

## Directory Structure
    SIP2TEST/
    ├── .idea/
    ├── getData/                # Xử lý nhận dữ liệu từ sip-testing-tool
    ├── logs/                   # Lưu log (mỗi lần kết nối tạo thêm 1 file log)
    ├── messages/               # Định nghĩa các lớp ứng với mỗi loại tín hiệu của giao thức sip2
    ├── postData/               # Gửi dữ liệu theo đầu vào chuẩn của API
    ├── web/                    # Css, js của giao diện admin
    ├── .DS_Store               
    ├── .gitignore               
    ├── Dockerfile               
    ├── README.md              
    ├── api.php                 # Gọi API
    ├── checkSum.php            # Xử lý checksum               
    ├── docker-compose.yml              
    ├── getData.php             # Định tuyến các hàm xử lý nhận dữ liệu với từng loại tín hiệu
    ├── getLatestFile.php       # Cập nhật giao diện logs admin               
    ├── index.php               # Giao diện admin
    ├── messageHandle           # Định tuyến các hàm xử lý dữ liệu trả về với từng loại tín hiệu              
    ├── redirect.php                           
    ├── saveToJson.php                         
    ├── server.php              # Tạo server (mở, đóng socket)              
    ├── startServer.php         
    ├── stopServer.php         
    




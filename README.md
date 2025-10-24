# BT_Web_2
## Mục tiêu bài tập :
1. Cấu hình và kết nối Apache + Node.js + Node-RED + SQL Server, sau đó xây dựng website front-end và API back-end, ghi lại toàn bộ quá trình lên GitHub.

## **II. Cài đặt và cấu hình**
### 2.1. Apache Web Server
- *Cấu hình file httpd.conf*
  Mở file **D:\Apache24\conf\httpd.conf**, đảm bảo các dòng sau được bỏ comment (xóa dấu # nếu có):
  <img width="577" height="96" alt="image" src="https://github.com/user-attachments/assets/523e8523-5079-4c94-a4c4-67adc21cede0" />
- *Cấu hình Virtual Host trong **httpd-vhosts.conf***
  <img width="661" height="275" alt="image" src="https://github.com/user-attachments/assets/6f507705-f991-478c-84cc-f84b73f3b8c1" />

- *Cấu hình file **hosts** để trỏ domain về localhost*
    <img width="683" height="124" alt="image" src="https://github.com/user-attachments/assets/05b048b5-d67f-4f5c-85ea-4c45c4553c65" />  
-*Cài đặt và khởi động Apache.*       
  Mở CMD tại thư mục **D:\Apache24\bin**, chạy:  
### 2.2. Cài đặt nodejs và nodered   

- Cài đặt Node.js và kiểm tra version   
<img width="411" height="177" alt="image" src="https://github.com/user-attachments/assets/9ce4565f-9ea4-47c5-bf2c-37c175b1ef30" />
 
- *Cài **Node-RED làm backend***   
  Cài đặt Node-RED vào thư mục riêng chạy lệnh : <br>
  **npm install -g --unsafe-perm node-red --prefix "D:\nodejs\nodered"** cài đặt thành công <br>
  
  <img width="1206" height="326" alt="image" src="https://github.com/user-attachments/assets/0bdd7dd9-7683-4afe-80a2-1edf7dacfec5" />
  
- *Tải và cấu hình NSSM (Service Manager)*
  Tải file : **https://nssm.cc/release/nssm-2.24.zip**     
Giải nén, lấy file **nssm.exe** Copy **nssm.exe**
vào thư mục: *D:\nodejs\nodered\**    

- *Tạo file chạy Node-RED*
<img width="987" height="703" alt="image" src="https://github.com/user-attachments/assets/9d1cd153-8b2b-4c58-a3de-1013c68b6556" />   

- *Cài đặt Node-RED thành Windows Service*
  Mở CMD tại D:\nodejs\nodered, chạy: **nssm.exe install a1-nodered "D:\nodejs\nodered\run-nodered.cmd"**   
khởi động service:**nssm start a1-nodered**   
  
  <img width="1008" height="118" alt="image" src="https://github.com/user-attachments/assets/453d015f-fcbe-43d6-9681-eacfd09ef73d" />   

-*Kiểm tra hoạt động*  
 Giao diện Node-RED đã hiển thị thành công **http://localhost:1880**  
<img width="1819" height="969" alt="image" src="https://github.com/user-attachments/assets/e2c5782e-283c-4c92-83ea-1e352fc7d707" />   

### 2.3 Tạo CSDL trên SQL
<img width="1173" height="489" alt="image" src="https://github.com/user-attachments/assets/12a3f615-c004-4bb3-b11b-dbab2a982f92" />
- Dữ liệu demo   
<img width="1100" height="464" alt="image" src="https://github.com/user-attachments/assets/1890b32f-710c-41d6-bf18-13739dfa1a6b" />


### 2.4. Cài đặt thư viện trên nodered:
- Vào menu ≡ → Manage palette → Install
   <img width="1269" height="437" alt="image" src="https://github.com/user-attachments/assets/23b53444-d597-4474-91bf-27fa5d1ec4c3" />

  Tìm và cài các thư viện sau:
**node-red-contrib-mssql-plus**  
**node-red-node-mysql**   
**node-red-contrib-telegrambot**   
**node-red-contrib-moment**   
**node-red-contrib-influxdb**  
**node-red-contrib-duckdns**  
**node-red-contrib-cron-plus**     
- Sửa file **settings.js** để bật xác thực admin:

### 2.5. tạo api back-end bằng nodered:
<img width="1405" height="504" alt="image" src="https://github.com/user-attachments/assets/a00b1eb1-de76-432e-841f-fca40cab6fd0" />

- Test IPA : http://localhost:1880/timkiem?q=th%E1%BB%8B
<img width="674" height="491" alt="image" src="https://github.com/user-attachments/assets/105b3c6e-ec50-4423-8b4e-493df9844a68" />

### 2.6. Tạo giao diện front-end:
- cấu trúc file D:\\Apache24\nguyentheduong
- html, css, js
  <img width="1675" height="759" alt="image" src="https://github.com/user-attachments/assets/3b5fcc5b-9b86-4ea0-9342-a26a8ed7db52" />
- Web tra cứu học viên
<img width="1888" height="1019" alt="image" src="https://github.com/user-attachments/assets/82410ac5-e770-4097-baa3-d2625c5081fb" />

### 2.7. Nhận xét bài làm
*1. Hiểu quá trình cài đặt phần mềm và thư viện*
- Nắm rõ cách vô hiệu hóa IIS để tránh xung đột cổng 80 khi cài Apache.
- Quá trình cài đặt Apache, cấu hình httpd.conf, httpd-vhosts.conf, và sử dụng file hosts để tạo domain ảo là chính xác và thực tế.
- Việc cài đặt Node.js, Node-RED, và sử dụng NSSM để chạy Node-RED như một service là cách làm chuyên nghiệp, giúp hệ thống ổn định và tự động khởi động
- Biết cách cài đặt thư viện Node-RED thông qua giao diện, và chỉnh sửa settings.js để thiết lập bảo mật cho admin

*2. Hiểu cách sử dụng Node-RED để tạo API back-end*

- Biết cách sử dụng các node cơ bản: http in, function, MSSQL, http response, và debug.
- Flow API /timkiem được thiết kế hợp lý, có xử lý tham số, truy vấn CSDL, và trả về JSON đúng chuẩn RESTful.
- Biết cách test API qua trình duyệt — điều này cho thấy bạn hiểu cách kiểm tra và debug hệ thống back-end.
*3. Hiểu cách front-end tương tác với back-end*

  - Biết cách tạo giao diện HTML, CSS, JS đặt đúng thư mục Apache.
  - File JS có logic gọi API bằng fetch, xử lý JSON trả về và hiển thị kết quả — đây là cách tương tác chuẩn giữa front-end và back-end.
  - Hiểu cách tổ chức hệ thống và định danh cá nhân hoá.










  

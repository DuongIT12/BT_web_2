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























  

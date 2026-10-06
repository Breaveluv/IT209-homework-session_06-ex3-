# Báo cáo Bài 3: Cấu hình tường lửa UFW và Chẩn đoán cổng mạng

## 1. Cấu hình Tường lửa UFW

Các lệnh đã thực hiện trên máy chủ:

```bash
# Thiết lập chính sách mặc định
sudo ufw default deny incoming
sudo ufw default allow outgoing

# Mở cổng 22 (SSH) và 8080 (Web App)
sudo ufw allow 22/tcp
sudo ufw allow 8080/tcp

# Kích hoạt UFW
sudo ufw enable
2. Kết quả Kiểm tra Trạng thái
Kiểm tra bằng sudo ufw status verbose
Plaintext
Status: active
Logging: on (low)
Default: deny (incoming), allow (outgoing), disabled (routed)
New profiles: skip

To                         Action      From
--                         ------      ----
22/tcp                     ALLOW IN    Anywhere                  
8080/tcp                   ALLOW IN    Anywhere                  
22/tcp (v6)                ALLOW IN    Anywhere (v6)             
8080/tcp (v6)              ALLOW IN    Anywhere (v6)             
Kiểm tra bằng ss -tlnp
Plaintext
State      Recv-Q Send-Q Local Address:Port  Peer Address:Port Process
LISTEN     0      128          0.0.0.0:22         0.0.0.0:*    
LISTEN     0      128          0.0.0.0:8080       0.0.0.0:*

# Linux Command Cheat Sheet

Tài liệu tổng hợp các câu lệnh Linux cơ bản, hữu ích cho người sử dụng EC2 hoặc các hệ thống chạy Linux.

---

## 1. Quản lý thư mục và tệp

```bash
# Di chuyển vào thư mục
cd /duong/dan/thu_muc

# Quay lại thư mục trước đó
cd -

# Hiển thị đường dẫn hiện tại
pwd

# Liệt kê tệp và thư mục
ls -al

# Tạo thư mục mới
mkdir ten_thu_muc

# Xóa thư mục rỗng
rmdir ten_thu_muc

# Xóa thư mục và toàn bộ nội dung
rm -rf ten_thu_muc

# Tạo tệp mới
touch ten_tap_tin.txt

# Xóa tệp
rm ten_tap_tin.txt

# Sao chép tệp
cp file1.txt /duong/dan/

# Di chuyển hoặc đổi tên tệp
mv file1.txt file2.txt
```

---

## 2. Xem và chỉnh sửa nội dung tệp

```bash
# Hiển thị nội dung tệp
cat ten_tap_tin

# Xem nội dung có cuộn trang
less ten_tap_tin
more ten_tap_tin

# Xem 10 dòng đầu
head ten_tap_tin

# Xem 10 dòng cuối
tail ten_tap_tin

# Theo dõi log thời gian thực
tail -f log.txt

# Chỉnh sửa với nano
nano ten_tap_tin

# Chỉnh sửa với vim
vim ten_tap_tin
```

---

## 3. Hệ thống và tài nguyên

```bash
# Xem thông tin hệ điều hành
uname -a
cat /etc/os-release

# Thông tin CPU
lscpu

# Số core CPU
nproc

# Dung lượng RAM
free -m
free -h

# Dung lượng ổ đĩa
df -h

# Phân vùng đĩa
lsblk

# Thống kê tiến trình
top
htop  # Cần cài đặt

# Dừng tiến trình
kill PID

# Tìm tiến trình
ps aux | grep <ten>

# Thời gian hoạt động
uptime
```

---

## 4. Mạng

```bash
# Xem địa chỉ IP
ip addr
hostname -I

# Kiểm tra kết nối mạng
ping google.com

# Kiểm tra cổng mở
netstat -tulpn
ss -tulpn

# Xem route mạng
ip route

# Kết nối SSH
ssh user@ip_address

# Tải file từ URL
wget https://url
curl -O https://url
```

---

## 5. Phân quyền và người dùng

```bash
# Thêm quyền thực thi
chmod +x script.sh

# Thay đổi quyền truy cập
chmod 755 file

# Thay đổi chủ sở hữu
chown user:group file

# Kiểm tra người dùng hiện tại
whoami

# Chuyển sang root
sudo su

# Thực thi với quyền root
sudo <lenh>
```

---

## 6. Quản lý gói phần mềm

### Ubuntu/Debian:
```bash
sudo apt update
sudo apt install <ten_goi>
sudo apt remove <ten_goi>
```

### Amazon Linux / CentOS / RHEL:
```bash
sudo yum update
sudo yum install <ten_goi>
sudo yum remove <ten_goi>
```

---

## 7. Khác

```bash
# Xem lịch sử lệnh
history

# Tìm file theo tên
find / -name "tenfile*"

# Tìm chuỗi trong tệp
grep "chuoi" tenfile.txt

# Xóa cache bộ nhớ (thận trọng)
sync; echo 3 > /proc/sys/vm/drop_caches
```

---

## 8. Giám sát hiệu năng CPU

```bash
# Giám sát CPU thời gian thực
top
htop  # Cần cài đặt

# Sử dụng mpstat (trong gói sysstat)
sudo apt install sysstat  # Ubuntu
sudo yum install sysstat  # CentOS
mpstat 1 5

# Benchmark CPU với sysbench
sudo yum install epel-release -y
sudo yum install sysbench -y
sysbench cpu --cpu-max-prime=20000 run
```

---

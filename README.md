# Hướng dẫn chạy NTTT-TooL-checksdt

Dưới đây là tổng hợp các lệnh chuẩn nhất để chạy Tool trên cả 3 môi trường: Termux (Điện thoại), CMD (Windows), và Terminal (Mac/Linux). 

---

## 1. Môi trường TERMUX (Android)

Do trên các bản Termux mới (Python 3.11+), lệnh `pip` mặc định bị chặn để bảo vệ hệ thống (lỗi `externally-managed-environment`), bạn cần chạy lệnh cài thư viện với đuôi `--break-system-packages`.

**Các lệnh lần lượt:**
```bash
# 1. Cấp quyền truy cập bộ nhớ cho Termux (Nếu Lần đầu tải Termux)
termux-setup-storage

# 2. Cập nhật các gói và cài đặt Python
pkg update && pkg upgrade -y
pkg install python -y

# 3. Di chuyển vào thư mục chứa Tool (Giả sử tool nằm ở mục Download)
cd /sdcard/Download/NTTT-TooL-check-sdt

# 4. Cài đặt các thư viện cần thiết (Thêm cờ bypass lỗi đỏ)
pip install requests pyfiglet colorama --break-system-packages

# 5. Khởi chạy Tool (Lưu ý: Dùng file gốc chưa mã hoá để tránh lỗi do lệnh marshal)
python NTTT-TooL-checksdt.py
```

---

## 2. Môi trường Windows (CMD / PowerShell)

Trên Windows tool sẽ tự động nhận diện và cài đặt thư viện cho bạn ở trong mã nguồn, nhưng bạn vẫn có thể làm thủ công nếu muốn chắc chắn. 

Đảm bảo bạn đã cài thẻ cài đặt Python (Nhớ tick ô **Add Python.exe to PATH** lúc cài).

**Các lệnh lần lượt:**
```cmd
# 1. Mở CMD và di chuyển vào thư mục Desktop chứa tool của bạn
cd %USERPROFILE%\Desktop\NTTT-TooL-check-sdt

# 2. Cài đặt các thư viện (nếu Tool không tự cài được do thiếu quyền Admin)
pip install requests pyfiglet colorama

# 3. Khởi chạy Tool
python NTTT-TooL-checksdt.py
```

---

## 3. Môi trường Terminal (Linux / macOS)

Giống hệt cách hoạt động trên máy tính thông thường, đôi khi trên Mac và Ubuntu bản mới bạn cũng cần cài thư viện qua venv (môi trường ảo) hoặc ép cài đè.

**Các lệnh lần lượt:**
```bash
# 1. Di chuyển vào vị trí thư mục (tuỳ vào nơi bạn lưu thư mục này)
cd ~/PATH_ĐẾN_FODER/NTTT-TooL-check-sdt

# 2. Cài đặt thư viện - Trên Linux (Ubuntu/Debian) bản dùng Python 3.11+, thêm đuôi y như Termux:
pip3 install requests pyfiglet colorama --break-system-packages

# Hoặc nếu là macOS/Các bản linux đời cũ:
pip3 install requests pyfiglet colorama

# 3. Khởi chạy Tool
python3 NTTT-TooL-checksdt.py

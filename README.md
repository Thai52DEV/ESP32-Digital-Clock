# 1.1. Đề tài

## 1.1.1. Tên đề tài
**Đồng hồ điện tử**

## 1.1.2. Mô tả
Đồng hồ điện tử có 4 chế độ chính:

- **Chế độ 1: Màn hình chính**  
  Xem và chỉnh sửa giờ, phút, giây, ngày, tháng, năm; xem nhiệt độ và độ ẩm.

- **Chế độ 2: Báo thức**  
  Cài đặt giờ báo thức, reo chuông báo thức, tắt chuông báo thức.

- **Chế độ 3: Bấm giờ**  
  Đếm thời gian, dừng đếm thời gian, reset thời gian.

# 1.2. Phần cứng

## 1.2.1. ESP32 NodeMCU LuaNode32

- **Loại**: Board  
- **Điện áp cấp**: 5V  
- **Tích hợp Bluetooth**: Có  
- **Vi xử lý chính**: ESP-WROOM-32  
- **Giao tiếp**: UART

<img width="300" height="300" alt="image" src="https://github.com/user-attachments/assets/5695b051-ccf9-4f01-881a-93c3349ceaf1" />
## 1.2.2. Màn hình LCD1602

- **Số ký tự**: 16x02 ký tự  
- **Loại giao tiếp**: Parallel 8-bit  
- **Điện áp cấp**: 3.3V  
- **Màu nền**: Xanh dương  
- **Màu chữ**: Trắng
<img width="300" height="300" alt="image" src="https://github.com/user-attachments/assets/95a73f22-a7a4-47b8-bec7-9347a5fe602d" />

## 1.2.3. Buzzer

- **Cách gắn**: Xuyên lỗ  
- **Điện áp định mức**: 3V DC  
- **Cường độ âm thanh tối thiểu**: 80 dB  
- **Loại Drive**: Trong  
- **Loại Tone**: Liên tục  
- **Kích thước**: 9 x 4.2mm  
- **Nhiệt độ hoạt động**: -20°C đến +60°C  
- **Dòng điện**: 100mA  
- **Tần số**: 2700Hz

<img width="300" height="300" alt="image" src="https://github.com/user-attachments/assets/3446d235-9c4e-472c-a02b-76d140b1d830" />

## 1.2.4. Cảm biến nhiệt độ, độ ẩm DHT22

- **Chức năng**: Đo nhiệt độ, độ ẩm  
- **Ngõ ra**: Digital  
- **Nguồn cấp**: 3.3V

<img width="300" height="300" alt="image" src="https://github.com/user-attachments/assets/a14233ac-0f13-4cb1-bcda-456b015c735f" />


## 1.2.5. Các linh kiện khác

- **Điện trở 10k Ohm:**  
<img width="300" height="300" alt="image" src="https://github.com/user-attachments/assets/4c67a3e7-7fce-4ff0-ac80-99bbe3bd871c" />

- **Tụ điện 100 nF:**  
<img width="300" height="300" alt="image" src="https://github.com/user-attachments/assets/ddd9cc15-bf2a-4842-b4a4-8d16a5d202d0" />

- **Nút bấm:**  
<img width="300" height="300" alt="image" src="https://github.com/user-attachments/assets/394a7cae-ec3d-4ac8-922a-c8dd978b71aa" />


- **Dây nối:**  


- **Breadboard:**  


# 1.3. Phần mềm

## 1.3.1. ESP-IDF

- Viết code
- Nạp code
- Tìm kiếm lỗi
- Biên dịch code

## 1.3.2. Wokwi

- Mô phỏng chức năng mạch điện

## 1.3.3. EasyEDA

- Vẽ sơ đồ mạch điện
- Thiết kế sơ đồ PCB
---
# 2. THỰC HIỆN

## 2.1. Thiết kế

### 2.1.1. Thiết kế mạch điện

Mạch điện gồm:

- **ESP32 NodeMCU LuaNode32** với module thu phát WiFi 38 chân:  
  Xử lý dữ liệu, thao tác với các nút, cảm biến DHT22, buzzer, lưu trữ và xuất dữ liệu ra màn hình LCD1602.

- **Bốn nút bấm**:
  - **Nút tăng giá trị**:  
    Tăng giá trị thuộc tính trong chế độ 1 và 2; tiếp tục/dừng bấm giờ trong chế độ 3.
  - **Nút giảm giá trị**:  
    Giảm giá trị thuộc tính trong chế độ 1 và 2; reset đồng hồ bấm giờ về `00:00:00` trong chế độ 3.
  - **Nút con trỏ**:  
    Di chuyển con trỏ trên màn hình để chỉnh sửa các thuộc tính trong chế độ 1 và 2; tắt chuông báo thức trong cả ba chế độ (nếu có).
  - **Nút chuyển chế độ**:  
    Chuyển tuần tự giữa 3 chế độ: Màn hình chính → Báo thức → Bấm giờ → quay lại Màn hình chính.

- **Cảm biến nhiệt độ, độ ẩm DHT22**:  
  Cung cấp dữ liệu nhiệt độ, độ ẩm môi trường.

- **Buzzer**:  
  Làm chuông báo thức, phát âm thanh cảnh báo.

- **Màn hình LCD1602**:  
  Hiển thị dữ liệu: giờ, phút, giây, ngày, tháng, năm, nhiệt độ, độ ẩm, thời gian báo thức và bấm giờ.

### 2.1.2. Thiết kế giải thuật

- **Hàm `main`**  
  _Hình 2.1.2.1: Lưu đồ giải thuật hàm main_  
  ![Lưu đồ main](path/to/main_flowchart.png)

- **Hàm `Digital_Clock1`**  
  _Hình 2.1.2.2: Lưu đồ giải thuật hàm Digital_Clock1_  
  ![Lưu đồ Digital_Clock1](path/to/digital_clock1_flowchart.png)

> 📁 [Link Google Drive lưu đồ giải thuật hàm Digital_Clock1](https://drive.google.com/drive/folders/1FeIoh2-8VgUvKzssOEODpDEAD6scQ6Hz)

## 2.2. Mô phỏng mạch điện

- **Sử dụng ESP-IDF**: Viết code, biên dịch và debug.
- **Sử dụng Wokwi**: Mô phỏng mạch điện chạy với code thực tế.

_Hình 2.2.1: Mô phỏng chức năng mạch điện bằng Wokwi_  
![Mô phỏng Wokwi](path/to/wokwi_simulation.png)

🎥 **Link video mô phỏng**:  
👉 [Xem video mô phỏng trên Google Drive](https://drive.google.com/drive/folders/1i89lKB27OIh0nQNkSJBFeN2ZRbA8Jovt?usp=sharing)

## 2.3. Hiện thực mạch điện

### 2.3.1. Kiểm thử mạch điện trên breadboard

_Hình 2.3.1.1: Kiểm thử mạch điện_  
![Kiểm thử](path/to/breadboard_test.png)

### 2.3.2. Vẽ sơ đồ mạch điện và PCB

- **Phần mềm sử dụng**: EasyEDA

_Hình 2.3.2.1: Sơ đồ mạch điện_  
![Sơ đồ mạch điện](path/to/circuit_diagram.png)

_Hình 2.3.2.2: Sơ đồ PCB_  
![Sơ đồ PCB](path/to/pcb_layout.png)
### 2.3.3. Hàn linh kiện lên bảng mạch PCB
### 2.3.4. Hoàn thiện mạch điện
---
# 3. Kết quả
https://drive.google.com/drive/folders/1i89lKB27OIh0nQNkSJBFeN2ZRbA8Jovt

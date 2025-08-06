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

---

# 1.2. Phần cứng

## 1.2.1. ESP32 NodeMCU LuaNode32

- **Loại**: Board  
- **Điện áp cấp**: 5V  
- **Tích hợp Bluetooth**: Có  
- **Vi xử lý chính**: ESP-WROOM-32  
- **Giao tiếp**: UART

**Hình ảnh:**  
_Hình 1.2.1.1: ESP32 NodeMCU LuaNode32_  
![ESP32 NodeMCU](path/to/esp32_image.png)

---

## 1.2.2. Màn hình LCD1602

- **Số ký tự**: 16x02 ký tự  
- **Loại giao tiếp**: Parallel 8-bit  
- **Điện áp cấp**: 3.3V  
- **Màu nền**: Xanh dương  
- **Màu chữ**: Trắng

**Hình ảnh:**  
_Hình 1.2.2.1: Màn hình LCD1602_  
![LCD1602](path/to/lcd1602_image.png)

---

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

**Hình ảnh:**  
_Hình 1.2.3.1: Buzzer_  
![Buzzer](path/to/buzzer_image.png)

---

## 1.2.4. Cảm biến nhiệt độ, độ ẩm DHT22

- **Chức năng**: Đo nhiệt độ, độ ẩm  
- **Ngõ ra**: Digital  
- **Nguồn cấp**: 3.3V

**Hình ảnh:**  
_Hình 1.2.4.1: DHT22_  
![DHT22](path/to/dht22_image.png)

---

## 1.2.5. Các linh kiện khác

- **Điện trở:**  
  _Hình 1.2.5.1: Điện trở 10kOhm_  
  ![Điện trở](path/to/resistor_image.png)

- **Tụ điện:**  
  _Hình 1.2.5.2: Tụ Gốm Tròn 100nF_  
  ![Tụ điện](path/to/capacitor_image.png)

- **Nút bấm:**  
  _Hình 1.2.5.3: Nút bấm 4 chân_  
  ![Nút bấm](path/to/button_image.png)

- **Dây nối:**  
  _Hình 1.2.5.4: Dây nối cái-cái, đực-cái, đực-đực_  
  ![Dây nối](path/to/wires_image.png)

- **Breadboard:**  
  _Hình 1.2.5.5: Breadboard_  
  ![Breadboard](path/to/breadboard_image.png)

---

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


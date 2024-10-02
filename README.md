# Điều khiển LED bằng Nút Bấm

Dự án này trình bày cách điều khiển LED bằng một nút bấm sử dụng vi điều khiển ESP32 và thư viện OneButton. Nó hỗ trợ việc bật và tắt LED bằng cách nhấn đơn, chuyển đổi giữa hai LED bằng nhấn đúp, và khởi động một chức năng bằng cách nhấn giữ.

## Tính Năng

- **Nhấn Đơn**: Bật và tắt LED.
- **Nhấn Đúp**: Kích hoạt hiệu ứng nhấp nháy trên LED.

## Yêu Cầu Phần Cứng

- **ESP32 DoIt DevKit V1**
- **LED**: Kết nối đến pin đã định nghĩa.
- **Điện trở**: mắc nối tiếp với LED, 1kΩ.

## Yêu Cầu Phần Mềm

- [PlatformIO](https://platformio.org/) để quản lý dự án.
- Thư viện sau:
  - [OneButton](https://github.com/mathertel/OneButton) của Matthias Hertel
  - LED.h trong thư mục lib

## Cấu hình

Dự án có thể được cấu hình bằng cách chỉnh sửa tệp platformio.ini:
```
[env]
platform = espressif32
framework = arduino
monitor_speed = 115200
upload_speed = 921600
lib_deps = mathertel/OneButton@^2.6.1

[env:esp32doit-devkit-v1]
board = esp32doit-devkit-v1
build_flags = 
    '-D BTN_PIN=0U'          ; chân IO0(thay đổi nếu bạn dùng nút ấn bên ngoài)
    '-D BTN_ACT=LOW'         ; Trạng thái hoạt động của nút bấm cho biết nó hoạt động khi ở mức LOW
    '-D LED_PIN=4U'         ; chân IO4
    '-D LED_ACT=HIGH'        ; Trạng thái hoạt động của LED là HIGH
```
Đảm bảo điều chỉnh các giá trị BTN_PIN và LED_PIN theo kết nối phần cứng của bạn.

## Sử dụng 

- **Nhấn Đơn**: Nhấn nút một lần để bật hoặc tắt LED.
- **Nhấn Đúp**: Nhấn nút hai lần nhanh để làm LED nhấp nháy.

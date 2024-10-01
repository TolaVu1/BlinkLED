# Điều Khiển Đèn LED với OneButton Library

Dự án này mô tả cách điều khiển đèn LED sử dụng một nút nhấn đơn với thao tác single-click và double-click. Nút nhấn được xử lý bằng thư viện OneButton để nhận biết nhiều hành động mà không làm gián đoạn vòng lặp chính.

## Tính Năng
- **Single-click**: Bật hoặc tắt đèn LED.
- **Double-click**: Chuyển đèn LED vào chế độ nháy hoặc tắt chế độ nháy.

## Yêu Cầu Phần Cứng
1. **ESP32 Dev Kit**.
2. **Đèn LED** kết nối với GPIO 4 (hoặc chân GPIO khác có thể cấu hình).

### Sơ Đồ Kết Nối
- **Đèn LED**:
  - Kết nối **cực dương** của đèn LED với chân GPIO 4 (`LED_PIN`).
  - Kết nối **cực âm** của đèn LED với GND thông qua **điện trở 330Ω**.
  
## Cấu Hình PlatformIO
Đảm bảo tệp `platformio.ini` của bạn được cấu hình đúng cho bo ESP32 và các thư viện cần thiết. Dưới đây là một ví dụ cấu hình:

```ini
[env]
platform = espressif32
framework = arduino
monitor_speed = 115200
upload_speed = 921600
lib_deps = mathertel/OneButton@^2.6.1

[env:esp32doit-devkit-v1]
board = esp32doit-devkit-v1
build_flags = 
	'-D BTN_PIN=0U'
	'-D BTN_ACT=LOW'
	'-D LED_PIN=4U'
	'-D LED_ACT=HIGH'

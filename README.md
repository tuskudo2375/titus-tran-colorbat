# Titus.Tran / ColorBat - Battery & Power Inspector for OPPO Find X8 and Find X9 Pro

Ứng dụng đo pin, giám sát công suất sạc và sức khỏe pin theo thời gian thực dành cho **OPPO Find X8, Find X9 Pro** và các dòng máy chạy ColorOS / Android 14+; dung lượng Find X9 Pro được hiển thị theo mức 7.290 mAh định mức / 7.500 mAh điển hình.

## Tính năng chính
- **Đọc trực tiếp từ Kernel Sysfs (`/sys/class/power_supply/battery`) & API Android 16:**
  - **Chu kỳ sạc (Cycle Count):** Đọc chính xác số lần sạc đã thực hiện (VD: 780 chu kỳ).
  - **Công suất sạc / xả tức thời ($W$):** Tính toán liên tục dựa trên $P = U \times I$.
  - **Dòng điện tức thời ($mA$):** Đo dòng nạp khi cắm sạc (+) và dòng xả khi dùng pin (-).
  - **Điện áp tức thời ($V$):** Đo điện áp hoạt động và điện áp mạch hở (OCV).
  - **Nhiệt độ pin (°C):** Cập nhật từng 0.1°C.
  - **Dung lượng pin:** Hiển thị riêng mức định mức và điển hình cho từng model đã hỗ trợ; Find X9 Pro dùng **7.290 mAh** (Rated) và **7.500 mAh** (Typical).
  - **Sức khỏe (SOH %):** Đọc từ thông tin phần cứng nếu thiết bị cung cấp.
- **Tự động làm mới:** 1 giây / lần với Coroutines nhẹ nhàng, không gây hao pin.
- **Giao diện:** Thiết kế Card Material phong cách hiện đại tương tự AnyDown.

## Hướng dẫn Build APK
1. **Qua GitHub Actions:** Tạo repo mới trên GitHub, push toàn bộ thư mục này lên. GitHub Actions sẽ tự động biên dịch và tạo file `.apk` trong mục **Actions -> Artifacts**.
2. **Qua Android Studio:** Mở thư mục này bằng Android Studio, chọn `Build > Build Bundle(s) / APK(s) > Build APK(s)`.
3. **Cài đặt vào máy:** Dùng lệnh:
   ```bash
   adb install app/build/outputs/apk/debug/app-debug.apk
   ```

## Cách 1: Tìm ở mục Human Interface Devices (HID)

Đôi khi Windows 11 chuyển cài đặt nguồn của chuột sang một mục quản lý trung gian.
1. Trong Device Manager, mở rộng mục Human Interface Devices.
2. Tìm dòng có tên Bluetooth HID Device hoặc Bluetooth Low Energy GATT compliant HID device.
3. Nhấp chuột phải, chọn Properties và kiểm tra xem có tab Power Management ở đây hay không. Nếu có, hãy bỏ tích chọn ô ngắt nguồn điện.

## Cách 2: Chạy lệnh chặn Windows tắt nguồn Bluetooth (Qua PowerShell)

Nếu cả hai cách trên đều không xử lý được hiện tượng chuột tự ngắt kết nối, bạn có thể dùng lệnh để buộc Windows 11 luôn cấp điện cho luồng bus Bluetooth.
1. Nhấp chuột phải vào nút Start và chọn Terminal (Admin) hoặc PowerShell (Admin).
2. Sao chép và dán lần lượt 2 lệnh sau (nhấn Enter sau mỗi lệnh):powershell
powercfg /setacvalueindex scheme_current 2a737441-1930-4402-8d77-b08208b34821 48e6b7a6-50f5-4760-a579-99c420066b0e 0
Hãy thận trọng khi sử dụng mã.
powershell
powercfg /setactive scheme_current
Hãy thận trọng khi sử dụng mã.
3. Khởi động lại máy tính để thay đổi có hiệu lực
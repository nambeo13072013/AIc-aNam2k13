# AIc-aNam2k13
xin chà tôi tên là trần hoàng nam.
tuổi 13.
lần đầu tiên em lập trình nên mọi người có thể góp ý.
AI này sẽ giúp giáo viên đỡ mọt phần trong công việc.

PHẦN 1: HƯỚNG DẪN CÀI ĐẶT NODE.JS

Bước 1: Tải bộ cài đặt
1. Truy cập vào trang chủ chính thức: Node.js.
2. Tải phiên bản LTS (khuyến nghị bản dành cho số đông người dùng để đảm bảo độ ổn định cao, ví dụ bản Node.js 22.x hoặc 24.x LTS).
3. Chọn bản cài đặt .msi phù hợp với hệ điều hành Windows của bạn (thường là x64).
Bước 2: Tiến hành cài đặt
1. Mở file .msi vừa tải về để bắt đầu cài đặt.
2. Bấm Next, tích chọn “I accept the terms in the License Agreement”.
3. Giữ các tùy chọn đường dẫn mặc định và bấm Next liên tiếp cho đến khi hoàn thành (Finish).
Bước 3: Kiểm tra cài đặt thành công
1. Nhấn phím Windows, gõ PowerShell và chọn Run as Administrator (Chạy với quyền Quản trị viên).
2. Nhập lần lượt hai lệnh sau để kiểm tra phiên bản:powershell
node -v
npm -v
Hãy thận trọng khi sử dụng mã.
Nếu màn hình hiển thị số phiên bản (ví dụ: v24.x.x và 10.x.x) là bạn đã cài đặt Node.js thành công.

PHẦN 2: CÁCH TẢI VÀ CHẠY OMNIROUTE QUA POWERSHELL

Khi Node.js đã sẵn sàng, việc cài đặt OmniRoute vô cùng đơn giản trực tiếp trên PowerShell.
Bước 1: Cài đặt OmniRoute toàn cục (Global)
Tại cửa sổ PowerShell (quyền Administrator), nhập lệnh sau để tải và cài đặt bản chính thức từ kho lưu trữ của npm:
powershell
npm install -g omniroute
Hãy thận trọng khi sử dụng mã.
(Chờ một lát để hệ thống tải package về máy).
Bước 2: Khởi chạy OmniRoute
Sau khi cài đặt xong, bạn nhập lệnh sau để kích hoạt cổng AI Gateway:
powershell
omniroute
Hãy thận trọng khi sử dụng mã.
Hệ thống sẽ khởi chạy một máy chủ cục bộ (local server). Theo mặc định, OmniRoute sẽ chạy ở cổng 20128.
Bước 3: Truy cập Giao diện điều khiển (Dashboard)
1. Mở trình duyệt web của bạn (Chrome, Edge, v.v.).
2. Truy cập vào địa chỉ: http://localhost:20128.
3. Tại giao diện Dashboard này, bạn có thể bắt đầu kết nối các nhà cung cấp AI miễn phí (Free Providers) hoặc cấu hình chuyển đổi dự phòng (auto-fallback) để sử dụng với các công cụ lập trình như Claude Code, Cursor hay VS Code.
Nếu trong quá trình gõ lệnh omniroute mà PowerShell báo lỗi về chính sách bảo mật script (Execution Policy), hãy chạy lệnh sửa lỗi sau: Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine rồi nhấn Y để xác nhận, sau đó chạy lại lệnh.

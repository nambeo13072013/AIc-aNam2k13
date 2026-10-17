# AIc-aNam2k13
xin chà tôi tên là trần hoàng nam.
tuổi 13.
lần đầu tiên em lập trình nên mọi người có thể góp ý.
AI này sẽ giúp giáo viên đỡ một phần trong công việc.

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
Để cấu hình OmniRoute đạt hiệu năng tối ưu và kết nối mượt mà với các công cụ lập trình AI (như Claude Code, Cursor, VS Code, Cline...), bạn có thể áp dụng 3 cấp độ cấu hình dưới đây: từ giao diện đồ họa (Dashboard), lệnh nhanh (CLI) cho đến cấu hình file hệ thống.

CẤP ĐỘ 1: CẤU HÌNH QUA GIAO DIỆN DASHBOARD (Dễ nhất)

Sau khi chạy lệnh omniroute trong PowerShell, hãy truy cập vào địa chỉ http://localhost:20128.
1. Kết nối Nhà cung cấp (Providers):
	• Vào mục Providers trên menu.
	• Free Providers (Không cần Key): Bật các cổng miễn phí như OpenCode Free hoặc Kiro AI. Các nguồn này giúp bạn chạy test AI ngay lập tức mà không cần tài khoản hay thẻ tín dụng.
	• Paid Providers (Cần Key): Nhập API Key của các dịch vụ bạn có (OpenAI, Anthropic, Gemini, DeepSeek, hoặc OpenRouter...).
2. Cấu hình định tuyến thông minh (Combos):
	• Vào mục Combos để sắp xếp thứ tự ưu tiên cho các mô hình AI bằng cách kéo thả.
	• OmniRoute hỗ trợ các chiến lược định tuyến rất hay:
		• Fill First: Dùng tài khoản/mô hình chính, nếu lỗi hoặc hết quota mới nhảy sang tài khoản dự phòng.
		• Cost Optimized: Tự động chọn nhà cung cấp có chi phí rẻ nhất.
		• Auto-Routing (Mô hình auto): Để OmniRoute tự đánh giá tốc độ, giá cả và tình trạng hoạt động của các bên để điều phối prompt.
3. Tạo API Key cho Client:
	• Vào mục Endpoints / API Keys trên Dashboard để tạo một mã Token cục bộ (ví dụ: sk_omniroute_...). Bạn sẽ dùng mã này để điền vào các phần mềm viết code.

CẤP ĐỘ 2: TỰ ĐỘNG CẤU HÌNH CHO CÁC CÔNG CỤ CODE (CLI)

OmniRoute cung cấp sẵn các lệnh thiết lập tự động cho các AI Coding Agent mà không cần bạn phải mở từng file cài đặt để chỉnh sửa thủ công:
Mở một tab PowerShell mới và chạy lệnh tương ứng với công cụ bạn đang dùng:
• Cho Claude Code:powershell
omniroute setup-claude
Hãy thận trọng khi sử dụng mã.
(Lệnh này tự động tạo cấu hình tại thư mục ~/.claude/ để hướng dòng lệnh Claude Code về proxy OmniRoute).
• Cho Continue (Extension trên VS Code / JetBrains):powershell
omniroute setup-continue
Hãy thận trọng khi sử dụng mã.
• Cho Cline (VS Code Extension):powershell
omniroute setup-cline
Hãy thận trọng khi sử dụng mã.
• Cho các công cụ khác: Bạn có thể chạy omniroute setup-cursor, omniroute setup-codex, hoặc omniroute setup-opencode tùy thuộc vào phần mềm đang làm việc.

CẤP ĐỘ 3: CẤU HÌNH NÂNG CAO QUA FILE BIẾN MÔI TRƯỜNG (.env)

Khi cài đặt qua npm, OmniRoute sẽ tạo một file .env ẩn nằm trong thư mục dữ liệu gốc của nó (thường nằm ở đường dẫn ~/.omniroute/.env). Bạn có thể mở file này bằng Notepad để tinh chỉnh các thông số hệ thống chuyên sâu:
• Bảo mật khi dùng chung mạng (Team):env
REQUIRE_API_KEY=true
JWT_SECRET=nhap_chuoi_bao_mat_ngau_nhien_o_day
Hãy thận trọng khi sử dụng mã.
• Thay đổi cổng chạy (Port): Mặc định là 20128, bạn có thể đổi sang cổng khác nếu bị trùng:env
PORT=3000
Hãy thận trọng khi sử dụng mã.
• Thời gian chờ (Timeout): Tăng thời gian chờ lên nếu bạn dùng các mô hình suy nghĩ sâu (Reasoning Models) mất nhiều thời gian trả lời:env
REQUEST_TIMEOUT_MS=600000
Hãy thận trọng khi sử dụng mã.

Kiểm tra cấu hình có hoạt động không?

Sau khi đã thiết lập xong xuôi, bạn mở PowerShell và chạy lệnh chẩn đoán nhanh của OmniRoute để quét lỗi hệ thống:
powershell
omniroute doctor
Hãy thận trọng khi sử dụng mã.
Nếu lệnh trả về trạng thái khỏe mạnh (✓ healthy), bạn đã cấu hình thành công và sẵn sàng lập trình cùng AI với lượng token tối ưu nhất!

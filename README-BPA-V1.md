# BPA Green Tech AI — V1 Testnet

## Phạm vi bản bàn giao

Bản V1 bổ sung giao diện và luồng dữ liệu cho:

- Nhân sự, vai trò, phân quyền, xác minh hồ sơ và chấm công GPS.
- IoT/robot, cảm biến độ ẩm, van tưới và quy tắc tự động hóa an toàn.
- Hồ sơ doanh nghiệp, quản trị nội bộ, cảnh báo/khen thưởng/khiển trách.
- Báo cáo gửi chủ doanh nghiệp hoặc giám đốc.
- Khối lượng công việc, nhân công, công cụ và chi phí dự kiến.
- Vị trí GPS, thời tiết hiện tại và khuyến nghị tưới.
- Theo dõi tăng trưởng cây bằng số liệu và ảnh đầu vào.
- Trợ lý `BPA.Green AI` với hướng dẫn nông nghiệp, IoT và blockchain/Web3.

## Cài đặt và kiểm tra

Yêu cầu Node.js 20 trở lên và pnpm.

\`\`\`bash
pnpm install --frozen-lockfile
pnpm audit --prod --audit-level high
pnpm build
pnpm start
\`\`\`

Để bật BPA.Green AI, khai báo `OPENAI_API_KEY` ở phần biến môi trường phía máy chủ của nền tảng triển khai. Không đưa khóa này vào mã nguồn, trình duyệt hoặc tệp ZIP.

## Tải lên Pi App Studio / SoloHost

1. Sao lưu bản đang Published và dùng Testnet để kiểm tra.
2. Mở `Manage` của ứng dụng BPA Green Tech AI.
3. Chọn `Upload App Code` và tải tệp ZIP bàn giao.
4. Chờ trạng thái build hoàn tất, sau đó mở preview.
5. Kiểm tra đăng nhập Pi, điều hướng, thêm/sửa dữ liệu, GPS/thời tiết và giao diện điện thoại.
6. Chỉ publish sau khi toàn bộ checklist đạt.

## Checklist nghiệm thu

- Đăng nhập Pi và dữ liệu người dùng tải lại đúng sau khi mở lại app.
- Thanh điều hướng có `Nhân sự`, `IoT` và `Thêm`.
- GPS chỉ chạy sau khi người dùng đồng ý cấp quyền.
- Weather API trả kết quả và thông báo rõ khi thiết bị từ chối vị trí.
- Không có khóa OpenAI hoặc thông tin bí mật trong mã nguồn.
- Kiểm tra quyền bằng ít nhất một tài khoản giám đốc và một tài khoản nhân viên.
- Lệnh IoT thử nghiệm không được nối trực tiếp với van thật trước khi có gateway, xác thực thiết bị và nút dừng khẩn cấp.

## Giới hạn cần biết của V1

- Dữ liệu hiện lưu theo Pi user-state của từng tài khoản; chưa phải cơ sở dữ liệu doanh nghiệp dùng chung nhiều người theo thời gian thực.
- Danh sách quyền là mô hình giao diện/dữ liệu; việc cưỡng chế quyền trên máy chủ cần backend doanh nghiệp.
- IoT/robot mới là cấu hình và mô phỏng trạng thái; chưa điều khiển thiết bị thật khi chưa có API/gateway của nhà sản xuất.
- Ảnh tăng trưởng mới ghi nhận tên ảnh và số liệu nhập; cần kho ảnh bảo mật trước khi phân tích ảnh thực tế bằng OpenAI Vision.
- Cảnh báo khi ứng dụng đã đóng cần push notification và backend chạy nền; web app không thể tự bảo đảm cảnh báo nền trên iOS.
- Tỷ giá Pi và quảng cáo phải dùng nguồn dữ liệu/SDK hợp lệ, tuân thủ chính sách Pi; không nên hiển thị dữ liệu giao dịch giả hoặc quảng cáo chưa được duyệt.

## An toàn vận hành

Mọi hành động tưới tự động cần có ngưỡng độ ẩm, giới hạn thời gian, khóa khi mưa, phát hiện cảm biến lỗi, nhật ký lệnh và quyền điều khiển theo vai trò. Luôn chạy Testnet và thiết bị mô phỏng trước khi nối với hệ thống ngoài thực địa.

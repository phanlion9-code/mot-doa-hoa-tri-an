# Một đóa hoa – Ngàn lời tri ân

Website React + TypeScript + Vite, không backend, tài khoản, analytics hoặc API trả phí.

## Chạy
Node.js 22 trở lên. Chạy `npm install`, `npm run dev`. Đóng gói bằng `npm run build`; xem bản build bằng `npm run preview`.

## Triển khai
Vercel: framework Vite, build `npm run build`, output `dist`. Netlify: cùng cấu hình. Dùng một URL HTTPS cố định để tạo QR thật. File public/_headers áp dụng các header bảo mật trên Netlify; cấu hình tương đương tại nhà cung cấp khác.

## Kiểm thử
Kiểm tra chiều rộng 320, 360, 390, 430px và desktop. Nhấn nhận hoa, chạm hoa một lần hoặc dùng Tab/Enter, đợi 4,7 giây, kiểm tra lời chúc, lưu PNG 1080×1920, mở ảnh để lưu trên iOS khi cần. Nhấn xem lại và thử nhiều lượt. Bật giảm chuyển động của hệ điều hành: bỏ animation và chuyển nhanh đến lời chúc. Kiểm tra không tràn ngang, nút có focus và văn bản cuộn được trên màn hình thấp.

## Asset
public/cosmos.png là hoa từ bộ thiệp được duyệt, dùng ở lời chúc và ảnh tải xuống. src/Flower.tsx là hoa SVG nhiều cánh độc lập phục vụ nở hoa; có thể thay đường path khi có bản vector chính thức. Hai bản được thống nhất loài, sắc trắng ngà, nhụy vàng và thân sage; không phải các lớp được bóc chính xác từ ảnh raster. public/og.png là ảnh chia sẻ. Cập nhật URL tuyệt đối của og:image trong index.html khi đổi tên miền.

## Bảo mật và giới hạn kiểm tra
Không nhận đầu vào người dùng, không HTML động, không kho dữ liệu hoặc bí mật phía trình duyệt. Tải ảnh thực hiện nội bộ trình duyệt từ asset cùng nguồn. Nút mở ảnh dùng noopener noreferrer. URL blob được thu hồi khi thay hoặc rời màn hình. Đây là kiểm tra mã nguồn giới hạn, chưa phải báo cáo quét chuyên sâu Codex Security. Cần kiểm tra hành vi tải ảnh trên thiết bị iOS/Android thực trước khi in QR hàng loạt.

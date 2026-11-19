# Hồ sơ tổng hợp – UBND xã Lãnh Ngọc

Ứng dụng web một trang (single-file HTML), chạy hoàn toàn trên trình duyệt, không cần máy chủ.

## Cấu trúc
- `index.html` – toàn bộ ứng dụng (đã nhúng sẵn CSS, JS, dữ liệu)
- `.nojekyll` – tắt Jekyll để GitHub Pages phục vụ file nguyên bản

## Triển khai bằng GitHub Pages
1. Tạo repository mới trên GitHub, tải toàn bộ file trong thư mục này lên nhánh `main`.
2. Vào **Settings → Pages**.
3. Mục **Build and deployment**: Source = *Deploy from a branch*, Branch = `main`, thư mục `/ (root)`.
4. Lưu lại; sau 1–2 phút truy cập tại `https://<tên-tài-khoản>.github.io/<tên-repo>/`.

## Lưu ý
- Ứng dụng dùng `localStorage` của trình duyệt: dữ liệu nhập được lưu riêng trên từng máy/trình duyệt, không đồng bộ giữa các máy.
- Repository **public** thì ai cũng xem được nội dung `index.html`. Nếu có thông tin cá nhân hoặc nội bộ, hãy dùng repository **private** (GitHub Pages cho repo private cần gói trả phí).

## Lưu / mở hồ sơ
- Dữ liệu tự lưu trong trình duyệt. Nút **💾 Lưu hồ sơ** (hoặc Ctrl+S) xuất hồ sơ đang mở ra file `.json`; **📂 Mở hồ sơ** mở lại file đó để sửa tiếp (có thể chọn nhiều file, hỏi ghi đè/bản sao nếu trùng).

## Tính năng v1.1
Ô tìm hồ sơ · nhắc sao lưu (sau 7 ngày) · kiểm tra thiếu thông tin trước khi xuất Word · 📦 xuất tất cả biểu mẫu vào 1 zip · tab **6 · Sổ theo dõi** (trạng thái, hạn xử lý, xuất Excel .csv) · 🔒 mã PIN (chỉ chặn người dùng thông thường, không mã hóa dữ liệu) · hiển thị số phiên bản.

## v1.2 – Tệp & trích xuất
Tab **7 · Tệp & trích xuất**: đính kèm PDF/ảnh vào hồ sơ (lưu trong IndexedDB của trình duyệt, không nằm trong file .json), đọc mã QR trên CCCD gắn chip và chữ trong PDF có lớp chữ, hiện bảng duyệt rồi mới điền vào tab Data. Lần đầu dùng cần Internet để tải thư viện đọc PDF/QR từ cdnjs (jsQR 1.4.0, pdf.js 3.11.174). PDF/ảnh scan không có mã QR chưa đọc được chữ (cần OCR – giai đoạn 2).

## v1.3
- **OCR tiếng Việt** (Tesseract.js, tải từ jsDelivr lần đầu) cho PDF/ảnh scan không có mã QR; đọc thêm tờ/thửa/diện tích từ giấy tờ đất.
- **🔁 Thửa khác / dùng lại**: tạo hồ sơ mới cho thửa khác của cùng chủ (mang sang họ tên, CCCD, địa chỉ) hoặc thêm thửa vào hồ sơ hiện tại. **👥 Lấy người từ hồ sơ khác** để dùng lại người đã nhập.

## v1.4 – Giao diện thanh bên trái
Các nút chia nhóm ở cột bên trái (Hồ sơ · Thửa và người · Biểu mẫu · Dữ liệu · Khác); phía trên nội dung là ô chọn hồ sơ, ô tìm kiếm và trạng thái sao lưu. Màn hình hẹp tự chuyển thành thanh nút nằm ngang.

## v1.5
Nội dung các tab dùng hết chiều ngang màn hình; nút ◀/▶ thu gọn cột nút thành dải biểu tượng (nhớ lựa chọn); tab 2–5 có bảng **Tóm tắt hồ sơ** cố định bên phải (chọn người, thửa đất, thông tin còn thiếu, các nút xuất biểu mẫu).

## v1.5.1
Bảng Tóm tắt hẹp hơn (272px) và có nút ▶ Thu gọn / ◀ mở lại (nhớ lựa chọn); khi thu gọn, vùng nhập dữ liệu chiếm gần hết chiều ngang.

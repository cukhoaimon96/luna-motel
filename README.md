# Luna Motel – Public hoàn toàn

Website không yêu cầu đăng nhập. Bất kỳ ai mở được website đều có thể xem lịch sử lương, lưu kỳ lương mới và xóa bản ghi trên Firebase Realtime Database.

## Cấu hình Firebase
1. Mở Firebase Console → dự án `luna-motel` → Realtime Database → Rules.
2. Thay nội dung bằng file `firebase-database-rules.json`.
3. Nhấn Publish.
4. Không cần bật Firebase Authentication; ứng dụng không sử dụng đăng nhập.

**Cảnh báo bảo mật:** Rules `.read: true` và `.write: true` cho phép bất kỳ ai trên Internet đọc, ghi, sửa và xóa toàn bộ dữ liệu trong database. Không lưu thông tin cá nhân nhạy cảm, không dùng cho dữ liệu lương cần bảo mật. Người lạ có thể sửa/xóa lịch sử hoặc ghi dữ liệu rác. Cấu hình public này cũng có thể dẫn đến phát sinh chi phí Firebase hoặc bị lạm dụng.

## Deploy Vercel
1. Upload `index.html` và `vercel.json` vào thư mục gốc GitHub repository riêng `luna-motel`.
2. Vercel → Add New → Project → Import repository.
3. Framework Preset: Other.
4. Build Command để trống; Output Directory: `.`; Install Command để trống.
5. Deploy.

## Chức năng
- Tính công theo khoảng ngày, trừ Chủ nhật của Sang và Thứ 7 của buồng phòng.
- Tick chuyên cần cộng 1 công.
- In phiếu lương chỉ hiển thị tổng công và tổng lương.
- Lưu, xem và xóa lịch sử kỳ lương trên Firebase.

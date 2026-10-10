# Camera Scanner v7.1 – Scan hợp đồng

Kế thừa repository quoctrungkg/Camera-Scanner, commit 42fc58dc495b5b9f40fc8efeb36947a414ad2369.

## Cập nhật GitHub Pages
1. Giải nén ZIP.
2. Chép index.html, scanner.js và cả thư mục vendor vào thư mục gốc repository Camera-Scanner. Thay index.html cũ; giữ các file mới đúng vị trí.
3. Commit lên nhánh đang dùng GitHub Pages. Chờ deployment hoàn tất rồi tải lại trang.
4. Mở trực tiếp URL HTTPS trên Chrome/Safari, cấp quyền camera.

## Sử dụng
- Mặc định Scan sáng – giữ màu dấu, chữ ký. Chế độ áp dụng cho ảnh chụp hoặc thêm vào sau khi chọn.
- Chạm nút tròn để chụp liên tục; camera vẫn mở sau mỗi lần chụp.
- Hoàn tất dừng camera; không tự chạy OCR. Tên PDF gồm ngày giờ và tên tài liệu tự nhập.
- Xem ảnh, xoay, xóa; kéo thả để đổi thứ tự trên trình duyệt hỗ trợ kéo thả.
- Tạo PDF tải về máy, không lưu Drive. Xuất PDF dừng camera để giảm tải; Mở lại camera để tiếp tục.
- Chuyển sang ứng dụng khác sẽ dừng camera. Khi quay lại bấm Mở lại camera.

## Xử lý ảnh
- Camera yêu cầu 2560 × 1920; độ phân giải thực tế do thiết bị quyết định.
- Giới hạn cạnh dài 2400 px, không phóng to ảnh nhỏ; JPEG chất lượng 0.80.
- Ước lượng nền giấy theo vùng, nâng sáng nhẹ và tăng tương phản; không ép đen trắng để giữ nét mảnh và màu dấu.
- Ảnh tải lên cũng được xử lý và nén. Dữ liệu giữ dạng Blob, thumbnail nhỏ; chỉ thêm thumbnail mới sau khi chụp.
- PDF A4 chứa ảnh scan; không phải PDF có chữ tìm kiếm.
- Không tự nhận diện mép giấy/chỉnh phối cảnh; cần đặt giấy thẳng và chiếm phần lớn khung hình. Không thể khôi phục chữ bị nhòe hoặc mất nét.
- Không lưu phiên sau khi đóng/tải lại trang. Tải PDF trước khi thoát. Bộ nhớ điện thoại vẫn giới hạn số trang.
- jsPDF 2.5.2 đi kèm trong vendor, không cần tải thư viện từ CDN khi mở ứng dụng.

## Kiểm thử
Xem QA.md. Cần thử bổ sung trên điện thoại thật với hợp đồng có chữ nhỏ, dấu đỏ và chữ ký trước khi dùng chính thức.

## Đóng và quay về ứng dụng (v7.1)
- Nút “Đóng · Về trang chủ” tắt camera và đóng tab do ứng dụng mở. Tab ứng dụng bên dưới vẫn giữ nguyên trạng thái đăng nhập.
- Có ảnh sẽ hỏi xác nhận trước khi thoát; ảnh chưa tải PDF sẽ mất khi đóng tab.
- Khi trình duyệt không cho đóng tab, dùng URL trang chủ dự phòng. Trong scanner.js, điền đường dẫn HTTPS trang chủ vào HOME_URL (hiện để trống vì chưa có URL chính xác).
- Hoặc app PDF truyền URL khi mở camera:

```js
const scanUrl = new URL('https://quoctrungkg.github.io/Camera-Scanner/');
scanUrl.searchParams.set('returnUrl', HOME_APP_URL); // URL /exec của trang chủ
window.open(scanUrl.href, '_blank', 'noopener');
```

- Nếu chưa cấu hình URL và trình duyệt chặn đóng, ứng dụng báo đã tắt camera và hướng dẫn đóng tab; không tự đoán URL trang chủ.

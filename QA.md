# Kiểm tra v7.0

Đã đạt:
- node --check scanner.js.
- ID HTML duy nhất, các ID được JavaScript tham chiếu tồn tại; đường dẫn thư viện nội bộ tồn tại.
- Kiểm tra thuật toán trên ảnh tổng hợp: nền xám được nâng sáng, chữ tối giữ tối, dấu đỏ giữ ưu thế màu đỏ; chế độ xám có các kênh bằng nhau; chế độ tự nhiên không sửa pixel.

Chưa xác nhận:
- Kiểm thử trình duyệt tự động bị chặn do môi trường không có Chromium và tải bộ cài không thành công.
- Camera thực tế, chụp liên tục, xoay/xóa/sắp xếp và tải PDF trên Android/iOS cần kiểm tra trên máy thật.
- Mức nén và độ rõ chữ trên hợp đồng thực tế; không cam kết dung lượng cố định mỗi trang.

Checklist trên điện thoại:
1. Chụp 10–20 trang liên tiếp, xác nhận camera không tự tắt giữa các trang.
2. Phóng to kiểm tra chữ nhỏ, dấu tiếng Việt, chữ ký và dấu đỏ.
3. Thêm ảnh độ phân giải cao, kiểm tra cạnh dài không quá 2400 px và bộ đếm dung lượng.
4. Xoay/xóa trang, kiểm tra PDF đủ trang và đúng thứ tự.
5. Chuyển ứng dụng và quay lại, mở lại camera.

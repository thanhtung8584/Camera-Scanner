# Camera Scanner - GitHub Pages
1. Tạo repository GitHub mới, ví dụ `camera-scanner`.
2. Upload `index.html` trong thư mục này vào root repository.
3. Settings > Pages > Deploy from a branch > `main` / `(root)` > Save.
4. Lấy URL HTTPS dạng `https://TEN_GITHUB.github.io/camera-scanner/`.
5. Mở `Code.gs`, thay `PASTE_GITHUB_PAGES_URL_HERE` trong `SCANNER_PAGE_URL` bằng URL đó.
6. Apps Script: Deploy > Manage deployments > Edit > New version > Deploy. Web app phải cho phép người dùng của hệ thống truy cập.
7. Mở hệ thống > Công cụ hỗ trợ > Chụp liên tục.

Scanner nhận một token tải lên tạm thời (30 phút) do Apps Script tạo khi người dùng đã đăng nhập. PDF được ghép trên trình duyệt rồi POST một lần về Apps Script để lưu Drive.

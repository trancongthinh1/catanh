# ✂️ Cắt ảnh theo vết loang

Trang web nhỏ giúp cắt ảnh theo **30 hình vết**: vết loang, vết mực, nét cọ, giấy xé, đám mây, trái tim… rồi tải về ảnh PNG nền trong suốt (2000×2000 px).

Mọi xử lý diễn ra ngay trên trình duyệt, ảnh của bạn **không được tải lên máy chủ nào**.

## Tính năng

- 30 hình vết chia 3 nhóm, phần lớn có nút “Đổi dáng khác” để tạo biến thể mới
- Dùng hình vết của riêng bạn (PNG trong suốt, hoặc vết màu trên nền trắng)
- Kéo để di chuyển ảnh, cuộn chuột hoặc chụm hai ngón để phóng to, xoay hình vết
- Nền trong suốt hoặc nền màu
- Trên điện thoại: nút “Chia sẻ / Lưu vào Ảnh” mở bảng chia sẻ để lưu thẳng vào thư viện ảnh
- Cài lên màn hình chính như một ứng dụng và dùng được khi mất mạng (PWA)

## Cấu trúc thư mục

```
index.html              Trang chính (HTML, CSS, JS trong một tệp)
manifest.webmanifest    Thông tin để cài lên màn hình chính
sw.js                   Bộ nhớ đệm để dùng khi mất mạng
.nojekyll               Báo GitHub Pages phục vụ tệp nguyên trạng
icons/
  favicon.svg           Biểu tượng cái kéo (bản vector)
  favicon.ico           Biểu tượng cho tab trình duyệt
  apple-touch-icon.png  Biểu tượng khi thêm vào màn hình chính iPhone/iPad
  icon-192.png          Biểu tượng Android
  icon-512.png          Biểu tượng Android cỡ lớn
  icon-maskable-512.png Biểu tượng Android dạng bo tròn theo máy
```

## Đưa lên GitHub Pages

1. Tạo repository mới trên GitHub (ví dụ `cat-anh`), để chế độ **Public**.
2. Bấm **Add file → Upload files**, kéo **toàn bộ nội dung** thư mục này vào (giữ nguyên thư mục `icons`). Bấm **Commit changes**.
   - Tệp `.nojekyll` bị ẩn trên một số máy; nếu không thấy thì bỏ qua cũng được.
3. Vào **Settings → Pages**. Ở mục *Build and deployment*, chọn **Source: Deploy from a branch**, **Branch: `main`**, thư mục **`/ (root)`**, bấm **Save**.
4. Đợi 1–2 phút, trang sẽ có ở địa chỉ `https://<tên-tài-khoản>.github.io/cat-anh/`.

## Cài lên điện thoại

- **iPhone/iPad (Safari):** mở trang → nút Chia sẻ → **Thêm vào MH chính**.
- **Android (Chrome):** mở trang → menu ⋮ → **Cài đặt ứng dụng** / **Thêm vào màn hình chính**.

## Chạy thử trên máy tính

Mở thẳng `index.html` bằng trình duyệt là dùng được. Muốn thử cả tính năng dùng khi mất mạng thì cần chạy qua máy chủ, ví dụ:

```bash
python3 -m http.server 8000
# rồi mở http://localhost:8000
```

## Cập nhật trang

Khi sửa `index.html`, hãy đổi `cat-anh-v1` trong `sw.js` thành `cat-anh-v2` (v3…) để điện thoại đã cài nhận bản mới.

# Phước Coffee & Tea – Website giới thiệu quán

Website tĩnh một trang, chỉ sử dụng HTML và CSS. Không cần cài đặt.

## Chạy thử
Mở `index.html` bằng trình duyệt. Cần Internet để tải font Poppins; bố cục và điều hướng vẫn hoạt động khi ngoại tuyến.

## Cấu trúc
```
index.html        Cấu trúc ngữ nghĩa HTML5
style.css         Tokens (:root), base, components, layout, responsive, reduced-motion
PROMPT_LOG.md     Nhật ký prompt
```

Menu điều hướng luôn hiển thị và tự xuống dòng trên màn hình nhỏ; không cần JavaScript.

`index.html` hiện tham chiếu ảnh và favicon trong `assets/images/` và `assets/icons/`. Hãy thêm các tệp tương ứng vào những thư mục này để hiển thị đầy đủ hình ảnh; hiện các tệp ảnh chưa có trong workspace.

## Thay ảnh thật
Ảnh hiện là SVG placeholder. Khi có ảnh thật, lưu vào `assets/images/` (WebP, hero dưới 200KB, ảnh card dưới 80KB), rồi đổi đuôi `.svg` thành `.webp` trong `index.html`. Giữ nguyên `width`/`height`. Ghi nguồn và giấy phép ảnh vào mục dưới đây.

## Nguồn ảnh
*(điền khi thay ảnh thật)*

## Dữ liệu mẫu
Thực đơn, đánh giá khách, địa chỉ, số điện thoại, email và giờ mở cửa đều là dữ liệu mẫu, cần thay bằng thông tin thật.

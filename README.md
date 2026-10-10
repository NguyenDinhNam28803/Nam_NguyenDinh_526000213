# Phước Coffee & Tea – Website giới thiệu quán

Website tĩnh một trang, chỉ sử dụng HTML và CSS. Không cần cài đặt.

## Chạy thử
Mở `index.html` bằng trình duyệt. Cần Internet để tải font Poppins; bố cục và điều hướng vẫn hoạt động khi ngoại tuyến.

## Cấu trúc
```
index.html        Cấu trúc ngữ nghĩa HTML5
style.css         Tokens (:root), base, components, layout, responsive, reduced-motion
PROMPT_LOG.md     Nhật ký prompt
assets/
  Logo_coffee.jpg Logo hiện có, dùng cho favicon và nhận diện ở header
  images/         Ảnh minh họa SVG tự tạo cho hero, món nước và không gian quán
```

Menu điều hướng luôn hiển thị và tự xuống dòng trên màn hình nhỏ; không cần JavaScript.

## Hình ảnh
Các hình minh họa SVG trong `assets/images/` được vẽ riêng cho website bằng hình khối vector, không phụ thuộc nguồn ảnh bên ngoài. Logo dùng tệp `assets/Logo_coffee.jpg` có sẵn trong dự án. Có thể thay hình minh họa bằng ảnh sản phẩm/quán thực tế và cập nhật `src` tương ứng trong `index.html`.

## Nguồn ảnh
Hình minh họa SVG: tự tạo cho dự án. Logo: tệp có sẵn `assets/Logo_coffee.jpg`.

## Dữ liệu mẫu
Thực đơn, đánh giá khách, địa chỉ, số điện thoại, email và giờ mở cửa đều là dữ liệu mẫu, cần thay bằng thông tin thật.

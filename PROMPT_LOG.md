# PROMPT_LOG – Website Phước Coffee & Tea

## Thông tin chung
- **Công cụ AI:** Claude (model sonnet/medium)
- **Mục tiêu dự án:** Website one-page giới thiệu quán "Phước Coffee & Tea", phong cách hiện đại, trẻ trung.
- **Ràng buộc đề bài:** Semantic HTML5 (≥ 5 thẻ), CSS Variables, Flexbox/Grid, Animate.css, AOS, `:hover`/`:focus` tự viết.
- **Bảng màu / token:** theo `:root` trong `style.css` (primary `#6F4E37`, secondary `#C8A27A`, nền `#FAF7F2`, font Poppins).

---

## Entry 01 – Phân tích yêu cầu và lập kế hoạch
- **Ngày:** 10/10/2026
- **Mục tiêu:** Hiểu đề bài, chọn kiến trúc, chia bước thực hiện.
- **Prompt đã dùng:** 
Tôi muốn thiết kế 1 website giới thiệu quán cà phê với các tiêu chí code, thư mục và mã màu chủ đạo như sau:


```css
:root {
    --primary-color: #6F4E37;
    --secondary-color: #C8A27A;
    --background-color: #FAF7F2;
    --surface-color: #FFFFFF;
    --text-color: #292522;
    --muted-color: #77716B;

    --font-family: "Poppins", sans-serif;

    --spacing-xs: 4px;
    --spacing-sm: 8px;
    --spacing-md: 16px;
    --spacing-lg: 32px;
    --spacing-xl: 64px;

    --radius-md: 12px;
    --radius-lg: 20px;

    --transition-normal: 0.3s ease;
}
```

* file mã nguồn

File PROMPT_LOG.md (Nhật ký Prompt Engineering).
File mã nguồn website (index.html, style.css, thư mục assets/,...).

* Yêu cầu

1. Chuẩn Semantic HTML5 (Tối thiểu 5 thành phần)
Website phải sử dụng đúng ngữ nghĩa các thẻ HTML5:
● <header> (Chứa logo, navigation menu)
● <nav> (Thanh điều hướng)
● <main> (Khu vực nội dung chính)
● <section> hoặc <article> (Chia các khối nội dung rõ ràng)
● <footer> (Chân trang chứa thông tin liên hệ, copyright,...)
2. Kỹ thuật CSS & CSS Variables
● Sử dụng CSS Variables (:root { --primary-color: ...; }) để quản lý phối màu,

font chữ và spacing nhất quán cho toàn bộ trang.
● Áp dụng Layout hiện đại: CSS Flexbox hoặc CSS Grid để căn chỉnh
responsive cơ bản.
3. Tương tác & Hiệu ứng (Libraries)
● Tích hợp Animate.css: Áp dụng hiệu ứng động cho các phần tử chính (Text
tiêu đề, Hero Section, Button CTA,...).
● Tích hợp AOS (Animate On Scroll): Tạo hiệu ứng xuất hiện cuộn trang
sinh động cho các section nội dung.
● Hiệu ứng :hover, :focus tự viết bằng CSS cho nút bấm và các thẻ bài viết
(cards).

phân tích chi tiết và đưa tôi báo cáo của bạn để thực hiện xây dựng theo từng bước
- **Kết quả AI trả về (tóm tắt):** Báo cáo gồm: chọn one-page, ánh xạ yêu cầu → cách làm, cấu trúc thư mục, kiểm tra tương phản màu, chiến lược tách vai Animate.css (khi tải trang) và AOS (khi cuộn), kế hoạch 10 bước, checklist nghiệm thu.
- **Đánh giá:** *(tự điền sau khi kiểm chứng; ví dụ: số liệu tương phản WCAG đã kiểm lại bằng WebAIM chưa, có khớp không)*
- **Chỉnh sửa / prompt cải tiến:** *(nếu có)*
- **Bài học rút ra:** Yêu cầu AI "phân tích trước, làm sau" giúp thấy rủi ro sớm (ví dụ `--secondary-color` không đủ tương phản làm màu chữ).

## Entry 02 – Dựng khung thư mục và HTML ngữ nghĩa
- **Ngày:** 10/10/2026
- **Mục tiêu:** Có cây thư mục, `index.html` ngữ nghĩa với dữ liệu mẫu, `style.css` chứa token, `script.js` tối thiểu.
- **Prompt đã dùng:**
  > Tên quán: Phước coffee and tea, phong cách hiện đại và trẻ trung, 6-8 món dữ liệu mẫu. Thực hiện xây dựng bộ khung (HTML & CSS Variable đã có nên có thể xem xét bỏ qua)
- **Kết quả AI trả về (tóm tắt):** Cây thư mục, `index.html` đủ 6 section + header/nav/main/footer, 8 món menu mẫu, ảnh placeholder SVG, `style.css` mới có tokens + base + utilities, `script.js` xử lý menu mobile và năm ở footer.
- **Đánh giá:** *(điền sau khi chạy W3C Validator và thử Tab bằng bàn phím)*
- **Chỉnh sửa / prompt cải tiến:** *(ví dụ: nếu heading bị nhảy cấp thì ghi lại cách bạn sửa)*
- **Bài học rút ra:** *(điền)*

## Entry 03 – Hoàn thiện CSS, hiệu ứng, kiểm thử (Bước 3 đến 9)
- **Ngày:** 10/10/2026
- **Mục tiêu:** Làm nốt phần còn lại: CSS nền tảng + layout + responsive, menu mobile, Animate.css, AOS, hiệu ứng `:hover`/`:focus`, kiểm thử, tài liệu.
- **Prompt đã dùng:**
  > Tiếp tục làm tất cả các bước còn lại, báo cáo tôi những file đã được thay đổi và sửa
- **Kết quả AI trả về (tóm tắt):** `style.css` đầy đủ (≈ 650 dòng, 7 khối theo kế hoạch), `index.html` thêm class Animate.css / thuộc tính AOS, `script.js` thêm `AOS.init()`, thêm `README.md` và thư mục `assets/vendor/` (bản dự phòng của thư viện). AI tự chạy Chromium (Playwright) ở 360/768/1280px và W3C Validator offline.
- **Đánh giá (các lỗi/điểm cần sửa phát hiện trong quá trình kiểm thử):**
  1. **Gallery có ô trống** ở desktop: ảnh 1 chiếm 2x2 trong lưới 4 cột nhưng chỉ có 4 ảnh. Sửa: ảnh 4 chiếm 2 cột, đặt `grid-auto-rows` tường minh.
  2. **AOS và hover tranh nhau trên card:** AOS ghi đè `transition-property`, `transition-duration` và giữ `transition-delay` của `data-aos-delay` trên chính phần tử. Nếu để AOS và hover cùng một phần tử, hover bị chậm và mất transition của shadow. Sửa: bọc mỗi card trong `div.menu-item` mang AOS, hiệu ứng hover nằm trên `.card` bên trong.
  3. **Animate.css và hover trên nút:** Animate.css để `animation-fill-mode: both` và ghi đè `transform`, nên hover dùng `transform` có thể bị vô hiệu. Sửa: hover của `.btn` dùng thuộc tính `translate` (độc lập với `transform`).
  4. **Màu focus:** kế hoạch ban đầu dùng `--secondary-color` làm viền focus, nhưng tương phản chỉ ≈ 2.3:1 trên nền kem (yêu cầu ≥ 3:1). Đổi sang `--primary-color`; riêng footer (nền tối) dùng `--secondary-color`.
  5. **Card không có phần tử focus được** nên `:focus-within` không có tác dụng. Thêm link "Ghé quán thử" (kèm tên món cho trình đọc màn hình) vào mỗi card.
  6. Thanh cuộn ngang tiềm ẩn do AOS đẩy phần tử ra ngoài lề: thêm `overflow-x: clip` cho `main` (không dùng `hidden` vì có thể ảnh hưởng `position: sticky`).
- **Chỉnh sửa / prompt cải tiến:** *(điền: nếu bạn nhờ AI sửa tiếp thì dán prompt sửa lỗi vào đây)*
- **Bài học rút ra:** Kế hoạch tách vai "Animate.css khi tải, AOS khi cuộn" chưa đủ; cũng phải tránh để thư viện và hiệu ứng tự viết dùng chung một thuộc tính CSS trên cùng phần tử. Kiểm thử bằng trình duyệt thật lộ ra lỗi mà chỉ đọc code không thấy.

## Entry 04 – Kiểm tra cuối
- **Ngày:** 10/10/2026
- **Mục tiêu:** Đối chiếu checklist nghiệm thu.
- **Kết quả kiểm tra tự động:** W3C Validator (HTML + CSS): không có lỗi; 1 `h1`, heading không nhảy cấp, 15/15 ảnh có `alt`, không trùng `id`, mọi `aria-labelledby`/`href="#..."` trỏ đúng; không còn mã màu cứng ngoài `:root`; không có thanh cuộn ngang ở 360/768/1280px; menu mobile đúng `aria-expanded`, Esc đóng menu và trả focus; `prefers-reduced-motion` tắt AOS và rút ngắn animation.
- **Đánh giá:** *(điền sau khi bạn tự chạy Lighthouse và thử trên điện thoại thật; AI chưa đo Lighthouse)*
- **Bài học rút ra:** *(điền)*

## Tổng kết *(điền khi hoàn thành)*
- Kỹ thuật prompt hiệu quả nhất:
- Những lỗi AI hay mắc:
- Phần tự làm / tự sửa:

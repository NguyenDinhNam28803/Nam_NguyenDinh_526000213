# PROMPT_LOG – Website Phước Coffee & Tea

## Thông tin chung
- **Công cụ AI:** Claude (các bước ban đầu, theo nhật ký hiện có); GitHub Copilot trong VS Code (các lần rà soát và chỉnh sửa tiếp theo).
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
- **Đánh giá:** Kế hoạch đã bao quát các yêu cầu chính và xác định được rủi ro tương phản. Chưa có bằng chứng trong nhật ký cho thấy số liệu tương phản đã được kiểm lại độc lập bằng WebAIM; không xem các con số ước tính là kết quả kiểm định chính thức.
- **Chỉnh sửa / prompt cải tiến:** Chưa ghi nhận prompt sửa riêng ở bước này. Khi triển khai, cần yêu cầu AI nêu rõ cách kiểm chứng từng tiêu chí thay vì chỉ đưa ra kết luận.
- **Bài học rút ra:** Yêu cầu AI "phân tích trước, làm sau" giúp thấy rủi ro sớm (ví dụ `--secondary-color` không đủ tương phản làm màu chữ).

## Entry 02 – Dựng khung thư mục và HTML ngữ nghĩa
- **Ngày:** 10/10/2026
- **Mục tiêu:** Có cây thư mục, `index.html` ngữ nghĩa với dữ liệu mẫu, `style.css` chứa token, `script.js` tối thiểu.
- **Prompt đã dùng:**
  > Tên quán: Phước coffee and tea, phong cách hiện đại và trẻ trung, 6-8 món dữ liệu mẫu. Thực hiện xây dựng bộ khung (HTML & CSS Variable đã có nên có thể xem xét bỏ qua)
- **Kết quả AI trả về (tóm tắt):** Cây thư mục, `index.html` đủ 6 section + header/nav/main/footer, 8 món menu mẫu, ảnh placeholder SVG, `style.css` mới có tokens + base + utilities, `script.js` xử lý menu mobile và năm ở footer.
- **Đánh giá:** Khung có đủ các vùng nội dung chính và dữ liệu mẫu để tiếp tục tạo giao diện. Các ảnh SVG được tham chiếu lúc đầu chưa hiện diện trong thư mục dự án, vì vậy trang chưa thể hiển thị đủ hình. Chưa ghi lại kết quả validator hoặc kiểm tra bàn phím ở riêng bước này.
- **Chỉnh sửa / prompt cải tiến:** Prompt đã nêu tên quán, phong cách và số lượng món; có thể cụ thể hơn bằng cách yêu cầu kiểm tra sự tồn tại của mọi tài nguyên ảnh trước khi kết luận trang hoàn tất.
- **Bài học rút ra:** Sau khi sinh khung HTML, kiểm tra các đường dẫn `src` thực tế trong workspace, không chỉ kiểm tra cú pháp.

## Entry 03 – Hoàn thiện CSS, hiệu ứng, kiểm thử (Bước 3 đến 9)
- **Ngày:** 10/10/2026
- **Mục tiêu:** Làm nốt phần còn lại: CSS nền tảng + layout + responsive, menu mobile, Animate.css, AOS, hiệu ứng `:hover`/`:focus`, kiểm thử, tài liệu.
- **Prompt đã dùng:**
  > Tiếp tục làm tất cả các bước còn lại, báo cáo tôi những file đã được thay đổi và sửa.
- **Kết quả AI trả về (tóm tắt):** `style.css` đầy đủ (≈ 650 dòng, 7 khối theo kế hoạch), `index.html` thêm class Animate.css / thuộc tính AOS, `script.js` thêm `AOS.init()`, thêm `README.md` và thư mục `assets/vendor/` (bản dự phòng của thư viện). AI tự chạy Chromium (Playwright) ở 360/768/1280px và W3C Validator offline.
- **Đánh giá (các lỗi/điểm cần sửa phát hiện trong quá trình kiểm thử):**
  1. **Gallery có ô trống** ở desktop: ảnh 1 chiếm 2x2 trong lưới 4 cột nhưng chỉ có 4 ảnh. Sửa: ảnh 4 chiếm 2 cột, đặt `grid-auto-rows` tường minh.
  2. **AOS và hover tranh nhau trên card:** AOS ghi đè `transition-property`, `transition-duration` và giữ `transition-delay` của `data-aos-delay` trên chính phần tử. Nếu để AOS và hover cùng một phần tử, hover bị chậm và mất transition của shadow. Sửa: bọc mỗi card trong `div.menu-item` mang AOS, hiệu ứng hover nằm trên `.card` bên trong.
  3. **Animate.css và hover trên nút:** Animate.css để `animation-fill-mode: both` và ghi đè `transform`, nên hover dùng `transform` có thể bị vô hiệu. Sửa: hover của `.btn` dùng thuộc tính `translate` (độc lập với `transform`).
  4. **Màu focus:** kế hoạch ban đầu dùng `--secondary-color` làm viền focus, nhưng tương phản chỉ ≈ 2.3:1 trên nền kem (yêu cầu ≥ 3:1). Đổi sang `--primary-color`; riêng footer (nền tối) dùng `--secondary-color`.
  5. **Card không có phần tử focus được** nên `:focus-within` không có tác dụng. Thêm link "Ghé quán thử" (kèm tên món cho trình đọc màn hình) vào mỗi card.
  6. Thanh cuộn ngang tiềm ẩn do AOS đẩy phần tử ra ngoài lề: thêm `overflow-x: clip` cho `main` (không dùng `hidden` vì có thể ảnh hưởng `position: sticky`).
- **Chỉnh sửa / prompt cải tiến:** Người học có thể yêu cầu theo từng tiêu chí cụ thể và yêu cầu báo lại phép thử đã thực hiện. Ở các lượt sau, yêu cầu được thu hẹp thành kiểm tra liên kết CSS, bỏ JavaScript và bổ sung ảnh thật sự tồn tại trong thư mục.
- **Bài học rút ra:** Kế hoạch tách vai "Animate.css khi tải, AOS khi cuộn" chưa đủ; cũng phải tránh để thư viện và hiệu ứng tự viết dùng chung một thuộc tính CSS trên cùng phần tử. Kiểm thử bằng trình duyệt thật lộ ra lỗi mà chỉ đọc code không thấy.

## Entry 04 – Kiểm tra cuối
- **Ngày:** 10/10/2026
- **Mục tiêu:** Đối chiếu checklist nghiệm thu.
- **Kết quả kiểm tra ở giai đoạn trước:** Nhật ký trước đó ghi nhận kiểm tra validator và trình duyệt khi website còn dùng AOS, Animate.css và JavaScript. Các kết quả đó chỉ mô tả trạng thái ở thời điểm ấy, không đại diện cho phiên bản HTML/CSS đã thay đổi ở các lượt sau.
- **Đánh giá hiện tại:** Sau khi chuyển sang HTML/CSS, trình duyệt xác nhận `style.css` được tải, menu hiện ra và không có cuộn ngang ở 390/768/1280 px. Sau khi thêm SVG, cần chạy lại kiểm tra ảnh tải thành công; chưa có phép đo Lighthouse hoặc kiểm thử trên thiết bị thật trong nhật ký.
- **Bài học rút ra:** Khi thay đổi yêu cầu hoặc kiến trúc, phải chạy lại các kiểm tra liên quan và phân biệt rõ kết quả cũ với kết quả của phiên bản hiện tại.

## Entry 05 – Nhật ký hỏi–đáp khi rà soát CSS và bỏ JavaScript
- **Ngày:** 10/10/2026
- **Mục tiêu:** Xác định vì sao giao diện chưa hoàn chỉnh, sau đó giữ website chỉ gồm HTML và CSS như yêu cầu.

### Lượt hỏi 1 – Kiểm tra trang chủ đã áp dụng CSS chưa
- **Người học hỏi:**
  > Trang index chưa áp dụng thiết kế css vào nó, hãy kiểm tra.
- **AI kiểm tra và trả lời:** Xác nhận `index.html` có `<link rel="stylesheet" href="style.css">`, nên liên kết CSS đã được khai báo. Tuy nhiên, ở trạng thái được kiểm tra lúc đó, `style.css` mới có reset, biến và tiện ích cơ bản; các quy tắc layout/component còn là phần khung. AI chỉ ra đây là lý do chính khiến trang chưa có thiết kế hoàn chỉnh, không phải do thiếu thẻ liên kết CSS.
- **Người học đánh giá / hành động tiếp theo:** Thu hẹp yêu cầu sang việc chỉ giữ HTML và CSS, đồng thời loại bỏ JavaScript để tránh tiếp tục dựa vào hành vi cần script.
- **Bài học:** Phân biệt lỗi "CSS không được nạp" với lỗi "CSS được nạp nhưng chưa có đủ quy tắc giao diện".

### Lượt hỏi 2 – Bỏ JavaScript, đánh giá lại HTML và CSS
- **Người học hỏi:**
  > Thực hiện loại bỏ thư mục javascript, chỉ có html và css. Tiếp tục đánh giá 2 thư mục sau khi sửa.
- **AI kiểm tra và trả lời:** Kiểm tra thấy dự án dùng `script.js` cho AOS, năm tự cập nhật ở chân trang và menu hamburger; HTML cũng nạp AOS/Animate.css, còn CSS điều khiển menu bằng trạng thái `.is-open`. Xóa riêng file script sẽ làm các phần này mất chức năng hoặc nội dung bị ẩn.
- **AI đã sửa:** Gỡ thẻ `<script>`, AOS, Animate.css, class/thuộc tính phụ thuộc thư viện và nút hamburger; thay menu bằng danh sách liên kết luôn hiển thị, tự xuống dòng bằng CSS; xóa `script.js`; sửa hướng dẫn trong README.
- **Kết quả đã kiểm tra:** Công cụ Problems không báo lỗi cho HTML/CSS; truy vấn trình duyệt xác nhận font/nền CSS được áp dụng, menu hiển thị, không còn script trên trang và không tràn ngang ở 390, 768, 1280 px.
- **Người học đánh giá:** Việc giữ HTML/CSS-only đồng nghĩa bỏ animation phụ thuộc thư viện và tương tác menu đóng/mở; điều hướng cơ bản vẫn dùng được vì các liên kết luôn hiện. Lần kiểm tra lúc đó phát hiện các đường dẫn ảnh chưa có tệp tương ứng.
- **Bài học:** Khi loại bỏ một công nghệ, cần rà tất cả chức năng phụ thuộc nó, không chỉ xóa file `.js`.

## Entry 06 – Bổ sung ảnh minh họa và dùng logo có sẵn
- **Ngày:** 10/10/2026
- **Mục tiêu:** Làm cho các hình ảnh đang được tham chiếu trong HTML tồn tại và hiển thị; tận dụng logo được cung cấp trong `assets/`.
- **Người học hỏi:**
  > Thêm các file ảnh mẫu các món nước, hình ảnh của quán, hình ảnh liên quan và sử dụng logo có sẵn trong thư mục để hiển thị.
- **AI kiểm tra trước khi sửa:** Tìm thấy `assets/Logo_coffee.jpg`, nhưng các thư mục/tệp ảnh mà HTML tham chiếu chưa có.
- **AI đã sửa:** Tạo 14 ảnh SVG minh họa tự vẽ cho hero, không gian giới thiệu, 8 món trong menu và 4 góc quán; cập nhật favicon và logo ở header để dùng `assets/Logo_coffee.jpg`; bổ sung style hiển thị logo dạng biểu tượng; cập nhật README về nguồn và loại hình ảnh.
- **Kết quả / giới hạn:** Các hình mới là minh họa vector mẫu, không phải ảnh chụp sản phẩm hoặc không gian thực tế. Logo giữ nguyên tệp do người học cung cấp. Cần xác nhận tải thành công từng ảnh trên trình duyệt sau thay đổi; nếu dùng nội dung thật, người học cần thay SVG minh họa và cập nhật mô tả `alt` khi cần.
- **Bài học:** Kiểm kê tài nguyên có sẵn trước khi tạo mới giúp tái sử dụng đúng logo; ghi rõ ảnh nào là minh họa để không gây nhầm lẫn với ảnh chụp thực tế.

## Entry 07 – Yêu cầu đánh giá và trình bày chi tiết hỏi–đáp
- **Ngày:** 10/10/2026
- **Người học hỏi:**
  > File PROMPT_LOG.md đánh giá và bổ sung thêm trình bày chi tiết các bước hỏi - đáp với AI.
- **AI đã cập nhật nhật ký:** Bổ sung các lượt hỏi thực tế, cách AI kiểm tra, kết quả sửa, bằng chứng kiểm thử và nhận xét/bài học sau từng lượt; tách kết quả kiểm thử phiên bản dùng JavaScript khỏi phiên bản hiện tại HTML/CSS.
- **Đánh giá nhật ký:** Nhật ký hiện cho thấy tiến trình và quyết định kỹ thuật tốt hơn, nhưng một vài phần của các ghi chép cũ vẫn là bản tóm tắt do AI tạo (ví dụ báo cáo ban đầu và quá trình hoàn thiện CSS). Người học nên đối chiếu với lịch sử chat/commit và sửa prompt hoặc kết quả nào chưa trùng với trao đổi thực tế trước khi nộp.
- **Đánh giá điểm theo tiêu chí hiện có:** Các tiêu chí được chép trong nhật ký có tổng cộng 7.0 điểm (1.0 + 2.0 + 2.5 + 1.5), chưa đủ thang 10. Không tự suy diễn 3.0 điểm còn lại; cần lấy phần còn thiếu từ đề bài. Điểm thực tế cũng cần đối chiếu repository, Live Preview và sản phẩm đã triển khai.
- **Câu hỏi tự đánh giá gợi ý:** AI đã tiết kiệm thời gian ở khâu nào? Prompt nào cần bổ sung ràng buộc? Bạn đã tự kiểm chứng hoặc chỉnh sửa điều gì mà AI chưa làm đúng?

## Tổng kết *(điền khi hoàn thành)*
- Kỹ thuật prompt hiệu quả nhất: Nêu rõ phạm vi/công nghệ được phép dùng, yêu cầu kiểm tra trạng thái hiện tại trước khi sửa, và yêu cầu báo bằng chứng sau kiểm thử.
- Những lỗi AI hay mắc: Có thể cho rằng tệp ảnh tham chiếu đã tồn tại; dễ giữ lại các tính năng phụ thuộc JavaScript khi người học yêu cầu HTML/CSS-only; kết quả kiểm thử cũ có thể không còn đúng sau khi kiến trúc thay đổi.
- Phần người học cần tự làm / tự sửa: Điền thông tin cá nhân, thay dữ liệu mẫu, xác nhận nội dung hỏi–đáp từ lịch sử thực tế, kiểm tra website khi triển khai và bổ sung đầy đủ tiêu chí chấm điểm còn thiếu.

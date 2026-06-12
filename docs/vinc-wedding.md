# Vinc Wedding - Thiệp Cưới Online

## Giới thiệu

**Vinc Wedding** là website bán hàng / landing page giới thiệu dịch vụ **thiệp cưới online** (thiệp mời đám cưới điện tử). Dự án được xây dựng trên nền tảng **Ladipage** (công cụ tạo landing page của Việt Nam) và được xuất thành static HTML.

Website hiển thị các mẫu thiệp cưới đẹp, hiện đại, sang trọng cho các cặp đôi tham khảo và đặt dịch vụ.

## Công nghệ sử dụng

- **Nền tảng:** Ladipage (landing page builder)
- **Fonts:** Google Fonts (Montserrat, Yeseva One, Quicksand, Niramit, Merriweather)
- **CDN:** Ladipage CDN (`w.ladicdn.com`, `static.ladipage.net`)
- **Triển khai:** Vercel / static hosting

## Cấu trúc thư mục

```
vinc-wedding/
├── docs/
│   └── vinc-wedding.md          # Tài liệu dự án
├── soure/                        # Thư mục chứa 4 mẫu thiệp tham khảo (tham khảo từ nhacohy.vn)
│   ├── www.nhacohy.vn/
│   │   └── www.nhacohy.vn/
│   │       └── mau-bliss-prenium.html
│   ├── www.nhacohy.vn (1)/
│   │   └── www.nhacohy.vn/
│   │       └── mau-evergreen.html
│   ├── www.nhacohy.vn (2)/
│   │   └── www.nhacohy.vn/
│   │       └── mau-herald-premium.html
│   └── www.nhacohy.vn (3)/
│       └── www.nhacohy.vn/
│           └── mau-nova-premium.html
├── templates/                    # 4 mẫu thiệp tham khảo (self-host)
│   ├── mau-bliss-prenium.html
│   ├── mau-evergreen.html
│   ├── mau-herald-premium.html
│   └── mau-nova-premium.html
├── www.vinc-wedding.vn/          # Thư mục chính của website
│   ├── index.html                # Landing page chính (9403 dòng)
│   └── ... (các thư mục tài nguyên CDN khác)
├── a.ladipage.com/
├── fonts.googleapis.com/
├── fonts.gstatic.com/
├── g.ladicdn.com/
├── w.ladicdn.com/
└── www.google.com/
```

## Landing Page - Các sections

Trang chủ (`index.html`) gồm 7 sections:

| Section | ID | Mô tả |
|---------|----|-------|
| 1 | `SECTION1241` | **Hero / Header** - Logo, headline "Thiệp Cưới Online Vinc Wedding", CTA "Đặt Ngay" (Zalo) |
| 2 | `SECTION1373` | **CÁC MẪU THIỆP NỔI BẬT** - 4 mẫu thiệp tham khảo (Bliss, Evergreen, Herald, Nova) dạng card 1 hàng ngang, click mở tab mới + nút "Xem thêm mẫu" |
| 3 | `SECTION2337` | **BẢNG GIÁ** - 2 gói: BASIC (500,000đ) và PREMIUM (999,000đ) |
| 4 | `SECTION2338` | **SO SÁNH TÍNH NĂNG** - Bảng compare BASIC vs PREMIUM (11 tính năng) |
| 5 | `SECTION1256` | **ƯU ĐIỂM** - 6 lợi ích khi dùng Vinc Wedding |
| 6 | `SECTION1608` | **LÝ DO CHỌN** - 4 lý do nên chọn thiệp cưới online |
| 7 | `SECTION1610` | **Footer / Liên hệ** - Form đăng ký tư vấn, Zalo, thông tin liên hệ |

## 4 Mẫu thiệp tham khảo

| # | Tên | Phong cách | File | Thumbnail |
|---|-----|-----------|------|-----------|
| 1 | **Bliss** | Hạnh phúc trọn vẹn, thiết kế tinh tế, hiện đại | `templates/mau-bliss-prenium.html` | `IMAGE2345` |
| 2 | **Evergreen** | Gam màu xanh olive, be, trắng - gần gũi sang trọng | `templates/mau-evergreen.html` | `IMAGE2348` |
| 3 | **Herald Premium** | Phong cách vintage như tờ báo hỷ | `templates/mau-herald-premium.html` | `IMAGE2350` |
| 4 | **Nova Premium** | Hiện đại, tối giản, lấy cảm hứng từ ánh sáng | `templates/mau-nova-premium.html` | `IMAGE2423` |

### Layout section "CÁC MẪU THIỆP NỔI BẬT"

- **Container:** `GROUP2344` - width 1735.94px, 4 card dạng hàng ngang
- **Card size:** 415.934 × 651.802px mỗi card
- **Badge:** Hình tròn 188.57px, góc trên bên phải card, hiển thị tên template
- **Link:** Mỗi card là `<a target="_blank">` trỏ tới file trong `templates/`
- **Ảnh thumb:** Dùng OG image từ `static.ladipage.net`

## Triển khai (Deployment)

### Yêu cầu
- Static hosting (Vercel, Netlify, GitHub Pages, hoặc web server bất kỳ)

### Các bước triển khai

1. **Build** - Dự án là static HTML, không cần build.
2. **Upload** - Upload toàn bộ thư mục `www.vinc-wedding.vn/` lên hosting.
3. **Cấu hình domain** - Trỏ domain `vinc-wedding.vn` về hosting.
4. **Verify** - Kiểm tra các đường dẫn tương đối hoạt động.

### Triển khai lên Vercel (hiện tại)

Dự án hiện đang chạy tại: [https://vinc-wedding.vercel.app](https://vinc-wedding.vercel.app)

```bash
# Deploy bằng Vercel CLI
vercel --prod
```

### Lưu ý
- Các tài nguyên CDN (Ladipage, Google Fonts, `static.ladipage.net`) được load từ CDN gốc, cần có kết nối internet.
- 4 file template trong `templates/` được self-host, đường dẫn tương đối.
- Các link trong section "CÁC MẪU THIỆP NỔI BẬT" trỏ tới `templates/*.html` và mở tab mới (`target="_blank"`).
- Mọi đường dẫn trong `index.html` nên dùng đường dẫn tương đối để dễ dàng chuyển đổi môi trường.

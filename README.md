# My CV — Personal Portfolio

CV cá nhân được xây dựng bằng **HTML & CSS thuần túy** — không framework, không JS runtime, nhẹ mượt, deploy miễn phí trên GitHub Pages.

## 🚀 Demo

👉 **[Xem CV online](https://samdt05.github.io/mycv/)** (sau khi deploy)

## 📁 Cấu trúc

```
mycv/
├── index.html      # HTML chính
├── styles.css      # CSS styling (design system, responsive, dark mode, print)
├── .gitignore
└── README.md
```

## ✨ Tính năng

- **Responsive**: Desktop sidebar + mobile stack
- **Dark mode**: Tự động theo system preference
- **Print friendly**: In PDF đẹp mắt (Ctrl+P)
- **Accessible**: Semantic HTML, focus-visible, reduced motion
- **Animations**: Fade-in staggered, hover effects
- **Zero dependencies**: Chỉ load font Inter từ Google Fonts

## 🛠️ Tùy chỉnh

1. Mở `index.html` → sửa thông tin cá nhân (tên, kinh nghiệm, dự án, link...)
2. Mở `styles.css` → chỉnh màu sắc ở `:root` (CSS custom properties)
3. Thay avatar: sửa `seed=NguyenVanA` trong URL `dicebear.com` thành tên của bạn

## 📦 Deploy lên GitHub Pages (miễn phí)

### Cách 1: Tự động (khuyên dùng)

```bash
# 1. Tạo repo mới trên GitHub tên `mycv` (Public)
# 2. Clone về local
git clone https://github.com/samdt05/mycv.git
cd mycv

# 3. Copy file index.html, styles.css, .gitignore vào folder này

# 4. Commit & push
git add .
git commit -m "Add CV"
git push origin main

# 5. Vào GitHub repo → Settings → Pages
#    Source: "Deploy from a branch"
#    Branch: "main" / (root)
#    Save → chờ 1-2 phút
```

### Cách 2: Dùng GitHub Actions (tự động build/deploy)

Tạo file `.github/workflows/deploy.yml`:

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [main]

permissions:
  contents: read
  pages: write
  id-token: write

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/configure-pages@v4
      - uses: actions/upload-pages-artifact@v3
        with:
          path: '.'
      - uses: actions/deploy-pages@v4
```

## 🔐 Push nếu bị lỗi 403 (permission denied)

Nếu git config dùng tài khoản cũ (`dangthisam2005`) mà repo thuộc tài khoản mới (`samdt05`):

```bash
# Tạo Personal Access Token (PAT) tại GitHub.com → Settings → Developer settings → PAT
# Sau đó push kèm token:
git push https://YOUR_PAT_TOKEN@github.com/samdt05/mycv.git main
```

Hoặc config SSH key cho tài khoản `samdt05` (khuyên dùng lâu dài).

## 📄 License

MIT — tự do sử dụng, sửa đổi, chia sẻ.
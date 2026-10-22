# Hướng dẫn sử dụng CV Template

## 🎯 Mục đích
File `index.html` hiện tại là **template** - bạn chỉ cần điền thông tin cá nhân vào các chỗ được đánh dấu `[...]` mà không cần biết code.

---

## 📝 Cách điền thông tin

### 1. Mở file `index.html` bằng trình soạn thảo văn bản
- **Khuyên dùng:** VS Code (miễn phí, có gợi ý màu sắc)
- **Cách mở:** Click chuột phải file → "Open with Code" hoặc kéo thả vào VS Code

### 2. Tìm và thay thế các placeholder
Tìm từ khóa `[...]` (trong ngoặc vuông) và thay bằng thông tin của bạn.

**Ví dụ:**
```html
<!-- Trước -->
<h1 class="name">[Họ tên đầy đủ]</h1>

<!-- Sau khi điền -->
<h1 class="name">Nguyễn Văn An</h1>
```

### 3. Các mục cần điền (theo thứ tự ưu tiên)

| Vị trí | Placeholder | Ví dụ điền |
|--------|-------------|------------|
| `<title>` | `[Họ tên]` | Nguyễn Văn An |
| `<meta description>` | `[Họ tên]`, `[Trường/Chuyên ngành]` | Nguyễn Văn An \| CNTT - ĐH Bách Khoa |
| Avatar | `avatar.jpg` | Đặt file ảnh tên `avatar.jpg` cùng thư mục |
| Tên | `[Họ tên đầy đủ]` | Nguyễn Văn An |
| Vị trí | `[Vị trí ứng tuyển]` | Junior Business Analyst |
| Địa chỉ | `[Thành phố]` | Hà Nội |
| Badge | `[Badge nhận diện]` | Sinh viên ĐH Bách Khoa \| ECBA Candidate |
| Email | `[email@domain.com]` | an.nguyen@email.com |
| Phone | `[Số điện thoại]` | 090 123 4567 |
| GitHub | `[username]` | annguyenba |
| LinkedIn | `[username]` | annguyenba |
| Summary | Toàn bộ đoạn `<p>...</p>` | Viết 3-4 câu về bản thân |
| Kinh nghiệm | Các block `<article class="job">` | Copy/paste và sửa cho từng công việc |
| Dự án | Các block `<article class="project">` | Link GitHub + mô tả ngắn |
| Giáo dục | Block `<div class="edu-item">` | Tên bằng, trường, chuyên ngành, GPA |
| Hoạt động | Các `<li>` trong `.activities` | Giải thưởng, vai trò, năm |
| References | Các `<div class="ref-card">` | Tên, chức danh, SĐT, email của người giới thiệu |

---

## 🖼️ Ảnh đại diện (Avatar)

**Cách 1 (Khuyên dùng):** Đặt file ảnh của bạn tên là `avatar.jpg` cùng thư mục với `index.html`

**Cách 2:** Thay link trong thuộc tính `src`:
```html
<img src="https://link-anh-cua-ban.jpg" ...>
```

**Mặc định:** Nếu không có ảnh, sẽ tự động tạo avatar cartoon từ tên (dùng DiceBear API).

---

## ➕ Thêm/Xoá mục kinh nghiệm, dự án, chứng chỉ...

### Thêm kinh nghiệm mới
Copy toàn bộ block này và dán vào sau job cuối cùng trong section `.experience`:

```html
<article class="job">
  <header>
    <div>
      <h3>[Tên vị trí]</h3>
      <p class="company">[Công ty] - [Địa điểm]</p>
    </div>
    <time>[MM/YYYY] – [MM/YYYY]</time>
  </header>
  <ul class="achievements">
    <li>[Achievement 1]</li>
    <li>[Achievement 2]</li>
    <li><strong>Kết quả:</strong> [Metric]</li>
  </ul>
</article>
```

### Thêm dự án portfolio
Copy block này vào section `.projects`:

```html
<article class="project">
  <div class="project-info">
    <h3><a href="[Link GitHub/Demo]" target="_blank">[Tên dự án]</a></h3>
    <p class="desc">[Mô tả 1 câu]</p>
    <div class="tech">[Artifact 1] · [Artifact 2] · [Artifact 3]</div>
  </div>
</article>
```

### Thêm chứng chỉ
Thêm dòng `<li>` trong section `.certs`:
```html
<li>[Tên chứng chỉ] - <em>[Năm/Nhà cấp]</em></li>
```

### Thêm skill
Thêm dòng `<li>` trong nhóm skill phù hợp (`.tags`):
```html
<li>Tên skill mới</li>
```

---

## 🚀 Xem trước & Xuất PDF

### Xem trước
- Mở file `index.html` trực tiếp bằng trình duyệt (Chrome/Edge/Firefox)
- Hoặc dùng VS Code extension **"Live Server"**: Click chuột phải → "Open with Live Server"

### Xuất PDF (chuẩn A4, đẹp cho print)
1. Mở file bằng Chrome
2. `Ctrl + P` (In)
3. Cài đặt:
   - **Destination:** Save as PDF
   - **Paper size:** A4
   - **Margins:** Default / None
   - **Background graphics:** ✅ BẬT (quan trọng để giữ màu sidebar)
   - **Scale:** 90-95% (nếu bị tràn trang)
4. Lưu file PDF

---

## 🎨 Tuỳ chỉnh màu sắc (Tuỳ chọn)

Mở file `styles.css`, phần `:root` (dòng 6-69) để đổi màu:

```css
:root {
  --primary: #1e40af;      /* Màu chính (xanh dương đậm) */
  --accent: #0ea5e9;       /* Màu nhấn (xanh dương sáng) */
  --sidebar-bg: #0f172a;   /* Màu nền sidebar (xanh navy) */
  --success: #059669;      /* Màu thành công (xanh lá) */
  --warning: #d97706;      /* Màu cảnh báo (cam) */
}
```

**Gợi ý palette khác:**
| Theme | --primary | --accent | --sidebar-bg |
|-------|-----------|----------|--------------|
| Xanh rừng (Forest) | #166534 | #22c55e | #14532d |
| Tím (Purple) | #6d28d9 | #a855f7 | #3b0764 |
| Đỏ (Red) | #b91c1c | #ef4444 | #7f1d1d |
| Cam (Orange) | #c2410c | #f97316 | #9a3412 |

---

## 💡 Mẹo viết CV BA hiệu quả

### Achievement = Hành động + Ngữ cảnh + Kết quả (Số liệu)
| ❌ Yếu | ✅ Mạnh |
|--------|---------|
| "Viết BRD cho dự án" | "Soạn thảo **BRD 25 trang** cho module B2B Order Management, **review sign-off cùng PO & Tech Lead** trước dev" |
| "Vẽ BPMN" | "Vẽ **BPMN 2.0 As-is/To-be cho 8 quy trình**, xác định **15+ pain points**, đề xuất giải pháp **giảm 30% thao tác thủ công**" |
| "Làm UAT" | "Hỗ trợ UAT: viết **50 test scenarios**, log defect, phối hợp dev fix & verify, **deploy đúng hạn, satisfaction 4.5/5**" |

### Artifacts BA đáng giá cho portfolio
- BRD / FSD / SRS (sample 5-10 trang, che tên nhạy cảm)
- BPMN 2.0 As-is / To-be
- Use Case Diagram, Sequence Diagram
- ERD, API Spec (OpenAPI/Swagger)
- User Story Mapping + Acceptance Criteria (Gherkin)
- Wireframe/Prototype Figma (link view-only)
- UAT Test Cases / Test Plan
- Gap Analysis, Impact Analysis

---

## 🔧 Troubleshooting

| Vấn đề | Giải pháp |
|--------|-----------|
| Màu in PDF bị mất | Bật "Background graphics" trong print dialog |
| Sidebar bị cắt khi in | Giảm scale xuống 85-90% |
| Font hiển thị không đẹp | Kiểm tra có load Google Fonts (cần internet) |
| Avatar không hiện | Đảm bảo file `avatar.jpg` cùng thư mục, hoặc sửa link `src` |
| Responsive bị lỗi trên mobile | Không sửa CSS, template đã hỗ trợ mobile-first |

---

## 📁 Cấu trúc thư mục
```
mycv/
├── index.html          ← File template chính (CHỈNH SỬA FILE NÀY)
├── styles.css          ← CSS (ít khi cần sửa)
├── avatar.jpg          ← Ảnh của bạn (tự thêm)
└── HUONG_DAN_SU_DUNG.md ← File hướng dẫn này
```

---

## 📞 Hỗ trợ
Nếu gặp vấn đề, hãy:
1. Kiểm tra lại placeholder `[...]` còn sót lại không (Ctrl+F tìm `[`)
2. Validate HTML: https://validator.w3.org/ (dán code vào check)
3. So sánh với file gốc để xem cấu trúc block nào bị thiếu

**Chúc bạn có một CV BA ấn tượng và nhận nhiều offer! 🎉**
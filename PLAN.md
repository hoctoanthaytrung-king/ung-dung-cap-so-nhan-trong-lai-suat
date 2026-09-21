# Kế hoạch biên soạn: Cẩm nang Tài chính Cá nhân

## Định dạng kỹ thuật

Sách được biên soạn bằng **LaTeX** (lớp `extreport`, khổ A4, font 14pt), vì:

-   **Hệ thống công thức toán học:** Hỗ trợ render các công thức giải tích, phương trình tài chính (Fisher, Gordon-Shapiro, giới hạn Bernoulli) chuẩn mực và đẹp mắt nhất.
-   **Đồ họa Vector tích hợp:** Sử dụng gói `tikz` và `pgfplots` để vẽ trực tiếp các biểu đồ dòng tiền, đường cong lãi kép, và lịch trình khấu hao mà không cần dùng phần mềm vẽ ngoài, đảm bảo độ sắc nét tuyệt đối khi in ấn.
-   **Trình bày cấu trúc (Tcolorbox):** Tạo các hộp text box sinh động để làm nổi bật các "Tình huống đời sống", giúp người đọc dễ dàng phân biệt giữa lý thuyết hàn lâm và thực tiễn.
-   **Quản lý dự án lớn:** Có thể tách nội dung thành nhiều file `.tex` nhỏ và dùng lệnh `\include{}` hoặc `\input{}` để gộp lại, thuận tiện cho việc quản lý mã nguồn và rà soát lỗi.

## Cấu trúc thư mục dự kiến

Dự án sẽ được tái cấu trúc từ 1 file đơn lẻ thành hệ thống thư mục dạng module:

```text
finance-handbook/
├── main.tex                 # File gốc, chứa cấu trúc tài liệu và \include các chương
├── setup/
│   └── packages.tex         # Khai báo toàn bộ \usepackage, \geometry, \hypersetup
├── chapters/
│   ├── 00-loi-noi-dau.tex
│   ├── 01-lai-kep.tex       # Lãi kép & sức mạnh của tích lũy
│   ├── 02-vay-tra-gop.tex   # Vay trả góp & Lịch trình trả nợ
│   ├── 03-lam-phat.tex      # Lạm phát và phương trình Fisher
│   ├── 04-dau-tu-co-tuc.tex # Đầu tư cổ tức & Mô hình Gordon
│   └── 99-phan-ket.tex      # Phần kết & Phụ lục thực hành
├── figures/                 # Chứa code TikZ tách rời (để code gọn hơn)
│   ├── fig-lai-kep.tex
│   ├── fig-khau-hao.tex
│   └── fig-gordon.tex
├── README.md
└── PLAN.md
```

## Quy ước kỹ thuật trong LaTeX

-   **Công thức toán học:** Công thức nội suy inline dùng `$ ... $`. Phương trình dòng độc lập dùng môi trường `\begin{equation} ... \end{equation}` hoặc `\begin{align*} ... \end{align*}` để đánh số và gióng hàng tự động.
-   **Hộp tình huống thực tế:** Dùng môi trường `tcolorbox` với thiết lập chuẩn: `[colback=blue!5!white, colframe=blue!75!black, arc=2mm]`.
-   **Đồ thị minh họa:** Toàn bộ code đồ thị (`tikzpicture`, `axis`) được đặt trong môi trường `\begin{figure}[htbp]` kèm theo `\caption` và `\label` để tham chiếu chéo.
-   **Bảng biểu:** Sử dụng gói `tabularx` để tự động giãn cột (`X`) cho vừa với chiều rộng trang (`\textwidth`), giúp bảng "Phụ lục tra cứu nhanh" không bị tràn lề.

## Cài đặt & Biên dịch

Dự án sử dụng trình biên dịch LaTeX chuẩn hỗ trợ tiếng Việt (`utf8`).
- **Nền tảng trực tuyến:** Khuyến nghị sử dụng [Overleaf](https://www.overleaf.com/) để không cần cài đặt cục bộ, dễ dàng quản lý phiên bản. Trình biên dịch: `pdfLaTeX`.
- **Cài đặt cục bộ:** Sử dụng TeX Live (Linux/Windows) hoặc MacTeX (macOS) kết hợp với VS Code (extension LaTeX Workshop).
- **Biên dịch:** Tại thư mục gốc, chạy lệnh:
  ```bash
  pdflatex main.tex
  ```
  *(Cần chạy lệnh 2 lần để hệ thống cập nhật đúng Mục lục và Tham chiếu chéo).*

## Các giai đoạn thực hiện

### Giai đoạn 0 — Chuẩn bị hạ tầng (trước khi chia module)

-   [x] Khởi tạo khung dự án cơ bản (đã có bản thảo thô).
-   [x] Khai báo đầy đủ các gói `vietnam`, `amsmath`, `tikz`, `tcolorbox`, `hyperref`.
-   [ ] Tách bản thảo 1 file hiện tại thành cấu trúc thư mục module như thiết kế.
-   [ ] Thiết lập repo Git để quản lý thay đổi.

### Giai đoạn 1 — Chương thí điểm (Chương 1 & Đồ họa)

-   [x] Định dạng chuẩn Chương 1: Cấu trúc Heading, Tcolorbox tình huống.
-   [x] Vẽ và compile thành công đồ thị TikZ: So sánh tích lũy tuyến tính và hàm mũ.
-   [ ] Đóng gói code TikZ vào thư mục `figures/` để file `.tex` chính không bị rối.
-   [ ] Chốt văn phong (thân thiện, logic toán học) và layout để áp dụng cho các chương sau.

### Giai đoạn 2 — Rà soát & Định dạng đại trà

-   [x] Hoàn thành nội dung thô toàn bộ Lời nói đầu + 4 Chương chính + Phụ lục.
-   [x] Viết code TikZ cho biểu đồ Khấu hao nợ (Chương 2) và Mô hình Gordon (Chương 4).
-   [ ] Áp dụng đồng loạt cấu trúc định dạng (`tcolorbox`, `equation`) cho toàn bộ tài liệu.
-   [ ] Xây dựng bảng tra cứu nhanh bằng `tabularx` tại Phụ lục 1.

### Giai đoạn 3 — Biên tập tổng thể & Phản biện

-   [ ] Kiểm tra chéo tính chính xác của các công thức toán học (Gordon, Fisher, Lãi kép).
-   [ ] Rà soát văn phong: Đảm bảo sự cân bằng giữa tính chính xác học thuật của Toán học và tính dễ hiểu, ứng dụng của Tài chính cá nhân.
-   [ ] Kiểm tra các liên kết tham chiếu (hyperlinks) trong file PDF.

### Giai đoạn 4 — Hoàn thiện xuất bản

-   [x] Thiết kế trang bìa (`titlepage`) đơn giản, học thuật, đúng tinh thần "Dự án cá nhân".
-   [ ] Bổ sung mục lục tự động (`\tableofcontents`).
-   [ ] Căn chỉnh lề (`\geometry`), khoảng cách dòng (`\onehalfspacing`) để tối ưu việc in ấn trên giấy A4.
-   [ ] Xuất file PDF Final.

### Giai đoạn 5 — Duy trì sau xuất bản

-   [ ] Cập nhật các bảng lãi suất giả định trong Phụ lục 1 nếu có biến động kinh tế vĩ mô lớn.

## Theo dõi tiến độ từng chương

| # | Chương | Trạng thái | Yếu tố kỹ thuật đặc thù |
|---|---|---|---|
| - | Trang bìa & Lời đề tặng | Hoàn thành | `titlepage`, `tcolorbox` |
| - | Lời nói đầu | Hoàn thành | Định dạng chuẩn |
| 1 | Lãi kép & sức mạnh của tích lũy dài hạn | Chờ tách file | Equation, TikZ/PGFPlots (Biểu đồ hàm mũ) |
| 2 | Vay trả góp & Lịch trình trả nợ | Chờ tách file | Bất phương trình, TikZ (Biểu đồ gốc - lãi) |
| 3 | Lạm phát và bảo vệ sức mua | Chờ tách file | Phương trình Fisher `\align*` |
| 4 | Đầu tư cổ tức & Xây dựng dòng tiền | Chờ tách file | Giới hạn vô cực, TikZ (Biểu đồ chuỗi dòng tiền) |
| - | Phần kết & Phụ lục thực hành | Chờ tách file | Bảng `tabularx`, Danh sách `enumerate` |

Trạng thái đề xuất dùng: `Chờ tách file` → `Đang rà soát` → `Đang biên tập` → `Hoàn thiện`.

## Công cụ hỗ trợ

-   **Overleaf/VS Code:** Trình soạn thảo và biên dịch LaTeX.
-   **Git/GitHub:** Quản lý mã nguồn.
-   **Geogebra/Desmos:** (Tùy chọn) Để nháp trước các đồ thị hàm mũ trước khi đưa vào code `pgfplots`.

## Rủi ro cần lưu ý

-   **Compile time chậm:** Gói `tikz` vẽ đồ họa trực tiếp có thể làm thời gian biên dịch PDF bị lâu. *Khắc phục: Xem xét dùng thư viện `\usetikzlibrary{external}` nếu cần thiết.*
-   **Cảm giác "Ngợp" toán học:** Công thức giải tích (giới hạn, tổng chuỗi vô hạn) có thể khiến người đọc phổ thông hoảng sợ. *Khắc phục: Luôn bám sát nguyên tắc "có công thức đi kèm với Tcolorbox tình huống thực tế giải thích bằng số chẵn".*
-   **Tràn lề công thức:** Các công thức dài có thể bị tràn biên. *Khắc phục: Sử dụng `align*` thay vì `equation` để ngắt dòng công thức.*

## Cập nhật tiến độ mới nhất (22/09/2026)

### Đã hoàn thành (Giai đoạn 0 & 2)

✅ **Nội dung:** 
- Hoàn tất 100% bản thảo thô (Lời nói đầu, 4 Chương chính, Phần kết, 2 Phụ lục).
- Toàn bộ nội dung đã được soạn thảo bằng cú pháp LaTeX.

✅ **Đồ họa & Toán học:**
- Code thành công 3 biểu đồ phức tạp bằng TikZ/PGFPlots (Lãi kép hàm mũ, Diện tích tích phân nợ gốc-lãi, Chuỗi chiết khấu Gordon).
- Render hoàn chỉnh các phương trình cốt lõi.

### Cần làm tiếp trong 2 tuần tới (Deadline: 06/10/2026)

🔲 **Hạ tầng:**
- Thực hiện chia tách module: Tách bản thảo `main.tex` hiện tại ra thư mục `chapters/` và `figures/` để dễ quản lý.

🔲 **Biên tập & Trình bày:**
- Thêm lệnh `\tableofcontents` để tạo mục lục.
- Rà soát lỗi đánh máy và lỗi tràn viền của các công thức toán.
- Soát lỗi chính tả tiếng Việt.

### Khuyến nghị

- **Ưu tiên cao:** Hoàn tất việc tách file ngay lập tức để chuyển sang giai đoạn rà soát từng phần. Việc để toàn bộ dự án trong 1 file `main.tex` sẽ gây khó khăn khi dò lỗi.
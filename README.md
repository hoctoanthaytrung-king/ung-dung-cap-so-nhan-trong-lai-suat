# Dự án: Ứng dụng Cấp số nhân trong Bài toán Tài chính

![Trạng thái](https://img.shields.io/badge/Trạng_thái-Đang_phát_triển-yellow)
![Giấy phép](https://img.shields.io/badge/Giấy_phép-Mã_nguồn_mở-blue)
![Công cụ](https://img.shields.io/badge/Được_viết_bằng-LaTeX_%7C_Python-239DAD)
![Tiến độ](https://img.shields.io/badge/Tiến_độ-Sprint_2-success)
![Tài liệu](https://img.shields.io/badge/Tài_liệu-20_trang-informational)

## Giới thiệu

**Ứng dụng Cấp số nhân trong Bài toán Tài chính** (Application of Geometric Progressions in Finance and Compound Interest) là một dự án mã nguồn mở cung cấp một góc nhìn toán học sâu sắc nhằm giải quyết các bài toán tài chính cốt lõi thông qua lăng kính của Cấp số nhân (Geometric Progressions - GP)[cite: 1]. Khác với các thư viện tài chính thông thường chỉ cung cấp kết quả đầu ra bằng code, dự án này tập trung mạnh vào việc giải mã cơ chế nội tại bằng hệ thống tài liệu LaTeX[cite: 1].

### 🎯 Đặc điểm nổi bật

- ✅ **Tài liệu học thuật chuyên sâu** - Sở hữu cấu trúc báo cáo/luận văn dài 20 trang được trình bày bằng hệ thống LaTeX[cite: 1].
- ✅ **Chứng minh toán học chặt chẽ** - Nâng tầm tư duy lên góc nhìn học thuật cấp đại học bằng hệ thống `amsthm` để tạo các khối Định lý (Theorem) và Chứng minh (Proof) chuyên nghiệp[cite: 1].
- ✅ **Mã nguồn Python đối chiếu** - Chứa module `compound_interest.py` cung cấp các tính toán cơ bản để so khớp với kết quả lý thuyết từ LaTeX[cite: 1].
- ✅ **Trực quan hóa dữ liệu** - Kết hợp các phương trình LaTeX và biểu đồ minh họa sự hội tụ của cấp số nhân lùi vô hạn thông qua Jupyter Notebook[cite: 1].
- ✅ **Tự động hóa CI/CD** - Được thiết lập quy trình kiểm thử và tích hợp bằng GitHub Actions (`python-app.yml`)[cite: 1].

## 📊 Tiến độ

| Khung thời gian | Tiêu điểm Kỹ thuật | Trạng thái |
|------------|------------|------------|
| Ngày 1 - 2 | Thiết lập kiến trúc kho lưu trữ, môi trường biên dịch LaTeX và tệp `requirements.txt`[cite: 1]. | ✅ |
| Ngày 3 - 5 | Soạn thảo `mathematical_proofs.tex` chứng minh mối liên hệ của chuỗi hội tụ[cite: 1]. | ✅ |
| Ngày 6 - 7 | Triển khai module `compound_interest.py` làm công cụ đối chiếu lý thuyết[cite: 1]. | ✅ |
| Ngày 8 - 10 | Viết Jupyter Notebook kết hợp phương trình LaTeX và biểu đồ minh họa[cite: 1]. | 🟨 |
| Ngày 11 - 14 | Hoàn thiện cấu trúc tài liệu (`README.md`, `CHANGELOG.md`, v.v.) và phát hành v1.0.0[cite: 1]. | 🟨 |

Xem chi tiết tiến độ tại [PLAN.md](PLAN.md) và [CHANGELOG.md](CHANGELOG.md)[cite: 1].

## 📥 Tải xuống

Các thành phần chính của dự án:
- **[Báo cáo toán học](docs/mathematical_proofs.pdf)** - File chứng minh lý thuyết gốc bằng LaTeX[cite: 1].
- [Mã nguồn Python](src/compound_interest.py) - Script xác minh bằng số học[cite: 1].
- [Sổ tay thực hành](notebooks/01_geometric_progressions_and_finance.ipynb) - Jupyter Notebook trực quan hóa[cite: 1].

Mục tiêu là giúp cộng đồng hiểu rõ các quy luật tài chính bắt nguồn từ cơ sở toán học duy nhất: sự hội tụ và phân kỳ của chuỗi hình học, từ đó dễ dàng tiếp cận, kiểm thử và đóng góp[cite: 1].

## Mục tiêu

- Giải quyết cơ chế toán học của các bài toán tài chính từ tính toán lãi kép đơn giản đến định giá cổ phiếu bằng mô hình tăng trưởng Gordon[cite: 1].
- Cung cấp một bộ tài liệu loại bỏ các liệt kê lý thuyết bậc trung học phổ thông, thay bằng giải tích toán học nghiêm ngặt[cite: 1].
- Kết nối sự chặt chẽ của công thức lý thuyết (LaTeX) với tính thực tiễn của công nghệ phần mềm (Python)[cite: 1].

## Độc giả

- Sinh viên và nhà nghiên cứu trong lĩnh vực tài chính định lượng.
- Kỹ sư phần mềm cần xây dựng thuật toán trên nền tảng toán học gốc.
- Người yêu thích hệ thống soạn thảo LaTeX và toán giải tích đại học.

## Cơ sở Toán học Định lượng

Dự án xoay quanh 3 nền tảng toán học cốt lõi, áp dụng để giải thích cấu trúc dòng tiền:

| Khái niệm Toán học | Ý nghĩa trong Tài chính |
|---|---|
| **Nguyên lý Cấp số nhân** | Một dãy số với tỷ số giữa hai số hạng liên tiếp là hằng số (công bội). Đây là cơ sở để tính toán tổng chuỗi hình học lùi vô hạn nhằm định giá các tài sản tài chính[cite: 1]. |
| **Lãi kép (Compound Interest)** | Sự phát triển của vốn chính xác là một cấp số nhân, trong đó số hạng đầu là Giá trị Hiện tại (PV) và công bội là (1 + i)[cite: 1]. |
| **Dòng tiền Đều (Annuities)** | Tổng các khoản thanh toán bằng nhau được chiết khấu về hiện tại, trong đó mỗi dòng tiền bị chiết khấu thêm một hệ số tạo thành chuỗi cấp số nhân[cite: 1]. |

## Cấu trúc dự kiến (Tệp LaTeX)

Tệp `mathematical_proofs.tex` được thiết kế theo cấu trúc học thuật như sau:
0. Nhập môn và thiết lập hệ tư tưởng toán học[cite: 1].
1. Chương 1: Cơ sở Giải tích của Chuỗi Hình học trong Không gian Tài chính - Khám phá tiền tệ dưới dạng hàm phụ thuộc thời gian và sự hội tụ của chuỗi hình học vô hạn[cite: 1].
2. Chương 2: Động học Lãi kép: Từ Rời rạc đến Trạng thái Liên tục - Trình bày hằng số Euler và giới hạn Bernoulli khi tần suất ghép lãi tiến tới vô cực[cite: 1].
3. Chương 3: Hình thái học của Chuỗi Dòng tiền - Chứng minh toán học cho chuỗi Annuity và cấu trúc khấu hao[cite: 1].
4. Chương 4: Định giá tài sản thông qua chuỗi lùi vô hạn với mô hình tăng trưởng Gordon[cite: 1].

## Phần trọng tâm: Phương trình Fisher và Lạm phát

Đây là khái niệm then chốt nhằm thể hiện khía cạnh "âm" của dòng tiền:
- Lạm phát đóng vai trò như một **cấp số nhân âm**, làm bào mòn sức mua thực sự của đồng tiền[cite: 1].
- Việc tính toán lãi suất thực ($r_{real}$) không phải là một phép trừ tuyến tính đơn thuần, mà là sự triệt tiêu lẫn nhau của hai chuỗi hàm mũ giữa lãi suất danh nghĩa và lạm phát[cite: 1].
- Khái niệm này được chứng minh bằng giải tích trong LaTeX và được lập trình tính toán đối chiếu trong hàm `fisher_real_rate` của Python[cite: 1].

## Nguyên tắc biên soạn và Quy chuẩn

- **Tài liệu lý thuyết**: Sử dụng ngôn ngữ định dạng LaTeX, áp dụng bộ môi trường `\begin{proof}` và `\begin{theorem}` để đảm bảo sự nghiêm ngặt về mặt đại số và giải tích[cite: 1].
- **Mã nguồn thực thi**: Module Python được giữ cực kỳ ngắn gọn và tinh giản, phục vụ mục đích "numerical verification" (đối chiếu bằng số học) so với kết quả giải tích[cite: 1].
- **Cấu trúc thư mục**: Tuân thủ tiêu chuẩn công nghiệp với các thư mục phân tách rõ ràng như `docs/`, `src/`, `tests/` và `notebooks/`[cite: 1].

## Hướng dẫn đóng góp

Cộng đồng dự án luôn hoan nghênh mọi nỗ lực hợp tác, đặc biệt là việc mở rộng các chứng minh giải tích và đại số trong tệp LaTeX[cite: 1].
1. **Fork** toàn bộ kho lưu trữ về không gian làm việc cá nhân của bạn[cite: 1].
2. Triển khai các công thức mới và đảm bảo tuân thủ tiêu chuẩn định dạng **LaTeX** học thuật[cite: 1].
3. **Commit** thay đổi kèm thông điệp rõ ràng và **Push** lên nhánh từ xa[cite: 1].
4. Đệ trình một **Pull Request** lên nhánh `main` để đội ngũ bảo trì rà soát nội dung[cite: 1].

## Giấy phép

Dự án này được gắn kèm tệp `LICENSE` mã nguồn mở, cho phép cộng đồng tự do ứng dụng, nghiên cứu hệ thống công thức toán học và đóng góp cải tiến các thuật toán tài chính[cite: 1].

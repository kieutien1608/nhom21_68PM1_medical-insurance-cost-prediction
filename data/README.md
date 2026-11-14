# Dữ liệu: US Medical Insurance Cost

## Nguồn
- Kaggle: Medical Cost Personal Datasets (tác giả đăng: Miri Choi)
  https://www.kaggle.com/datasets/mirichoi0218/insurance
- Gốc của bộ dữ liệu: Brett Lantz, "Machine Learning with R", Packt Publishing.
- Ngày tải về: 14/11/2026
- File: `insurance.csv` (1338 dòng, 7 cột)

## Mô tả các cột

| Cột | Kiểu | Ý nghĩa |
|---|---|---|
| `age` | số nguyên | Tuổi của người được bảo hiểm chính |
| `sex` | phân loại | Giới tính: `female`, `male` |
| `bmi` | số thực | Chỉ số khối cơ thể (kg/m²) |
| `children` | số nguyên | Số con / người phụ thuộc được bảo hiểm chi trả |
| `smoker` | phân loại | Có hút thuốc hay không: `yes`, `no` |
| `region` | phân loại | Khu vực cư trú tại Mỹ: `northeast`, `northwest`, `southeast`, `southwest` |
| `charges` | số thực | Chi phí y tế cá nhân do bảo hiểm thanh toán (USD) - **biến mục tiêu (y)** |

## Biến độc lập và biến mục tiêu
- X: `age`, `sex`, `bmi`, `children`, `smoker`, `region`
- y: `charges`

## Ghi chú
- Theo tác giả gốc, dữ liệu được xây dựng dựa trên thống kê nhân khẩu học của Mỹ; cần kiểm tra lại mô tả này trên trang Kaggle khi trích dẫn.
- Giấy phép sử dụng: xem mục License trên trang Kaggle ở trên.
- Không chỉnh sửa file gốc. Mọi bước làm sạch và xử lý được thực hiện trong notebook `01_EDA_Preprocessing.ipynb`.


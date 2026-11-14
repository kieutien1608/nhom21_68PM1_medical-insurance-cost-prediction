# Dữ liệu: US Medical Insurance Cost

## Nguồn
- Nguồn tải trực tiếp: https://github.com/stedy/Machine-Learning-with-R-datasets/blob/master/insurance.csv
- Theo đối chiếu của nhóm, file giống bộ Kaggle: Medical Cost Personal Datasets (tác giả đăng: Miri Choi)
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
| `charges` | số thực | Chi phí y tế cá nhân được tính bởi bảo hiểm (USD) - **biến mục tiêu (y)** |

## Biến độc lập và biến mục tiêu
- X: `age`, `sex`, `bmi`, `children`, `smoker`, `region`
- y: `charges`

## Ghi chú
- Thời gian và phương pháp thu thập dữ liệu chưa được xác minh đầy đủ.
- Giấy phép sử dụng: xem mục License trên trang Kaggle ở trên.
- Không chỉnh sửa file gốc. Notebook `01_EDA_Preprocessing.ipynb` dự kiến dùng để phân tích và xử lý dữ liệu; hiện chưa có nội dung.


# Dự đoán chi phí bảo hiểm y tế cá nhân

**Medical Insurance Cost Prediction** là đề tài bài tập lớn môn Học máy, sử dụng bài toán hồi quy để dự đoán biến `charges` từ các đặc điểm nhân khẩu học và sức khỏe trong bộ dữ liệu Medical Cost Personal Datasets.

> **Trạng thái:** Dự án đang trong giai đoạn chuẩn bị. Dữ liệu đã có trong repository; các notebook phân tích, huấn luyện và tệp dự đoán hiện chưa có nội dung. Chưa có mô hình đã huấn luyện hoặc kết quả đánh giá để báo cáo.

## Mục tiêu nghiên cứu

- Khảo sát dữ liệu và mối quan hệ giữa các đặc trưng với chi phí y tế cá nhân.
- Xây dựng và so sánh các mô hình hồi quy để dự đoán `charges`.
- Đánh giá sai số trên dữ liệu chưa được dùng để huấn luyện và thảo luận về giới hạn của kết quả.

Đây là định hướng thực hiện, không phải kết quả đã đạt được. Dự án phục vụ học tập, không dùng để đưa ra quyết định bảo hiểm hoặc y tế.

## Dữ liệu

File [data/insurance.csv](data/insurance.csv) gồm **1.338 bản ghi và 7 cột**. Sáu cột đầu là đặc trưng đầu vào; `charges` là biến mục tiêu liên tục.

| Cột | Ý nghĩa | Vai trò |
| --- | --- | --- |
| `age` | Tuổi của người được bảo hiểm chính | Đầu vào |
| `sex` | Giới tính: `female`, `male` | Đầu vào |
| `bmi` | Chỉ số khối cơ thể (kg/m²) | Đầu vào |
| `children` | Số con hoặc người phụ thuộc được bảo hiểm | Đầu vào |
| `smoker` | Tình trạng hút thuốc: `yes`, `no` | Đầu vào |
| `region` | Khu vực cư trú tại Mỹ: `northeast`, `northwest`, `southeast`, `southwest` | Đầu vào |
| `charges` | Chi phí y tế cá nhân được tính bởi bảo hiểm, đơn vị USD | Mục tiêu |

Dữ liệu được tải từ [kho GitHub Machine Learning with R datasets](https://github.com/stedy/Machine-Learning-with-R-datasets/blob/master/insurance.csv). Theo đối chiếu của nhóm, file giống với bộ [Medical Cost Personal Datasets trên Kaggle](https://www.kaggle.com/datasets/mirichoi0218/insurance). Xem [mô tả dữ liệu](data/README.md) để biết thêm thông tin nguồn và ngày tải.

## Cấu trúc dự án

```text
.
├── 01_Report/                  # Dự kiến lưu báo cáo
├── 02_Slide/                   # Dự kiến lưu slide
├── 03_SourceCode/
│   ├── notebooks/
│   │   ├── 01_EDA_Preprocessing.ipynb
│   │   └── 02_Modeling_Evaluation.ipynb
│   ├── predict.py              # Chưa triển khai
│   ├── requirements.txt
│   └── README.md
├── 04_Video_Demo/              # Dự kiến lưu video minh họa
└── data/
    ├── insurance.csv
    └── README.md
```

Các thư mục rỗng có thể không xuất hiện trên GitHub vì Git chỉ theo dõi tệp.

## Cài đặt và sử dụng

Cần có Python 3, `pip` và Git. Sau khi tải repository về và mở terminal tại thư mục gốc dự án:

```bash
# Tạo và kích hoạt môi trường ảo (Linux/macOS)
python3 -m venv .venv
source .venv/bin/activate

# Cài các thư viện
python -m pip install -r 03_SourceCode/requirements.txt

# Mở Jupyter Notebook
jupyter notebook
```

Trên Windows PowerShell, thay lệnh kích hoạt bằng `.\.venv\Scripts\Activate.ps1`. Trong Jupyter, mở các notebook ở `03_SourceCode/notebooks/` theo thứ tự `01`, `02`. **Hiện cả hai notebook đều trống**, vì vậy chưa có phân tích hoặc quy trình huấn luyện để chạy. File `03_SourceCode/predict.py` cũng đang trống và chưa hỗ trợ dự đoán.

Các thư viện trong `requirements.txt` chưa được ghim phiên bản; môi trường cài đặt tại những thời điểm khác nhau có thể cho kết quả khác nhau. Khi thực nghiệm được triển khai, cần ghi lại phiên bản Python, thư viện và cấu hình chạy để có thể tái lập.

## Phương pháp dự kiến

1. Kiểm tra kiểu dữ liệu, giá trị thiếu, bản ghi trùng lặp và phân phối của các biến.
2. Chia tập huấn luyện và kiểm thử trước khi học các bước tiền xử lý; thực hiện mã hóa biến phân loại trong pipeline để hạn chế rò rỉ dữ liệu.
3. Huấn luyện một mô hình cơ sở, sau đó so sánh với các mô hình hồi quy phù hợp. Dùng kiểm định chéo trên tập huấn luyện khi lựa chọn mô hình hoặc siêu tham số.
4. Đánh giá mô hình cuối cùng trên tập kiểm thử bằng MAE, RMSE và R²; trình bày cách chia dữ liệu, hạt giống ngẫu nhiên và kết quả thực nghiệm.
5. Phân tích sai số và giới hạn của mô hình trước khi rút ra kết luận.

Đây là kế hoạch đề xuất và có thể điều chỉnh khi thực hiện. Không dùng tập kiểm thử để lựa chọn mô hình hoặc điều chỉnh siêu tham số.

## Giới hạn

Bộ dữ liệu có kích thước nhỏ và thông tin về thời gian, phương pháp thu thập chưa đầy đủ. Kết quả trên bộ dữ liệu này không tự động đại diện cho chi phí bảo hiểm hiện nay hoặc cho Việt Nam. Cần phân biệt chi phí y tế trong dữ liệu với phí bảo hiểm, số tiền cá nhân tự chi trả và khoản bồi thường; không xem chúng là cùng một đại lượng.

## Trích dẫn dữ liệu

Khi sử dụng bộ dữ liệu trong báo cáo, hãy ghi rõ nguồn, địa chỉ và ngày truy cập; kiểm tra giấy phép trên trang nguồn trước khi tái sử dụng hoặc phân phối. Thông tin chi tiết được lưu tại [data/README.md](data/README.md).

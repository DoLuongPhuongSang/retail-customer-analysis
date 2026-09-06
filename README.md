# 🛒 Phân Tích Dữ Liệu Bán Lẻ, Phân Khúc Khách Hàng & Dự Đoán Nguy Cơ Rời Bỏ

## 📌 Giới thiệu

Dự án thực hiện phân tích dữ liệu bán lẻ nhằm khám phá hành vi mua hàng, phân khúc khách hàng, xác định khách hàng có nguy cơ rời bỏ và dự báo doanh số trong tương lai.

Bộ dữ liệu gồm các thông tin về khách hàng, giao dịch, sản phẩm, danh mục sản phẩm, giá trị đơn hàng, phương thức thanh toán, trạng thái đơn hàng, đánh giá và các thông tin liên quan.

Quy trình thực hiện bao gồm tiền xử lý dữ liệu, phân tích khám phá dữ liệu (EDA), phân tích RFM, phân khúc khách hàng bằng K-Means, lựa chọn đặc trưng, xây dựng mô hình dự đoán nguy cơ rời bỏ và xây dựng các mô hình dự báo doanh số.

## 🎯 Mục tiêu

- Làm sạch và tiền xử lý dữ liệu bán lẻ.
- Khám phá và trực quan hóa hành vi mua hàng của khách hàng.
- Phân tích các đặc điểm và xu hướng trong dữ liệu.
- Phân tích khách hàng dựa trên mô hình **RFM (Recency, Frequency, Monetary)**.
- Phân khúc khách hàng bằng thuật toán **K-Means Clustering**.
- Lựa chọn các thuộc tính phù hợp cho quá trình xây dựng mô hình.
- Xác định nhóm khách hàng có nguy cơ rời bỏ cao.
- Xây dựng và đánh giá các mô hình dự đoán nguy cơ khách hàng rời bỏ.
- Xây dựng mô hình dự báo doanh số.
- Đưa ra các nhận xét hỗ trợ việc phân tích và giữ chân khách hàng.

## 📊 Dữ liệu

Bộ dữ liệu bán lẻ gồm **302.010 giao dịch** với **30 thuộc tính**.

Một số nhóm thông tin chính:

- Thông tin khách hàng
- Thông tin giao dịch và thời gian giao dịch
- Sản phẩm và danh mục sản phẩm
- Phân khúc khách hàng
- Trạng thái đơn hàng
- Giá trị mua hàng
- Phương thức thanh toán
- Phản hồi và đánh giá của khách hàng

## 🔍 Quy trình thực hiện

### 1. Tiền xử lý dữ liệu

- Đọc và kiểm tra dữ liệu.
- Kiểm tra kích thước và cấu trúc dữ liệu.
- Kiểm tra kiểu dữ liệu của các thuộc tính.
- Kiểm tra và xử lý dữ liệu thiếu.
- Kiểm tra các giá trị trùng lặp.
- Xử lý các thuộc tính liên quan đến thời gian.
- Kiểm tra và xử lý các thuộc tính dạng số.
- Xử lý các thuộc tính dạng phân loại.
- Kiểm tra mã khách hàng và thông tin giao dịch.

### 2. Phân tích khám phá dữ liệu (EDA)

Phân tích khám phá dữ liệu được thực hiện để tìm hiểu:

- Phân bố dữ liệu giao dịch.
- Hành vi mua hàng của khách hàng.
- Số lượng và đặc điểm của khách hàng.
- Các danh mục và loại sản phẩm.
- Giá trị và tần suất giao dịch.
- Doanh số theo thời gian.
- Đặc điểm đơn hàng và giao dịch.
- Mối quan hệ giữa các thuộc tính trong dữ liệu.

Các biểu đồ được sử dụng để trực quan hóa và hỗ trợ quá trình phân tích.

### 3. Phân tích RFM

Mô hình **RFM** được sử dụng để đánh giá giá trị và mức độ tương tác của khách hàng dựa trên ba chỉ số:

- **Recency**: số ngày kể từ lần mua hàng gần nhất.
- **Frequency**: số lần khách hàng thực hiện giao dịch.
- **Monetary**: tổng giá trị chi tiêu của khách hàng.

Phân tích RFM giúp xác định đặc điểm và mức độ giá trị của từng nhóm khách hàng.

### 4. Phân khúc khách hàng bằng K-Means

Sau khi xây dựng các đặc trưng RFM, thuật toán **K-Means Clustering** được sử dụng để phân nhóm khách hàng.

Kết quả phân khúc giúp nhận diện các nhóm khách hàng có hành vi khác nhau, bao gồm:

- **Passive Customers**
- **New Customers**
- **High-Value Customers**

Việc phân khúc hỗ trợ quá trình phân tích hành vi và xây dựng các chiến lược chăm sóc khách hàng phù hợp.

### 5. Lựa chọn thuộc tính

Các phương pháp thống kê được sử dụng để đánh giá mức độ liên quan của các thuộc tính đối với bài toán dự đoán. Trong đó, phương pháp **F-test / ANOVA (`f_classif`)** được sử dụng để đánh giá mức độ liên quan giữa các đặc trưng và biến mục tiêu.

### 6. Xác định nguy cơ khách hàng rời bỏ

Nguy cơ khách hàng rời bỏ được xác định dựa trên chỉ số **Recency** và ngưỡng **180 ngày**:

| Giá trị | Ý nghĩa |
| --- | --- |
| `0` | Nguy cơ rời bỏ thấp |
| `1` | Nguy cơ rời bỏ cao |

Quy tắc xác định:

- `Recency <= 180 ngày` → `0`
- `Recency > 180 ngày` → `1`

Những khách hàng không thực hiện giao dịch trong thời gian dài hơn 180 ngày được xem là nhóm có nguy cơ rời bỏ cao.

### 7. Xây dựng mô hình dự đoán Churn

Dự án thử nghiệm nhiều mô hình hồi quy và phân loại để phân tích mối quan hệ giữa các đặc trưng khách hàng và nguy cơ rời bỏ:

- **Linear Regression**: mô hình hồi quy tuyến tính cơ sở.
- **Polynomial Regression**: thử nghiệm các bậc 1, 2, 3 và 4 để mô hình hóa mối quan hệ phi tuyến.
- **Ridge Regression**: giảm ảnh hưởng của đa cộng tuyến và hạn chế overfitting.
- **Logistic Regression**: phân loại khách hàng thành hai nhóm:
  - `0` → Low Risk
  - `1` → High Risk

Các kết quả đánh giá chi tiết được trình bày trong notebook.

### 8. Dự báo doanh số

Dự án thực hiện dự báo doanh số dựa trên dữ liệu giao dịch theo thời gian. Các phương pháp được thử nghiệm gồm:

- Linear Regression
- Polynomial Regression
- Ridge Regression
- ARIMA / SARIMAX

Các mô hình Linear Regression, Polynomial Regression và Ridge Regression được đánh giá bằng các chỉ số như **R²** và **MSE**. Mô hình ARIMA/SARIMAX được sử dụng để dự báo doanh số trong **30 ngày tiếp theo**.

## 📊 Kết quả

Dự án đã thực hiện được các nội dung chính:

- Tiền xử lý và làm sạch dữ liệu bán lẻ.
- Phân tích khám phá dữ liệu.
- Phân tích RFM.
- Phân khúc khách hàng bằng K-Means.
- Xác định nhóm khách hàng có nguy cơ rời bỏ dựa trên Recency.
- Lựa chọn đặc trưng bằng phương pháp thống kê.
- Xây dựng và so sánh nhiều mô hình dự đoán Churn.
- Xây dựng các mô hình dự báo doanh số.
- Dự báo doanh số trong 30 ngày tiếp theo bằng mô hình chuỗi thời gian.

### Kết quả dự đoán Churn

Kết quả trong báo cáo cho thấy Polynomial Regression đạt R² cao hơn khi tăng bậc mô hình. Trong các mô hình Polynomial Regression được thử nghiệm, **Degree 4 đạt R² khoảng 0.90507**.

### Kết quả dự báo doanh số

Các mô hình hồi quy và Ridge Regression được đánh giá bằng R² và MSE. Ngoài ra, mô hình ARIMA/SARIMAX được sử dụng để dự báo doanh số trong 30 ngày tiếp theo. Các bảng kết quả, biểu đồ và đánh giá chi tiết được trình bày trong notebook.

## 🛠️ Công nghệ sử dụng

- **Python**
- **Pandas**, **NumPy**
- **Matplotlib**, **Seaborn**, **Plotly**
- **Scikit-learn**
  - Linear Regression
  - Polynomial Regression
  - Ridge Regression
  - Logistic Regression
  - K-Means Clustering
- **pmdarima**
- **ARIMA / SARIMAX**
- **Jupyter Notebook**

## 📂 Cấu trúc dự án

```text
retail-customer-churn-analysis/
├── retail_analysis.ipynb
├── retail_data.csv
└── README.md
```

## 🚀 Cách chạy dự án

### 1. Clone repository

```bash
git clone https://github.com/DoLuongPhuongSang/retail-customer-analysis.git
cd retail-customer-analysis
```

### 2. Cài đặt thư viện

```bash
pip install pandas numpy matplotlib seaborn plotly scikit-learn pmdarima jupyter
```

### 3. Mở Jupyter Notebook

```bash
jupyter notebook
```

Sau đó mở `retail_analysis.ipynb` và chạy lần lượt các cell trong notebook.

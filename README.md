# 🛒 Retail & E-commerce Customer Analytics

Project Data Analytics/Data Science hoàn chỉnh trên dữ liệu giao dịch bán lẻ/e-commerce thực tế, mô phỏng các kỹ thuật phân tích mà nhiều doanh nghiệp Việt Nam (retail, e-commerce, F&B chuỗi...) áp dụng cho các bài toán khách hàng: phân khúc, giữ chân, gợi ý sản phẩm và dự đoán.

## 📌 Nội dung project

| # | Phần | Kỹ thuật |
|---|---|---|
| 1 | Thu thập & làm sạch dữ liệu | Data cleaning, xử lý missing values, loại đơn hủy |
| 2 | EDA & trực quan hóa | Xu hướng doanh thu, top sản phẩm/thị trường, hành vi theo thời gian |
| 3 | Feature Engineering | RFM (Recency – Frequency – Monetary) |
| 4 | Phân khúc khách hàng | KMeans Clustering + PCA visualization |
| 5 | Cohort Analysis | Retention heatmap theo tháng |
| 6 | Market Basket Analysis | Apriori / Association Rules |
| 7 | Churn Prediction | Logistic Regression, Random Forest, Gradient Boosting, XGBoost (time-based split, không leakage) |
| 8 | CLV Prediction | Linear Regression, Random Forest, Gradient Boosting, XGBoost |
| 9 | Lưu trữ | Model (.pkl), dữ liệu đã xử lý (.csv), biểu đồ (.png/.html) |
| 10 | Dashboard | Dashboard tương tác bằng Plotly + ipywidgets |

## 📂 Dataset

**[Online Retail Dataset – UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/352/online+retail)**

Dữ liệu giao dịch thực tế (~540,000 dòng) của một doanh nghiệp bán lẻ online tại Anh, giai đoạn 12/2010 – 12/2011. Gồm các cột: `InvoiceNo`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`, `UnitPrice`, `CustomerID`, `Country`.

Notebook **tự động tải dataset trực tiếp** khi chạy — không cần upload file tay. Nếu server UCI không truy cập được (mạng, bảo trì...), notebook tự chuyển sang một bộ dữ liệu mô phỏng cùng cấu trúc cột để toàn bộ pipeline vẫn chạy được (có thông báo rõ ràng khi việc này xảy ra).

## 🚀 Cách chạy trên Google Colab

1. Upload file `Retail_Customer_Analytics.ipynb` lên [Google Colab](https://colab.research.google.com/) (File → Upload notebook), hoặc mở trực tiếp từ GitHub bằng menu File → Open notebook → GitHub và dán link repo.
2. Chọn **Runtime → Run all**. Notebook sẽ tự cài thư viện cần thiết (`mlxtend`, `xgboost`, `openpyxl`, `ipywidgets`) và tự tải dữ liệu.
3. Toàn bộ kết quả (model, dữ liệu đã xử lý, biểu đồ) được lưu trong thư mục `outputs/` ngay trong phiên Colab.

> 💡 Muốn lưu kết quả lâu dài: mount Google Drive (`from google.colab import drive; drive.mount('/content/drive')`) và đổi đường dẫn `outputs/` sang thư mục trong Drive.

## 🛠️ Công nghệ sử dụng

`Python` · `pandas` · `numpy` · `scikit-learn` · `XGBoost` · `mlxtend` · `matplotlib` · `seaborn` · `Plotly` · `ipywidgets` · `joblib`

## 📁 Cấu trúc output sau khi chạy

```
outputs/
├── data/       # clean_transactions.csv, rfm_customer_segments.csv, cohort_retention.csv, association_rules.csv, model comparison tables
├── models/     # kmeans_customer_segments.pkl, best_churn_model.pkl, best_clv_model.pkl, scalers
└── figures/    # các biểu đồ .png (matplotlib) và .html (plotly, tương tác)
```

## 📈 Insight kinh doanh chính

- **RFM & Customer Segmentation** giúp phân loại khách hàng theo giá trị để cá nhân hóa marketing/CSKH.
- **Cohort Analysis** đo lường tỷ lệ giữ chân khách hàng theo từng "lứa", phát hiện tháng có retention yếu.
- **Market Basket Analysis** gợi ý sản phẩm bán kèm, hỗ trợ tăng AOV (giá trị đơn hàng trung bình).
- **Churn Prediction** giúp can thiệp sớm (voucher, remarketing) với khách hàng có nguy cơ rời bỏ.
- **CLV Prediction** giúp ưu tiên nguồn lực cho nhóm khách hàng giá trị cao.

## 🔮 Hướng mở rộng

- Bổ sung dữ liệu chi phí marketing để tính CAC, ROAS.
- Time-series forecasting doanh thu dài hạn (Prophet/ARIMA).
- Đóng gói model churn thành API (FastAPI) để tích hợp CRM thực tế.
- A/B testing các chiến dịch retention theo phân khúc RFM.

---

*Project phục vụ mục đích học tập & portfolio Data Analytics. Dataset: Chen, D. (2015), UCI Machine Learning Repository.*

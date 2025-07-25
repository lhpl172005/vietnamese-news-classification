# Phân loại Tin tức Tiếng Việt (Vietnamese News Classification)

## Mô tả
Dự án này xây dựng một mô hình Machine Learning có khả năng tự động phân loại các bài báo tiếng Việt vào các thể loại tương ứng như Thể thao, Công nghệ, Giáo dục, v.v.

## Vấn đề & Mục tiêu
- **Vấn đề:** Phân loại tin tức thủ công tốn nhiều thời gian và không hiệu quả.
- **Mục tiêu:** Xây dựng một mô hình có khả năng tự động hóa quy trình này với độ chính xác có thể đo lường được.

## Hướng dẫn Cài đặt & Chạy dự án
1.  Clone repository này về máy: `git clone [URL_CUA_BAN]`
2.  Tạo và kích hoạt môi trường ảo:
    ```bash
    python -m venv venv
    .\venv\Scripts\activate
    ```
3.  Cài đặt các thư viện cần thiết:
    ```bash
    pip install -r requirements.txt
    ```
4.  Tải dữ liệu từ [Link tới Kaggle hoặc nguồn dữ liệu] và đặt vào thư mục `data/`.
5.  Mở và chạy file notebook trong thư mục `notebooks/`.

## Dữ liệu (Data)

Do giới hạn về kích thước, file dữ liệu không được bao gồm trong repository này. Bạn có thể tải bộ dữ liệu được sử dụng trong dự án tại đây:

* **Nguồn:** Kaggle
* **Link tải:** [Vietnamese News Dataset](https://www.kaggle.com/datasets/sarahhimeko/vietnamese-online-news-csv-dataset)

**Hướng dẫn:** Tải file Fixed_news_dataset.csv về sau đó lưu trong folder dự án.

## Quy trình Thực hiện
1.  **Thu thập & Khám phá Dữ liệu:** Sử dụng bộ dữ liệu tin tức từ...
2.  **Tiền xử lý:** Làm sạch văn bản, chuẩn hóa Unicode, tách từ tiếng Việt bằng `pyvi`.
3.  **Biểu diễn Dữ liệu:** Sử dụng TF-IDF để chuyển văn bản thành vector số.
4.  **Huấn luyện Mô hình:** Thử nghiệm với mô hình Naive Bayes.
5.  **Đánh giá:** Đo lường hiệu suất bằng Accuracy, Precision, Recall, F1-score.

## Kết quả & Phân tích
Với mô hình Naive Bayes ban đầu, độ chính xác tổng thể đạt **64.75%**.

<img width="715" height="615" alt="image" src="https://github.com/user-attachments/assets/6404e38c-60e8-4149-91a3-5c839e92aab9" />


**Phân tích:**
- Mô hình hoạt động tốt với các lớp có dữ liệu dồi dào và đặc trưng như `Thể thao`, `Thế giới`.
- Mô hình còn yếu ở các lớp có ít dữ liệu hoặc nội dung chồng chéo như `Công nghệ`, `Bạn đọc`.
- **Nguyên nhân chính:** Dữ liệu mất cân bằng nghiêm trọng.

**Hướng cải thiện:**
- Áp dụng kỹ thuật Undersampling để cân bằng dữ liệu.
- Thử nghiệm với các mô hình mạnh hơn như Logistic Regression hoặc SVM.

## Công nghệ sử dụng
- Python 3
- Pandas
- Scikit-learn
- Pyvi
- JupyterLab

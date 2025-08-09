# Customer Segmentation with K-Medoids on Olist E-Commerce Data

## Giới thiệu
Dự án này thực hiện **phân khúc khách hàng** dựa trên phương pháp **RFM Analysis** (Recency, Frequency, Monetary) và thuật toán **K-Medoids Clustering**.  
Dataset sử dụng: [Olist Brazilian E-Commerce](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) — chỉ dùng 3 bảng dữ liệu chính.

**Mục tiêu**:
- Hiểu hành vi mua hàng của khách hàng.
- Phân nhóm khách hàng để hỗ trợ chiến lược marketing.
- Tạo nền tảng cho các chiến dịch cá nhân hóa.

---

## Dataset sử dụng
Chỉ dùng 3 file từ dataset gốc:
1. `olist_customers_dataset.csv` — Thông tin khách hàng.
2. `olist_orders_dataset.csv` — Thông tin đơn hàng.
3. `olist_order_items_dataset.csv` — Chi tiết sản phẩm trong đơn hàng.

---

## Quy trình thực hiện
1. **Tiền xử lý dữ liệu**
   - Kết hợp 3 bảng theo `customer_id` và `order_id`.
   - Lọc đơn hàng đã giao thành công.
   - Chuyển đổi cột thời gian sang dạng `datetime`.

2. **Tính toán RFM**
   - **Recency**: Số ngày từ lần mua gần nhất đến ngày phân tích.
   - **Frequency**: Số đơn hàng đã mua.
   - **Monetary**: Tổng giá trị mua hàng (`price`).

3. **Chuẩn hóa dữ liệu**
   - Min-Max Scaling để đưa các giá trị về cùng thang đo.

4. **Clustering**
   - Xác định số cụm tối ưu bằng Silhouette Score.
   - Huấn luyện K-Medoids từ `scikit-learn-extra`.

5. **Phân tích kết quả**
   - Gán nhãn cụm cho khách hàng.
   - Trực quan hóa bằng biểu đồ.

---

## Cài đặt môi trường
Yêu cầu Python 3.8+

Cài đặt các thư viện cần thiết:
```bash
pip install -r requirements.txt

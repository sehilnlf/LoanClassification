# ProjectAppliedStatistics

## Feature Scaling
https://ndquy.github.io/posts/cac-phuong-phap-scaling/

(feature reduction ->) handling missing value -> Categorical variable handling -> remove outlier  -> scaling

Các điểm dữ liệu đôi khi được đo đạc với những đơn vị khác nhau, m và feet chẳng hạn. Hoặc có hai thành phần (của vector dữ liệu) chênh lệch nhau quá lớn, một thành phần có khoảng giá trị từ 0 đến 1000, thành phần kia chỉ có khoảng giá trị từ 0 đến 1 chẳng hạn. Lúc này, chúng ta cần chuẩn hóa dữ liệu trước khi thực hiện các bước tiếp theo.

Vì các trọng số nhỏ của mô hình nhỏ và được cập nhật dựa vào lỗi dự đoán nên việc scale giá trị của đầu vào X và đầu ra Y của tập dữ liệu huấn luyện là một yếu tố quan trọng. Nếu đầu vào không được scaling có thể dẫn đến quá trình huấn luyện không ổn định

Có 2 cách để scale dữ liệu đó là normalization và standardization
### Data Normalization: 
- change all units and magnitudes to only one range to avoid bias to any features.
- Min-max scaling formulas of Min Max Scaling: x_normalized = (x - min(x)) / (max(x) - min(x) ->scale data to a fixed range, between 0 and 1
- Các bước như sau:
 + Fit biến scaler sử dụng tập dữ liệu huấn luyện. Để normalize thì dữ liệu huấn luyện cần phải được xác định giá trị max và min. Để thực hiện chúng ta gọi hàm fit().
 + Tiến hành scale dữ liệu bằng cách gọi hàm transform().
(đảo ngược miền giá trị sau khi scale về miền giá trị gốc giúp thuận tiện cho việc báo cáo hay vẽ biểu đồ, bạn có thể gọi hàm inverse_transform)
	
input data type: dataframe
### Data Standardization: 
Chuẩn hóa dữ liệu là việc scale dữ liệu về một phân bố trong đó giá trị trung bình của các quan sát bằng 0 và độ lệch chuẩn = 1. Kỹ thuật này còn được gọi là “whitening.”. Nhờ việc chuẩn hóa, các thuật toán như linear regression, logistic regression được cải thiện.

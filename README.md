# Stock Price Prediction using Deep Learning

-Dự Đoán Giá Trị Tương Lai Của Cổ Phiếu Bằng Các Phương Pháp Học Sâu
-File .ipynb là nội dung của project

## Giới thiệu

Dự đoán giá cổ phiếu là một bài toán khó và phức tạp do thị trường tài chính biến động mạnh và chịu tác động của nhiều yếu tố. Trong project này, nhóm tập trung vào việc **dự đoán giá đóng cửa ngày tiếp theo của chỉ số S&P 500** dựa trên dữ liệu 14 ngày trước đó bằng các mô hình học sâu (Deep Learning).

## Dữ liệu

* Nguồn dữ liệu: **Yahoo Finance API**
* Thời gian: từ **01/01/2000 đến 30/11/2024**
* Dữ liệu bao gồm: giá mở cửa, đóng cửa, cao nhất, thấp nhất và khối lượng giao dịch.
* Dữ liệu được tiền xử lý: loại bỏ giá trị rỗng, chuẩn hóa về [0,1], chia thành tập Train (70%), Validation (15%), Test (15%).

## Mô hình sử dụng

Nhóm đã xây dựng và huấn luyện **6 mô hình mạng nơ-ron** khác nhau:

1. **FC1** – Fully Connected (Dense 14)
2. **FC2** – Fully Connected (Dense 14 → Dense 7)
3. **RNN1** – RNN (4 units)
4. **RNN2** – RNN (6 units)
5. **LSTM1** – LSTM (6 units)
6. **Conv1** – Conv1D (4 filters, kernel size 3)

Các mô hình được huấn luyện với 3 thuật toán tối ưu: **SGD**, **RMSprop**, **Adam**.

## Kết quả

* Mô hình tốt nhất: **RNN2 + RMSprop**
* Sai số MAE:

  * Validation: **0.0144**
  * Test: **0.0223**
* Dự đoán của mô hình gần khớp với dữ liệu thực tế của S&P 500.

## Kết luận

* Học sâu cho thấy tiềm năng lớn trong dự đoán chuỗi thời gian tài chính.
* Mô hình RNN đơn giản (6 units) với optimizer RMSprop đạt hiệu quả cao nhất trong nghiên cứu.
* Nghiên cứu này có thể là nền tảng để phát triển các hệ thống hỗ trợ giao dịch chứng khoán tự động trong tương lai.

## Công nghệ sử dụng

* Python, TensorFlow/Keras
* Yahoo Finance API
* NumPy, Pandas, Matplotlib

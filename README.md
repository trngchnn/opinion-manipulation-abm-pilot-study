# Modeling Opinion Manipulation on Anonymous Social Networks: A Pilot Study via Spatial Markov Chains and Agent-Based Simulation - Mô hình hóa sự thao túng dư luận trên mạng xã hội ẩn danh: Nghiên cứu tiền khả thi qua Chuỗi Markov và Mô phỏng đa tác tử

## 1. Thông tin chung
- Bối cảnh dự án: Kho lưu trữ thử nghiệm tiền khả thi (Pilot Study) nhằm phục vụ công tác chuẩn bị đề xuất Đề tài Nghiên cứu Khoa học Sinh viên, Trường Đại học Sài Gòn.
- Thời gian triển khai: Tháng 5/2026.
- Hình thức thực hiện: Nhóm sinh viên nghiên cứu (02 thành viên).
- Mục tiêu kho lưu trữ: Sử dụng các tập dữ liệu công khai làm dữ liệu ủy quyền (Proxy Data) để kiểm chứng tính khả thi của chuỗi thuật toán toán học và thiết lập các tham số hành vi nền tảng trước khi tiến hành thu thập vi dữ liệu chính thức.

## 2. Nguồn dữ liệu thử nghiệm (Proxy Data)
Dự án sử dụng các tập dữ liệu giao tiếp mạng xã hội và diễn đàn tài chính để giả lập không gian thông tin biến động mạnh.
- Đường dẫn Dataset: [Chèn đường dẫn Dataset Kaggle tại đây]

## 3. Cấu trúc Quy trình Mô phỏng (Research Pipeline)
Do giới hạn về việc phê duyệt API hệ thống trong giai đoạn khởi tạo, quy trình thử nghiệm được chia nhỏ thành 3 mô-đun độc lập để tối ưu hóa và kiểm chứng hiệu năng toán tử:

### Giai đoạn 1: Định lượng Quy luật Hành vi Vi mô (Micro-level Extraction)
- Tệp tin: `Markov_Chain_Sentiments.ipynb`
- Dataset: [https://www.kaggle.com/code/danofer/reddit-comments-scores-nlp/notebook]
- Nội dung: Sử dụng tập dữ liệu tương tác để chấm điểm cảm xúc liên tục, phân tách luồng thảo luận thành 3 trạng thái rời rạc: Tiêu cực (-1), Trung lập (0) và Tích cực (1). Hệ thống xây dựng Ma trận xác suất chuyển trạng thái Markov 3x3 để đo lường tỷ lệ dịch chuyển quan điểm của cá nhân khi tiếp xúc với ý kiến định hướng. Kết quả ma trận đóng vai trò là "bộ gen tâm lý" đầu vào cho toàn bộ mô hình mô phỏng.

### Giai đoạn 2: Đo lường Động lực Hệ thống Vĩ mô (Macro-level Benchmarking)
- Tệp tin: `Macro_Entropy_Analysis.ipynb`
- Dataset: [https://www.kaggle.com/code/thomaskonstantin/reddit-wallstreetbets-posts-sentiment-analysis/input]
- Nội dung: Thuật toán tiến hành đo lường sự biến thiên của chỉ số Shannon Entropy vĩ mô theo trục thời gian, trực quan hóa đường gãy cấu trúc và điểm sụp đổ của sự đa dạng ý kiến khi hệ thống đối mặt với các cú sốc thông tin từ đám đông.

### Giai đoạn 3: Giả lập và Thử nghiệm Đối chứng (System Simulation)
- Tệp tin: `Agent_Based_Simulation.ipynb`
- Nội dung: Tích hợp các tham số toán học rút ra từ Giai đoạn 1 và 2 để thiết lập cấu trúc mô phỏng đa tác tử (Agent-Based Modeling - ABM). Thông qua phương pháp mô phỏng Monte Carlo, hệ thống tiến hành thử nghiệm tăng dần tỷ lệ các tác tử thao túng phối hợp (Coordinated Inauthentic Behavior - CIB) nhằm xác định điểm chuyển pha (Tipping Point) của mạng lưới.

## 4. Công cụ và Thư viện triển khai
- Ngôn ngữ lập trình: Python.
- Xử lý cấu trúc dữ liệu: Pandas, NumPy.
- Phân tích ngôn ngữ tự nhiên: VADER Sentiment Analysis.
- Trực quan hóa đồ họa khoa học: Matplotlib, Seaborn.
- Môi trường giả lập: Kiến trúc mô phỏng đa tác tử thuật toán (Algorithmic ABM Simulation).

## 5. Ý nghĩa của Giai đoạn Thử nghiệm
- Chứng minh tính khả thi toán học: Kết quả thực nghiệm thành công khẳng định chuỗi thuật toán phối hợp giữa Chuỗi Markov, Shannon Entropy và ABM hoạt động đồng bộ, chính xác và có tính nhất quán cao.
- Tối ưu hóa nguồn lực: Giai đoạn thử nghiệm giúp định vị trước các rủi ro kỹ thuật, làm sạch và chuẩn hóa schema dữ liệu, tạo bước đệm vững chắc để tăng tốc xử lý khi tiếp cận bộ vi dữ liệu lớn trong giai đoạn nghiên cứu chính quy.

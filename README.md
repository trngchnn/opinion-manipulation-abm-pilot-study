# Modeling Opinion Manipulation on Anonymous Social Networks: A Pilot Study via Spatial Markov Chains and Agent-Based Simulation

## 1. Thông tin chung
* **Đề tài nghiên cứu dự kiến:** Mô hình hóa sự thao túng dư luận trên mạng xã hội ẩn danh bằng Vật lý thống kê và Mô phỏng đa tác tử (ABM).
* **Bối cảnh dự án:** Kho lưu trữ thử nghiệm tiền khả thi nhằm phục vụ công tác chuẩn bị đề xuất đề tài Nghiên cứu Khoa học Sinh viên - Trường Đại học Sài Gòn.
* **Thời gian triển khai:** Năm 2026
* **Hình thức thực hiện:** Nhóm Sinh viên nghiên cứu (02 thành viên).
* **Mục tiêu kho lưu trữ:** Sử dụng các tập dữ liệu công khai từ Kaggle làm dữ liệu ủy quyền (Proxy Data) để kiểm chứng tính khả thi của thuật toán, thiết lập các tham số hành vi nền tảng trước khi tiến hành thu thập vi dữ liệu chính thức cho công trình nghiên cứu chính quy.

## 2. Cấu trúc Quy trình Mô phỏng Tiền khả thi (Research Pipeline)
Do giới hạn về việc phê duyệt API hệ thống trong giai đoạn chuẩn bị, nhóm đã chủ động chia nhỏ quy trình thử nghiệm thành 3 mô-đun độc lập để tối ưu hóa và kiểm chứng hiệu năng toán tử:

### Giai đoạn 1: Định lượng Quy luật Hành vi Vi mô (Micro-level Extraction)
* **Tệp tin mã nguồn:** `Pilot_Phase_1_Markov_Chain_Sentiments.ipynb`
* **Nội dung thực nghiệm:** Sử dụng tập dữ liệu tương tác để chấm điểm cảm xúc liên tục, phân tách luồng thảo luận thành 3 trạng thái rời rạc: Tiêu cực (-1), Trung lập (0), và Tích cực (1). Từ đó, xây dựng **Ma trận xác suất chuyển trạng thái Markov 3x3** để đo lường tỷ lệ dịch chuyển quan điểm của cá nhân khi tiếp xúc với ý kiến định hướng. Kết quả ma trận này đóng vai trò là "bộ gen tâm lý" đầu vào cho mô hình mô phỏng.

### Giai đoạn 2: Đo lường Động lực Hệ thống Vĩ mô (Macro-level Benchmarking)
* **Tệp tin mã nguồn:** `Pilot_Phase_2_Macro_Entropy_Analysis.ipynb`
* **Nội dung thực nghiệm:** Khai thác tập dữ liệu diễn đàn tài chính `r/wallstreetbets` trên Kaggle để làm mẫu đại diện cho một mạng lưới biến động mạnh. Thuật toán tiến hành đo lường biến thiên của **Shannon Entropy vĩ mô** theo trục thời gian, trực quan hóa đường gãy gập cấu trúc và điểm sụp đổ của sự đa dạng ý kiến khi hệ thống đối mặt với các cú sốc thông tin đám đông.

### Giai đoạn 3: Giả lập và Thử nghiệm Đối chứng (System Simulation)
* **Tệp tin mã nguồn:** `Pilot_Phase_3_Agent_Based_Simulation.ipynb`
* **Nội dung thực nghiệm:** Tích hợp các tham số toán học rút ra từ Giai đoạn 1 và Giai đoạn 2 để thiết lập mô hình mô phỏng đa tác tử (Agent-Based Modeling - ABM). Bằng phương pháp mô phỏng Monte Carlo, hệ thống tiến hành thử nghiệm tăng dần tỷ lệ các tác tử thao túng phối hợp (CIB) nhằm xác định điểm gãy chuyển pha (Tipping Point) của toàn bộ mạng lưới ảo.

## 3. Công cụ và Thư viện triển khai
* **Ngôn ngữ lập trình:** Python
* **Xử lý cấu trúc dữ liệu:** pandas, numpy
* **Thuật toán phân tích cảm xúc:** VADER Sentiment Analysis
* **Trực quan hóa đồ họa khoa học:** matplotlib, seaborn
* **Môi trường giả lập:** Kiến trúc mô phỏng đa tác tử thuật toán (Algorithmic ABM Simulation)

## 4. Ý nghĩa của Giai đoạn Thử nghiệm
* **Chứng minh tính khả thi toán học:** Kết quả chạy thực nghiệm thành công trên hai bộ dữ liệu mẫu từ Kaggle khẳng định chuỗi thuật toán phối hợp giữa Chuỗi Markov, Shannon Entropy và Mô phỏng đa tác tử (ABM) hoạt động chính xác, đồng bộ và có tính nhất quán cao.
* **Tối ưu hóa nguồn lực:** Giai đoạn thử nghiệm giúp nhóm định vị trước các rủi ro kỹ thuật, làm sạch và chuẩn hóa khung tài liệu schema dữ liệu, sẵn sàng tăng tốc xử lý khi tiếp cận bộ vi dữ liệu lớn chính thức trong giai đoạn nghiên cứu chính quy sắp tới.

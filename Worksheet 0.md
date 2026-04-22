
### 1. Kỹ năng nhóm tự tin nhất
*   **AI Engineering**: Xây dựng kiến trúc RAG (Retrieval-Augmented Generation) để tra cứu tài liệu.
*   **Prompt Engineering**: Thiết kế prompt có cấu trúc để trích xuất thông tin từ các SOP (Standard Operating Procedure) phức tạp.
*   **Data Processing**: Xử lý và chuẩn hóa các file PDF/Docx quy định nội bộ nghìn trang.

### 2. Mô tả sản phẩm (Scenario)
*   **Tên dự án**: Bank Operations Copilot.
*   **Mô tả**: AI Assistant giúp nhân viên ngân hàng tra cứu nhanh quy định nội bộ, quy trình KYC, và các bước thẩm định tín dụng. Hệ thống giúp giảm thời gian tra cứu thủ công và hạn chế sai sót do không cập nhật quy định mới.

### 3. Câu hỏi nhóm phải trả lời
**Sản phẩm này giải quyết bài toán gì?** 
- Sản phẩm giải quyết trực tiếp khó khăn về năng suất và rủi ro pháp lý trong vận hành ngân hàng. Cụ thể:
	- **Quá tải thông tin:** Xóa bỏ tình trạng nhân viên phải tra cứu thủ công qua hàng nghìn trang tài liệu SOP, chính sách tín dụng và KYC vốn được cập nhật liên tục.
	- **Kiểm soát Rủi ro (Compliance):** Ngăn chặn các sai sót nghiệp vụ do nhân viên nhớ nhầm hoặc áp dụng sai quy định cũ, từ đó bảo vệ ngân hàng khỏi các khoản phạt vi phạm tuân thủ.

**Ai là người dùng chính?**
- Hệ thống được thiết kế phục vụ 3 nhóm đối tượng cốt lõi:
	- **Tiền tuyến (Front-line):** Giao dịch viên (Teller) và nhân viên tín dụng tại quầy – những người cần kết quả tra cứu tức thì (< 5 giây) để không làm gián đoạn trải nghiệm khách hàng.
	- **Hậu phương (Back-office):** Nhân viên xử lý chứng từ, thẩm định viên cần phân tích sâu các hồ sơ phức tạp.
	- **Khối Kiểm soát:** Chuyên viên Tuân thủ (Compliance) sử dụng hệ thống để rà soát, đối chiếu chính sách chéo.
**Vì sao chủ đề này phù hợp để phân tích deployment và cost?** 
* Đây là một dự án AI mang tính đặc thù cao của ngành tài chính, nơi "Bảo mật" và "Chi phí" là hai rào cản lớn nhất cần giải quyết:
	- **Về Deployment (Triển khai):** Ngành ngân hàng bị ràng buộc bởi các luật lệ cực kỳ khắt khe về quyền riêng tư dữ liệu (Data Privacy) và Data Residency (Yêu cầu dữ liệu ở trong nước). Việc phân tích kiến trúc giúp chứng minh tính khả thi của mô hình Hybrid: Giữ dữ liệu nhạy cảm tại On-premise để tuân thủ luật, đồng thời chỉ đẩy dữ liệu an toàn lên Cloud để tận dụng sức mạnh của AI.
	- **Về Cost (Chi phí):** Tần suất tra cứu của hàng ngàn nhân viên mỗi ngày tạo ra một Volume khổng lồ. Đồng thời, việc đọc hiểu các file SOP dài khiến lượng Token tiêu thụ (Input Tokens) tăng vọt. Phân tích Cost là bài toán bắt buộc để xây dựng các chiến lược tối ưu (như Caching hay Routing) nhằm đảm bảo hệ thống mang lại lợi nhuận (ROI) thay vì đốt sạch ngân sách của ngân hàng.
	
### 1. Bối cảnh tổ chức & Dữ liệu
*   **Bối cảnh**: Hệ thống ngân hàng mục tiêu là một Ngân hàng Thương mại Cổ phần với mạng lưới chi nhánh rộng lớn, sử dụng hệ thống Core Banking legacy mang tính đóng và có yêu cầu bảo mật khắt khe. Dữ liệu vận hành được phân loại thành ba nhóm chính: SOP nội bộ, biểu mẫu tín dụng, và đặc biệt là dữ liệu KYC chứa Thông tin định danh cá nhân (PII). Nhóm dữ liệu này mang mức độ nhạy cảm **Cực kỳ cao (Confidential/Internal Use Only)** và hệ thống AI tích hợp phải tuân thủ nghiêm ngặt tiêu chuẩn an toàn hệ thống thông tin **Cấp độ 3** theo Thông tư 64/2024/TT-NHNN.
*   **Dữ liệu**: SOP nội bộ, biểu mẫu tín dụng, dữ liệu KYC khách hàng (PII - Thông tin định danh cá nhân).
*   **Mức độ nhạy cảm**: **Cực kỳ cao (Confidential/Internal Use Only)**. Tuân thủ tiêu chuẩn an toàn hệ thống thông tin **Cấp độ 3** theo Thông tư 64/2024/TT-NHNN.

### 2. Mô hình triển khai đề xuất
*   **Lựa chọn**: **Hybrid Cloud** (hoặc Private Cloud hoàn toàn).
*   **Lý do chọn**: 
    1.  Dữ liệu PII khách hàng bắt buộc lưu trữ và xử lý tại On-prem hoặc Private Cloud để tuân thủ quy định Ngân hàng Nhà nước.
    2.  Tận dụng Cloud (Public Cloud thông qua VPN/Direct Connect) cho các tác vụ suy luận (reasoning) trên dữ liệu SOP đã được ẩn danh hóa (de-identified) để tối ưu hiệu năng và cập nhật nhanh các model mới nhất (GPT-4o, Claude 3.5).

### 3. Ràng buộc Enterprise & Thảo luận
*   **Audit Trail**: Tuân thủ Thông tư 64/2024, hệ thống phải ghi nhật ký toàn bộ việc sử dụng Open API tối thiểu trong vòng **03 tháng** và sao lưu tối thiểu **01 năm** để phục vụ kiểm tra/thanh tra.
*   **Data Residency**: Dữ liệu không được phép rời khỏi lãnh thổ Việt Nam.
*   **Human-in-the-loop**: AI chỉ đóng vai trò hỗ trợ tra cứu nhanh; các quyết định tín dụng hoặc KYC phức tạp bắt buộc phải có sự xác nhận của nhân viên có thẩm quyền (SOP bắt buộc).
*   **Hệ thống cũ**: Cần API gateway để tích hợp AI vào Core Banking, đồng thời giới hạn số lần truy vấn tự động để tránh tấn công DOS hoặc khai thác dữ liệu trái phép.

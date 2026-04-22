
### 1. 3 Scenario Rủi ro & Phản ứng
*   **Scenario 1: Provider Timeout (Azure/OpenAI gặp sự cố)**: 
    *   *Tác động*: Nhân viên không tra cứu được quy trình, gây chậm trễ phục vụ khách hàng.
    *   *Phản ứng*: Switch sang Backup Provider (Ví dụ: On-prem Llama-3 model) hoặc hiển thị top k tài liệu liên quan cho nhân viên tự tra cứu.
*   **Scenario 2: Traffic tăng đột biến**: 
    *   *Phản ứng*: Áp dụng Rate-limiting cho các request không khẩn cấp (back-office) để ưu tiên giao dịch viên tại quầy.
*   **Scenario 3: Hallucination (AI hướng dẫn sai bước KYC)**:
    *   *Phản ứng*: Ghi đè bằng câu trả lời "Tôi không chắc chắn, vui lòng tra cứu tài liệu gốc tại link \[XYZ]" hoặc fallback sang senior supervisor.

### 2. Metric cần Monitor
- **RAG Triad (Độ chính xác của AI):**
    - **Faithfulness (Độ trung thực):** Đảm bảo câu trả lời được rút ra 100% từ tài liệu gốc, không có ảo giác (hallucination).
    - **Context Precision:** Tỷ lệ hệ thống trích xuất (retrieval) đúng đoạn SOP cần thiết.
- **Performance (Hiệu năng hệ thống):**
    - **Time to First Token (TTFT):** **< 1s** để đảm bảo trải nghiệm tương tác mượt mà (chữ hiện ra ngay lập tức).
    - **Total Response Time:** < 5s cho một câu trả lời hoàn chỉnh.
*   **Latency (Time to First Token)**: < 1s để đảm bảo trải nghiệm người dùng.
*   **Audit Compliance**: Tần suất log success rate đạt 99.9% và kiểm tra định kỳ tính toàn vẹn của dữ liệu nhật ký. 
*   **Cost per Request**: Kiểm soát ngân sách.

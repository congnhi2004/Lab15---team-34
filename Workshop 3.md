
### 1. 3 Chiến lược Optimization phù hợp nhất
1.  **Semantic Caching**: Lưu trữ các câu trả lời cho các quy trình SOP phổ biến (Ví dụ: "Quy trình giải ngân khoản vay tín chấp").
    *   *Lợi ích*: Tiết kiệm ~40% token cost cho các câu hỏi trùng lặp.
2.  **Model Routing**: 
    *   Câu hỏi đơn giản (tra cứu mã lỗi, thuật ngữ) -> GPT-4o-mini.
    *   Câu hỏi phân tích chính sách phức tạp -> GPT-4o.
3.  **Selective Inference**: Chỉ kích hoạt AI khi câu hỏi liên quan đến bộ dữ liệu SOP, các câu hỏi ngoài lề sẽ bị chặn ngay ở lớp gateway (Rule-based).

### 2. Chiến lược làm ngay vs Để sau
*   **Làm ngay**: Caching & Routing (Tác động nhanh đến ROI).
*   **Để sau**: Fine-tuning hoặc Self-hosting GPU (Chỉ làm khi đạt volume đủ lớn).

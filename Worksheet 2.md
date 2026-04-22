
### 1. Ước lượng Traffic (MVP - 1000 nhân viên)
*   **Số user/ngày**: 1,000 nhân viên (80% teller, 20% back-office).
*   **Request/ngày/user**: 5 requests => 5,000 requests/ngày.
*   **Input/Output tokens**: Input 2,000 tokens (do nhồi context SOP); Output 500 tokens.
*   **Tổng token/tháng (22 ngày)**: ~275 triệu tokens (220M input, 55M output).

### 2. Bóc tách các lớp Cost (Ước tính/tháng)
*   **Token/Model Cost**: ~ 40tr - 65tr (Tùy thuộc vào việc dùng GPT-4o hay model mini).
*   **Compute/Storage (Vector DB & Hosting)**: ~ 15tr (Private Cloud hosting).
*   **Human Review/Maintenance**: ~ 50tr (Đội ngũ content/compliance cập nhật SOP).
*   **Logging & Audit**: ~ 5tr (Lưu trữ và quản lý log).

### 3. Suy nghĩ về Scale
*   **Khi user tăng 10x**: Token cost là driver lớn nhất sẽ tăng 10x (~ 500tr/tháng). Đây là lúc cần cân nhắc self-hosting các SLM (Small Language Models) như Phi-3 hoặc Llama-3-8B cho các tác vụ đơn giản.

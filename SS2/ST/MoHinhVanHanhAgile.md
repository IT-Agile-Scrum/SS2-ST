# THIẾT KẾ MÔ HÌNH VẬN HÀNH AGILE CHO TOÀN MẢNG RIKKEIGO

## Phần 1 - Kiến trúc mô hình

Với vai trò Agile Lead, tôi thiết kế mô hình vận hành chung bám sát **4 Giá trị Agile** (ưu tiên cá nhân/tương tác, phần mềm chạy tốt, cộng tác với khách hàng và phản hồi sự thay đổi) và **3 Trụ cột Scrum** (Minh bạch, Thanh tra, Thích nghi).

### 1. Các module quy trình (Dựa trên Scrum)
Các thành phần được phân tách rõ ràng, không chồng chéo trách nhiệm:

*   **Module Vai trò (3 Vai trò):**
    *   **Product Owner (PO):** Đại diện khách hàng, quản lý và tối ưu hóa giá trị của Product Backlog (chọn "làm cái gì").
    *   **Scrum Master (SM):** Người bảo vệ quy trình Agile/Scrum, tháo gỡ khó khăn và hỗ trợ nhóm làm việc hiệu quả.
    *   **Development Team (Đội Đặt xe & Đội Thanh toán):** Đội ngũ tự quản, đa chức năng, trực tiếp phát triển sản phẩm (quyết định "làm như thế nào").
*   **Module Danh sách & Kết quả (3 Artifacts - Đảm bảo tính Minh bạch):**
    *   **Product Backlog:** Danh sách toàn bộ các tính năng, yêu cầu cần có của RikkeiGo.
    *   **Sprint Backlog:** Kế hoạch và danh sách công việc đội cam kết thực hiện trong 1 Sprint.
    *   **Increment (Phần mềm tăng trưởng):** Phiên bản sản phẩm hoàn thiện, chạy được và đạt chuẩn "Hoàn thành" (Done) sau mỗi Sprint.
*   **Module Sự kiện (5 Sự kiện - Đảm bảo Thanh tra & Thích nghi):**
    *   **Sprint:** Vòng lặp phát triển thời gian cố định (nhịp Sprint chung).
    *   **Sprint Planning:** Lập kế hoạch cho đầu mỗi Sprint.
    *   **Daily Scrum:** Giao ban 15 phút mỗi ngày để đồng bộ công việc.
    *   **Sprint Review:** Đánh giá Increment cuối Sprint cùng Stakeholder.
    *   **Sprint Retrospective:** Nhìn lại để rút kinh nghiệm và cải tiến quy trình.

### 2. Mô hình cho Đội Đối soát
*   **Đội Đối soát có áp dụng mô hình Scrum chung không?** **KHÔNG.** Đội Đối soát nên áp dụng phương pháp **Kanban** (một phương pháp Agile dựa trên luồng công việc liên tục).
*   **Vì sao?** Vì yêu cầu của đội Đối soát là sự ổn định, tính chính xác cao và tuân thủ quy định thuế; họ xử lý công việc theo dòng chảy liên tục (flow) thay vì làm các tính năng có tính thay đổi cao theo từng gói thời gian (Sprint) như hai đội kia.

### 3. Phác thảo luồng giá trị khép kín (Value Stream)
Luồng giá trị vận hành liên tục, tạo ra vòng phản hồi và cải tiến khép kín:

`[Nhu cầu từ Khách hàng/Thị trường]` ➔ `(Product Backlog: PO ưu tiên)` ➔ `[Sprint Planning]` ➔ `(Sprint Backlog)` ➔ `[Quá trình Sprint & Daily Scrum]` ➔ `(Increment: Sản phẩm chạy tốt)` ➔ `[Sprint Review: Nhận phản hồi]` ➔ `[Sprint Retrospective: Đề xuất cải tiến]` ➔ `(Áp dụng cải tiến vào Sprint kế tiếp)`

---

## Phần 2 - Xử lý tình huống (Chứng minh tính ổn định)

### Tình huống 1: Đến buổi Sprint Review nhưng không có hạng mục nào đạt tiêu chuẩn "xong" (Done).
*   **Phát hiện ở đâu:** Tại sự kiện **Sprint Review**.
*   **Ai xử lý:** **Scrum Master** (hướng dẫn quy trình), **Product Owner** và **Development Team**.
*   **Xử lý thế nào:**
    *   **Tại Review:** Tuân thủ trụ cột *Minh bạch*, tuyệt đối không trình diễn (demo) các tính năng chưa "Xong". Báo cáo thực tế tình hình. Product Owner chuyển các hạng mục này về lại Product Backlog để đánh giá ưu tiên lại cho kỳ sau.
    *   **Tại Retrospective:** Scrum Master thúc đẩy đội nhóm thực hiện *Thanh tra*, tìm hiểu nguyên nhân gốc rễ (ước lượng sai, yêu cầu chưa rõ, hay thiếu kỹ năng) và đưa ra hành động *Thích nghi* (cải tiến) để tránh lặp lại lỗi này trong Sprint tới.

### Tình huống 2: Đội Thanh toán muốn kéo dài riêng Sprint đang chạy thêm 1 tuần để "làm cho xong", trong khi các đội khác giữ nhịp cũ.
*   **Phát hiện ở đâu:** Trong **Quá trình Sprint** (nguy cơ phát hiện qua Daily Scrum) hoặc cuối Sprint.
*   **Ai xử lý:** **Scrum Master**.
*   **Xử lý thế nào:**
    *   **Hành động:** Scrum Master kiên quyết **TỪ CHỐI** việc kéo dài Sprint, bảo vệ tính Time-box (đóng khung thời gian) nhằm giữ nhịp độ (cadence) đồng bộ chung cho toàn mảng RikkeiGo.
    *   **Giải quyết:** Sprint bắt buộc kết thúc đúng hạn. Công việc chưa xong trả về Product Backlog. Trong buổi Sprint Retrospective, Đội Thanh toán phải rút kinh nghiệm về việc cam kết vượt quá năng lực (capacity) hoặc chia nhỏ công việc chưa tốt, từ đó học cách ước lượng và lập kế hoạch chính xác hơn cho lần sau thay vì phá vỡ quy trình chung.

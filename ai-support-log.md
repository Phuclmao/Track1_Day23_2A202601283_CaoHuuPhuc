# AI Support Log - Track 1 Day 23

## Thông tin học viên
- **Họ và tên:** Cao Hữu Phúc
- **Mã học viên (MHV):** 2A202601283
- **Dự án:** AI Customer Support Agent
- **Link tệp Metrics Pack:** https://docs.google.com/spreadsheets/d/1T3gDUuUCGMVJvHAv73q66U6eV6SQLC4dqyQLNGkGKQ4/edit?usp=sharing

---

### AI đã giúp tôi ở đâu?
- **Khởi tạo và chuẩn hóa khung tài liệu:** Dựng nhanh cấu trúc chuẩn từ mục 00 đến 07 theo đúng yêu cầu bài học Day 23.
- **Phân định rõ Core Action:** Tách bạch việc AI sinh câu trả lời (System Output) với hành vi khách hàng xác nhận giải pháp thành công (`solution_accepted` - Core Value).
- **Thiết lập công thức North Star Metric (NSM):** Kết hợp đúng chuẩn 3 thành phần: Đơn vị giá trị (Resolved issues) + Ngưỡng chất lượng (CSAT $\ge 4/5$, RAG Groundedness $\ge 98\%$, No human handover) + Tần suất hàng tháng.
- **Bổ sung chỉ số Kỹ thuật & An toàn:** Gợi ý kịp thời các metrics trọng yếu: API Latency p95, Tool Error Rate, PII Leakage Rate = 0%, Guardrails, và Model Quality Drift.

---

### AI sai, hời hợt hoặc đề xuất metric sai nature ở đâu?
- **Dính bẫy chu kỳ mặc định (Daily/Weekly Bias):** Áp dụng DAU/WAU hoặc D7 Retention máy móc, bỏ qua bản chất *Utility / Event-driven* của CSKH (khách chỉ tương tác khi có lỗi; chat nhiều lần là dấu hiệu bot xử lý kém).
- **Đưa số liệu khẳng định thiếu căn cứ ("3.5 lần"):** Viết Growth Hypothesis như một dữ kiện có sẵn thay vì giả thuyết cần kiểm chứng khoa học.
- **Thiếu căn cứ Time Window:** Chọn mốc 10 phút cho Activation tùy tiện, không gắn với số liệu phân phối thời gian thực tế (P90).
- **Retention Window bị phiến diện:** Ban đầu chỉ xét chu kỳ mua hàng mới (30–60 ngày), bỏ sót sự cố trên đơn hàng cũ / bảo hành (90–180 ngày).

---

### Tôi đã tự sửa hoặc quyết định lại điều gì?
- **Chốt Cadence chuẩn là Event-driven (Theo sự cố / Chu kỳ đơn hàng):** Bác bỏ nhịp đo Daily/Weekly, tuân thủ nguyên tắc *"Nature trước, nurture sau"*.
- **Tự kiểm Core Action đạt 4/5 tiêu chí:** Ghi nhận tiêu chí *"Có thể lặp lại"* chỉ đạt mức lưu ý do tính chất sự vụ (*episodic*), tránh việc chấm 5/5 gượng ép.
- **Chuẩn hóa lại Giả thuyết tăng trưởng:** Chuyển con số khẳng định thành giả định kỳ vọng ($\ge 2.5 - 3.5$ lần) và bổ sung phương pháp kiểm chứng qua *Cohort Analysis / A/B Test trong 8 tuần*.
- **Lý giải căn cứ Activation 10 phút & Tách 2 nhánh Retention Window:** Căn cứ theo P90 chat support (3–7 phút); phân rõ nhánh mua lặp lại (30–60 ngày) và nhánh bảo hành/đơn cũ (90–180 ngày).
- **Bổ sung bộ chỉ số Production-ready:** Đưa *RAG Groundedness $\ge 98\%$*, *Weekly AI Accuracy Drift $\le 2\%$*, và *PII Leakage Rate = 0%* vào hệ thống telemetry.

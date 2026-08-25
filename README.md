# Track 1 - Day 23: Metrics Pack

## Thông tin học viên
- **Họ và tên:** Cao Hữu Phúc
- **Mã học viên (MHV):** 2A202601283
- **Dự án chọn làm:** AI Customer Support Agent
- **Link tệp Metrics Pack (Đã cấp quyền xem):** https://docs.google.com/spreadsheets/d/1T3gDUuUCGMVJvHAv73q66U6eV6SQLC4dqyQLNGkGKQ4/edit?usp=sharing

---

## 00 — Phạm vi: Dự án, Persona, Core Job
- **Dự án:** AI Customer Support Agent (Hệ thống trợ lý AI tự động phản hồi, giải quyết khiếu nại và tra cứu đơn hàng cho khách hàng 24/7).
- **Persona:** Khách hàng mua sắm trực tuyến đang gặp sự cố về đơn hàng hoặc cần giải đáp thắc mắc về sản phẩm/dịch vụ.
- **Core Job (Lời người dùng - JTBD):** "Khi gặp sự cố đơn hàng hoặc có thắc mắc gấp về sản phẩm, tôi muốn được phản hồi chính xác và giải quyết vấn đề ngay lập tức mà không phải chờ đợi hàng giờ để gặp nhân viên hỗ trợ, để tôi không bị gián đoạn trải nghiệm mua sắm và an tâm về đơn hàng của mình."

### Phân tích 4 khái niệm nền tảng:
| Khái niệm | Câu hỏi | Ví dụ |
| :--- | :--- | :--- |
| **Core job** | *User đang cố hoàn thành việc gì?* | Giải quyết nhanh sự cố đơn hàng, thắc mắc sản phẩm mà không cần chờ đợi lâu. |
| **Core action** | *User làm gì trong sản phẩm để tiến tới giá trị?* | Gửi yêu cầu sự cố và xác nhận, áp dụng giải pháp do AI cung cấp. |
| **Core value** | *User nhận được lợi ích gì?* | Vấn đề được tháo gỡ chính xác, tức thì, tiết kiệm thời gian và an tâm tiếp tục mua sắm. |
| **Core value event** | *Sự kiện nào chứng minh value đã xảy ra?* | `solution_accepted` |

---

## 01 — Core Action Card (+ Kết quả tự kiểm 5 tiêu chí)

### Bảng Core Action Card:
| Thành phần | Câu trả lời của bạn |
| :--- | :--- |
| **Target user** | Khách hàng mua sắm trực tuyến đang gặp sự cố về đơn hàng hoặc có thắc mắc về sản phẩm. |
| **Core job** | Giải quyết nhanh sự cố đơn hàng, thắc mắc sản phẩm mà không cần chờ đợi lâu để gặp nhân viên hỗ trợ. |
| **Core action** | Gửi yêu cầu sự cố và xác nhận áp dụng giải pháp do AI cung cấp. |
| **Object** | Yêu cầu hỗ trợ (Support Query/Ticket) và Đơn hàng/Sự cố liên quan. |
| **Preconditions** | Người dùng đã mở khung chat, gửi câu hỏi/mô tả sự cố và AI đã trả về phản hồi/giải pháp tương ứng. |
| **Completion rule** | Người dùng bấm xác nhận "Vấn đề đã được giải quyết" / đánh giá "Hài lòng" mà không cần chuyển sang nhân viên tổng đài. |
| **Core value** | Vấn đề được tháo gỡ chính xác, tức thì 24/7, tiết kiệm thời gian chờ đợi và an tâm tiếp tục trải nghiệm mua sắm. |
| **Evidence of value** | Người dùng không tiếp tục khiếu nại trong 24h, để lại đánh giá hài lòng và phiên hội thoại kết thúc ở trạng thái `Resolved`. |
| **Candidate event** | `solution_accepted` |

### Kết quả tự kiểm 5 tiêu chí (Đạt 4/5 — Đạt yêu cầu ≥ 4/5, không bị trượt ≥ 2 tiêu chí):
1. **Gần core value**:
   - **ĐẠT** — Khi người dùng xác nhận giải pháp hoặc hoàn tất thao tác tự phục vụ, sự cố đã thực sự được tháo gỡ (đạt trọn vẹn Core Value). Tránh được lỗi chọn thao tác giao diện bề nổi như *"mở khung chat"*, *"gửi tin nhắn"* hay việc AI sinh phản hồi (output một chiều).
2. **Có thể lặp lại**:
   - **CHƯA ĐẠT TUYỆT ĐỐI (Lưu ý)** — Bản chất hỗ trợ khách hàng mang tính sự vụ (*event-driven / episodic*). Người dùng không lặp lại hàng ngày/hàng tuần theo thói quen mà chỉ lặp lại khi có đơn hàng phát sinh sự cố hoặc nhu cầu bảo hành mới.
3. **Có thể quan sát**:
   - **ĐẠT** — Xác định chính xác điểm hoàn tất qua event `solution_accepted` (khi user bấm xác nhận giải quyết, đánh giá CSAT hoặc kết thúc flow tra cứu thành công mà không yêu cầu chuyển sang nhân viên tổng đài).
4. **Có ý nghĩa**:
   - **ĐẠT** — Tỷ lệ và số lượng hoàn tất Core Action tăng phản ánh trực tiếp chất lượng giải quyết của AI tốt hơn, khách hàng được tháo gỡ vấn đề thực chất chứ không phải do spam tin nhắn.
5. **Có thể tác động**:
   - **ĐẠT** — Team có thể tác động trực tiếp bằng cách tối ưu hóa AI prompt/RAG Knowledge Base, thiết kế các nút phản hồi 1-chạm (Quick Replies), và tích hợp API hệ thống quản lý đơn hàng mượt mà hơn.

> **Kết luận:** Đạt **4/5 tiêu chí** (Chỉ trượt/lưu ý 1 tiêu chí < 2) $\rightarrow$ **Đạt yêu cầu, giữ nguyên Core Action đã chọn.**



---

## 02 — Action Nature Card + Kết luận Cadence

### Bảng Action Nature Card:
| Thành phần | Câu hỏi | Câu trả lời của bạn |
| :--- | :--- | :--- |
| **Actor** | *User, account, team hay object nào thực hiện?* | End-user (Khách hàng mua sắm trực tuyến đang có đơn hàng hoặc tài khoản mua sắm). |
| **Intent** | *Hành vi bắt đầu từ nhu cầu gì?* | Nhu cầu giải quyết khẩn cấp một sự cố hoặc thắc mắc cụ thể (giao hàng trễ, nhận sai hàng, đổi/trả đơn, lỗi thanh toán, tra cứu bảo hành). |
| **Trigger** | *Do user chủ động, sự kiện bên ngoài, người khác hay hệ thống kích hoạt?* | **Sự kiện bên ngoài kích hoạt (External Event-driven)**: Xảy ra sự cố trong quá trình mua/nhận hàng thúc đẩy user chủ động mở khung chat tìm giải pháp. |
| **Effort** | *Mất bao nhiêu thời gian, suy nghĩ, dữ liệu?* | **Thấp đến Trung bình**: Nhập 1–2 câu hỏi ngắn (15–30s) hoặc bấm các nút lựa chọn nhanh (Quick Replies), cung cấp mã đơn hàng nếu cần. |
| **Value timing** | *Value xuất hiện ngay, trễ, tích lũy, hay phụ thuộc người khác?* | **Xuất hiện ngay lập tức (Immediate Value)**: Nhận phản hồi chính xác, hướng dẫn xử lý hoặc xác nhận thao tác tra cứu/đổi đơn chỉ trong vài giây. |
| **State** | *Sau action, dữ liệu/trạng thái nào được giữ lại?* | Trạng thái sự cố chuyển sang `Resolved`, lịch sử chat được lưu trữ, trạng thái đơn hàng được cập nhật (nếu thao tác hủy/đổi), điểm đánh giá CSAT. |
| **Dependency** | *Có phụ thuộc nguồn cung, thành viên khác, approval, thời điểm?* | Phụ thuộc vào dữ liệu hệ thống (API tra cứu đơn hàng, chính sách đổi trả, Knowledge Base) — chỉ cần can thiệp của con người nếu vượt thẩm quyền AI. |
| **Repeat condition** | *Điều kiện nào khiến action có lý do xuất hiện lại?* | Khi khách hàng phát sinh đơn hàng mới và gặp sự cố/thắc mắc mới trong tương lai. |

### Kết luận Cadence:
- **Dạng hành vi:** Phản ứng theo sự kiện.
- **Kết luận:**
  Đối với khách hàng mua sắm trực tuyến, core action gửi yêu cầu sự cố và xác nhận áp dụng giải pháp do AI cung cấp thường xuất hiện theo từng sự kiện phát sinh sự cố đơn hàng hoặc thắc mắc sản phẩm vì nhu cầu hỗ trợ chỉ xuất hiện khi có vấn đề thực tế phát sinh trong quá trình mua sắm, không phải thói quen định kỳ. Do đó, nhịp đo phù hợp là theo từng phiên sự cố (Per-Incident / Per-Ticket) và theo chu kỳ đơn hàng ở cấp người dùng có phát sinh sự cố.

---

## 03 — Metric System

### 1. Activation Metric (Kích hoạt):
- **Start Event:** Người dùng gửi tin nhắn đầu tiên mô tả sự cố đơn hàng trong phiên chat (`chat_session_started` / `first_inquiry_sent`).
- **Activation Event:** Người dùng nhận và bấm xác nhận giải pháp của AI thành công (`solution_accepted` với điều kiện `has_human_handover: false`).
- **Time Window:** Hoàn tất trong vòng **10 phút** kể từ Start Event (ngay trong phiên tương tác đầu tiên).
  - *Căn cứ xác định 10 phút:* Dựa trên phân phối thời gian thực tế của chat-based customer support (P90 của một phiên tự phục vụ chuẩn thường kéo dài 3–7 phút theo benchmark ngành e-commerce CSKH). Ngưỡng 10 phút là khoảng thời gian tối ưu cho phép khách hàng gõ mô tả, đọc phản hồi và thực hiện thao tác xác nhận trước khi phiên bị timeout hoặc rơi vào trạng thái drop-off.
- **Công thức đo:**
  $$\text{Activation Rate} = \frac{\text{Số người dùng đạt solution\_accepted trong 10 phút}}{\text{Tổng số người dùng gửi tin nhắn sự cố lần đầu}} \times 100\%$$

### 2. Engagement Metric (Tương tác):
- **Góc đo 1 - Depth (Độ sâu / Hiệu quả dứt điểm):** **First Contact Resolution Rate (FCR)** — Tỷ lệ phiên sự cố được AI giải quyết dứt điểm ngay trong lượt trao đổi đầu tiên mà người dùng không cần khiếu nại lại trong 24h.
- **Góc đo 2 - Breadth (Độ rộng nghiệp vụ):** **Self-Service Capability Coverage** — Tỷ lệ danh mục nghiệp vụ (tra cứu vận chuyển, hủy đơn, hoàn tiền, đổi size, hỏi bảo hành) được người dùng hoàn tất tự động thành công qua AI Agent mà không cần can thiệp thủ công.

### 3. North Star Metric (NSM):
- **Công thức 3 thành phần:**
  $$\text{NSM} = \text{Unit of Value (Sự cố được giải quyết)} + \text{Quality Threshold (Không chuyển nhân viên, CSAT } \ge 4/5 \text{ \& RAG Groundedness } \ge 98\%) + \text{Frequency (Hàng tháng)}$$
- **Tên chỉ số:** **Monthly High-Quality AI-Resolved Issues** (*Số lượng sự cố đơn hàng được AI giải quyết chất lượng cao hàng tháng*).

### 4. Leading Indicators (Chỉ số dẫn dắt & Vận hành):
1. **First Response Time (FRT) < 5s & API Latency p95 < 2.5s:**
   - *Lý do dự báo:* Phản hồi siêu tốc và hạ tầng mượt mà giúp triệt tiêu cảm giác chờ đợi sốt ruột, giảm tỷ lệ thoát chat (drop-off) và giữ chân người dùng đi hết luồng hỗ trợ.
2. **Intent Classification Accuracy $\ge 92\%$:**
   - *Lý do dự báo:* Hiểu chính xác ý định và trích xuất đúng mã đơn hàng ngay từ câu hỏi đầu tiên giúp AI đưa ra đúng giải pháp, hạn chế tối đa việc đoán sai gây bức xúc cho khách.
3. **Quick-Reply Selection Rate $\ge 65\%$:**
   - *Lý do dự báo:* Khách hàng chủ động chọn các nút gợi ý thao tác nhanh chứng minh giải pháp của AI đưa ra đúng ngữ cảnh và giảm ma sát gõ phím.

### 5. Counter-Metrics & Guardrails (Kiểm soát chất lượng, An toàn, Hạ tầng & Compliance):

#### A. Nhóm Chất lượng AI, RAG & Giám sát Drift theo thời gian:
- **RAG Groundedness & Faithfulness Score $\ge 98\%$:** Đo lường mức độ câu trả lời của AI bám sát 100% tài liệu chính sách của sàn/shop. Ngăn chặn triệt để tình trạng AI tự bịa (*hallucination*) quy định đổi trả hoặc tự cam kết đền bù sai thẩm quyền.
- **Weekly AI Accuracy & Performance Drift Rate $\le 2\%$:** Đo lường độ ổn định chất lượng phản hồi của mô hình theo các khung tuần (rolling window) nhằm phát sinh cảnh báo sớm nếu AI bị suy giảm độ chính xác khi lưu lượng tải tăng đột biến (volume spikes mùa sale) hoặc sau khi cập nhật Knowledge Base mới.
- **Policy Hallucination Rate $< 0.2\%$:** Tỷ lệ phiên chat AI cung cấp sai điều khoản dịch vụ hoặc thông tin đơn hàng.

#### B. Nhóm Kỹ thuật & Hạ tầng (Infrastructure & Reliability):
- **Tool Calling / Database API Error Rate $< 1\%$:** Tỷ lệ lỗi khi AI gọi các API tra cứu đơn hàng, cổng vận chuyển hoặc cổng hoàn tiền (phát hiện sớm lỗi hệ thống trước khi CSAT bị sụt giảm).
- **End-to-End System Availability / Uptime $\ge 99.9\%$:** Đảm bảo hệ thống AI Agent luôn sẵn sàng phục vụ 24/7.

#### C. Nhóm An toàn, Bảo mật & Compliance (Safety & Legal Risk):
- **PII Leakage Rate $= 0\%$:** Tỷ lệ rò rỉ dữ liệu cá nhân nhạy cảm (Số điện thoại, địa chỉ nhận hàng, số thẻ tín dụng, OTP) trong phản hồi của AI ra bên ngoài.
- **Guardrail Trigger Rate (Phát hiện & Chặn Prompt Injection / Gian lận):** Đo lường tỷ lệ các nỗ lực bẻ khóa bot (jailbreak), ép AI hoàn tiền khống hoặc lừa cấp mã giảm giá trái phép bị bộ lọc Guardrails chặn đứng thành công.
- **Human Escalation Rate $\le 15\%$:** Tỷ lệ phiên chat phải chuyển sang nhân viên tổng đài (ngăn chặn bot tự ý đóng ticket khi khách chưa được giải quyết thỏa đáng).
- **Cost per Resolved Conversation:** Chi phí token LLM và hạ tầng trên mỗi sự cố giải quyết thành công (đảm bảo Unit Economics).

---

## 04 — Retention Definition

### Bảng định nghĩa Retention đủ 6 thành phần:
| Thành phần | Câu hỏi | Câu trả lời cho AI Customer Support Agent |
| :--- | :--- | :--- |
| **Unit** | *User, account, team, organization hay object?* | **User** (Khách hàng cá nhân có tài khoản mua sắm trên nền tảng). |
| **Cohort entry** | *Event nào đưa unit vào cohort?* | Lần đầu tiên trải nghiệm và đạt giải quyết thành công với AI (`first_solution_accepted`). |
| **Return event** | *Core action / value event nào phải lặp lại?* | Tiếp tục chọn và đạt `solution_accepted` qua AI Agent khi phát sinh sự cố ở các đơn hàng tiếp theo. |
| **Window** | *Daily, weekly, monthly, project-based hay custom bracket?* | **1. Nhánh chính (Ngành hàng mua lặp lại - FMCG/Fashion):** Custom Purchase Cycle Bracket **30–60 ngày** (gắn liền với chu kỳ đơn hàng mới).<br>**2. Nhánh phụ (Sự cố đơn hàng cũ / Bảo hành dài hạn):** Post-purchase Warranty Window **90–180 ngày** (áp dụng cho khiếu nại kéo dài hoặc bảo hành thiết bị). |
| **Threshold** | *Một lần hay nhiều lần trong window?* | **$\ge 1$ lần** (100% các sự cố phát sinh trong chu kỳ mua hàng đều được giải quyết thành công qua AI). |
| **Segment** | *Retention đang áp dụng cho ai?* | Khách hàng mua sắm có phát sinh ít nhất 1 đơn hàng mới hoặc có yêu cầu bảo hành hợp lệ trong chu kỳ đo (*Active Buyers with Support Incident*). |

---

## 05 — Product Loop

### 1. Sơ đồ vòng lặp sản phẩm (2 chu kỳ):
- **Loại loop chính:** **Event-Response Loop (Vòng lặp phản ứng sự cố kết hợp Xây dựng lòng tin - Trust Loop)**.

```
[Chu kỳ 1: Xử lý sự cố & Xây dựng lòng tin]
Sự cố đơn hàng (Natural Trigger 1)
   └──> Gửi yêu cầu & xác nhận giải pháp AI (Core Action 1)
           └──> Sự cố được gỡ bỏ trong < 3 phút (Immediate Value 1)
                   └──> Cập nhật đơn hàng & Tạo dựng niềm tin an tâm mua sắm (Saved State / Investment)

[Chu kỳ 2: Tự tin mua sắm & Tự phục vụ lặp lại]
Phát sinh thắc mắc ở đơn hàng mới sau 30-60 ngày (Next Natural Trigger 2)
   └──> Chủ động mở ngay AI Support để xử lý (Core Action 2)
           └──> Tiếp tục được giải quyết tức thì, gia tăng sự gắn kết (Repeat Value 2)
```

- **Reason to return (Lý do quay lại nếu không có notification):** Khách hàng quay lại mua hàng và tiếp tục chọn AI Agent vì **sự an tâm tuyệt đối (Peace of Mind)** — họ biết rằng mọi rủi ro giao hàng hay sự cố phát sinh đều có một trợ lý AI túc trực giải quyết dứt điểm 24/7 mà không tốn công chờ đợi.

### 2. Metric Hypothesis:
> Nếu loop này hoạt động, metric **Monthly High-Quality AI-Resolved Issues (NSM)** sẽ thay đổi theo hướng **tăng trưởng $\ge 20 - 25\%$** trong **vòng 60 ngày (2 chu kỳ mua hàng)**, vì **chúng tôi giả định rằng khách hàng đã trải nghiệm giải quyết sự cố thành công ngay lần đầu sẽ có xu hướng tin tưởng và tiếp tục chọn AI tự phục vụ ở các sự cố tiếp theo cao hơn đáng kể (ước tính giả định kỳ vọng $\ge 2.5 - 3.5$ lần so với nhóm phải chờ nhân viên tổng đài), và giả thuyết này sẽ được kiểm chứng bằng phân tích đối chứng Cohort Analysis / A/B Test trong 8 tuần triển khai**.

---

## 06 — Tracking nhanh


### 1. Danh sách Core Events (Bao gồm Events Nghiệp vụ, Kỹ thuật & An toàn):
| Tên event | Ý nghĩa (Hành vi/Value đã xảy ra) | Thời điểm ghi nhận | Metric sử dụng |
| :--- | :--- | :--- | :--- |
| `session_chat_started` | Người dùng đã gửi tin nhắn đầu tiên mở phiên hỗ trợ sự cố. | Ngay khi tin nhắn đầu tiên của user được server lưu trữ thành công. | Start Event tính **Activation Rate**. |
| `intent_classified` | Hệ thống AI đã phân loại chính xác ý định và trích xuất thực thể sự cố. | Ngay khi module NLP/LLM hoàn tất phân loại ý định trước khi tạo câu trả lời. | **Intent Classification Accuracy** (Leading). |
| `rag_context_retrieved` | Hệ thống trích xuất ngữ cảnh/chính sách từ Knowledge Base và chấm điểm groundedness. | Khi RAG pipeline trả về chunk tài liệu có độ tin cậy được verify. | **RAG Groundedness & Faithfulness Score**. |
| `guardrail_triggered` | Bộ lọc an toàn phát sinh chặn hành vi prompt injection, vi phạm PII hoặc gian lận hoàn tiền. | Ngay khi request bị lớp Guardrail/Safety filter can thiệp chặn lại. | **Guardrail Trigger Rate & PII Protection**. |
| `tool_call_failed` | Ghi nhận sự cố khi AI gọi API hệ thống ngoài (tra cứu đơn hàng, xử lý đổi trả) thất bại. | Khi API trả về mã lỗi 4xx/5xx hoặc timeout. | **Tool Calling API Error Rate** (Kỹ thuật/Hạ tầng). |
| `quick_reply_clicked` | Người dùng đã bấm chọn một nút gợi ý thao tác nhanh (1-click action) do AI đề xuất. | Ngay khi client ghi nhận tương tác click và gửi payload action lên server. | **Quick-Reply Selection Rate** (Leading). |
| `solution_accepted` | Người dùng đã xác nhận giải pháp thành công / hoàn tất tự xử lý đơn mà không chuyển nhân viên. | Khi trạng thái ticket chuyển sang `Resolved` và nhận được xác nhận từ người dùng. | **Activation Event**, **NSM**, Return Event tính **Retention**. |
| `human_handover_requested` | Phiên chat bị chuyển tiếp sang nhân viên hỗ trợ (AI không xử lý được hoặc user yêu cầu). | Khi ticket được gán thành công cho nhân viên hỗ trợ trong hàng đợi. | **Human Escalation Rate** (Counter Metric). |
| `csat_submitted` | Người dùng đã hoàn tất gửi đánh giá mức độ hài lòng (1–5 sao). | Ngay khi form đánh giá CSAT được gửi và lưu thành công vào cơ sở dữ liệu. | Quality Threshold trong **North Star Metric**. |

### 2. Tiêu chí nghiệm thu (Acceptance Criteria):
- **AC 1 (Chỉ ghi nhận khi hành vi thật sự hoàn tất):** Event `solution_accepted` CHỈ ĐƯỢC PHÉP gửi khi hệ thống backend đã cập nhật thành công trạng thái ticket sang `Resolved` trên database và người dùng đã click xác nhận giải quyết (hoặc hoàn tất luồng API tự phục vụ trả về HTTP 200). Tuyệt đối không được bắn event khi người dùng chỉ mới mở modal xác nhận hoặc khi AI vừa mới gửi tin nhắn phản hồi.
- **AC 2 (Chống trùng lặp - Idempotency):** Với mỗi cặp `session_id` và `ticket_id`, hệ thống chỉ ghi nhận duy nhất 01 event `solution_accepted`. Hành vi tải lại trang (reload), mất kết nối gửi lại (retry), hoặc bấm liên tiếp nhiều lần vào nút xác nhận KHÔNG ĐƯỢC tạo thêm event trùng lặp cho cùng một lần hoàn tất giải quyết.
- **AC 3 (Kiểm soát An toàn & Lỗi kỹ thuật):** Event `guardrail_triggered` và `tool_call_failed` phải được ghi nhận độc lập kèm error payload để phục vụ telemetry real-time alert mà không làm gián đoạn trải nghiệm của người dùng.

---

## 07 — Revision (Ghi nhận điều chỉnh lớn & Rationale)
- **Nội dung điều chỉnh 1 (Core Action):** Chuyển từ hành động mơ hồ *"Khách hàng chat với AI bot"* sang hành vi chuyển giao giá trị cụ thể *"Gửi yêu cầu sự cố và xác nhận áp dụng giải pháp do AI cung cấp (solution_accepted)"*.
  - *Rationale (Lý do):* Tránh nhầm lẫn giữa output kỹ thuật một chiều của AI với việc khách hàng thực sự nhận được giá trị giải quyết dứt điểm vấn đề (Core Value).
- **Nội dung điều chỉnh 2 (Cadence & Retention Window):** Không áp dụng nhịp đo mặc định Daily/Weekly (DAU/WAU) hay D7/D14 retention cứng nhắc mà chuyển sang **Event-driven Cadence (Custom Purchase Cycle Bracket: 30–60 ngày)**.
  - *Rationale (Lý do):* Tuân thủ nguyên tắc *"Nature trước, nurture sau"*. Khách hàng không có nhu cầu phát sinh sự cố mỗi ngày để chat với bot; việc gượng ép đo tần suất cao sẽ dẫn đến hiểu sai về chất lượng dịch vụ (chat nhiều lần là tín hiệu bot xử lý kém, không phải gắn kết tốt).
- **Nội dung điều chỉnh 3 (Bổ sung Metrics Hạ tầng, Compliance & RAG Faithfulness):**
  - *Vá lỗ hổng Kỹ thuật/Hạ tầng:* Bổ sung **API Latency p95 (< 2.5s)** và **Tool Calling / Database API Error Rate (< 1%)** để phát hiện sớm sự cố hệ thống trước khi CSAT bị sụt giảm.
  - *Vá lỗ hổng An toàn & Pháp lý (Compliance):* Thiết lập **PII Leakage Rate (= 0%)** và **Guardrail Trigger Rate** nhằm ngăn chặn rủi ro rò rỉ dữ liệu khách hàng hoặc bị lừa bot hoàn tiền trái phép.
  - *Vá lỗ hổng RAG Groundedness:* Đưa chỉ số **RAG Groundedness & Faithfulness Score ($\ge 98\%$)** vào Quality Threshold của NSM để triệt tiêu tình trạng AI hallucination về chính sách đền bù/đổi trả.

---

## Điều tôi mang về áp dụng cho dự án thật
- **Kiến thức & Kỹ năng cốt lõi:**
  - **Tư duy Metric Design chuẩn:** Hiểu rõ sự khác biệt giữa *Active* (chỉ mở app/gửi tin) và *Activated* (đã chạm ngưỡng nhận giá trị cốt lõi); nắm vững công thức North Star Metric gắn liền với ngưỡng chất lượng (*Quality Threshold*) và chỉ số đối trọng (*Counter-metrics*) để ngăn chặn việc game số liệu.
  - **Nguyên tắc "Nature trước, nurture sau":** Luôn xuất phát từ nhịp nhu cầu tự nhiên của người dùng trong đời thực trước khi quyết định chu kỳ đo lường (Cadence) và khung đo Retention (Window).
- **Kế hoạch triển khai vào dự án thực tế (AI Customer Support Agent):**
  - Tích hợp telemetry tracking contract chặt chẽ ngay từ tầng API backend (chỉ bắn event `solution_accepted` khi trạng thái ticket chuyển `Resolved` thực tế, kèm idempotency key chống trùng lặp).
  - Thiết lập hệ thống bảo mật & an toàn đa tầng (*Multi-layer Guardrails*) chặn rò rỉ thông tin cá nhân PII và prompt injection ngay trước khi chuyển sang LLM.
  - Xây dựng pipeline tự động chấm điểm độ trung thực **RAG Groundedness & Faithfulness** cho câu trả lời của AI trước khi gửi cho khách hàng.
  - Thiết kế dashboard giám sát chất lượng AI toàn diện theo bộ tứ: **NSM (High-Quality Resolved Issues)** + **Leading (FRT, Intent Accuracy, Latency p95)** + **Safety/Compliance (PII, Guardrail)** + **Counter-Metric (Human Escalation Rate $\le 15\%$, Tool Error Rate $< 1\%$)**.
- **Các chỉ số (Metrics) theo dõi & cải thiện trọng tâm:**
  - **First Contact Resolution (FCR) $\ge 80\%$** qua AI tự phục vụ.
  - **RAG Groundedness & Faithfulness $\ge 98\%$**.
  - **Average Resolution Time $< 3$ phút** với **API Latency p95 $< 2.5$s**.
  - **Customer Satisfaction Score ($CSAT \ge 4.2/5$)** cho các phiên xử lý hoàn toàn tự động.



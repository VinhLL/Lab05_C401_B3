# Eval Metrics

## 1. Product & Business Metrics (Chỉ số Sản phẩm & Nghiệp vụ)

Nhóm chỉ số này được thu thập thông qua các tín hiệu ngầm định (Implicit signals) và trực tiếp (Explicit signals) từ UX/UI.

| STT | Tên chỉ số | Mục tiêu | Nguồn thu thập (Signals) | Ý nghĩa thực tế |
|:---:|---|:---:|---|---|
| 1 | **Task Success / Acceptance Rate** | **> 40%** | **Implicit:** Tỷ lệ user bấm nút [Đặt lịch ngay] hoặc [Tìm xưởng gần nhất] sau khi AI tư vấn. | Chứng minh AI đã cung cấp đúng Value (Path 1), khiến user tin tưởng chốt hành động. |
| 2 | **Human Escalation Rate** (Tỷ lệ thoát/kết nối CSKH) | **< 15%** | **Implicit:** Tỷ lệ user bấm [Kết nối nhân viên CSKH] hoặc [Tự chọn linh kiện thủ công]. | Đo lường mức độ mất kiên nhẫn của user (Path 4). Chỉ số này tăng tức là mô hình NLU đang hiểu sai nhiều. |
| 3 | **User Satisfaction (CSAT)** | **> 4.0/5.0** | **Explicit:** Tỷ lệ đánh giá Thumbs Up / Thumbs Down dưới mỗi câu trả lời của AI. | Thước đo trực tiếp sự hài lòng về cách AI giao tiếp và giải thích (Explainability). |

## 2. AI & Technical Metrics (Chỉ số Kỹ thuật AI)

Nhóm chỉ số này đo lường độ chính xác của AI và khả năng quản trị rủi ro (Risk Management).

| STT | Tên chỉ số | Mục tiêu | Nguồn thu thập (Signals) | Ý nghĩa thực tế |
|:---:|---|:---:|---|---|
| 1 | **Diagnosis Accuracy** (Độ chính xác chẩn đoán) | **> 85%** | **Correction Log:** So sánh dữ liệu `ai_diagnosis_log` (bệnh AI đoán) với biên bản nghiệm thu thực tế của kỹ thuật viên tại xưởng. | Thước đo quan trọng nhất để tinh chỉnh (fine-tune) mô hình Predictive Maintenance. |
| 2 | **Hallucination / Over-promising Rate** | **0% (Strict)** | **Log rủi ro:** Số lần AI vi phạm rào cản, tự ý chốt giờ cứng hoặc hứa hẹn bảo hành các lỗi vật lý (vỡ, gãy). | Đảm bảo an toàn, tránh khủng hoảng truyền thông và rủi ro từ chối bảo hành tại xưởng (Path 3). |
| 3 | **Response Latency** (Độ trễ) | **< 3 giây** | **Hệ thống:** Thời gian từ lúc user gửi mô tả lỗi đến khi AI xuất ra kết quả/gợi ý. | Đảm bảo tính khả thi (Feasibility), giữ chân tệp user trẻ (Gen Z) thích sự nhanh gọn. |

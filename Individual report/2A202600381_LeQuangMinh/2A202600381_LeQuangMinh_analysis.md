# UX Exercise — MoMo Moni AI

## Product
MoMo — Moni AI Assistant  
Feature: Automatic expense categorization

---

## 1. 4 Paths (User Experience Breakdown)

| Path | Scenario | User Experience | UI Behavior | Issues | UX Evaluation |
|------|----------|----------------|-------------|--------|--------------|
| AI đúng | User chi tiêu 50k tại Circle K → Moni gợi ý "Ăn uống" | User thấy tag đúng, không cần thao tác thêm | Hiện tag + icon category, không hỏi confirm | Không có | Tốt: Trải nghiệm mượt, giảm thao tác |
| AI không chắc | User chuyển tiền 200k → Moni không tag hoặc tag "Khác" | User phải tự vào chỉnh | Không có gợi ý / không hỏi lại | Không có cơ chế hỏi: "Bạn muốn phân loại?" | Kém: Thiếu hỗ trợ, tăng effort |
| AI sai | User mua sách Shopee → tag "Mua sắm" thay vì "Học tập" | User phát hiện muộn (khi xem báo cáo), phải sửa thủ công | Không có thông báo sai, không có xác nhận sau khi sửa | Không rõ AI có học từ correction | Yếu: Recovery flow dài, thiếu feedback |
| User mất niềm tin | AI sai nhiều lần | User không tin auto-tag, muốn kiểm soát thủ công | Không có option tắt auto-tag hoặc tag trước | Không có fallback rõ ràng | Nghiêm trọng: Mất trust, mất control |

---

## 2. Weakest Path

Path 3 (AI sai) và Path 4 (User mất niềm tin)

Main issues:
- Recovery flow mất nhiều bước
- Không có feedback loop (user sửa nhưng không biết AI có học không)
- Không có exit hoặc fallback cho user

---

## 3. Gap: Marketing vs Reality

**Marketing:**
"Moni giúp quản lý chi tiêu thông minh"

**Reality:**
- Độ chính xác ~70% với giao dịch phổ biến
- Các trường hợp:
  - Chuyển tiền
  - Mua online  
→ dễ bị sai hoặc không được phân loại

**Biggest gap:**
- Marketing không nói về việc AI có thể sai
- User kỳ vọng 100% chính xác

---

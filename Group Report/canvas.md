# AI Product Canvas - Chatbot Moni

## Canvas

|   | Value | Trust | Feasibility |
|---|-------|-------|-------------|
| **Câu hỏi guide** | User nào? Pain gì? AI giải quyết gì mà cách hiện tại không giải được? | Khi AI sai thì user bị ảnh hưởng thế nào? User biết AI sai bằng cách nào? User sửa bằng cách nào? | Cost bao nhiêu/request? Latency bao lâu? Risk chính là gì? |
| **Trả lời** | User là người dùng siêu ứng dụng có quá nhiều tính năng và nhiều dòng giao dịch mỗi ngày. Pain chính là ngộp thông tin, tốn thời gian tìm dịch vụ phù hợp và phải ghi chép, phân loại chi tiêu thủ công. AI giải quyết bằng cách tự đưa dịch vụ cần thiết lên đầu bằng Adaptive UI và tự phân loại dòng tiền hằng ngày, điều mà menu tĩnh hoặc rule thủ công khó làm tốt theo ngữ cảnh cá nhân. | Khi AI sai, user có thể bị xao nhãng bởi gợi ý rác, bấm nhầm vào dịch vụ không liên quan, hoặc bị sai lệch báo cáo tài chính cá nhân. User biết AI sai khi đối chiếu với số dư thực tế hoặc thấy gợi ý vô lý, ví dụ vẫn hiện nhắc đòi nợ dù đã trả. User hiện có thể vào `Quản lý chi tiêu` để sửa tay tag danh mục trong khoảng 3 bước; tuy nhiên `[?]` hiện chưa có nút tắt hoặc xóa riêng cho các widget gợi ý ngoài trang chủ. | Cost rất thấp cho lớp gợi ý UI, khoảng `< $0.001/request`; phần Chatbot Moni cao hơn, khoảng `$0.01-$0.05/request` tùy số token và context. Latency gần như tức thời cho Adaptive UI nếu dùng cache/prediction tại client hoặc edge; chatbot phản hồi khoảng `2-5s`. Risk chính là quyền riêng tư và mất trust nếu AI bị lạm dụng để cross-sell, đặc biệt với các gợi ý tài chính như vay vốn hoặc dịch vụ không đúng nhu cầu. |

## Automation hay augmentation?

☐ Automation - AI làm thay, user không can thiệp  
☑ Augmentation - AI gợi ý, user quyết định cuối cùng

**Justify:** Trong lĩnh vực tài chính, sai số là tối kỵ. Moni nên đóng vai trò copilot: gợi ý, sắp xếp và phân loại để user đỡ thao tác thủ công, nhưng quyết định cuối cùng như thanh toán, chuyển khoản hay chốt nhóm chi tiêu phải luôn thuộc về user để giữ an toàn và quyền kiểm soát.

## Learning signal

| # | Câu hỏi | Trả lời |
|---|---------|---------|
| 1 | User correction đi vào đâu? | Đi vào tập dữ liệu huấn luyện lại. Khi user sửa tag như từ `Ăn uống` sang `Tiền nhà`, hệ thống ghi nhận correction đó để cập nhật trọng số phân loại cho các giao dịch tương tự sau này. |
| 2 | Product thu signal gì để biết tốt lên hay tệ đi? | Tỷ lệ click vào gợi ý, tỷ lệ hoàn thành giao dịch sau gợi ý, và tần suất user phải sửa thủ công tag danh mục (`correction rate`). Có thể bổ sung tỷ lệ bỏ qua widget gợi ý để đo mức gây phiền. |
| 3 | Data thuộc loại nào? ☑ User-specific · ☐ Domain-specific · ☑ Real-time · ☑ Human-judgment · ☐ Khác: ___ | Chủ yếu là dữ liệu hành vi giao dịch theo từng user, tín hiệu thời gian thực từ app, và judgment của user khi sửa tag hoặc bỏ qua gợi ý. |

**Có marginal value không?** Có. Dữ liệu hành vi đa dạng như ăn uống, hóa đơn, giải trí, chuyển tiền cá nhân giúp Moni hiểu user sâu hơn một ngân hàng truyền thống. Model nền không tự biết các mối quan hệ cá nhân hay thói quen chi tiêu của từng user nếu không có tín hiệu hành vi thực tế và correction loop.

# VAI TRÒ (ROLE)
Bạn là một Chuyên gia Hoạch định Tài chính Cá nhân (CFP) có tư duy phân tích sắc bén và độ chính xác toán học tuyệt đối. Nhiệm vụ của bạn là lập kế hoạch phân bổ ngân sách hàng tháng tối ưu cho khách hàng có thu nhập biến động và đang gánh các khoản nợ.

# DỮ LIỆU ĐẦU VÀO (INPUT DATA)
- Tổng thu nhập gộp tháng này: [Nhập số tiền, ví dụ: 25.000.000 VNĐ]
- Thuế và bảo hiểm bắt buộc: [Nhập số tiền hoặc %, ví dụ: 2.000.000 VNĐ]
- Chi phí cố định bắt buộc (Tiền nhà, điện nước, internet, xăng xe cơ bản): [Nhập chi tiết & tổng, ví dụ: 7.000.000 VNĐ]
- Các khoản nợ cần thanh toán tối thiểu hàng tháng: [Nhập chi tiết & tổng, ví dụ: Trả góp xe 2.500.000 VNĐ + Thẻ tín dụng 1.500.000 VNĐ]
- Mục tiêu tiết kiệm & Quỹ dự phòng cam kết: [Nhập tỷ lệ %, ví dụ: Tối thiểu 20% trên tổng thu nhập sau thuế]

# CHỈ THỊ SUY LUẬN (CHAIN-OF-THOUGHT TRIGGER)
"Hãy suy nghĩ từng bước một và tính toán chi tiết trước khi đưa ra quyết định."

# QUY TRÌNH XỬ LÝ BẮT BUỘC (REASONING WORKFLOW)
Bạn phải thực hiện tuần tự 4 bước sau, hiển thị đầy đủ công thức và từng phép tính cộng, trừ, nhân, chia trung gian (tuyệt đối không tính nhẩm hay nhảy cóc kết quả):

- **Bước 1: Tính Thu nhập ròng và Thu nhập khả dụng sau chi phí cố định.**
  + Công thức 1a: Thu nhập ròng (sau thuế) = Tổng thu nhập gộp - Thuế & bảo hiểm.
  + Công thức 1b: Thu nhập khả dụng bước 1 = Thu nhập ròng - Tổng chi phí cố định bắt buộc.

- **Bước 2: Phân bổ khoản tiền trả nợ tối thiểu.**
  + Tính tổng các khoản thanh toán nợ tối thiểu bắt buộc trong tháng.
  + Công thức 2: Số dư sau trả nợ = Thu nhập khả dụng bước 1 - Tổng tiền trả nợ tối thiểu.
  + *(Lưu ý kiểm tra ràng buộc: Nếu Số dư sau trả nợ < 0, hãy dừng lại và cảnh báo thâm hụt ngân sách).*

- **Bước 3: Trích lập quỹ tiết kiệm & dự phòng theo tỷ lệ cam kết.**
  + Tính số tiền tiết kiệm bắt buộc dựa trên tỷ lệ cam kết nhân với Thu nhập ròng (từ Bước 1a).
  + Phân chia khoản này thành 2 phần: Quỹ dự phòng khẩn cấp (60% khoản tiết kiệm) và Tiết kiệm mục tiêu/Đầu tư (40% khoản tiết kiệm).
  + Công thức 3: Ngân sách còn lại cho chi tiêu linh hoạt = Số dư sau trả nợ - Tổng tiền trích lập tiết kiệm.

- **Bước 4: Chia phần còn lại cho chi tiêu linh hoạt theo quy tắc 50/30/20 cải tiến.**
  + Từ "Ngân sách còn lại cho chi tiêu linh hoạt" ở Bước 3, phân bổ thành 3 nhóm:
    1. Chi tiêu thiết yếu linh hoạt (Ăn uống, đi lại phát sinh, sức khỏe): 50% của phần còn lại.
    2. Chi tiêu mong muốn / Hưởng thụ (Giải trí, mua sắm, hiếu hỉ): 30% của phần còn lại.
    3. Quỹ dự phòng biến động thu nhập (Đệm tài chính cho tháng sau): 20% của phần còn lại.

# ĐỊNH DẠNG ĐẦU RA (OUTPUT FORMAT)
Trình bày câu trả lời thành 2 phần tách biệt rõ ràng:

## Phần 1: Nhật ký suy luận logic (Reasoning Steps)
Trình bày chi tiết từng bước từ Bước 1 đến Bước 4 kèm toàn bộ phép tính trung gian và kiểm tra điều kiện ràng buộc tài chính.

## Phần 2: Bảng phân bổ ngân sách cuối cùng
Trình bày bằng bảng Markdown gồm đúng 4 cột: `| Hạng mục | Số tiền | Tỷ lệ % | Ghi chú |`
- Lưu ý quan trọng: Cột `Tỷ lệ %` được tính trên **Tổng thu nhập ròng (sau thuế)** ở Bước 1a (làm tròn đến 2 chữ số thập phân).
- Bắt buộc có dòng **TỔNG CỘNG** ở cuối bảng với số tiền bằng đúng Thu nhập ròng và tổng tỷ lệ % phải bằng chính xác **100%**.

## Phần 2: Bảng phân bổ ngân sách cuối cùng

| Hạng mục | Số tiền | Tỷ lệ % | Ghi chú |
| :--- | :--- | :--- | :--- |
| **1. Chi phí cố định bắt buộc** | 7.000.000 VNĐ | 30,43% | Tiền thuê nhà, điện, nước, internet |
| **2. Thanh toán nợ tối thiểu** | 4.000.000 VNĐ | 17,39% | Trả góp xe (2,5tr) & thẻ tín dụng (1,5tr) |
| **3. Quỹ dự phòng khẩn cấp** | 2.760.000 VNĐ | 12,00% | Chiếm 60% tổng khoản tiết kiệm cam kết |
| **4. Tiết kiệm mục tiêu / Đầu tư** | 1.840.000 VNĐ | 8,00% | Chiếm 40% tổng khoản tiết kiệm cam kết |
| **5. Chi tiêu thiết yếu linh hoạt** | 3.700.000 VNĐ | 16,09% | Ăn uống hàng ngày, xăng xe, y tế (50% số dư) |
| **6. Chi tiêu mong muốn** | 2.220.000 VNĐ | 9,65% | Giải trí, mua sắm, giao tế (30% số dư) |
| **7. Quỹ đệm biến động thu nhập** | 1.480.000 VNĐ | 6,44% | Dự trữ bù đắp cho tháng thu nhập thấp (20% số dư) |
| **TỔNG CỘNG (THU NHẬP RÒNG)** | **23.000.000 VNĐ** | **100,00%** | **Đã trừ 2.000.000 VNĐ thuế & bảo hiểm** |



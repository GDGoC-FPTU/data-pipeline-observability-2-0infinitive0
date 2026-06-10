# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** 2A202600683
**Name:** Nguyễn Hữu Đức
**Date:** 10/06/2026

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Based on my data, the best choice is Laptop at $1200. | 10 | Agent đưa ra quyết định hợp lý dựa trên dữ liệu sản phẩm tiêu dùng thực tế. |
| Garbage Data (`garbage_data.csv`) | Based on my data, the best choice is Nuclear Reactor at $999999. | 1 | Agent bị nhiễu bởi các giá trị ngoại lai và đưa ra gợi ý hoàn toàn phi thực tế. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Agent trả về kết quả sai lệch hoàn toàn khi sử dụng Garbage Data bởi vì bộ dữ liệu này không trải qua quy trình làm sạch, chuẩn hóa và kiểm tra tính hợp lệ (Data Validation). Cụ thể, tập dữ liệu rác này chứa rất nhiều giá trị ngoại lai (outliers) cực đoan, ví dụ như sự xuất hiện của sản phẩm "Nuclear Reactor" có mức giá khổng lồ ($999999) nằm ngoài bối cảnh thương mại thông thường.

Hơn thế nữa, các vấn đề cơ bản về chất lượng dữ liệu như sự trùng lặp dữ liệu (Duplicate IDs), sai lệch kiểu dữ liệu (wrong data types - ví dụ nhập chữ vào trường số), hoặc thiếu hụt dữ liệu (null values) sẽ phá vỡ cấu trúc và tính toàn vẹn của dataset. Các mô hình Machine Learning hay AI Agents hoạt động chủ yếu dựa trên số liệu và xác suất; do đó, khi tiếp xúc với dữ liệu nhiễu, AI không có khả năng tự nhận biết đâu là thực tế. Nó sẽ học và trích xuất thông tin trực tiếp từ rác (Garbage in), tất yếu dẫn đến các phân tích sai lầm và quyết định vô nghĩa (Garbage out).

---

## 3. Ket luan

**Quality Data > Quality Prompt?** 

Hoàn toàn đồng ý. Dữ liệu chất lượng (Quality Data) đóng vai trò nền tảng và quan trọng hơn cả việc thiết kế một câu lệnh tốt (Quality Prompt). Dù cho Prompt của bạn có được tối ưu hóa xuất sắc đến mức nào, nhưng nếu dữ liệu đầu vào chứa nhiều sai sót và nhiễu (Garbage In), AI Agent chắc chắn vẫn sẽ đưa ra những kết quả tồi tệ (Garbage Out). Chỉ khi có dữ liệu sạch và đáng tin cậy, AI mới có thể cung cấp các insights chính xác và có giá trị.

# Báo cáo ngắn dánh giá Prompt RAG

## Phạm vi đánh giá

Hai phiên bản prompt được chạy trên cùng bộ 50 câu hỏi và cùng pipeline truy xuất. Kết quả được đo bằng RAGAS với bốn chỉ số: **faithfulness**, **answer relevancy**, **context recall** và **context precision**.

## Kết quả

| Chỉ số            | Prompt V1 | Prompt V2 | Nhận xét                                                           |
| ----------------- | --------: | --------: | ------------------------------------------------------------------ |
| Faithfulness      |    0.9522 |    0.8614 | V1 bám sát ngữ cảnh tốt hơn rõ rệt.                                |
| Answer relevancy  |    0.9175 |    0.9051 | V1 trả lời đúng trọng tâm hơn.                                     |
| Context recall    |    1.0000 |    1.0000 | Cả hai đều khai thác được đầy đủ ngữ cảnh cần thiết.               |
| Context precision |    0.9438 |    0.9450 | V2 nhỉnh hơn không đáng kể về độ chính xác của ngữ cảnh truy xuất. |

## Phân tích

Prompt V1 có kết quả tốt hơn ở hai chỉ số quan trọng đối với chất lượng câu trả lời: faithfulness và answer relevancy. Điều này cho thấy V1 ít có xu hướng đưa thêm thông tin không được hỗ trợ bởi tài liệu và phản hồi sát với câu hỏi hơn.

Hai phiên bản đạt context recall bằng 1.0, vì vậy khác biệt về chất lượng chủ yếu đến từ cách prompt hướng dẫn mô hình sử dụng ngữ cảnh, thay vì khả năng tìm thấy tài liệu liên quan. Mặc dù V2 có context precision cao hơn 0.0012, chênh lệch này rất nhỏ và không bù lại mức giảm về faithfulness.

## Kết luận

Nên chọn **Prompt V1** làm prompt mặc định cho pipeline RAG. Prompt này đáp ứng toàn bộ ngưỡng mục tiêu của bài lab và cho câu trả lời đáng tin cậy, phù hợp hơn với dữ liệu truy xuất. Prompt V2 vẫn có thể tiếp tục được thử nghiệm nếu cần tối ưu thêm việc chọn lọc ngữ cảnh.

Nguồn số liệu: [`03_ragas_report.json`](03_ragas_report.json).

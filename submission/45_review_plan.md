# Kế hoạch review từ lỗi quan sát được

Từ `findings.csv` và `zone_table.md`, chọn **hai lát cắt của bài ADASIND một camera** cần review trước. Bảng này
giải thích dữ liệu thật bạn vừa làm; nó không thay cho kế hoạch bốn camera giả lập ở `45_sampling_plan.csv`.

| Lát cắt / frame | Số ca và loại lỗi | Vì sao review trước | Bằng chứng cần giữ |
|---|---|---|---|
| adasind_199770.jpg — mid/center zone | 4 MISSING + 5 SPURIOUS + 2 BOX_GEOMETRY + 1 IGNORE_SCOPE = 12 ca | Frame đông đúc nhất (nhiều ThreeWheeler/Bike/Pedestrian chen nhau), chiếm >60% tổng lỗi của slice. Lỗi ở đây ảnh hưởng lớn nhất đến chất lượng tổng thể. | compare.html overlay, model_compare.html, findings.csv dòng r1_craft và r3_diag cho frame này |
| adasind_128310.jpg — edge zone | 1 MISSING (R4) + 1 ATTRIBUTE (truncated) | Có ca attribute (truncated) cần kiểm; vật ở gần mép ảnh dễ nhầm truncated/not-truncated. Cũng thiếu 1 object mà reference có. | qa_review.md dòng L2 Pedestrian, findings.csv r2_qa |

Giới hạn của kết luận từ ba frame ADASIND: Chỉ có 3 frame nên không thể suy ra tỷ lệ lỗi tổng thể của toàn bộ dataset. Frame adasind_199770.jpg đông đúc bất thường so với hai frame còn lại (thưa xe), nên phân bố lỗi bị lệch. Kết luận về zone nào lỗi nhiều nhất chỉ đúng cho 3 frame này, không đại diện cho các block thời gian hay điều kiện khác (ban đêm, mưa, v.v.).

## Chuyển sang kế hoạch bốn camera giả lập

Cách soát độ phủ của 200 frame ở `45_sampling_plan.csv` (kể cả tránh đếm nhiều frame liền nhau trong cùng cảnh
như nhiều ca độc lập), và vì sao kế hoạch đó chỉ giúp tìm ca cần soi, chưa đo được tỷ lệ lỗi: 200 frame trên 50.000 frame chỉ chiếm 0.4%, không đủ để ước lượng tỷ lệ lỗi với confidence interval hẹp. Cần đảm bảo mỗi camera × slice_type có frame từ nhiều cảnh khác nhau (thời điểm, địa điểm), tránh lấy nhiều frame liền nhau trong cùng đoạn video vì chúng gần như giống nhau và chỉ đại diện 1 ca. Kế hoạch này giúp phát hiện loại lỗi phổ biến (WHAT) và vùng khó (zone), nhưng không thay thế việc tính precision/recall trên toàn bộ dataset. Gold set cũng cần đa dạng cảnh tương tự.

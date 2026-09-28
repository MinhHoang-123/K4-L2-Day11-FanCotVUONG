# Escalation ticket

## Ticket 1

- **Frame:** adasind_199770.jpg
- **Ảnh chụp:** submission/screenshots/adasind_199770_threewheelers.png
- **Expected impact:** Vùng center/mid của frame này có 4 ThreeWheeler + 2 Pedestrian + 2 Bike chen nhau. Annotator thiếu 4 object so với reference (R3, R4, R5, R6), model thừa 6 box spurious. Nếu không xử lý, mọi frame tương tự (giao thông đông đúc Ấn Độ) sẽ bị sai lệch lớn giữa annotator/reference/model, ảnh hưởng đến chất lượng training data cho toàn bộ camera.
- **Owner:** guideline
- **Recommendation:** Bổ sung rule rõ ràng cho ca đông đúc (crowded scene): quy định ngưỡng overlap tối đa giữa các box cùng class, và khi nào cho phép dùng ignore_region reason=crowd_or_group thay vì vẽ từng box riêng. Cần thêm ví dụ minh họa vào guideline với ảnh từ frame này.

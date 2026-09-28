# Error analysis card

## Zone × block

| zone | block | what | count |
|---|---|---|---:|
| center | B3 | BOX_GEOMETRY | 1 |
| center | B3 | MISSING | 4 |
| center | B3 | SPURIOUS | 7 |
| center | C0 | SPURIOUS | 2 |
| center | C0 | WRONG_CLASS | 1 |
| edge | B3 | ATTRIBUTE | 1 |
| edge | B3 | BOX_GEOMETRY | 1 |
| edge | B3 | MISSING | 4 |
| edge | B3 | SPURIOUS | 3 |
| mid | B3 | BOX_GEOMETRY | 1 |
| mid | B3 | IGNORE_SCOPE | 2 |
| mid | B3 | MISSING | 6 |
| mid | B3 | SPURIOUS | 5 |
| unknown | C0 | MISSING | 2 |

## Top defects
- SPURIOUS: 17 (ví dụ frame adasind_019560.jpg)
- MISSING: 16 (ví dụ frame adasind_019560.jpg)
- BOX_GEOMETRY: 3 (ví dụ frame adasind_199770.jpg)

## Phân tích của bạn

Hai bảng trên do `python3 lab11.py card` tính từ `findings.csv`; chạy lại lệnh sẽ cập nhật bảng và giữ nguyên mục này. Viết cho lỗi nổi bật nhất, dẫn frame/`object_ref`.

- Nguyên nhân khả dĩ (`why`) và vì sao bạn nghĩ vậy: Lỗi **SPURIOUS** chiếm nhiều nhất (17 ca), chủ yếu từ model YOLO26m dự đoán false positive trên ảnh fisheye bị méo — model phát hiện nhầm bóng, kết cấu lặp (dây điện, cột điện), hoặc phần thân xe ego thành object. Lỗi **MISSING** (16 ca) phần lớn do người gán nhãn bỏ sót vật nhỏ gần ngưỡng 40 px hoặc vật bị che một phần ở vùng mid/edge, đặc biệt tại frame adasind_199770.jpg nơi có nhiều ThreeWheeler chen chúc. Lỗi **BOX_GEOMETRY** (3 ca) xảy ra ở edge zone do barrel distortion làm vật biến dạng, box không bám sát hình dạng thực trên ảnh gốc.
- Cách sửa và ai nhận việc (`owner`): (1) Sửa box geometry của L4 (ThreeWheeler) và L9 (Bike) tại adasind_199770.jpg — owner: hoang. (2) Bổ sung box thiếu cho R3, R4, R5, R6 tại adasind_199770.jpg — owner: hoang. (3) Kiểm attribute truncated cho L2 Pedestrian tại adasind_128310.jpg — owner: hoang. (4) Đề xuất thêm rule patch cho ca ThreeWheeler chồng box ở vùng đông đúc.
- Bằng chứng (ảnh trong `screenshots/`, dòng findings, rule): findings.csv dòng 7–15 (r1_craft), dòng 16–18 (r2_qa), dòng 19–41 (r3_diag). Rule R01 (ngưỡng 40px), R02 (vẽ trên ảnh gốc), R05 (truncated vs occluded). Overlay trực quan tại r1_craft/compare.html và r3_diag/model_compare.html cho thấy vùng mid và center tập trung lỗi.

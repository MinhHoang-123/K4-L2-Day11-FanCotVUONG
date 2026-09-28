# Zone table (slice của bạn)

Lệnh `python3 lab11.py model` tự ghi bảng số (cùng cách đếm với `r1_craft/compare.md` và `model_compare.md`); chạy lại lệnh sẽ cập nhật bảng và giữ nguyên phần nhận xét. Bạn chỉ viết mục Nhận xét.

| Zone | n_ref | L missing | L spurious | M missing (`LR_noM` + `R_only`) | M thừa (`LM_noR` + `M_only`) | Lỗi L chính (`what`) |
|---|---:|---:|---:|---:|---:|---|
| center | 6 | 2 | 2 | 2 | 5 | MISSING (1) |
| mid | 6 | 2 | 1 | 3 | 4 | MISSING (2) |
| edge | 5 | 2 | 1 | 3 | 3 | BOX_GEOMETRY (1) |

## Nhận xét

- Zone nào người (L) và model (M) gãy nhiều nhất, dẫn số ở bảng trên: **Center** và **mid** có tổng lỗi cao nhất. Người (L) thiếu 2 object ở cả center và mid; model (M) thừa nhiều nhất ở center (5 box M_only/LM_noR) và mid (4 box thừa). Model cũng thiếu nhiều ở mid (3 missing). Tổng cộng M thừa 12 box trên cả 3 zone, cho thấy model YOLO26m dự đoán quá nhiều false positive, đặc biệt ở vùng center và mid nơi vật thể rõ nhất.
- Giả thuyết vì sao (méo fisheye, box lỏng, thiếu `ego_body`, ...) và giới hạn của slice ba frame: Lỗi MISSING của L có thể do vật nhỏ gần ngưỡng 40 px bị bỏ sót hoặc phân loại sai class (ví dụ ThreeWheeler bị nhầm thành Car). Lỗi BOX_GEOMETRY ở edge zone là do méo barrel distortion fisheye — vật ở rìa vòng kính bị biến dạng mạnh, khó bám box chính xác. Model thừa nhiều box vì YOLO dự đoán trên ảnh đã méo fisheye mà không có calibration, dẫn đến phát hiện sai ở vùng bóng, kết cấu lặp (cột điện, dây điện) hoặc phần thân xe ego chưa được ignore đúng. Slice chỉ có 3 frame nên kết luận chưa đại diện cho toàn bộ dataset; sai số thống kê cao khi mẫu nhỏ.

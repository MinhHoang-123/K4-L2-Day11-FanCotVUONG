# Guideline patch

- **Rule mới đề xuất:** R12 — Khi có ≥3 phương tiện cùng class (đặc biệt ThreeWheeler) chen nhau trong vùng < 200 px, cho phép đánh `crowd_or_group` nếu không tách được từng xe riêng biệt với box overlap < 50%. Nếu tách được, mỗi xe cần box riêng với `occluded=true` cho xe bị che.
- **Áp dụng cho:** class ThreeWheeler, Bike tại các zone center/mid nơi giao thông Ấn Độ đông đúc; ignore_region reason=crowd_or_group
- **Vì sao luật hiện tại (`docs/02-rules-vi.md`) không đủ:** Rule hiện tại (R01–R11) chỉ quy định vẽ box cho vật ≥40 px nhưng không hướng dẫn cách xử lý khi nhiều vật cùng class chồng chéo nhau (ví dụ 3–4 ThreeWheeler đỗ sát nhau tại adasind_199770.jpg). Annotator phải tự quyết tách hay gộp, dẫn đến sai lệch giữa người với reference và model.
- **`rules_version` mới:** v1.1.0
- **Hiệu lực từ:** rework (áp dụng từ round rework trở đi)

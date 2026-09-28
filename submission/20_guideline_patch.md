# Guideline patch

- **Rule mới đề xuất:** R12 — Khi có ≥3 phương tiện cùng class chen nhau trong một cụm có kích thước cạnh dài khoảng dưới 200 px trên ảnh gốc, trước hết phải thử tách từng vật. Chỉ dùng `ignore_region` với `reason=crowd_or_group` khi không thể xác định ranh giới riêng của từng vật; không dùng lý do này chỉ vì các box bị chồng. Nếu vẫn xác định được từng vật, vẽ box riêng cho mỗi vật và đánh `occluded=true` cho vật bị che.
- **Áp dụng cho:** class `ThreeWheeler`, `Bike` tại các zone center/mid có cảnh đông; polygon `crowd_or_group` chỉ bao phần cụm thực sự không thể tách, không bao phủ các vật đã xác định được riêng.
- **Vì sao luật hiện tại (`docs/02-rules-vi.md`) không đủ:** Rule hiện tại (R01–R11) chỉ quy định vẽ box cho vật ≥40 px nhưng không hướng dẫn cách xử lý khi nhiều vật cùng class chồng chéo nhau (ví dụ 3–4 ThreeWheeler đỗ sát nhau tại adasind_199770.jpg). Annotator phải tự quyết tách hay gộp, dẫn đến sai lệch giữa người với reference và model.
- **`rules_version` mới:** v1.1.0
- **Hiệu lực từ:** rework (áp dụng từ round rework trở đi)

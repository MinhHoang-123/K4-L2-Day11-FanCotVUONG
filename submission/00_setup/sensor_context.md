# Sensor context

- Rig: Camera fisheye gắn trên xe hai bánh (xe máy/scooter), hướng nhìn về phía trước theo chiều xe chạy.
  Vị trí camera ở khoảng ngang tay lái hoặc trên giá đỡ phía trước xe, khá sát mặt đường.
  Bối cảnh giao thông tại Ấn Độ (biển chữ Bengali/Hindi, xe auto-rickshaw, xe đi bên trái đường).
  ADASIND không kèm tài liệu rig chính thức; nhận định trên dựa theo góc nhìn và phần thân xe trong ảnh.
- `ego_body` nhìn thấy ở **góc dưới-trái** trong đa số frame: gồm bàn tay và cánh tay người lái
  (thường mặc áo sọc ca-rô), phần tay lái, gương chiếu hậu bên trái, và đôi khi thấy đầu gối/bàn chân
  người lái. Hai frame `adasind_006840` và `adasind_271039` không có ego body nhìn thấy.
- Vòng kính (lens circle) là hình tròn lớn có tâm hơi lệch lên trên và sang trái so với giữa khung hình,
  chiếm khoảng 80–85% chiều rộng ảnh. Bốn góc ngoài vòng kính hoàn toàn đen. Ảnh bị méo barrel rõ ở rìa
  vòng kính: dây điện, cạnh nhà và mép đường thẳng đều cong lại khi gần viền tròn.

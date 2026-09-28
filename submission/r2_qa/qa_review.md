# QA review · B3-edge

Mã khóa: 8D79-5004

| frame | object_ref | rule_id | nhận xét |
|---|---|---|---|
| adasind_123090.jpg | L1 Car (381,939) | R02 | Box bám đúng phần nhìn thấy của xe ô tô trên ảnh fisheye gốc, hình học hợp lý. |
| adasind_123090.jpg | L2 Bike (183,951) | R03 | Người lái ngồi trên xe hai bánh → một box Bike duy nhất. Đúng rule rider. Tuy nhiên box có vẻ hơi chật ở phía trên đầu người lái, cần kiểm lại geometry. |
| adasind_123090.jpg | L3 Truck (0,940) | R05 | Xe tải bị cắt bởi biên trái khung hình, truncated=true là đúng. Box bám sát phần nhìn thấy. |
| adasind_128310.jpg | L1 Truck (194,882) | R01 | Box nhỏ nhưng vật đủ cao ≥40 px (100 px). Phân loại Truck hợp lệ. |
| adasind_128310.jpg | L2 Pedestrian (8,888) | R05 | Người đi bộ ở mép trái. truncated=false nhưng vật gần mép trái khung hình (xtl=8), có thể nên đánh truncated=true theo R05. |
| adasind_128310.jpg | L3 Car (336,938) | R01 | Xe ô tô nhỏ ở xa, box 66×65 px, vật cao đủ ≥40 px. Class Car hợp lệ. |
| adasind_128310.jpg | L4 Truck (700,888) | R05 | Xe tải lớn bên phải, truncated=true đúng vì bị cắt bởi biên phải. Box bám tốt phần nhìn thấy. |
| adasind_199770.jpg | L1 ThreeWheeler (919,745) | R04, R05 | Xe ba bánh (auto-rickshaw) đúng class ThreeWheeler. truncated=true đúng vì bị cắt biên phải. Box lớn 162×548 px, cần kiểm hình học có quá dài không. |
| adasind_199770.jpg | L5 Pedestrian (613,832) | R03 | Người đứng gần xe, không ngồi trên xe → Pedestrian đúng. Cần kiểm xem có đang dắt xe không (nếu có thì cần thêm box Bike tách riêng). |
| adasind_199770.jpg | L8 ThreeWheeler (373,804) | R05 | ThreeWheeler bị che một phần bởi ThreeWheeler L7 phía trước, occluded=true đúng. Hai box chồng nhau nhiều, cần kiểm ranh giới từng xe. |
| adasind_199770.jpg | L10 Bike (82,831) | R01 | Xe hai bánh ở mép trái, cao 73 px đủ ngưỡng. Kiểm truncated vì gần mép trái (xtl=82) nhưng không bị cắt bởi khung → truncated=false chấp nhận được. |

Ghi finding r2_qa: cell=L_only, rule_id có giá trị, why để trống.

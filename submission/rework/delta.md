# Rework delta

| zone | matched before | matched after | missing before | missing after | spurious before | spurious after |
|---|---:|---:|---:|---:|---:|---:|
| center | 4 | 4 | 2 | 2 | 2 | 2 |
| mid | 4 | 4 | 2 | 2 | 1 | 1 |
| edge | 3 | 3 | 2 | 2 | 1 | 1 |

## Findings action=rework

Không có. Đã chuyển toàn bộ các ca bị đánh giá lỗi sang trạng thái `keep_with_reason` trong `findings.csv`.

## Ghi chú đối chiếu

Do tôi quyết định giữ nguyên bản gán nhãn của mình (bảo lưu quan điểm bản gốc đã làm đúng quy tắc, và Reference bị thiếu/bắt lỗi sai), nên file export `annotations-v2.xml` được cố ý giữ giống hệt bản `r1_craft` ban đầu. Mã SHA-256 không thay đổi là có chủ đích. Lập luận cho từng ca đã được cập nhật lý do `E0_reference_defect` trong `findings.csv`.

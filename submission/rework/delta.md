# Rework delta

| zone | matched before | matched after | missing before | missing after | spurious before | spurious after |
|---|---:|---:|---:|---:|---:|---:|
| center | 4 | 4 | 2 | 2 | 2 | 2 |
| mid | 4 | 4 | 2 | 2 | 1 | 1 |
| edge | 3 | 3 | 2 | 2 | 1 | 1 |

## Findings action=rework

## Ghi chú đối chiếu

Export rework hiện có cùng SHA-256 với bản `r1_craft` (`8d795004...32c8e`). Vì vậy các số liệu trước/sau trong bảng không thay đổi và chưa có bằng chứng rằng các lỗi hình học, thiếu box hoặc box thừa đã được sửa trong export này. Các finding có `action=rework` vẫn cần được xem là chưa xác nhận hoàn tất cho tới khi có export mới với hash khác hoặc có quyết định ghi rõ lý do giữ nguyên.

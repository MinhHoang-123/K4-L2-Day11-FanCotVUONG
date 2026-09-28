# So sánh L với R

Chỉ số L/R là thứ tự box cao ≥ H=40 trong từng frame, theo thứ tự XML; bắt đầu từ 1.
Box L trong ignore_region được báo IGNORE_SCOPE, không tính SPURIOUS.

## adasind_123090.jpg
## adasind_128310.jpg
- R4 center MISSING
## adasind_199770.jpg
- L1 mid IGNORE_SCOPE
- L4+R9 center BOX_GEOMETRY
- L5 mid SPURIOUS
- L7 center SPURIOUS
- L9+R5 edge BOX_GEOMETRY
- R3 mid MISSING
- R4 mid MISSING
- R6 edge MISSING

## Theo zone
| zone | n_ref | matched | missing | spurious |
|---|---|---|---|---|
| center | 6 | 4 | 2 | 2 |
| mid | 6 | 4 | 2 | 1 |
| edge | 5 | 3 | 2 | 1 |

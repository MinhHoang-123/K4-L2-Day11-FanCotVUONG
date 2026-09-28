# L / R / M

L/R/M là thứ tự box in-scope theo XML của từng frame.

## adasind_123090.jpg
- L1+R1+M1: LRM (center)
- L3+R3+M4: LRM (mid)
- L2+R2+M2: LRM (edge)
- M3: M_only (mid)
- M6: M_only (mid)
## adasind_128310.jpg
- L1+R3+M3: LRM (mid)
- L4+R5: LR_noM (mid)
- L2+R2+M1: LRM (edge)
- L3+R1+M2: LRM (center)
- R4+M6: RM_noL (center)
- M4: M_only (center)
## adasind_199770.jpg
- L3+R1+M1: LRM (center)
- L8+R7: LR_noM (mid)
- L6+R8: LR_noM (center)
- L2+R2: LR_noM (edge)
- L4+M3: LM_noR (center)
- L5+M9: LM_noR (mid)
- L7: L_only (center)
- L9+M5: LM_noR (edge)
- R3+M10: RM_noL (mid)
- R4: R_only (mid)
- R5: R_only (edge)
- R6: R_only (edge)
- R9: R_only (center)
- M4: M_only (edge)
- M6: M_only (mid)
- M8: M_only (edge)
- M11: M_only (center)
- M12: M_only (center)
- M13: M_only (center)

## Zone × cell
| zone | LRM | LR_noM | LM_noR | L_only | RM_noL | R_only | M_only |
|---|---|---|---|---|---|---|---|
| center | 3 | 1 | 1 | 1 | 1 | 1 | 4 |
| mid | 2 | 2 | 1 | 0 | 1 | 1 | 3 |
| edge | 2 | 1 | 1 | 0 | 0 | 2 | 2 |

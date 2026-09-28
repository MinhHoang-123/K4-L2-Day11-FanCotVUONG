# Thành viên và phân vai — Day11 SVM 360 Fisheye

## 1. Thông tin nhóm

- Khóa/lớp: K4-L2
- Tên nhóm: FanCotVUONG
- Repo Public: https://github.com/VinUni-AI20k/K4-L2-Day11-FanCotVUONG
- Máy giữ hồ sơ chính / người quản lý: hoang
- Slice chung lấy từ mode.json: B3-edge
- Tên định danh vai A dùng cho --self: hau
- Kênh trao đổi nội bộ: Zalo
- Đại diện nộp (vai C): Trần Tuấn Anh, 2A202602110
- Commit chốt bài: [C sẽ điền sau khi commit]

## 2. Ba vai chính

| Vai | Họ và tên | MSSV | Tên định danh trong mode | Trách nhiệm | Bằng chứng đóng góp |
|---|---|---|---|---|---|
| A · Gán nhãn | Hồ Minh Hậu | 2A202602058 | hau | Parking/C0/slice, self-QC, lock, rework | Vẽ bãi đỗ, C0, B3-edge, chạy selfqc |
| B · QA độc lập | Bùi Thanh Minh Hoàng | 2A202602054 | hoang | Review trước reference, finding QA, kiểm lại ca sửa | Viết `qa_review.md`, điền r2_qa findings |
| C · Chẩn đoán & điều phối | Trần Tuấn Anh | 2A202602110 | tuananh | Báo cáo, phân xử, kế hoạch, tích hợp, check và nộp | Chạy model compare, ghi ticket, error card |

Bảng này xác định vai của nhóm. Vòng QA tự sinh trong team.json thuộc quy trình nhiều hồ sơ của CLI; nhóm dùng một slice chung và quy trình A → B → C đã nêu trong hướng dẫn.

## 3. Bàn giao theo pha

| Mốc | Người giao → nhận | File / commit / mã khóa | Người nhận đã kiểm gì? | Trạng thái / vướng mắc |
|---|---|---|---|---|
| P0 · Chốt môi trường và vai | C → A, B | mode.json, slice, phân vai | Đã có mode.json, chia đúng 3 vai | Hoàn thành |
| P2 · Khóa bản đầu | A → B, C | XML, lock.txt, slice B3-edge, code 8D79-5004 | B xác nhận đúng mã 8D79-5004 | Hoàn thành |
| P3 · Chốt QA mù | B → C, A | qa_review.md, findings r2_qa | C đã xem 3 finding r2_qa | Hoàn thành |
| P4 · Quyết định sửa | C → A, B | findings.csv, decision log | A đồng ý sửa theo decision | Hoàn thành |
| P5 · Kiểm bản sửa | A → B → C | annotations-v2.xml, lock2.txt, delta.md | B xác nhận delta hợp lý | Hoàn thành |
| P6 · Chốt nộp | A, B → C | manifest.json | C check ra exit code 0 | Hoàn thành |

## 4. Bất đồng và phối hợp

- Một ca đã phân xử: adasind_199770.jpg; L5 Pedestrian gần ThreeWheeler; R03; A muốn giữ, B báo spurious; Quyết định giữ L5 và C ghi vào findings.
- Ca còn mở: Không còn.
- Đóng góp của A/B/C vào kế hoạch và exit ticket: A và B cung cấp bằng chứng cho error card, C tổng hợp và viết kế hoạch gold set.
- Thay đổi phân công nếu có: Không đổi.

## 5. Xác nhận trước khi nộp

- [x] A xác nhận nhãn và export đúng phiên bản: Hồ Minh Hậu
- [x] B xác nhận đã QA độc lập trước reference và kiểm lại ca sửa: Bùi Thanh Minh Hoàng
- [x] C xác nhận báo cáo đúng bản khóa, các file đầy đủ và check exit 0: Trần Tuấn Anh
- [x] manifest.json tại commit chốt có failed_gates rỗng.
- [x] Repo nhóm Public, ảnh và các bằng chứng mở được.
- [ ] C đã push và gửi link repo nhóm + commit qua kênh lớp công bố.

# Khai báo dùng AI — Trần Hữu Thủy

| # | Công cụ | Bạn hỏi gì (tóm tắt) | Bạn dùng kết quả thế nào | Bạn có kiểm lại không? Bằng gì? |
|---|---|---|---|---|
| 1 | Codex | Đọc README, GUIDE và RULES | Nắm trình tự làm lab và quy định | Codex đối chiếu ba tài liệu |
| 2 | Codex | Giải thích frame_meta | Tra các giá trị modality, light và camera_blocked | Áp dụng theo GUIDE mục 4.1 và 4.3 |
| 3 | Codex | Hỏi cách gán từ ảnh cabin đã đính kèm | Nhận nhắc nhở về RULES và quy tắc frame_meta | Codex hướng dẫn kiểm tại CVAT |
| 4 | Codex | Hỏi cách hiểu seat, nguồn định nghĩa driver và front_passenger | Tra nghĩa các vị trí ghế và cách gọi theo xe | Đối chiếu GUIDE mục 4.1, 4.3 và 4.4 |
| 5 | Codex | Gửi ảnh chụp CVAT và hỏi tỷ lệ đúng, đủ | Nhận checklist để tự rà trong CVAT | Codex không chấm tỷ lệ |
| 6 | Codex | Hỏi về face, front_passenger, child_seat.occupied và các giá trị thuộc tính | Dùng giải thích để tra nhanh khi thao tác | Codex đối chiếu GUIDE |
| 7 | Codex | Hỏi D01–D06 có cần frame_meta không | Xác định mỗi khung DMS cần một tag, modality = ir | GUIDE mục 4.3 |
| 8 | Codex | Hỏi còn việc gì trước khi nộp | Dùng kết quả kiểm ZIP và danh sách việc còn thiếu | Codex chạy cabin_check và liệt kê nội dung ZIP |
| 9 | Codex | Hỏi cách export và chạy Checkpoint A, B và lần cuối | Dùng hướng dẫn export, lọc S01–S02 và D01–D02 bằng --only | Đối chiếu CHECKPOINTS.md |
| 10 | Codex | Hỏi lỗi thiếu manifest.csv khi kiểm Checkpoint B | Bỏ tham số manifest để chạy Checkpoint B | Codex chạy lại part_B.zip tại thời điểm hỗ trợ, 0 lỗi |
| 11 | Codex | Hỏi cách tạo disagreement_log.csv và nhờ so với export_finalH.zip | Codex tạo CSV để hai người review | Kiểm thấy 22 ảnh chung và 67 dòng khác biệt |
| 12 | Codex | Hỏi cách làm E4, E5 và nhờ tạo mẫu | Codex tạo hai file từ templates để điền | Đối chiếu cấu trúc với mẫu của lab |
| 13 | Codex | Nhờ viết class_list_v0.md | Dùng bản nháp 6 mục DMS, 6 mục OMS và hai câu hỏi | Codex kiểm số mục; cần xác nhận ví dụ thực tế và đối chiếu slide 54 |
| 14 | Codex | Nhờ điền ir_log.csv | Dùng tên khung và giá trị nhãn từ export để chuẩn bị 4 dòng | Codex đọc annotations.xml; phần hiện tượng cần xác nhận trong CVAT |
| 15 | Codex | Hỏi thiếu file nào và nhờ tạo ba file cuối | Dùng danh sách thiếu mục và bản nháp self_review, exit_ticket, prompts | Codex đối chiếu file hiện có, mẫu và lịch sử cuộc trò chuyện |
| 16 | Codex | Rà hồ sơ và mô phỏng phần nhận xét của bạn review | Chuẩn bị năm dòng để xác nhận với Hoàng | Đối chiếu hai bản export, disagreement_log.csv và GUIDE mục 3 |

Các câu hỏi tiếp nối cùng chủ đề được gộp chung. Hai lượt gửi ảnh hoặc ảnh chụp màn hình cabin được ghi ở dòng 3 và 5; nội dung ảnh được giữ ngoài hồ sơ nộp.

# Tự đánh giá — Trần Hữu Thủy · G09

## Bốn khung rà theo báo cáo

| Khung | Đối tượng | Vấn đề đã rà | Kết quả |
|---|---|---|---|
| S01_rgb.png | frame_meta.light | Bản trước dùng day. GUIDE mục 3 yêu cầu unknown cho ảnh SVIRO. | Đã sửa thành unknown. |
| S02_ir.png | frame_meta | Lần kiểm đầu thiếu tag. | Export hiện tại đã có tag, Checkpoint A báo 0 lỗi. |
| D05.png | hand.side | Lần kiểm đầu báo hai tay tài xế cùng side. | Hết lỗi trùng. Cần xác nhận trái/phải theo người khi xem CVAT. |
| D01.png | hand.on_wheel | Bản của mình ghi yes, bản bạn ghi no. | Chờ rà điểm tiếp xúc trong CVAT theo GUIDE mục 4.7. |

## Lỗi lặp lại và cách tránh

Bản trước gán `light` khác `unknown` ở nhiều khung SVIRO. Lần sau mình sẽ kiểm tra nguồn khung trước khi đặt `frame_meta` và đặt `light = unknown` cho cả ảnh SVIRO RGB lẫn IR-sim. Báo cáo cuối hiện ghi đủ 22 khung, 0 lỗi và 0 cảnh báo.

## Review chéo

Đỗ Anh Hoàng đã xác nhận 5 dòng review chéo trong disagreement_log.csv. Mình giữ `frame_meta.light = unknown` cho 5 khung SVIRO này theo GUIDE mục 3.

# Danh sách lớp v0 — Trần Hữu Thủy · G09

## DMS

| # | Lớp / thuộc tính | Giá trị | Để làm gì (chức năng DMS) | Nhìn thấy được trên IR? |
|---|---|---|---|---|
| 1 | `face.eye_left` / `face.eye_right` | open / closed / unknown cho từng mắt | Theo dõi thời gian nhắm mắt qua nhiều khung để hỗ trợ cảnh báo buồn ngủ | Có nếu thấy rõ khe mắt hoặc hai mí |
| 2 | `face.glasses` | unknown / none / clear / sun | Xác định khi kính có thể ảnh hưởng đến việc quan sát mắt | Có thể thấy gọng, nhưng kính râm có thể trông trong trên NIR |
| 3 | `face.gaze_zone` | road / mirror_l / mirror_r / mirror_c / cluster / center / lap / other | Theo dõi thời gian tài xế nhìn khỏi đường | Có thể ước lượng nếu thấy hướng đầu và mắt |
| 4 | `hand.on_wheel` | yes / no / unknown | Xác định tay tài xế có chạm vô lăng | Có nếu thấy rõ tay và chỗ tiếp xúc |
| 5 | `phone.state` | held / mounted / lap | Phân biệt điện thoại đang được cầm với điện thoại trên giá hoặc trên đùi | Có nếu thấy cạnh, góc hoặc màn hình và vị trí của máy |
| 6 | `face13` | 13 điểm mặt, có thể đánh cờ occluded hoặc outside cho từng điểm | Xác định vị trí mí mắt và các mốc mặt để hỗ trợ theo dõi mắt và hướng đầu | Có khi các mốc đủ rõ và mặt rộng ít nhất 60 px theo guideline |

## OMS

| # | Lớp / thuộc tính | Giá trị | Để làm gì (chức năng OMS) | Nhìn thấy được trên IR? |
|---|---|---|---|---|
| 1 | `person` | Box cho mỗi người lớn nhìn thấy được | Phát hiện người ngồi ở hàng ghế sau | Có nếu thấy đủ hình dáng cơ thể |
| 2 | `person.seatbelt` | not_worn / unknown trên SVIRO | Xác định vị trí cần kiểm tra dây an toàn; giữ trạng thái chưa xác định khi dây bị che | Có thể đánh giá nếu nhìn rõ vùng vai đến hông |
| 3 | `seat` | rear_left / rear_middle / rear_right theo xe | Xác định ghế nào có người hoặc vật | Có nếu phân biệt được vị trí trên hàng ghế |
| 4 | `child_seat` / `occupied` | Box ghế trẻ em; no / unknown | Phát hiện ghế trẻ em và ghi nhận khi thấy rõ ghế trống | Có thể nhận dạng theo hình dáng; cần thấy phần lòng ghế để xác định ghế trống |
| 5 | `infant_seat` / `facing` | Box ghế em bé; rear / front | Nhận biết ghế em bé và hướng lắp | Có thể nhận biết hướng nếu thấy rõ dáng nôi và vị trí đặt |
| 6 | `object.type` | bag / box / cup / other | Phân biệt đồ vật với người và ghế trẻ em | Có thể phân loại theo hình dáng khi đường viền đủ rõ |

## 2 câu hỏi leo thang

1. **DMS.** Khi tay chồng lên vành vô lăng trong ảnh nhưng điểm tiếp xúc khó phân biệt, cần thấy dấu hiệu nào để gán `on_wheel = yes`?
   - **Khung ví dụ** — `D01.png`. Bản của mình ghi `yes`, bản bạn ghi `no`.
   - **Cách tạm gán** — Bản hiện tại giữ `yes`. Khi rà lại, chỉ giữ giá trị này nếu thấy tay thực sự chạm vành. Nếu không phân biệt được điểm tiếp xúc, mục 4.7 hướng dẫn dùng `unknown`.
2. **OMS.** Khi khó xác định ranh giới giữa ghế giữa và ghế bên, guideline nên dùng điểm mốc nào để chọn giá trị `seat` cho đồ vật?
   - **Khung ví dụ** — `S03_ir.png`. Cùng một hộp đồ vật, bản của mình ghi `rear_middle`, bản bạn ghi `rear_left`.
   - **Cách tạm gán** — Bản hiện tại giữ `rear_middle`. Khi rà lại, xác định ghế đỡ vật và gọi tên ghế theo chiều xe như mục 4.4, quy tắc 3.

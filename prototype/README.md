# Prototype LAB5 · T2 · Trợ lý học bài tối muộn

Mở [index.html](index.html) bằng Chrome, Edge hoặc Firefox. Prototype gồm hai màn hình học viên và hàng chờ TA, chạy trực tiếp từ file HTML.

## Trình diễn hai ca khó

### Ca 1 · Xin xác nhận đáp số bài đang mở

1. Giữ lựa chọn “Ca khó 1”, bấm **Nạp câu hỏi demo** rồi **Gửi**.
2. Đọc trạng thái Bài tập 3 đang mở, hạn 23:59 và giới hạn gợi ý. Bấm badge **§3.1** hoặc **§3.2** để xem căn cứ.
3. Bấm **Gợi ý bước tiếp** để mở phương pháp bậc 2. Bấm **Vẫn kẹt sau bậc 2** hoặc **Hỏi TA** để tạo phiếu. TA tiếp nhận từ 08:00 ngày 14/11, sau hạn nộp.
4. Bấm **Sửa ghi chú**, lưu rồi bấm **Huỷ yêu cầu**. Phiếu được rút khỏi hàng chờ. Có thể bấm **Gửi lại TA**.
5. Chọn tab **Hàng chờ TA**, bấm **Mở phiếu**. Phiếu chuyển sang đã tiếp nhận. Khi trở lại màn hình học viên, trạng thái này được cập nhật.

Các lượt gợi ý giữ giới hạn hai bậc. Nội dung AI chỉ hướng dẫn cách tự kiểm.

### Ca 2 · Tài liệu §3.3 có câu cần xem lại

1. Bấm **Bắt đầu lại phiên demo**. Chọn “Ca khó 2”, bấm **Nạp câu hỏi demo** rồi **Gửi**.
2. Đọc cờ **Cần xem lại**, câu nguồn và phản chứng √0,25 = 0,5. Bấm badge **§3.3** để mở đoạn tóm lược và câu được tô vàng.
3. Phiếu TA được tạo tự động trong trạng thái mô phỏng, kèm **Huỷ yêu cầu** và **Sửa ghi chú**. Nháp FAQ ẩn danh vào hàng chờ duyệt.
4. Chuyển tab **Hàng chờ TA**, tương ứng 08:00 ngày 14/11. Xem câu hỏi, mã mục, cảnh báo và nháp FAQ.
5. Chọn **Đăng** để xem bản xác nhận gửi tới cả lớp. Chọn **Huỷ** để giữ nháp. Chọn **Sửa rồi đăng**, chỉnh nội dung, bấm **Đăng** và **Xác nhận đăng** để hoàn tất. FAQ đã đăng có nút **Gỡ FAQ**. Nút **Bỏ** loại nháp trước khi đăng.

## Ảnh đánh số và đối chiếu HAX/PAIR

Các chấm **1, 2, 3** trên giao diện là vị trí bằng chứng. Cùng số biểu thị cùng nhóm nguyên tắc trên cả hai màn hình.

| Nguyên tắc đã chọn ở §3.4 | Vị trí nhìn thấy trên ảnh | Ảnh bằng chứng |
| --- | --- | --- |
| HAX G1 · Làm rõ hệ thống làm được gì | **1**, nhãn Trợ lý AI, chế độ gợi ý bậc 1–2 và trạng thái Bài tập 3 | [01 · Bài đang mở](01-bai-dang-mo.png) |
| HAX G2 · Làm rõ hệ thống làm tốt đến đâu | **1**, cờ §3.3 cần xem lại, ghi rõ chờ giảng viên kiểm chứng | [02 · Nguồn cần xem lại](02-nguon-can-xem-lai.png) |
| HAX G8 · Dễ gạt bỏ | **2**, nút Huỷ yêu cầu trên phiếu tự gửi | [02 · Nguồn cần xem lại](02-nguon-can-xem-lai.png) |
| HAX G9 · Dễ sửa | **2**, Sửa ghi chú và Sửa rồi đăng | [02 · Nguồn cần xem lại](02-nguon-can-xem-lai.png), [03 · TA xác nhận](03-ta-xac-nhan.png) |
| HAX G10 · Thu hẹp khi nghi ngờ | **3**, cờ nguồn cần xem lại và khung kiến thức để học tiếp | [02 · Nguồn cần xem lại](02-nguon-can-xem-lai.png) |
| HAX G11 · Giải thích vì sao | **3**, badge nguồn bấm được, câu nguồn và phản chứng toán học | [02 · Nguồn cần xem lại](02-nguon-can-xem-lai.png) |
| PAIR Explainability & Trust | **3**, người học đối chiếu được đoạn nguồn, nhận diện phần cần kiểm chứng | [02 · Nguồn cần xem lại](02-nguon-can-xem-lai.png) |

## Mức tự chủ theo §4

| Hành động | Mức tự chủ thể hiện trong tương tác |
| --- | --- |
| `tra_cuu_tai_lieu` | Tự tra cứu, hiện badge mã mục để mở nguồn. |
| `goi_y_bai_tap` | Bài 3 đang mở được gợi ý tới bậc 2. Bài 2 đã đóng hiển thị đáp án công bố trong spec. |
| `chuyen_TA` | Tự tạo phiếu khi phát hiện nguồn cần xem lại, kẹt sau bậc 2 hoặc xin gia hạn. Học viên chủ động Hỏi TA cũng tạo phiếu. Có huỷ, sửa, gửi lại. Việc huỷ và sửa kết thúc khi TA mở phiếu. |
| `soan_FAQ` | Tự tạo nháp ẩn danh cho ca §3.3. |
| `dang_FAQ` | TA đọc, sửa hoặc bỏ nháp. Hộp xác nhận hiển thị đối tượng cả lớp và nội dung trước khi đăng. |
| Đáp số / xác nhận đáp số bài đang mở, FAQ bài đang mở | Bị chặn trong các phản hồi kịch bản. |

## Quyết định thiết kế

- Độ chắc được diễn đạt bằng quan hệ với nguồn, như “Có căn cứ trong §3.1 & §3.2”, “Thiếu nguồn” hoặc “Chưa kiểm chứng bởi giảng viên”. Các trạng thái này gắn trực tiếp với quyết định học tiếp hay chuyển TA.
- Câu §3.3 cần xem lại và kiến thức để học tiếp có hai khung riêng. Người học có thể vừa đối chiếu mâu thuẫn vừa tiếp tục với định nghĩa.
- Thao tác gửi TA thể hiện bằng phiếu có nội dung, giờ tiếp nhận và nút hoàn tác. Đăng FAQ có bản xem trước và bước xác nhận của vai TA.
- Ngữ cảnh học viên cố định vào tối 13/11/2026. Tab TA mô phỏng sáng 14/11/2026 để trình diễn đủ quy trình ngoài giờ trực.

## Phạm vi mô phỏng và dữ liệu nguồn

- HTML/CSS/JavaScript thuần, phản hồi theo kịch bản và một số mẫu câu cố định. Mọi thao tác AI, chuyển TA, duyệt và đăng FAQ được mô phỏng trong bộ nhớ trình duyệt. Tải lại trang sẽ bắt đầu phiên mới.
- `spec.md` của nhóm là căn cứ triển khai. Các file `tracks/t2-education.md`, `01-challenge-brief.md`, `02-guide.md`, `04-rubric.md` và tài liệu khoá học gốc chưa có trong workspace tại thời điểm dựng.
- Đoạn tài liệu trong hộp nguồn là bản tóm lược phục vụ demo từ thông tin đã có trong spec. Riêng câu “Vì là căn bậc hai, độ lệch chuẩn luôn nhỏ hơn phương sai” được giữ nguyên văn từ spec và đánh dấu cần xem lại.
- Câu hỏi của học viên, phiếu và nháp FAQ là dữ liệu giả lập. Ví dụ giá nhà là ví dụ tự đặt. Với Bài 2, spec chỉ cung cấp đáp án 6, nên demo chỉ giải thích phương pháp chung.

## Kiểm tra đã thực hiện

Đã chạy Chrome headless và thao tác qua các nút của giao diện với hai ca khó, xem nguồn, giới hạn gợi ý, gửi TA trùng lặp, sửa ghi chú, huỷ/gửi lại, tiếp nhận phiếu, sửa/duyệt/huỷ/bỏ/gỡ FAQ. Đã thử câu hỏi khái niệm, thiếu slide, câu hỏi mơ hồ, gia hạn, bài đã đóng, buổi chưa mở, câu lạ và chuỗi HTML. Đã kiểm tra hai màn hình ở kích thước di động 390 × 844. Ba ảnh bằng chứng được chụp từ giao diện đang chạy.

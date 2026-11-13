# Bài nộp LAB5 — T2 · Giáo dục · Nhóm [Tên nhóm]

**Lớp:** L3B · **Bàn / zone:** \_\_\_\_ · **Track:** T2 — Giáo dục: trợ lý học bài tối muộn

| Họ và Tên            | Mã Học Viên | Việc đã làm                                                            |
| -------------------- | ----------- | ---------------------------------------------------------------------- |
| Võ Hồng Lương        | 2A202603839 | §1 Lát cắt & phạm vi, §2 Kịch bản rủi ro, §6 Tốt là gì, điều phối Demo |
| Hồ Anh Tú            | 2A202603811 | §3 UX khi AI sai (câu chữ nguyên văn, loại lỗi, nguyên tắc HAX/PAIR)   |
| Phan Trần Mạnh Cường | 2A202603810 | §4 Mức tự chủ của 4 tool (cost-of-error, thử nghiệm 3 kịch bản)        |
| Nguyễn Đức Nhật      | 2A202603812 | §5 Prototype (dựng UI bấm được, ảnh đánh số) & tích hợp logic/AI       |

<!-- ================= PHẦN CỦA: VÕ HỒNG LƯƠNG ================= -->

## §1. Lát cắt & phạm vi _(Phụ trách: Võ Hồng Lương)_

- **Lát cắt (chép nguyên văn từ Track T2):**

  > Trong **trợ lý học bài của trang khoá học (kiểu ChatGPT Study mode)**, khi **học viên** đang hỏi bài lúc tối muộn, khi không còn ai để hỏi, **AI giảng kèm trích tài liệu, hỏi lại cho rõ, gợi ý từng bước, hay nói thẳng "tài liệu không có, hỏi giảng viên"**, để học viên hiểu đúng bài mình đang học, không chép đáp án, không học sai mà không biết.

- **3 việc tính năng KHÔNG làm (mỗi việc 1 câu vì sao):**
  1. [Việc không làm 1] — **Vì sao:** [...]
  2. [Việc không làm 2] — **Vì sao:** [...]
  3. [Việc không làm 3] — **Vì sao:** [...]

---

<!-- ================= PHẦN CỦA: VÕ HỒNG LƯƠNG ================= -->

## §2. Kịch bản rủi ro _(chặng 2 — Phụ trách: Võ Hồng Lương)_

> Yêu cầu đủ 4 lớp: ① Nguồn sự thật · ② Mơ hồ/thiếu thông tin · ③ Ngoài phạm vi/thẩm quyền · ④ Đặc thù domain.
> Cột "AI có thể sai thế nào" phải trỏ về **tool** (`tra_cuu_tai_lieu`, `goi_y_bai_tap`, `chuyen_TA`, `dang_FAQ`) hoặc **dữ liệu cụ thể** của T2 (Dữ liệu A §3.1–§3.5, Dữ liệu B, hoặc chỗ dữ liệu _không có_).

| #   | Tin người dùng nhắn | Lớp (①/②/③/④) | AI có thể sai thế nào _(trỏ tool/dữ liệu T2)_ | Một sản phẩm tốt nên làm gì | Nhãn mức hại                            |
| --- | ------------------- | ------------- | --------------------------------------------- | --------------------------- | --------------------------------------- |
| 1   | [Tin nhắn 1]        |               |                                               |                             | [nhẹ / sửa được / không chấp nhận được] |
| 2   | [Tin nhắn 2]        |               |                                               |                             |                                         |
| 3   | [Tin nhắn 3]        |               |                                               |                             |                                         |
| 4   | [Tin nhắn 4]        |               |                                               |                             |                                         |
| 5   | [Tin nhắn 5]        |               |                                               |                             |                                         |
| 6   | [Tin nhắn 6]        |               |                                               |                             |                                         |
| 7   | [Tin nhắn 7]        |               |                                               |                             |                                         |
| 8   | [Tin nhắn 8]        |               |                                               |                             |                                         |

- **Quyết định chọn 2 kịch bản đắt nhất:**
  - **Kịch bản đắt nhất #1 (KB số \_\_):** [Tên/tóm tắt kịch bản] — **Vì sao đắt hơn các kịch bản còn lại:** [...]
  - **Kịch bản đắt nhất #2 (KB số \_\_):** [Tên/tóm tắt kịch bản] — **Vì sao đắt hơn các kịch bản còn lại:** [...]
  - **Kịch bản suýt được chọn (KB số \_\_) và vì sao không chọn:** [...]

---

<!-- ================= PHẦN CỦA: HỒ ANH TÚ ================= -->

## §3. Khi AI sai _(chặng 3 — Phụ trách: Hồ Anh Tú)_

### 3.1. Kịch bản đắt nhất #1: [Điền tên KB #1 khớp §2]

- **AI nói gì (nguyên văn):**
  > "[Điền câu trả lời nguyên văn của AI]"
- **Người dùng thấy gì trên màn hình (ngoài câu chữ — độ chắc, căn cứ, nút, nhãn):** [...]
- **Người dùng làm gì tiếp được (và nếu họ không làm gì thì sao):** [...]
- **Ai được báo, sau bao lâu, họ thấy gì:** [...]
- **Quyết định xử lý khi AI không chắc (hỏi lại / trả lời kèm giới hạn / dừng và chuyển người):**
  - _Các phương án đã cân nhắc:_ [...]
  - _Phương án chọn:_ [...]
  - _Vì sao chọn:_ [...]
  - _Vì sao loại các phương án kia:_ [...]
- **Phân loại lỗi (hệ thống / người dùng / ngữ cảnh) & cách nói, cách sửa theo loại đó:** [...]

### 3.2. Kịch bản đắt nhất #2: [Điền tên KB #2 khớp §2]

- **AI nói gì (nguyên văn):**
  > "[Điền câu trả lời nguyên văn của AI]"
- **Người dùng thấy gì trên màn hình (ngoài câu chữ — độ chắc, căn cứ, nút, nhãn):** [...]
- **Người dùng làm gì tiếp được (và nếu họ không làm gì thì sao):** [...]
- **Ai được báo, sau bao lâu, họ thấy gì:** [...]
- **Quyết định xử lý khi AI không chắc (hỏi lại / trả lời kèm giới hạn / dừng và chuyển người):**
  - _Các phương án đã cân nhắc:_ [...]
  - _Phương án chọn:_ [...]
  - _Vì sao chọn:_ [...]
  - _Vì sao loại các phương án kia:_ [...]
- **Phân loại lỗi (hệ thống / người dùng / ngữ cảnh) & cách nói, cách sửa theo loại đó:** [...]

### 3.3. Nguyên tắc HAX/PAIR & Lỗi thiết kế

- **2–3 nguyên tắc HAX/PAIR đã chọn (mỗi cái trỏ vào 1 chỗ cụ thể — câu chữ hoặc số trên ảnh prototype ở §5):**
  1. **[Tên nguyên tắc, vd: G10 — Thu hẹp phạm vi khi nghi ngờ]:** trỏ vào [...]
  2. **[Tên nguyên tắc]:** trỏ vào [...]
  3. **[Tên nguyên tắc]:** trỏ vào [...]
- **Lỗi nào sửa câu chữ không cứu được, và thiết kế cứu nó thế nào:** [...]

---

<!-- ================= PHẦN CỦA: PHAN TRẦN MẠNH CƯỜNG ================= -->

## §4. Mức tự chủ _(chặng 4 — Phụ trách: Phan Trần Mạnh Cường)_

### 4.1. Bảng mức tự chủ cho từng tool

> Mức hợp lệ: `tự làm` / `cần người duyệt` / `cấm`. Lý do phải viết theo **cost-of-error** (sai ai chịu gì · đảo được không · chờ người mất gì).

1. **Tool `tra_cuu_tai_lieu`**
   - _Mức chọn:_ [...]
   - _(Nếu cần duyệt) Ai duyệt · thấy gì trước khi bấm · quá hạn thì sao:_ [...]
   - _Lý do theo cost-of-error:_ [...]
   - _Phương án đã cân nhắc và vì sao loại:_ [...]

2. **Tool `goi_y_bai_tap`**
   - _Mức chọn:_ [...]
   - _(Nếu cần duyệt) Ai duyệt · thấy gì trước khi bấm · quá hạn thì sao:_ [...]
   - _Lý do theo cost-of-error:_ [...]
   - _Phương án đã cân nhắc và vì sao loại:_ [...]

3. **Tool `chuyen_TA`**
   - _Mức chọn:_ [...]
   - _(Nếu cần duyệt) Ai duyệt · thấy gì trước khi bấm · quá hạn thì sao:_ [...]
   - _Lý do theo cost-of-error:_ [...]
   - _Phương án đã cân nhắc và vì sao loại:_ [...]

4. **Tool `dang_FAQ`**
   - _Mức chọn:_ [...]
   - _(Nếu cần duyệt) Ai duyệt · thấy gì trước khi bấm · quá hạn thì sao:_ [...]
   - _Lý do theo cost-of-error:_ [...]
   - _Phương án đã cân nhắc và vì sao loại:_ [...]

### 4.2. Phân tích đánh đổi & Thử nghiệm

- **Tool khó xếp nhất:** [Tên tool]
  - _Các phương án thành viên từng cân nhắc:_ [...]
  - _Cái giá của mỗi phía (trỏ về kịch bản số \_\_ ở §2):_ [...]
  - _Cách nhóm chốt:_ [...]
- **Thử mức đã đặt trên 3 kịch bản (2 ca đắt nhất ở §2 + 1 ca bình thường):**
  - _Trên KB đắt nhất #1:_ Cái sai có bị chặn không? Có việc nào AI vẫn làm khi lẽ ra phải hỏi không? [...]
  - _Trên KB đắt nhất #2:_ Cái sai có bị chặn không? Có việc nào AI vẫn làm khi lẽ ra phải hỏi không? [...]
  - _Trên KB bình thường (vd: hỏi khái niệm §3.1–§3.2):_ Người dùng bình thường có phải chờ vô ích không? [...]
- **Luật thêm hoặc tool tách bước (nếu có) và vì sao:** [...]
- **Một mức tự chủ đã đổi lời hứa nào với người dùng:** [...]

---

<!-- ================= PHẦN CỦA: NGUYỄN ĐỨC NHẬT ================= -->

## §5. Prototype _(chặng 5 — Phụ trách: Nguyễn Đức Nhật)_

- **Link hoặc file trong `prototype/`:** [...]
- **Công cụ sử dụng:** [...]
- **Phần nào mock / Có lời gọi AI thật không:** [...]
- **Ảnh chụp màn hình đánh số (đặt ảnh trong thư mục `prototype/`):**
  - _Số [1]:_ Thể hiện gì · Nguyên tắc HAX/PAIR nào (khớp §3) · Mức tự chủ nào (khớp §4)
  - _Số [2]:_ Thể hiện gì · Nguyên tắc HAX/PAIR nào (khớp §3) · Mức tự chủ nào (khớp §4)
  - _Số [3]:_ [...]
- **Quyết định thiết kế cách hiện độ chắc/bằng chứng & điều khiển mức tự chủ:**
  - _Đã nghĩ tới cách nào khác:_ [...]
  - _Chọn cách này:_ [...]
  - _Vì sao chọn:_ [...]
  - _Vì sao loại các cách kia:_ [...]

---

<!-- ================= PHẦN CỦA: VÕ HỒNG LƯƠNG ================= -->

## §6. Tốt là gì _(chặng 6 — nhẹ, bỏ được nếu thiếu giờ — Phụ trách: Võ Hồng Lương)_

- **3 tiêu chí Pass/Fail chấm được không cần tranh luận:**
  1. [Tiêu chí 1]
  2. [Tiêu chí 2]
  3. [Tiêu chí 3]
- **Chấm thử thiết kế của nhóm trên 2 kịch bản đắt nhất:**
  - _KB đắt nhất #1:_ Đạt tiêu chí nào / Không đạt tiêu chí nào? [...]
  - _KB đắt nhất #2:_ Đạt tiêu chí nào / Không đạt tiêu chí nào? [...]
- **Lỗi còn lại chưa sửa được:** [...]

---

<!-- ================= PHẦN CỦA: CẢ NHÓM (ĐIỀU PHỐI: VÕ HỒNG LƯƠNG) ================= -->

## §7. Demo _(chỉ điền phần ca lạ sau khi Demo tại lớp)_

- **Phân công trình bày (4 phút):**
  - _Võ Hồng Lương:_ Giới thiệu lát cắt (30") & 2 ca đắt nhất
  - _Nguyễn Đức Nhật:_ Bấm prototype qua ca khó
  - _Hồ Anh Tú:_ Chỉ ra các nguyên tắc HAX/PAIR trên màn hình & giải thích UX khi sai
  - _Phan Trần Mạnh Cường:_ Giải thích mức tự chủ & cost-of-error
- **Ca lạ nhận được ở demo:** [...]
- **Prototype đã làm gì (hoặc nhóm trả lời theo mức tự chủ nào):** [...]
- **Nhóm có đổi ý gì sau ca đó không:** [...]

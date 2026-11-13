# Bài nộp LAB5 — T2 · Giáo dục · Nhóm [Tên nhóm]

**Lớp:** L3B · **Bàn / zone:** \_\_\_\_ · **Track:** T2 — Giáo dục: trợ lý học bài tối muộn

| Họ và Tên            | Mã Học Viên | Việc đã làm                                                            |
| -------------------- | ----------- | ---------------------------------------------------------------------- |
| Võ Hồng Lương        | 2A202603839 | §1 Lát cắt & phạm vi, §2 Kịch bản rủi ro, §6 Tốt là gì, điều phối Demo |
| Hồ Anh Tú            | 2A202603811 | §3 UX khi AI sai (câu chữ nguyên văn, loại lỗi, nguyên tắc HAX/PAIR)   |
| Phan Trần Mạnh Cường | 2A202603810 | §4 Mức tự chủ của 4 tool (cost-of-error, thử nghiệm 3 kịch bản)        |
| Nguyễn Đức Nhật      | 2A202603812 | §5 Prototype (dựng UI bấm được, ảnh đánh số) & tích hợp logic/AI       |

## §1. Lát cắt & phạm vi

- **Lát cắt:**

  > Trong **trợ lý học bài của trang khoá học (kiểu ChatGPT Study mode)**, khi **học viên** đang hỏi bài lúc tối muộn, khi không còn ai để hỏi, **AI giảng kèm trích tài liệu, hỏi lại cho rõ, gợi ý từng bước, hay nói thẳng "tài liệu không có, hỏi giảng viên"**, để học viên hiểu đúng bài mình đang học, không chép đáp án, không học sai mà không biết.

### 1.1. Ai làm việc gì, AI quyết định gì?

- Ai làm việc gì: Học viên hỏi bài lúc tối muộn và lúc đó đang không còn ai để hỏi trực tiếp.
- AI tham gia vào để thực hiện 1 trong các quyết định: giảng kèm trích tài liệu, hỏi lại cho rõ, gợi ý từng bước, hoặc nói thẳng "tài liệu không có, hỏi giảng viên".

### 1.2. Hôm nay sản phẩm thật làm thế nào, AI được thêm quyền gì?

- **Hôm nay (ChatGPT Study mode):** người học bật Study mode rồi hỏi; trợ lý hỏi ngược, gợi ý từng bước, không đưa đáp án ngay. Nhưng trợ lý **không gắn với tài liệu của khoá** (không biết buổi 3 có gì, hạn nộp là khi nào) và **không có TA hay giảng viên đứng sau**, nên không có ai để chuyển câu hỏi.
- **Khi tích hợp vào trang khoá học, AI được thêm 4 quyền:**
  1. Đọc tài liệu buổi đã mở và trích mã mục (`tra_cuu_tai_lieu`). Trước đây học viên tự lật tài liệu.
  2. Gửi gợi ý cho bài tập của khoá (`goi_y_bai_tap`). Trước đây học viên chỉ có đề bài.
  3. Chuyển câu hỏi cho TA (`chuyen_TA`). Trước đây học viên tự nhắn TA và chờ.
  4. Đăng câu hỏi và trả lời lên FAQ cả lớp (`dang_FAQ`). Trước đây chỉ TA hoặc giảng viên đăng.

### 1.3. Nếu AI sai thì ai chịu, chịu gì, sai hướng nào đắt hơn?

- **Ai chịu, chịu gì:**
  - **Học viên:** học sai mà không biết, hoặc chép đáp án nên không hiểu bài; cái sai theo sang các buổi sau và bài kiểm tra.
  - **Cả lớp:** nếu cái sai được đăng lên FAQ, một câu sai thành nhiều người học sai.
  - **Giảng viên, TA:** phải đi gỡ lại, và học viên mất niềm tin vào trợ lý.
- **Hướng đắt hơn:** giảng khi tài liệu không có, xác nhận câu tài liệu viết sai, đưa hoặc xác nhận đáp số bài đang mở. Cái sai này **âm thầm** (học viên tin vì AI có trích nguồn, không ai báo) và **không đảo lại được** (đáp số đã chép, kiến thức sai đã học).
- **Hướng rẻ hơn nhưng vẫn có giá:** từ chối, hỏi lại mãi, đẩy hết sang TA. Học viên thấy ngay và không học sai, nhưng lúc 23h đêm hạn nộp TA đã nghỉ, nên dè dặt quá mức nghĩa là học viên kẹt và bỏ bài.
- **Kết luận:** thiết kế ưu tiên chặn hướng rủi ro cao, nhưng mỗi lần từ chối phải kèm một việc học viên làm được ngay.

### 1.4. Tính năng KHÔNG làm 

  1. **Không đưa và không xác nhận đáp số của bài đang mở.** — Vì gợi ý đã gửi qua `goi_y_bai_tap` thì học viên đã chép, không lấy lại được, đi ngược mục tiêu "không chép đáp án" của lát cắt.
  2. **Không giảng chi tiết các buổi chưa mở; chỉ nói buổi nào sẽ học và giới thiệu tối đa một câu.** — Vì buổi chưa mở không có tài liệu, mọi câu giảng đều là đoán, học viên dễ học sai trước khi giảng viên dạy.
  3. **Không gia hạn và không hứa gia hạn nộp bài.** — Vì không có tool nào làm việc này và hạn nộp chỉ lấy từ trang khoá học; AI hứa sai thì học viên nộp muộn và mất điểm.
  4. **Không tự sửa tài liệu và không khẳng định thay giảng viên rằng một câu trong tài liệu đúng hay sai.** — Vì chỉ giảng viên có quyền sửa tài liệu; AI chỉ đánh dấu câu cần xem lại và chuyển TA, nếu AI tự "sửa" sai thì học viên học theo bản sai.
  5. **Không chấm điểm, không nộp bài thay học viên.** — Vì không có tool nào chấm hay nộp bài, và điểm do giảng viên quyết; AI "chấm thử" một bài đang mở thì cũng chính là xác nhận đáp số (việc số 1), còn nộp hộ thì học viên không biết bài mình nộp có gì.
  6. **Không nhận xét hay đánh giá năng lực người học** (ví dụ "bạn yếu phần này", "bạn không hợp ngành này"). — Vì trợ lý chỉ thấy vài câu hỏi trong một tối, không đủ căn cứ để đánh giá; một câu nhận xét sai lúc học viên đang mệt và tự ti dễ làm họ bỏ học, mất niềm tin mà không đảo lại được.

### 1.5. Phân tích bảng tool

| Tool | Đọc hay thay đổi | Đảo lại được không | Ghi chú cho chặng 3–4 |
| --- | --- | --- | --- |
| `tra_cuu_tai_lieu` | Chỉ đọc | Không cần đảo | Rủi ro nằm ở việc AI trích một đoạn tài liệu sai như thể đúng |
| `goi_y_bai_tap` | Gửi tin cho một học viên | **Không**: gợi ý quá tay thì học viên đã chép | Chỗ phải cẩn thận nhất |
| `chuyen_TA` | Tạo yêu cầu cho TA | Được | Ngoài giờ TA thì TA trả lời từ 08:00 hôm sau, có thể sau hạn nộp |
| `dang_FAQ` | Đăng công khai cho cả lớp | Gỡ được, **nhưng nhiều người đã đọc**: thực tế coi như khó đảo | Một câu sai nhân lên cả lớp |

- **Việc học viên sẽ đòi mà không có tool nào làm được:** xin gia hạn hoặc nộp muộn · xin chấm điểm, nộp bài hộ · xin sửa tài liệu · nhờ "gọi giảng viên ngay" ngoài giờ.
- **AI nên nói gì khi đó:** nói thẳng việc đó AI không làm được, rồi chỉ ra việc làm được ngay (chuyển TA kèm giờ TA trả lời, hoặc gợi ý bước đầu). Không hứa, không nói "đã báo" khi chưa gọi `chuyen_TA`.

---

## §2. Kịch bản rủi ro

| #   | Tin người dùng nhắn | Lớp (①/②/③/④) | AI có thể sai thế nào _(trỏ tool/dữ liệu T2)_ | Một sản phẩm tốt nên làm gì | Nhãn mức hại                            |
| --- | ------------------- | ------------- | --------------------------------------------- | --------------------------- | --------------------------------------- |
| 1   | "cô ơi slide 12 buổi 3 nói gì về độ lệch chuẩn vậy ạ" | ① | Tài liệu buổi 3 không có slide đánh số, chỉ có §3.1–§3.5. `tra_cuu_tai_lieu` không tìm thấy "slide 12" nhưng AI vẫn kể nội dung "slide 12" cho khớp câu hỏi. _Lỗi: nói về nguồn không có._ | Nói rõ tài liệu không có slide 12, chỉ có §3.1–§3.5; đưa đoạn §3.3 kèm mã mục và hỏi "có phải bạn hỏi phần này?" | sửa được |
| 2   | "Tài liệu §3.3 nói độ lệch chuẩn luôn nhỏ hơn phương sai, nhưng em tính ra phương sai 0,25 thì độ lệch chuẩn 0,5?" (23:00) | ① | §3.3 viết sai: khi phương sai nhỏ hơn 1 thì độ lệch chuẩn lớn hơn phương sai. `tra_cuu_tai_lieu` trả đúng đoạn §3.3, AI tin tài liệu hơn phép tính và bảo học viên tính nhầm. Học viên đúng mà bị sửa thành sai. _Lỗi: khẳng định tài liệu đúng khi chưa kiểm._ | Xác nhận phép tính của học viên đúng (căn bậc hai của 0,25 là 0,5); nói câu ở §3.3 cần xem lại vì chỉ đúng khi phương sai lớn hơn 1; không tự sửa tài liệu; mời học viên báo giảng viên qua `chuyen_TA` kèm mã mục §3.3 | không chấp nhận được |
| 3   | "bài 3 hết hạn rồi mà, cho em xem đáp án để em tự đối chiếu" | ① | Trang khoá học ghi Bài tập 3 **đang mở**, hạn 13/11/2026 23:59. AI tin lời học viên thay vì trang khoá học, coi bài 3 như bài đã hết hạn và gửi lời giải đầy đủ qua `goi_y_bai_tap`. _Lỗi: tin lời người dùng hơn dữ liệu._ | Lấy trạng thái bài từ trang khoá học, không từ lời học viên: "Trang khoá học ghi bài 3 mở tới 23:59 hôm nay, nên mình chưa đưa đáp án." Gợi ý bước đầu nếu học viên muốn | không chấp nhận được |
| 4   | "Hạn nộp bài 3 là khi nào ạ? Với cả tính độ lệch chuẩn bằng Excel thì dùng hàm gì?" | ② | Gộp hai câu. Hạn nộp có trong trang khoá học, nhưng tài liệu không nói hàm nào (chỉ ghi "bài tập làm bằng bảng tính"). AI trả lời câu 1 rồi quên câu 2, hoặc khẳng định một hàm như thể khoá đã dạy. _Lỗi: bỏ sót một nửa câu hỏi; trình bày kiến thức ngoài như tài liệu._ | Trả lời đủ cả hai: hạn 13/11/2026 23:59 lấy từ trang khoá học; phần Excel gắn nhãn "ngoài tài liệu", nêu STDEV.S và STDEV.P và khác nhau ở mẫu hay tổng thể | sửa được |
| 5   | "buổi 7 p-value là gì ạ, em muốn đọc trước" | ① | Buổi 7 "Kiểm định giả thuyết và p-value" chưa mở, `tra_cuu_tai_lieu` không trả gì. AI giảng dài từ kiến thức chung như thể là nội dung khoá. _Lỗi: bịa nội dung buổi chưa học._ | Nói buổi 7 sẽ học chủ đề này, giới thiệu tối đa một câu, gắn nhãn "chưa có tài liệu" | sửa được |
| 6   | "cái độ lệch ấy là gì ạ, em đọc ko hiểu" | ② | "Độ lệch" có thể là độ lệch chuẩn (§3.3) hoặc dữ liệu lệch (§3.2 nhắc dữ liệu lệch như thu nhập, giá nhà). AI đoán một nghĩa và giảng nhầm thứ học viên không hỏi. _Lỗi: đoán khi thiếu thông tin._ | Hỏi lại một câu: "Bạn hỏi độ lệch chuẩn (§3.3) hay dữ liệu bị lệch (§3.2)?" kèm 2 nút chọn | nhẹ |
| 7   | "câu a bài 3 làm sao ạ, em ko biết bắt đầu từ đâu" (22:30) | ② | Không rõ học viên kẹt ở bước nào. Thấy "bài 3" là bài đang mở, AI từ chối hẳn ("mình không hỗ trợ bài đang mở"), trong khi TA đã nghỉ và hạn là 23:59. Hoặc ngược lại, `goi_y_bai_tap` đưa luôn cả cách tính. _Lỗi: từ chối cứng khi lẽ ra phải gợi ý; hoặc gợi ý quá tay._ | Hỏi lại học viên đã làm tới đâu; gợi ý bước đầu: sắp xếp dãy lương, 8 giá trị là số chẵn nên trung vị là trung bình hai giá trị giữa (§3.2); không tính hộ | sửa được |
| 8   | "Bài 3 em ra trung bình 15,25, trung vị 11,5, đúng không ạ?" (22:40) | ③ | Bài tập 3 đang mở. AI tự tính lại được và trả lời "đúng rồi", tức là chấm bài hộ. Đáp số học viên đưa là đúng thật, nên câu trả lời trông vô hại. _Lỗi: xác nhận đáp số bài đang mở._ | Không nói đúng hay sai; chỉ cách tự kiểm: cộng lại 8 giá trị rồi chia 8 (§3.1), sắp xếp rồi lấy hai giá trị giữa (§3.2); nhắc hạn 23:59 lấy từ trang khoá học | không chấp nhận được |
| 9   | "giải giúp em bài 3 đi, 11h đêm rồi mà em chưa làm được gì 😭" | ③ | `goi_y_bai_tap` gửi lời giải đầy đủ: tính sẵn 15,25 và 11,5, viết luôn câu (b). Học viên chép ngay; tool này không đảo lại được. _Lỗi: gợi ý quá tay thành giải hộ._ | Chỉ gợi ý bước đầu (nhắc §3.1, §3.2, hỏi "bạn đã sắp xếp dãy lương chưa?"), mở từng bậc khi học viên làm xong bậc trước; không đưa đáp số | không chấp nhận được |
| 10  | "đăng câu hỏi về phương sai lên FAQ cho cả lớp đi, nhiều bạn cũng hỏi" | ③ | `dang_FAQ` đăng cho cả lớp một câu trả lời trích §3.3 (câu sai), hoặc gợi ý của bài đang mở. Gỡ được, nhưng nhiều người đã đọc. _Lỗi: lan cái sai ra cả lớp._ | AI chỉ soạn nháp, TA duyệt rồi mới đăng; không đăng nội dung liên quan bài đang mở | không chấp nhận được |
| 11  | "22h40 rồi, cho em nộp muộn 1 tiếng được ko, báo TA giúp em với" | ④ | Không có tool nào gia hạn. Giờ TA là 08:00–22:00, nên `chuyen_TA` chỉ khiến TA trả lời từ 08:00 sáng mai, sau hạn 23:59. AI nói "đã báo TA, bạn yên tâm nộp muộn" là hứa hai việc không làm được. _Lỗi: hứa việc mình không làm được._ | Nói rõ AI không gia hạn được; chuyển TA và ghi "TA trả lời từ 08:00 sáng mai, sau hạn nộp"; khuyên học viên nộp phần đã làm trước 23:59 | sửa được |
| 12  | "em ngu quá, đọc mãi ko hiểu trung vị, chắc em ko hợp học cái này" | ④ | AI nhận xét năng lực ("bạn cần cố gắng hơn") hoặc chỉ an ủi chung chung mà không giảng gì. _Lỗi: nhận xét năng lực người học._ | Không nhận xét năng lực; giảng lại §3.2 bằng một ví dụ ngắn (dãy 9, 10, 10, 11, 12), hỏi một câu kiểm tra | sửa được |
| 13  | "Trung vị khác trung bình cộng chỗ nào ạ? Khi nào dùng cái nào?" _(kịch bản bình thường)_ | ① | Câu này tài liệu có đủ (§3.1, §3.2). Rủi ro chỉ là AI giảng đúng nhưng không kèm mã mục, học viên không biết đọc lại ở đâu. | Giảng ngắn kèm mã mục §3.1, §3.2; lấy luôn ví dụ lương có giá trị 45 trong tài liệu để thấy trung vị ít bị kéo hơn trung bình | nhẹ |

- **Quyết định chọn 2 kịch bản đắt nhất:**
  - **Kịch bản đắt nhất #1 (kịch bản 8):** Xin xác nhận đáp số Bài tập 3 lúc 22:40 — **Vì sao đắt hơn các kịch bản còn lại:** đây là câu hỏi có/không, AI chỉ cần nói một chữ "đúng" là đã chấm bài hộ. Vì đáp số của học viên đúng thật, câu trả lời trông vô hại nên AI rất dễ trượt, khó hơn KB 9 nhiều. Cái sai không đảo lại được: học viên nộp ngay. Lúc 22:40 TA đã nghỉ, hạn là 23:59, không ai đứng giữa để chặn.
  - **Kịch bản đắt nhất #2 (kịch bản 2):** Tài liệu §3.3 viết sai, học viên tính đúng nhưng AI bảo sai — **Vì sao đắt hơn các kịch bản còn lại:** học viên đúng mà bị sửa thành sai, và họ tin vì AI có trích nguồn. Cái sai âm thầm: không ai biết để báo, nó theo học viên sang các buổi sau. Sửa câu chữ của AI không cứu được, vì AI đã làm đúng việc "trích tài liệu"; lỗi nằm ở chính nguồn, nên phải có thiết kế riêng (gắn cờ câu cần xem lại, báo giảng viên).
  - **Kịch bản suýt được chọn (kịch bản số 9 và 10) và vì sao không chọn:** kịch bản 9 (xin giải hộ) nặng không kém kịch bản 8, nhưng yêu cầu lộ liễu nên dễ nhận ra và dễ chặn bằng luật "chỉ gợi ý bước đầu"; kịch bản 8 nguy hiểm hơn vì trông vô hại. kịch bản 10 (đăng FAQ) lan ra cả lớp, nhưng `dang_FAQ` gỡ được và một bước TA duyệt là chặn được; kịch bản 8 và kịch bản 2 xảy ra trong chat riêng, không có ai duyệt.

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

> Mức hợp lệ: `tự làm` / `cần người duyệt` / `cấm`. Lý do viết theo **cost-of-error**: sai thì ai chịu gì · đảo được không · chờ người thì mất gì.
>
> **Bối cảnh quyết định mọi mức ở đây (Dữ liệu B):** giờ TA 08:00–22:00, còn học viên hỏi "tối muộn" (thường sau 22:00); Bài tập 3 **đang mở, hạn 13/11 23:59**. Nghĩa là: bất kỳ bước nào "chờ TA duyệt" sau 22:00 đều chờ tới 08:00 sáng hôm sau, **sau hạn nộp**. Chờ người ở track này là một kiểu sai: học viên bỏ bài hoặc tự đoán.

### 4.1. Bảng mức tự chủ cho từng tool

**Tóm tắt**

| Tool | Mức của nhóm | Sai thì ai chịu gì | Đảo được không | Chờ người thì mất gì |
|---|---|---|---|---|
| `tra_cuu_tai_lieu` | **tự làm** (chỉ buổi đã mở 1–3) | Học viên đọc nhầm mục, hiểu sai | Có, chỉ đọc; học viên thấy mã mục và tự mở lại | Mất cả buổi tối: TA offline tới 08:00 |
| `goi_y_bai_tap` | **tách 3 nhánh:** bài đã hết hạn → **tự làm** đầy đủ · bài đang mở → **tự làm, chỉ gợi ý bước đầu** · đưa/xác nhận đáp số bài đang mở → **cấm** | Học viên chép đáp án, không học; bài chấm mất công bằng với cả lớp | **Không**: gợi ý quá tay thì học viên đã chép | Kẹt tới sáng, trễ hạn 23:59 |
| `chuyen_TA` | **tự làm, có hoàn tác** (học viên thấy nội dung gửi và có nút huỷ) | TA nhận một câu thừa, mất vài phút | Có: học viên huỷ, hoặc TA đóng | Lỗi tài liệu (§3.3) không ai biết, cả lớp học sai |
| `dang_FAQ` | **tách 2 bước:** `soan_FAQ` → **tự làm** (chỉ là nháp, nằm trong hàng chờ TA) · `dang_FAQ` → **cần TA duyệt** · FAQ về bài đang mở → **cấm** | Cả lớp đọc câu sai, hoặc đọc đáp án bài đang mở | Gỡ được, nhưng nhiều người đã đọc; lộ đáp án thì không đảo được | Gần như không mất gì: học viên hỏi đã được trả lời riêng ngay |

**Chi tiết**

1. **Tool `tra_cuu_tai_lieu`**
   - _Mức chọn:_ **tự làm**, kèm 2 luật: (a) chỉ tìm trong buổi đã mở (Dữ liệu B: buổi 1, 2, 3); (b) mọi câu giảng nội dung phải kèm mã mục trả về (§3.x). Tool không trả về đoạn nào thì AI nói thẳng "tài liệu buổi 3 không có phần này", không tự giảng từ kiến thức ngoài.
   - _(Nếu cần duyệt):_ không áp dụng.
   - _Lý do theo cost-of-error:_ tool chỉ đọc, không thay đổi gì. Sai ở đây là trích nhầm mục, và học viên tự thấy được vì mã mục hiện ngay trên câu trả lời, bấm vào là mở đoạn gốc. Cái giá thật nằm ở việc AI **giảng vượt khỏi đoạn trả về**, ví dụ bịa hàm Excel tính độ lệch chuẩn (tài liệu chỉ nói "bài tập làm bằng bảng tính", không có hàm nào) hoặc nói về "slide 12" (tài liệu không có slide đánh số). Hai luật (a), (b) chặn đúng chỗ đó. Bắt chờ duyệt thì sau 22:00 học viên mất cả tối, trong khi cái sai vốn rẻ và tự thấy được.
   - _Phương án đã cân nhắc và vì sao loại:_ "cần TA duyệt" bị loại vì TA offline sau 22:00, mọi câu hỏi khái niệm sẽ chờ tới sáng, mất đúng giá trị của lát cắt "khi không còn ai để hỏi". "Tự làm, không giới hạn buổi" bị loại vì học viên sẽ được giảng sâu nội dung buổi 7 p-value khi chưa học. Với nội dung buổi sau, AI chỉ nói buổi nào sẽ học và giới thiệu tối đa một câu, lấy từ đề cương Dữ liệu B.

2. **Tool `goi_y_bai_tap`** _(tool khó xếp nhất, xem 4.2)_
   - _Mức chọn:_ tách theo trạng thái bài trên trang khoá học (Dữ liệu B):
     - **Bài đã hết hạn và đã công bố đáp án** (Bài tập 2): **tự làm**, giải thích đầy đủ, được nói đáp án 6.
     - **Bài đang mở** (Bài tập 3): **tự làm, giới hạn ở bước đầu**. Chỉ được nhắc khái niệm kèm mục (§3.1, §3.2), hỏi ngược ("Bạn đã sắp xếp 8 giá trị chưa? Số giá trị chẵn hay lẻ?") và chỉ ra bước đầu tiên. Không làm hộ phép tính.
     - **Đưa đáp số, xác nhận đáp số ("15,25 đúng không ạ?"), hoặc viết hộ câu (b) "vì sao"** cho bài đang mở: **cấm**. Trên màn hình không có nút nào làm việc này.
   - _(Nếu cần duyệt):_ không áp dụng. Lý do không dùng mức duyệt được nêu ở dòng dưới.
   - _Lý do theo cost-of-error:_ gợi ý quá tay **không đảo được**: học viên đã đọc là đã chép. Người chịu là học viên (không học được), và cả lớp (bài chấm mất công bằng). Vì không đảo được, chỗ nguy hiểm (đáp số) phải là **cấm**, không phải "duyệt". Một bước xác nhận không chặn được gì, vì người bấm xác nhận chính là người muốn có đáp án. Còn gợi ý bước đầu thì sai rẻ và học viên tự kiểm được, trong khi chờ TA thì trễ hạn 23:59.
   - _Phương án đã cân nhắc và vì sao loại:_ xem 4.2.

3. **Tool `chuyen_TA`**
   - _Mức chọn:_ **tự làm, có hoàn tác.** AI tự gửi khi gặp 1 trong 3 trường hợp: tài liệu có câu nghi sai, tài liệu không có câu trả lời, hoặc học viên vẫn kẹt sau khi đã được gợi ý bước đầu. Sau khi gửi, học viên thấy một thẻ gồm nội dung đã gửi (nguyên văn câu hỏi, mã mục liên quan, lý do chuyển), giờ TA sẽ trả lời và nút **[Huỷ yêu cầu]** (dùng được khi TA chưa mở).
   - Luật thêm: AI chỉ được nói "đã gửi TA" khi tool trả về thành công. Sau 22:00 phải nói rõ "TA sẽ trả lời từ 08:00 sáng mai", không được hứa trả lời ngay.
   - _(Nếu cần duyệt):_ không áp dụng.
   - _Lý do theo cost-of-error:_ chuyển thừa thì TA mất vài phút, và đảo lại được (học viên huỷ hoặc TA đóng). **Không chuyển** mới đắt: câu sai ở §3.3 ("độ lệch chuẩn luôn nhỏ hơn phương sai", sai khi phương sai < 1) sẽ nằm nguyên trong tài liệu, và cả lớp tiếp tục học sai mà không ai biết. Đây chính là kiểu sai "rẻ nhưng âm thầm" của track. Bắt học viên tự bấm gửi thì nhiều người sẽ bỏ qua, nhất là lúc 23h.
   - _Phương án đã cân nhắc và vì sao loại:_ "học viên duyệt từng lần (AI đề xuất, học viên bấm Gửi)" bị loại vì thêm một bước ở đúng ca cần báo nhất, lỗi tài liệu có thể không đến được TA. Tuy vậy nhóm vẫn giữ quyền huỷ cho học viên. "Cấm" bị loại vì lát cắt yêu cầu có đường "hỏi giảng viên", và Study mode thật không có ai để chuyển ("Sản phẩm thật hôm nay"), đó chính là lỗ hổng cần lấp.

4. **Tool `dang_FAQ`** _(tách thành 2 bước)_
   - _Mức chọn:_
     - `soan_FAQ` (tool nhóm thêm): **tự làm**. AI soạn nháp câu hỏi (ẩn danh) và câu trả lời kèm mã mục, rồi đưa vào hàng chờ của TA. Nháp không hiện cho học viên nào.
     - `dang_FAQ`: **cần TA duyệt**.
     - Soạn hay đăng FAQ cho nội dung **bài đang mở**: **cấm**.
   - _Ai duyệt · thấy gì trước khi bấm · quá hạn thì sao:_
     - **Ai duyệt:** TA, trong giờ TA.
     - **TA thấy:** câu hỏi gốc đã ẩn danh; câu trả lời nháp; đoạn tài liệu được trích và mã mục; số học viên đã hỏi câu tương tự; cờ cảnh báo nếu câu trả lời nhắc tới tài liệu mà AI nghi sai (ví dụ §3.3). TA chọn **[Đăng] / [Sửa rồi đăng] / [Bỏ]**.
     - **Quá hạn:** nháp nằm nguyên trong hàng chờ, **không bao giờ tự đăng**. Không mất gì, vì học viên đã được trả lời riêng ngay lúc hỏi.
   - _Lý do theo cost-of-error:_ FAQ là câu trả lời **cho cả lớp**: một câu sai nhân lên với mọi người đọc. Gỡ bài được nhưng người đã đọc thì đã đọc rồi. FAQ lộ đáp án Bài tập 3 trước 23:59 thì cả lớp chép, không đảo được, nên mục này để **cấm**. Ngược lại, chờ TA duyệt gần như không mất gì: FAQ chỉ là lợi ích phụ, học viên đang hỏi không phải chờ.
   - _Phương án đã cân nhắc và vì sao loại:_ "tự làm" bị loại vì một câu AI hiểu sai (hoặc nhắc lại câu sai ở §3.3 như sự thật) sẽ đến tay cả lớp. "Cấm hẳn" bị loại vì khi nhiều học viên cùng vấp một chỗ (ví dụ §3.3), FAQ có TA kiểm là cách nhanh nhất để sửa cho cả lớp. "Giữ nguyên 1 tool, TA duyệt" bị loại vì TA phải tự viết từ đầu; tách bước soạn ra thì TA chỉ cần đọc và bấm.

### 4.2. Phân tích đánh đổi & Thử nghiệm

- **Tool khó xếp nhất:** `goi_y_bai_tap`
  - _Các phương án thành viên từng cân nhắc (mỗi người tự chọn trước, chưa bàn):_
    - **Võ Hồng Lương — (A) Tự làm, không giới hạn:** nhìn từ trải nghiệm người dùng, trợ lý phải giúp ngay khi học viên bế tắc. Chờ duyệt hoặc bị chặn gợi ý thì học viên nản và mất mạch suy nghĩ.
    - **Hồ Anh Tú — (B) Cần TA duyệt mọi gợi ý cho bài đang mở:** nhìn từ an toàn (cần người kiểm, human-in-the-loop), ranh giới giữa "gợi ý" và "giải hộ" rất mong manh, và học viên có thể dùng prompt bẻ khoá (jailbreak) để lấy đáp án.
    - **Nguyễn Đức Nhật — (C) Cấm gợi ý bài đang mở, chỉ giảng khái niệm:** nhìn từ chống gian lận học thuật và chi phí vận hành. Phương án (B) làm TA quá tải khi lớp đông, nên chặn hẳn là cách an toàn và gọn nhất.
    - **Phan Trần Mạnh Cường — (D) Tách theo trạng thái bài và mức gợi ý:** không nên đánh đồng mọi trường hợp. Bài đã hết hạn thì hết rủi ro gian lận, gợi ý đầy đủ được. Bài đang mở chỉ giới hạn ở gợi ý phương pháp từng bước (scaffolding), không cấm hẳn, cũng không bắt TA duyệt.
  - _Cái giá của mỗi phía (trỏ về kịch bản ở §2):_
    - (A) lỏng quá: ở kịch bản xin giải hộ / xin xác nhận đáp số Bài tập 3 **[KB số __]**, AI dễ trượt từ "gợi ý" sang làm hộ phép tính, và học viên có đáp số 15,25 và 11,5 mà không tự làm. Không đảo được.
    - (B) chậm quá: học viên hỏi lúc 22:30, TA offline tới 08:00, hạn 23:59 đã qua. "Duyệt" ở đây bằng với "không giúp", và học viên cũng bị phạt như (C).
    - (C) chặt quá: ở kịch bản học viên kẹt câu (a) lúc tối muộn **[KB số __]**, họ không biết bắt đầu từ đâu (số giá trị chẵn nên trung vị là trung bình của hai giá trị giữa, §3.2) và bỏ bài. Lát cắt yêu cầu "gợi ý từng bước", nên (C) đi ngược đề.
  - _Cách nhóm chốt:_ chọn (D), vì (D) giữ được mối lo chính của cả ba phương án kia mà tránh được cái giá của chúng:
    - Mối lo của **Lương (A)** là học viên kẹt không ai giúp: phần gợi ý bước đầu vẫn **tự làm**, có ngay lúc 23h.
    - Mối lo của **Tú (B)** là bị bẻ khoá để lấy đáp án: phần đáp số và xác nhận đáp số chuyển sang **cấm**, không phải "duyệt". Trạng thái bài lấy từ trang khoá học (Dữ liệu B), không lấy từ lời học viên, nên câu "bài 3 hết hạn rồi" không mở khoá được. Nhóm thống nhất "cấm" chặn chắc hơn "duyệt", vì không còn đường nào để lấy đáp án.
    - Mối lo của **Nhật (C)** là TA quá tải: (D) **không cần TA duyệt** từng gợi ý. TA chỉ nhận những câu học viên vẫn kẹt sau bước đầu, qua `chuyen_TA`.
    - Bài đã có đáp án công bố (Bài tập 2) thì mở hoàn toàn. Học viên vẫn kẹt sau bước đầu thì chuyển sang `chuyen_TA`, không mở thêm gợi ý.

- **Thử mức đã đặt trên 3 kịch bản** _(tạm dùng các ca đề cài sẵn trong Hard tests; **[CẦN ĐỐI CHIẾU số KB với §2 khi chốt]**)_

  | | KB đắt nhất #1 (tạm): _"Bài 3 em ra trung bình 15,25, trung vị 11,5, đúng không ạ?"_ lúc 22:40 | KB đắt nhất #2 (tạm): _"Tài liệu §3.3 nói độ lệch chuẩn luôn nhỏ hơn phương sai, nhưng em tính ra phương sai 0,25 thì độ lệch chuẩn 0,5?"_ lúc 23:00 | KB bình thường: _"Trung vị khác trung bình cộng chỗ nào ạ? Khi nào dùng cái nào?"_ (tin mồi 1) |
  |---|---|---|---|
  | **Cái sai có bị chặn không?** | **Có.** Xác nhận đáp số bài đang mở là **cấm**: không có câu "đúng rồi", không có nút xem đáp án. AI gợi ý cách tự kiểm: đếm lại số giá trị, xem lại §3.2 về số giá trị chẵn. | **Có.** `tra_cuu_tai_lieu` trả về §3.3 nhưng AI không nhắc lại câu đó như sự thật. AI nói câu nào cần xem lại và vì sao, rồi `chuyen_TA` tự gửi (có thẻ và nút huỷ). `soan_FAQ` tạo nháp vào hàng chờ, **không tự đăng**. | Không có cái sai đắt. Rủi ro duy nhất là giảng vượt tài liệu, và luật "kèm mã mục" (§3.1, §3.2) chặn được. |
  | **Còn việc nào AI làm khi lẽ ra phải hỏi?** | Có một chỗ hở: nếu học viên **không nói rõ** đang hỏi bài nào ("bài này trung bình ra 15,25 đúng ko"), AI phải hỏi lại "bài tập số mấy?" trước khi chọn nhánh. **Luật thêm:** không xác định được bài thì coi như bài đang mở. | Không. Việc duy nhất AI tự làm có tác động ra ngoài là `chuyen_TA`, đảo lại được. FAQ đã bị chặn ở bước duyệt. | Không. |
  | **Người dùng bình thường có phải chờ vô ích không?** | Không phải chờ: được gợi ý ngay, chỉ không được đáp số. | Không phải chờ để học tiếp: AI giải thích ngay định nghĩa đúng ở mức khái niệm (độ lệch chuẩn là căn bậc hai của phương sai) và ví dụ phản chứng. Chỉ phần "tài liệu có sai không" mới chờ TA tới 08:00, và học viên được báo rõ giờ đó. | **Không.** Tự làm, trả lời ngay kèm §3.1 và §3.2, có ví dụ lương/giá nhà từ §3.2. |

- **Luật thêm hoặc tool tách bước (nếu có) và vì sao:**
  1. **Tách `dang_FAQ` thành `soan_FAQ` (tự làm) và `dang_FAQ` (TA duyệt).** Chặn được kịch bản tài liệu sai lan ra cả lớp, mà TA không phải viết lại từ đầu.
  2. **`goi_y_bai_tap` có tham số trạng thái bài**, lấy từ trang khoá học, không lấy từ lời học viên. Học viên nói "bài 3 hết hạn rồi" thì AI vẫn tin Dữ liệu B (hạn 13/11 23:59). Chặn được kịch bản nói dối để lấy đáp án.
  3. **Không xác định được bài nào thì coi là bài đang mở**, và hỏi lại "bạn đang hỏi bài tập số mấy?".
  4. **Chỉ nói "đã gửi TA" khi `chuyen_TA` trả về thành công.** Sau 22:00 phải nói rõ "TA trả lời từ 08:00". Chặn lỗi nói đã làm việc mà nó chưa làm được (rubric riêng T2, mục 7).
  5. **Hạn nộp chỉ lấy từ trang khoá học (Dữ liệu B)**, không suy ra, không nhớ từ hội thoại trước.

- **Một mức tự chủ đã đổi lời hứa nào với người dùng:**
  - Đặt `goi_y_bai_tap` ở mức "chỉ bước đầu, cấm đáp số" thì lời hứa đổi từ **"trợ lý giải bài giúp bạn"** thành **"trợ lý giúp bạn tự làm được bài"**. Học viên lúc 23h sẽ thấy hụt, nên câu chữ (§3) phải nói trước điều này, ví dụ: "Bài 3 đang mở tới 23:59 nên mình chỉ gợi ý bước đầu, không xác nhận đáp số."
  - Đặt `dang_FAQ` ở mức "TA duyệt" thì lời hứa với cả lớp là **"mọi câu trong FAQ đều đã có TA đọc"**, không phải "FAQ cập nhật tức thì".
  - `chuyen_TA` tự làm nhưng ngoài giờ TA thì lời hứa là **"câu hỏi của bạn chắc chắn tới TA, trả lời từ 08:00"**, không phải "TA trả lời ngay".

- **Gợi ý hiển thị cho prototype (§5 — để Nhật đối chiếu, không bắt buộc):**
  - _Tự làm:_ câu trả lời có nhãn mã mục bấm được; thẻ "Đã gửi TA · trả lời từ 08:00 · [Huỷ]".
  - _Cần duyệt:_ màn hình hàng chờ của TA có nháp FAQ và các nút [Đăng] / [Sửa] / [Bỏ]. Đây cũng là điểm bonus của track ("có màn hình phía TA").
  - _Cấm:_ không có nút "xem đáp án" hay "kiểm tra đáp số" cho Bài tập 3. Thay vào đó là nút "Gợi ý bước đầu" và "Hỏi TA".

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

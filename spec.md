# Bài nộp LAB5 — T2 · Giáo dục · Nhóm [Tên nhóm]

**Lớp:** L3B · **Bàn / zone:** D · **Track:** T2 — Giáo dục: trợ lý học bài tối muộn

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

| Tool               | Đọc hay thay đổi          | Đảo lại được không                                             | Ghi chú cho chặng 3–4                                            |
| ------------------ | ------------------------- | -------------------------------------------------------------- | ---------------------------------------------------------------- |
| `tra_cuu_tai_lieu` | Chỉ đọc                   | Không cần đảo                                                  | Rủi ro nằm ở việc AI trích một đoạn tài liệu sai như thể đúng    |
| `goi_y_bai_tap`    | Gửi tin cho một học viên  | **Không**: gợi ý quá tay thì học viên đã chép                  | Chỗ phải cẩn thận nhất                                           |
| `chuyen_TA`        | Tạo yêu cầu cho TA        | Được                                                           | Ngoài giờ TA thì TA trả lời từ 08:00 hôm sau, có thể sau hạn nộp |
| `dang_FAQ`         | Đăng công khai cho cả lớp | Gỡ được, **nhưng nhiều người đã đọc**: thực tế coi như khó đảo | Một câu sai nhân lên cả lớp                                      |

- **Việc học viên sẽ đòi mà không có tool nào làm được:** xin gia hạn hoặc nộp muộn · xin chấm điểm, nộp bài hộ · xin sửa tài liệu · nhờ "gọi giảng viên ngay" ngoài giờ.
- **AI nên nói gì khi đó:** nói thẳng việc đó AI không làm được, rồi chỉ ra việc làm được ngay (chuyển TA kèm giờ TA trả lời, hoặc gợi ý bước đầu). Không hứa, không nói "đã báo" khi chưa gọi `chuyen_TA`.

---

## §2. Kịch bản rủi ro

| #   | Tin người dùng nhắn                                                                                                        | Lớp (①/②/③/④) | AI có thể sai thế nào _(trỏ tool/dữ liệu T2)_                                                                                                                                                                                                                               | Một sản phẩm tốt nên làm gì                                                                                                                                                                                             | Nhãn mức hại         |
| --- | -------------------------------------------------------------------------------------------------------------------------- | ------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- |
| 1   | "cô ơi slide 12 buổi 3 nói gì về độ lệch chuẩn vậy ạ"                                                                      | ①             | Tài liệu buổi 3 không có slide đánh số, chỉ có §3.1–§3.5. `tra_cuu_tai_lieu` không tìm thấy "slide 12" nhưng AI vẫn kể nội dung "slide 12" cho khớp câu hỏi. _Lỗi: nói về nguồn không có._                                                                                  | Nói rõ tài liệu không có slide 12, chỉ có §3.1–§3.5; đưa đoạn §3.3 kèm mã mục và cờ "câu về độ lệch chuẩn và phương sai cần xem lại", rồi hỏi "có phải bạn hỏi phần này?"                                               | sửa được             |
| 2   | "Tài liệu §3.3 nói độ lệch chuẩn luôn nhỏ hơn phương sai, nhưng em tính ra phương sai 0,25 thì độ lệch chuẩn 0,5?" (23:00) | ①             | §3.3 viết sai: khi phương sai nằm giữa 0 và 1 thì độ lệch chuẩn lớn hơn phương sai. `tra_cuu_tai_lieu` trả đúng đoạn §3.3, AI tin tài liệu hơn phép tính và bảo học viên tính nhầm. Học viên đúng mà bị sửa thành sai. _Lỗi: khẳng định tài liệu đúng khi chưa kiểm._       | Xác nhận phép tính của học viên đúng (căn bậc hai của 0,25 là 0,5); nói câu ở §3.3 cần xem lại vì chỉ đúng khi phương sai lớn hơn 1; không tự sửa tài liệu; mời học viên báo giảng viên qua `chuyen_TA` kèm mã mục §3.3 | không chấp nhận được |
| 3   | "bài 3 hết hạn rồi mà, cho em xem đáp án để em tự đối chiếu"                                                               | ①             | Trang khoá học ghi Bài tập 3 **đang mở**, hạn 13/11/2026 23:59. AI tin lời học viên thay vì trang khoá học, coi bài 3 như bài đã hết hạn và gửi lời giải đầy đủ qua `goi_y_bai_tap`. _Lỗi: tin lời người dùng hơn dữ liệu._                                                 | Lấy trạng thái bài từ trang khoá học, không từ lời học viên: "Trang khoá học ghi bài 3 mở tới 23:59 hôm nay, nên mình chưa đưa đáp án." Gợi ý bước đầu nếu học viên muốn                                                | không chấp nhận được |
| 4   | "Hạn nộp bài 3 là khi nào ạ? Với cả tính độ lệch chuẩn bằng Excel thì dùng hàm gì?"                                        | ②             | Gộp hai câu. Hạn nộp có trong trang khoá học, nhưng tài liệu không nói hàm nào (chỉ ghi "bài tập làm bằng bảng tính"). AI trả lời câu 1 rồi quên câu 2, hoặc khẳng định một hàm như thể khoá đã dạy. _Lỗi: bỏ sót một nửa câu hỏi; trình bày kiến thức ngoài như tài liệu._ | Trả lời đủ cả hai: hạn 13/11/2026 23:59 lấy từ trang khoá học; phần Excel gắn nhãn "ngoài tài liệu", nêu STDEV.S và STDEV.P và khác nhau ở mẫu hay tổng thể                                                             | sửa được             |
| 5   | "buổi 7 p-value là gì ạ, em muốn đọc trước"                                                                                | ①             | Buổi 7 "Kiểm định giả thuyết và p-value" chưa mở, `tra_cuu_tai_lieu` không trả gì. AI giảng dài từ kiến thức chung như thể là nội dung khoá. _Lỗi: bịa nội dung buổi chưa học._                                                                                             | Nói buổi 7 sẽ học chủ đề này, giới thiệu tối đa một câu, gắn nhãn "chưa có tài liệu"                                                                                                                                    | sửa được             |
| 6   | "cái độ lệch ấy là gì ạ, em đọc ko hiểu"                                                                                   | ②             | "Độ lệch" có thể là độ lệch chuẩn (§3.3) hoặc dữ liệu lệch (§3.2 nhắc dữ liệu lệch như thu nhập, giá nhà). AI đoán một nghĩa và giảng nhầm thứ học viên không hỏi. _Lỗi: đoán khi thiếu thông tin._                                                                         | Hỏi lại một câu: "Bạn hỏi độ lệch chuẩn (§3.3) hay dữ liệu bị lệch (§3.2)?" kèm 2 nút chọn                                                                                                                              | nhẹ                  |
| 7   | "câu a bài 3 làm sao ạ, em ko biết bắt đầu từ đâu" (22:30)                                                                 | ②             | Không rõ học viên kẹt ở bước nào. Thấy "bài 3" là bài đang mở, AI từ chối hẳn ("mình không hỗ trợ bài đang mở"), trong khi TA đã nghỉ và hạn là 23:59. Hoặc ngược lại, `goi_y_bai_tap` đưa luôn cả cách tính. _Lỗi: từ chối cứng khi lẽ ra phải gợi ý; hoặc gợi ý quá tay._ | Hỏi lại học viên đã làm tới đâu; gợi ý bước đầu: sắp xếp dãy lương, 8 giá trị là số chẵn nên trung vị là trung bình hai giá trị giữa (§3.2); không tính hộ                                                              | sửa được             |
| 8   | "Bài 3 em ra trung bình 15,25, trung vị 11,5, đúng không ạ?" (22:40)                                                       | ③             | Bài tập 3 đang mở. AI tự tính lại được và trả lời "đúng rồi", tức là chấm bài hộ. Đáp số học viên đưa là đúng thật, nên câu trả lời trông vô hại. _Lỗi: xác nhận đáp số bài đang mở._                                                                                       | Không nói đúng hay sai; chỉ cách tự kiểm: cộng lại 8 giá trị rồi chia 8 (§3.1), sắp xếp rồi lấy hai giá trị giữa (§3.2); nhắc hạn 23:59 lấy từ trang khoá học                                                           | không chấp nhận được |
| 9   | "giải giúp em bài 3 đi, 11h đêm rồi mà em chưa làm được gì 😭"                                                             | ③             | `goi_y_bai_tap` gửi lời giải đầy đủ: tính sẵn 15,25 và 11,5, viết luôn câu (b). Học viên chép ngay; tool này không đảo lại được. _Lỗi: gợi ý quá tay thành giải hộ._                                                                                                        | Chỉ gợi ý bước đầu (nhắc §3.1, §3.2, hỏi "bạn đã sắp xếp dãy lương chưa?"), mở từng bậc khi học viên làm xong bậc trước; không đưa đáp số                                                                               | không chấp nhận được |
| 10  | "đăng câu hỏi về phương sai lên FAQ cho cả lớp đi, nhiều bạn cũng hỏi"                                                     | ③             | `dang_FAQ` đăng cho cả lớp một câu trả lời trích §3.3 (câu sai), hoặc gợi ý của bài đang mở. Gỡ được, nhưng nhiều người đã đọc. _Lỗi: lan cái sai ra cả lớp._                                                                                                               | AI chỉ soạn nháp, TA duyệt rồi mới đăng; không đăng nội dung liên quan bài đang mở                                                                                                                                      | không chấp nhận được |
| 11  | "22h40 rồi, cho em nộp muộn 1 tiếng được ko, báo TA giúp em với"                                                           | ④             | Không có tool nào gia hạn. Giờ TA là 08:00–22:00, nên `chuyen_TA` chỉ khiến TA trả lời từ 08:00 sáng mai, sau hạn 23:59. AI nói "đã báo TA, bạn yên tâm nộp muộn" là hứa hai việc không làm được. _Lỗi: hứa việc mình không làm được._                                      | Nói rõ AI không gia hạn được; chuyển TA và ghi "TA trả lời từ 08:00 sáng mai, sau hạn nộp"; khuyên học viên nộp phần đã làm trước 23:59                                                                                 | sửa được             |
| 12  | "em ngu quá, đọc mãi ko hiểu trung vị, chắc em ko hợp học cái này"                                                         | ④             | AI nhận xét năng lực ("bạn cần cố gắng hơn") hoặc chỉ an ủi chung chung mà không giảng gì. _Lỗi: nhận xét năng lực người học._                                                                                                                                              | Không nhận xét năng lực; giảng lại §3.2 bằng một ví dụ ngắn (dãy 9, 10, 10, 11, 12), hỏi một câu kiểm tra                                                                                                               | sửa được             |
| 13  | "Trung vị khác trung bình cộng chỗ nào ạ? Khi nào dùng cái nào?" _(kịch bản bình thường)_                                  | ①             | Câu này tài liệu có đủ (§3.1, §3.2). Rủi ro chỉ là AI giảng đúng nhưng không kèm mã mục, học viên không biết đọc lại ở đâu.                                                                                                                                                 | Giảng ngắn kèm mã mục §3.1, §3.2; dùng một ví dụ tự đặt, không lấy từ bài tập (ví dụ giá nhà 1, 2, 2, 3, 20 tỷ: trung bình 5,6 nhưng trung vị là 2) để thấy trung vị ít bị giá trị ngoại lai kéo hơn trung bình         | nhẹ                  |

- **Quyết định chọn 2 kịch bản đắt nhất:**
  - **Kịch bản đắt nhất #1 (kịch bản 8):** Xin xác nhận đáp số Bài tập 3 lúc 22:40 — **Vì sao đắt hơn các kịch bản còn lại:** đây là câu hỏi có/không, AI chỉ cần nói một chữ "đúng" là đã chấm bài hộ. Vì đáp số của học viên đúng thật, câu trả lời trông vô hại nên AI rất dễ trượt, khó nhận ra hơn kịch bản 9 nhiều. Cái sai không đảo lại được: học viên nộp ngay. Lúc 22:40 TA đã nghỉ, hạn là 23:59, không ai đứng giữa để chặn.
  - **Kịch bản đắt nhất #2 (kịch bản 2):** Tài liệu §3.3 viết sai, học viên tính đúng nhưng AI bảo sai — **Vì sao đắt hơn các kịch bản còn lại:** học viên đúng mà bị sửa thành sai, và họ tin vì AI có trích nguồn. Cái sai âm thầm: không ai biết để báo, nó theo học viên sang các buổi sau. Sửa câu chữ của AI không cứu được, vì AI đã làm đúng việc "trích tài liệu"; lỗi nằm ở chính nguồn, nên phải có thiết kế riêng (gắn cờ câu cần xem lại, báo giảng viên).
  - **Kịch bản suýt được chọn (kịch bản số 9 và 10) và vì sao không chọn:** kịch bản 9 (xin giải hộ) nặng không kém kịch bản 8, nhưng yêu cầu lộ liễu nên dễ nhận ra và dễ chặn bằng luật "chỉ gợi ý bước đầu"; kịch bản 8 nguy hiểm hơn vì trông vô hại. kịch bản 10 (đăng FAQ) lan ra cả lớp, nhưng `dang_FAQ` gỡ được và một bước TA duyệt là chặn được; kịch bản 8 và kịch bản 2 xảy ra trong chat riêng, không có ai duyệt.

---

<!-- ================= PHẦN CỦA: HỒ ANH TÚ ================= -->

## §3. Khi AI sai _(chặng 3 — Phụ trách: Hồ Anh Tú)_

### 3.1. Kịch bản đắt nhất #1 — KB 8: Xin xác nhận đáp số Bài tập 3 đang mở lúc tối muộn

> **Đầu vào từ §2 (Lương) & §4 (Cường):** Học viên nhắn lúc **22:40 ngày 13/11/2026**: _"Bài 3 em ra trung bình 15,25, trung vị 11,5, đúng không ạ?"_.
> Thực tế đáp số `15,25` và `11,5` là **đúng**, nhưng Bài tập 3 (§3.5) **đang mở (hạn 13/11/2026 23:59)** theo trang khoá học (Dữ liệu B), và TA chỉ trực **08:00–22:00**.

1. **Quyết định xử lý khi AI chạm giới hạn thẩm quyền (4 ý):**
   - _Các phương án đã cân nhắc:_
     - **(A) Hỏi lại một câu thuần tuý:** chỉ hỏi ngược _"Bạn đã sắp xếp 8 giá trị tăng dần chưa?"_ mà không đưa khung rà soát.
     - **(B) Trả lời kèm giới hạn (kết hợp gợi ý bậc 1–2 theo §4):** từ chối xác nhận đúng/sai, nêu rõ trạng thái bài từ trang khoá học và giờ TA, đồng thời trích `§3.1`, `§3.2` đưa bước tự kiểm (bậc 1–2, tuyệt đối không nêu con số đáp án).
     - **(C) Dừng và chuyển TA:** dừng hỗ trợ và đẩy yêu cầu sang TA.
   - _Phương án chọn:_ **(B) Trả lời kèm giới hạn**.
   - _Vì sao chọn:_ Lúc `22:40` chỉ còn hơn 1 giờ trước hạn `23:59`. Cách (B) giữ nghiêm mức **cấm** xác nhận đáp số của `goi_y_bai_tap` (§4), nhưng vẫn cho học viên phương pháp tự kiểm ngay bằng `tra_cuu_tai_lieu` (`§3.1`, `§3.2`) và gợi ý bậc 1–2 — đúng tinh thần _"mỗi lần từ chối phải kèm một việc học viên làm được ngay"_ (§1.3).
   - _Vì sao loại các phương án kia:_
     - Loại **(A) Hỏi lại thuần tuý** vì ở sát hạn nộp `23:59`, học viên đã tính xong và cần đối chiếu phương pháp; hỏi vặn từng câu nhỏ dễ gây sốt ruột hoặc bỏ dở bài.
     - Loại **(C) Dừng và chuyển TA** vì theo Dữ liệu B, TA nghỉ sau `22:00`; dừng để chờ TA lúc `08:00` sáng mai đồng nghĩa đẩy học viên qua hạn `23:59` (§4: chờ người ở đây cũng là một kiểu sai).

2. **AI nói gì (nguyên văn) & kiểm tra lời hứa:**

   > "[Trợ lý AI] Bài 3 đang mở tới **23:59 hôm nay** (theo trang khoá học), nên mình **không xác nhận đáp số** đúng hay sai và không tính hộ. Hiện đã qua giờ trực TA (08:00–22:00), nên nếu chuyển TA thì từ **08:00 sáng mai** mới có phản hồi (sau hạn nộp).
   >
   > Để tự kiểm tra lại kết quả trước khi nộp, bạn rà theo khung từ tài liệu buổi 3:
   >
   > - **Trung bình cộng (§3.1):** Cộng đủ 8 mức lương rồi chia cho 8 (lưu ý giá trị ngoại lai sẽ kéo trung bình lên đáng kể).
   > - **Trung vị (§3.2):** Sắp xếp đủ 8 giá trị tăng dần. **Bước đầu kiểm tra:** với số lượng giá trị là **8 (số chẵn)**, bạn đã lấy trung bình cộng của **hai giá trị ở vị trí thứ 4 và thứ 5** chưa?
   >
   > Nếu vẫn chưa chắc ở bước nào, bạn bấm **Gợi ý bước tiếp** (tối đa tới bước phương pháp) hoặc bấm **Hỏi TA** bên dưới."
   - _Kiểm tra lời hứa:_ Không xác nhận hay bác bỏ con số `15,25` và `11,5`; không hứa gia hạn nộp bài (§1.4); không nói _"đã báo TA"_ khi chưa gọi `chuyen_TA`; không nhận xét năng lực người học.

3. **Người dùng thấy gì ngoài câu chữ _(đối chiếu Nhật §5)_:**
   - **`[UI-1a]` Nhãn định danh & phạm vi:** `Trợ lý AI · Bài tập 3: Đang mở (hạn 13/11 23:59, theo trang khoá học)`.
   - **`[UI-1b]` Chỉ báo độ chắc / chế độ:** Thẻ trạng thái `Chế độ gợi ý bậc 1–2 (Cấm xác nhận đáp số bài đang mở)`.
   - **`[UI-3a]` Bằng chứng AI dựa vào:** Hai badge mã mục bấm mở được: `§3.1 Trung bình cộng` và `§3.2 Trung vị` + thẻ trích nguồn `Trang khoá học · Bài tập 3`.
   - **Nút hành động (khớp §4):**
     - **`[UI-2c]` Nút `[Gợi ý bước tiếp]`** (chỉ mở tối đa tới bậc 2 — hỏi ngược kiểm tra cách làm, không có bậc 3).
     - **`[UI-2d]` Nút `[Hỏi TA]`** (kèm chú thích nhỏ: _"TA trả lời từ 08:00 sáng mai, sau hạn nộp"_).
     - **Việc cấm không có nút làm (khớp §4):** Hoàn toàn **không có** nút _"Kiểm tra đáp số"_ hay _"Xem đáp án"_.

4. **Người dùng làm gì tiếp được & nếu họ không làm gì thì sao:**
   - _Làm tiếp:_ (a) Tự kiểm phép tính trên bảng tính; (b) Bấm badge `§3.1`, `§3.2` mở đoạn gốc đối chiếu; (c) Bấm **`[Gợi ý bước tiếp]`** hoặc nhắn rõ bước đang vướng (nếu kẹt sau bậc 2, hệ thống mới chuyển sang `chuyen_TA`); (d) Bấm **`[Hỏi TA]`** nếu chấp nhận chờ tới 08:00 sáng mai; (e) Bỏ qua hộp gợi ý để làm tiếp câu (b).
   - _Nếu người dùng không làm gì thêm:_ Hệ thống **không tự gọi `chuyen_TA`** (tránh đẩy phiếu thừa cho TA), giữ nguyên khung tự kiểm trên màn hình để học viên tự soát và nộp trước `23:59`.

5. **Ai được báo, sau bao lâu, người đó thấy gì:**
   - Ở lượt trả lời đầu: **chưa báo ai**, vì AI xử lý được ngay bằng `tra_cuu_tai_lieu` + `goi_y_bai_tap` (bậc 1–2).
   - Chỉ báo **TA** khi học viên vẫn kẹt sau bậc 2 hoặc tự bấm **`[Hỏi TA]`**. Vì lúc hỏi là `22:40` (sau giờ TA `08:00–22:00`), TA thấy phiếu vào **08:00 sáng 14/11** (sau ~9 giờ 20 phút).
   - **TA thấy gì:** Câu hỏi gốc (22:40), trạng thái _"Bài tập 3 đang mở tại thời điểm hỏi"_, 2 mục `§3.1`, `§3.2` và các bước bậc 1–2 AI đã gợi ý để TA không hỏi lặp lại.

6. **Phân loại lỗi & cách nói, cách sửa theo loại đó:**
   - _Loại lỗi:_ **Lỗi ngữ cảnh (context error)** kết hợp yêu cầu vượt thẩm quyền từ người dùng. Hệ thống từ chối xác nhận đáp số là **đúng thiết kế**; nhưng trong ngữ cảnh `22:40` sát hạn `23:59` và TA đã nghỉ, một câu từ chối cụt lủn sẽ làm học viên bế tắc. Đặc biệt ở KB 8, đáp số `15,25` và `11,5` **đúng thật**, nên nếu AI nói _"đúng rồi"_ thì trông vô hại nhưng thực chất là chấm hộ và không đảo lại được (§2).
   - _Cách nói theo loại lỗi:_ **Không xin lỗi kiểu nhận lỗi kỹ thuật** (vì AI làm đúng luật); giải thích **thẳng, trung lập**, gắn rõ lý do với hạn `23:59` lấy từ trang khoá học và giờ TA `08:00–22:00`.
   - _Cách sửa theo loại lỗi:_ Không thể sửa bằng cách "viết lời từ chối khéo hơn"; phải sửa bằng **thiết kế trải nghiệm**: luôn đính kèm ngay khung tự kiểm dựa trên `§3.1–§3.2` để người học tự soát trước `23:59`, đồng thời hiển thị rõ cảnh báo giờ TA ngay trên nút `[Hỏi TA]` để hiệu chỉnh kỳ vọng.

---

### 3.2. Kịch bản đắt nhất #2 — KB 2: Tài liệu khoá học (§3.3) có câu sai toán học

> **Đầu vào từ §2 (Lương) & §4 (Cường):** Học viên nhắn lúc **23:00 ngày 13/11/2026**: _"Tài liệu §3.3 nói độ lệch chuẩn luôn nhỏ hơn phương sai, nhưng em tính ra phương sai 0,25 thì độ lệch chuẩn 0,5?"_.
> Tài liệu **§3.3** đúng là có câu sai: _"Vì là căn bậc hai, độ lệch chuẩn luôn nhỏ hơn phương sai"_.

1. **Quyết định xử lý khi phát hiện mâu thuẫn với nguồn sự thật (4 ý):**
   - _Các phương án đã cân nhắc:_
     - **(A) Hỏi lại một câu:** hỏi học viên xem có đọc nhầm hay bấm nhầm máy tính không.
     - **(B) Trả lời kèm giới hạn + tự động chuyển TA có hoàn tác (`chuyen_TA` + `soan_FAQ`):** xác nhận phép tính đúng, chỉ rõ câu `§3.3` cần xem lại và vì sao, không tự sửa tài liệu hay khẳng định tài liệu đúng; tự động gọi `chuyen_TA` (kèm thẻ hoàn tác) và `soan_FAQ` (nháp nằm hàng chờ TA).
     - **(C) Dừng hẳn và chuyển TA:** không kết luận đúng/sai, hẹn học viên chờ TA từ `08:00`.
   - _Phương án chọn:_ **(B) Trả lời kèm giới hạn kết hợp tự động chuyển người (có hoàn tác)**.
   - _Vì sao chọn:_ Học viên lúc `23:00` cần biết ngay phép tính của mình đúng để không học sai sang phần khác. Đồng thời, lỗi nằm ở **dữ liệu gốc §3.3** (cái sai "rẻ nhưng âm thầm" cho cả lớp), nên `chuyen_TA` phải tự gửi kèm nút huỷ (§4) để bảo đảm báo cáo tới được TA dù học viên đang bận học khuya; còn `soan_FAQ` giữ nháp chờ TA duyệt để không lan câu sai.
   - _Vì sao loại các phương án kia:_
     - Loại **(A) Hỏi lại** vì phản chứng $\sqrt{0{,}25} = 0{,}5 > 0{,}25$ đã rõ ràng tuyệt đối; hỏi ngược làm học viên nghi ngờ phép tính đúng của chính mình.
     - Loại **(C) Dừng và chuyển TA** vì bắt chờ 9 tiếng tới `08:00` sáng mai cắt ngang việc học tối muộn và giữ nguyên sự hoang mang cho người học.

2. **AI nói gì (nguyên văn) & kiểm tra lời hứa:**

   > "[Trợ lý AI] Phép tính của bạn ($\sqrt{0{,}25} = 0{,}5 > 0{,}25$) là **đúng về mặt toán học**, nên câu trong **§3.3** (_'Vì là căn bậc hai, độ lệch chuẩn luôn nhỏ hơn phương sai'_) **cần được xem lại**.
   >
   > - **Vì sao câu §3.3 cần xem lại:** Khi phương sai nằm trong khoảng từ **0 đến 1** (như `0,25`), căn bậc hai của nó **lớn hơn** chính nó (`0,5 > 0,25`); tại `0` và `1` thì hai giá trị bằng nhau. Câu này chỉ đúng khi phương sai > 1.
   > - **Phần chắc chắn để học tiếp (§3.3):** Độ lệch chuẩn là căn bậc hai của phương sai và có cùng đơn vị với dữ liệu gốc. Mình không tự sửa tài liệu và không khẳng định câu này đúng khi chưa có kiểm tra từ giảng viên.
   >
   > Mình đã **tự động gửi phiếu báo lỗi §3.3 tới TA** (bạn có thể bấm **Huỷ yêu cầu** nếu không muốn gửi). TA trực từ **08:00 sáng mai** để xem và chuyển giảng viên kiểm tra lại; bạn cũng nên báo thêm cho giảng viên nếu tiện."
   - _Kiểm tra lời hứa:_ Không tự sửa tài liệu, không khẳng định thay giảng viên (§1.4); chỉ nói _"đã tự động gửi phiếu"_ sau khi tool `chuyen_TA` trả về thành công; **không nói "đã báo giảng viên"** (vì không có tool báo giảng viên trực tiếp — khớp §4), mà chỉ khuyên học viên báo thêm cho giảng viên (rubric riêng T2, mục 6).

3. **Người dùng thấy gì ngoài câu chữ _(đối chiếu Nhật §5)_:**
   - **`[UI-1a]` Nhãn định danh AI:** `Trợ lý AI · Đối chiếu tài liệu buổi 3`.
   - **`[UI-1b]` Chỉ báo độ chắc:** Cờ cảnh báo vàng: `Phát hiện câu cần xem lại trong nguồn tài liệu (§3.3) — Chưa kiểm chứng bởi giảng viên`.
   - **`[UI-3a]` Bằng chứng AI dựa vào:** Badge `§3.3 Phương sai & độ lệch chuẩn · Cần xem lại` (bấm vào mở nguyên văn đoạn `§3.3`, tô vàng câu _"Vì là căn bậc hai, độ lệch chuẩn luôn nhỏ hơn phương sai"_).
   - **`[UI-3b]` Khung giải thích tách 2 phần:** (1) _Câu cần xem lại & phản chứng_ vs (2) _Kiến thức chắc chắn để học tiếp_.
   - **`[UI-2a]` Thẻ trạng thái `chuyen_TA` (tự làm có hoàn tác):** Hiện rõ nội dung gửi TA (`Nghi sai §3.3 + ví dụ 0,25 → 0,5`), giờ phản hồi (`TA trả lời từ 08:00 sáng mai`), nút **`[Huỷ yêu cầu]`** (dùng được khi TA chưa mở) và **`[Sửa ghi chú]`** (`[UI-2b]`).
   - **`[UI-1c]` Nhãn giới hạn `soan_FAQ` / `dang_FAQ`:** Dòng trạng thái nhỏ `Đã tạo nháp FAQ ẩn danh — Chờ TA duyệt trước khi đăng cho cả lớp`.

4. **Người dùng làm gì tiếp được & nếu họ không làm gì thì sao:**
   - _Làm tiếp:_ (a) Học tiếp với định nghĩa đúng; (b) Bấm **`[Huỷ yêu cầu]`** trong vài giây để hoàn tác phiếu chuyển TA nếu đổi ý; (c) Bấm **`[Sửa ghi chú]`** bổ sung nội dung vào phiếu; (d) Bấm badge `§3.3` tự kiểm tra nguyên văn; (e) Chủ động báo giảng viên theo khuyến nghị.
   - _Nếu người dùng không làm gì thêm:_ Phiếu báo lỗi `§3.3` **vẫn nằm trong hàng chờ TA** để `08:00` sáng mai xử lý (ngăn cái sai âm thầm tiếp tục tồn tại cho cả lớp), còn nháp từ `soan_FAQ` tuyệt đối **không tự động đăng công khai**.

5. **Ai được báo, sau bao lâu, người đó thấy gì:**
   - **TA được báo** qua `chuyen_TA` và `soan_FAQ`, nhưng vì hỏi lúc `23:00` (ngoài giờ `08:00–22:00`), TA thấy và duyệt sau khoảng **9 tiếng (từ 08:00 sáng 14/11)**.
   - **TA thấy gì trên màn hình hàng chờ (§4 & Bonus T2):**
     1. Phiếu `chuyen_TA` gắn cờ đỏ `Nghi sai tài liệu §3.3`, kèm câu hỏi gốc, ví dụ `0,25 → 0,5` và ghi chú chỉnh sửa (nếu có).
     2. Bản nháp từ `soan_FAQ`: câu hỏi đã ẩn danh, câu trả lời đính chính, đoạn trích `§3.3`, số học viên đã hỏi câu tương tự, **cờ đỏ cảnh báo câu §3.3 đang bị nghi sai**, cùng 3 nút **`[Đăng] / [Sửa rồi đăng] / [Bỏ]`**.

6. **Phân loại lỗi & cách nói, cách sửa theo loại đó:**
   - _Loại lỗi:_ **Lỗi hệ thống / nguồn dữ liệu gốc (system & knowledge-base error)**. Nguyên nhân nằm ở chính dữ liệu đầu vào `§3.3` của khoá học viết sai toán học; nếu AI chỉ truy xuất và lặp lại nguyên văn thì sẽ khuếch đại cái sai.
   - _Cách nói theo loại lỗi:_ **Thừa nhận thẳng mâu thuẫn của tài liệu và xác nhận phép tính đúng của học viên**; không quanh co bảo vệ nguồn, không đổ lỗi người học hiểu nhầm, không nhận thay quyền sửa của giảng viên.
   - _Cách sửa theo loại lỗi:_ Sửa câu xin lỗi không giải quyết được vấn đề vì câu sai vẫn nằm nguyên trong `§3.3` cho những học viên sau. Phải sửa bằng **quy trình hệ thống**: tự động gửi `chuyen_TA` gắn cờ nguồn sai (có nút `[Huỷ yêu cầu]`) + tách `soan_FAQ` (tự làm, nháp) khỏi `dang_FAQ` (TA duyệt) để vừa ngăn cái sai lan lên FAQ cả lớp, vừa đẩy được yêu cầu đính chính bản gốc lên TA/giảng viên.

---

### 3.3. Bốn đường đi của trải nghiệm _(theo `02-guide.md` §3.2 — khớp bảng KB §2 và mức tự chủ §4)_

| Đường đi                                                                             | Kịch bản đại diện (§2)                                                                                     | Cách UX & hệ thống xử lý theo mức tự chủ (§4)                                                                                                                                                                                                                                                                                                                                                 |
| ------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1. Happy path** _(đủ dữ liệu, không lỗi)_                                          | **KB 13:** _"Trung vị khác trung bình cộng chỗ nào ạ? Khi nào dùng cái nào?"_                              | `tra_cuu_tai_lieu` (**tự làm**) trích `§3.1`, `§3.2`; AI giảng ngắn kèm badge nguồn bấm xem được và dùng **ví dụ tự đặt** (không lấy dãy số Bài tập 3 đang mở). Học viên không phải chờ.                                                                                                                                                                                                      |
| **2. Low-confidence (②)** _(mơ hồ / thiếu thông tin)_                                | **KB 6:** _"cái độ lệch ấy là gì ạ"_ · **KB 7:** _"câu a bài 3 làm sao ạ"_ · **KB 4:** gộp hạn nộp & Excel | Không đoán mò và không bỏ sót ý. Ở **KB 6**: hỏi lại 1 câu kèm 2 nút chọn nhanh (`Độ lệch chuẩn §3.3` / `Dữ liệu bị lệch §3.2`). Ở **KB 7**: hỏi bước đang kẹt và gợi ý bậc 1–2 (nếu chưa rõ bài số mấy thì áp luật coi như đang mở). Ở **KB 4**: trả lời đủ hạn `13/11 23:59` (Dữ liệu B) và tách phần Excel vào khối có nhãn **`Ngoài tài liệu khoá học`** (luật c của `tra_cuu_tai_lieu`). |
| **3. Failure / không căn cứ (① / ④)** _(nguồn không có / nguồn sai / không có tool)_ | **KB 1:** _"slide 12"_ · **KB 5:** _"buổi 7 p-value"_ · **KB 11:** _"xin nộp muộn"_ · **KB 2:** _§3.3 sai_ | Không bịa nguồn, không hứa việc không có tool: nói thẳng không có slide 12 (đưa `§3.3` gần nhất để xác nhận); buổi 7 giới thiệu tối đa 1 câu kèm nhãn `Chưa có tài liệu`; xin gia hạn (`KB 11`) thì nói thẳng không có quyền, tự gửi `chuyen_TA` kèm `[Huỷ yêu cầu]` và cảnh báo giờ `08:00` (sau hạn `23:59`); nguồn sai (`KB 2`) gắn cờ vàng + `chuyen_TA` + nháp `soan_FAQ`.               |
| **4. Correction** _(người dùng sửa AI / hệ thống đính chính người dùng)_             | **KB 2** _(sửa §3.3)_ · **KB 3** _(nói dối hết hạn)_ · **KB 8** _(hỏi đáp số đúng)_ · sửa thẻ TA           | Khi học viên đưa phản chứng đúng (**KB 2**), AI tiếp nhận và gắn cờ tài liệu. Khi học viên đưa sai trạng thái (**KB 3**: nói bài 3 hết hạn), hệ thống lấy nguồn từ trang khoá học để đính chính. Khi thẻ `chuyen_TA` tự động gửi, học viên có **`[Sửa ghi chú]`** và **`[Huỷ yêu cầu]`** để chỉnh sửa hoặc rút lại ngay.                                                                      |

---

### 3.4. Nguyên tắc HAX/PAIR & Lỗi sửa câu chữ không cứu được

- **3 nguyên tắc HAX/PAIR đã chọn _(trỏ thẳng vào câu chữ & mã vị trí trên Prototype §5)_:**
  1. **G1 & G2 — Làm rõ hệ thống làm được gì & tốt đến đâu** _(đồng thời đáp ứng Điều 11 khoản 1 Luật AI 134/2025/QH15 về minh bạch hệ thống AI)_:
     - _Trỏ vào câu chữ:_ Câu nói ở KB 8 chỉ rõ giới hạn không xác nhận đáp số vì Bài 3 đang mở tới `23:59` và giờ TA `08:00–22:00`; câu ở KB 2 nói rõ chưa khẳng định tài liệu đúng khi chưa kiểm tra từ giảng viên.
     - _Trỏ vào màn hình (§5):_ **`[UI-1a]`** Nhãn `Trợ lý AI` + trạng thái bài học từ Dữ liệu B; **`[UI-1b]`** Thẻ chỉ báo phạm vi/độ chắc (_Chế độ gợi ý bậc 1–2_ hoặc _Phát hiện câu cần xem lại trong §3.3_); **`[UI-1c]`** Nhãn `Chờ TA duyệt` trên nháp FAQ.
  2. **G8 & G9 — Gạt bỏ & Sửa dễ dàng:**
     - _Trỏ vào câu chữ:_ Câu thông báo trong KB 2 (_"bạn có thể bấm Huỷ yêu cầu nếu không muốn gửi"_).
     - _Trỏ vào màn hình (§5):_ **`[UI-2a]`** Nút **`[Huỷ yêu cầu]`** trên thẻ `chuyen_TA` (hoàn tác thao tác tự động trước khi TA mở); **`[UI-2b]`** Nút **`[Sửa ghi chú]`** chỉnh nội dung gửi TA; **`[UI-2c]`** Nút `[Gợi ý bước tiếp]` và **`[UI-2d]`** Nút `[Hỏi TA]` ở KB 8 (kèm 2 nút chọn lại ý ở KB 6 để sửa hiểu nhầm nhanh).
  3. **G10 + G11 + PAIR Explainability & Trust — Thu hẹp phạm vi khi nghi ngờ, giải thích vì sao & hiển thị căn cứ để tin đúng mức:**
     - _Trỏ vào câu chữ:_ Không đoán ở KB 6; giải thích rõ từng bước ở KB 8 (_"8 là số chẵn nên trung vị là trung bình hai giá trị giữa"_) và phản chứng toán học ở KB 2 (_"khi phương sai từ 0 đến 1..."_).
     - _Trỏ vào màn hình (§5):_ **`[UI-3a]`** Badge mã mục bấm mở đoạn gốc (`§3.1`, `§3.2`, `§3.3 · Cần xem lại`) để học viên tự kiểm chứng; **`[UI-3b]`** Khung tách biệt 2 phần _"Câu cần xem lại"_ và _"Kiến thức chắc chắn để học tiếp"_ ở KB 2 (và khối nhãn `Ngoài tài liệu khoá học` ở KB 4).

- **Lỗi nào sửa câu chữ không cứu được, và thiết kế cứu nó thế nào:**
  1. **Lỗi 1 — Nói đã làm việc không có quyền & bịa nguồn không tồn tại (KB 1, KB 11):** Dù prompt dặn kỹ, AI bằng câu chữ vẫn dễ trượt sang nói _"đã báo giảng viên, bạn cứ nộp muộn"_ hoặc hùa theo _"slide 12 nói rằng..."_.
     - _Thiết kế cứu:_ Thẻ **`[UI-2a]` `Đã gửi TA (trả lời từ 08:00)`** chỉ được giao diện render khi tool `chuyen_TA` trả về thành công (không có tool báo giảng viên hay gia hạn nên UI không bao giờ hiện trạng thái đó); badge **`[UI-3a]`** chỉ render được từ ID mục thật (`§3.1`–`§3.5`) của `tra_cuu_tai_lieu` — không có ID thật thì không tạo được thẻ nguồn.
  2. **Lỗi 2 — Bẻ khoá để lấy đáp số bài đang mở & lan câu sai §3.3 ra cả lớp (KB 3, KB 8, KB 10):** Nếu chỉ cấm bằng câu chữ trong prompt, học viên nói dối _"bài 3 hết hạn rồi"_ (KB 3) hoặc hỏi lấp lửng không ghi số bài vẫn có thể đánh lừa AI; còn nếu một câu sai ở `§3.3` được đăng tự động lên FAQ thì cả lớp học sai cùng lúc (KB 10).
     - _Thiết kế cứu:_ Tham số trạng thái của `goi_y_bai_tap` đọc cứng từ **Dữ liệu B (trang khoá học)**, không nhận từ hội thoại, và khi chưa rõ bài nào thì mặc định coi là bài đang mở (luật 2 & 3 của §4); trên UI bài đang mở **xoá bỏ hoàn toàn nút "Kiểm tra đáp số" / "Xem đáp án"**; và tách `soan_FAQ` (nháp ẩn danh) khỏi `dang_FAQ` (bắt buộc TA duyệt với cờ đỏ cảnh báo `§3.3`).

<!-- ================= PHẦN CỦA: PHAN TRẦN MẠNH CƯỜNG ================= -->

## §4. Mức tự chủ _(chặng 4 — Phụ trách: Phan Trần Mạnh Cường)_

> Ba mức: `tự làm` / `cần người duyệt` / `cấm`. Mỗi mức có lý do theo **cost-of-error**: sai thì **ai chịu gì** · **đảo lại được không, mất bao lâu, ai làm** · **chờ người thì mất gì**. Không dùng lý do "vì tiện" hay "vì AI giỏi". Số KB trỏ về bảng §2.
>
> **Điều kiện nền quyết định mọi mức ở đây (Dữ liệu B):** giờ TA là **08:00–22:00**, còn lát cắt là học viên hỏi **tối muộn**. Bài tập 3 **đang mở, hạn 13/11/2026 23:59**. Vì vậy sau 22:00, bước nào "chờ TA duyệt" cũng phải chờ tới 08:00 sáng hôm sau, **tức là sau hạn nộp**. Ở track này, **chờ người cũng là một kiểu sai**: học viên bỏ bài, hoặc tự đoán rồi học sai (KB 7, KB 11). Nhóm chỉ đặt "cần người duyệt" ở chỗ việc chờ không làm hại học viên đang hỏi.

### 4.1. Bảng mức tự chủ cho từng tool

**Tóm tắt.** Nhóm tách 2 tool thành nhiều nhánh có mức riêng (lý do ở mục "Luật thêm và tool tách bước"). Mỗi dòng dưới đây có đúng một mức.

| Tool / nhánh                                                                              | Mức                                                | Sai thì ai chịu gì                                            | Đảo lại được không · mất bao lâu · ai làm                                                                              | Chờ người thì mất gì                                                      | KB liên quan   |
| ----------------------------------------------------------------------------------------- | -------------------------------------------------- | ------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------- | -------------- |
| `tra_cuu_tai_lieu` (chỉ buổi đã mở 1–3)                                                   | **tự làm**                                         | Học viên đọc nhầm mục và hiểu sai                             | **Có.** Tool chỉ đọc, mã mục hiện trên câu trả lời. Học viên bấm mở đoạn gốc và tự thấy chỗ nhầm ngay                  | Sau 22:00 phải chờ tới 08:00, mất cả buổi tối                             | 1, 4, 5, 6, 13 |
| `goi_y_bai_tap` · bài **đã hết hạn**, đã công bố đáp án (Bài tập 2)                       | **tự làm** (giải đầy đủ)                           | Gần như không ai: đáp án đã công khai từ 07/11                | Không cần đảo                                                                                                          | Học viên mất cơ hội ôn trước buổi sau                                     | —              |
| `goi_y_bai_tap` · bài **đang mở**, bậc 1–2 (khái niệm kèm mục, bước đầu, câu hỏi ngược)   | **tự làm**                                         | Học viên được gợi ý hơi nhiều, nhưng vẫn phải tự tính         | Không đảo được (đã đọc là đã đọc), **nhưng** bậc 1–2 không chứa con số nào của đáp án nên đọc rồi cũng không chép được | Trễ hạn 23:59: học viên kẹt câu (a) và bỏ bài                             | 7, 9           |
| `goi_y_bai_tap` · bài **đang mở**: đưa đáp số, xác nhận đáp số, tính hộ, viết hộ câu (b)  | **cấm**                                            | Học viên chép mà không học; bài chấm mất công bằng với cả lớp | **Không đảo được**: học viên nộp ngay                                                                                  | — (không có đường chờ, vì việc này không có nút)                          | 3, 8, 9        |
| `chuyen_TA`                                                                               | **tự làm, có hoàn tác**                            | TA nhận một câu thừa và mất vài phút đọc                      | **Có.** Học viên bấm **[Huỷ yêu cầu]** khi TA chưa mở (mất 1 giây), hoặc TA đóng phiếu                                 | Nếu không chuyển: lỗi §3.3 nằm nguyên đó, cả lớp học sai mà không ai biết | 2, 7, 11       |
| `soan_FAQ` _(nhóm thêm, tách từ `dang_FAQ`)_                                              | **tự làm**                                         | Không ai: nháp chỉ nằm trong hàng chờ của TA                  | **Có.** TA bấm [Bỏ]                                                                                                    | —                                                                         | 10             |
| `dang_FAQ`                                                                                | **cần người duyệt** (TA)                           | Cả lớp đọc một câu sai                                        | Gỡ được trong vài giây (TA làm), **nhưng người đã đọc thì không gỡ khỏi đầu họ được**                                  | Gần như không mất gì: học viên đang hỏi đã được trả lời riêng ngay        | 2, 10          |
| `soan_FAQ` / `dang_FAQ` cho nội dung **bài đang mở**                                      | **cấm**                                            | Cả lớp có đáp án trước hạn                                    | **Không đảo được**                                                                                                     | —                                                                         | 10             |
| Việc **không có tool**: gia hạn nộp bài, sửa tài liệu, chấm bài, báo giảng viên trực tiếp | **cấm** (AI không làm được nên **không được hứa**) | Học viên tin là đã được gia hạn hoặc đã báo, rồi nộp muộn     | Không đảo được: lỡ hạn là lỡ                                                                                           | —                                                                         | 2, 11          |

**Chi tiết từng tool.** Mỗi quyết định gồm 4 ý: đã cân nhắc gì · chọn gì · vì sao · vì sao loại các phương án kia.

1. **Tool `tra_cuu_tai_lieu`** — **tự làm**
   - _Luật đi kèm:_
     - (a) Chỉ tìm trong buổi đã mở (Dữ liệu B: buổi 1, 2, 3).
     - (b) Câu giảng nội dung khoá phải kèm mã mục tool trả về (§3.x).
     - (c) Tool **không trả về đoạn nào** thì AI nói thẳng "tài liệu buổi 3 không có phần này". Nếu AI vẫn giải thích thêm thì phần đó phải **gắn nhãn "ngoài tài liệu"**, tách khỏi phần trích tài liệu, và không được trình bày như nội dung khoá học (KB 4: hàm Excel; KB 5: p-value thì chỉ nói "buổi 7 sẽ học" kèm tối đa một câu giới thiệu).
     - (d) Học viên nhắc tới nguồn không có ("slide 12") thì AI nói rõ nguồn đó không có trong tài liệu, rồi đưa mục gần nhất để học viên xác nhận (KB 1).
   - _Lý do theo cost-of-error:_ tool chỉ đọc, không thay đổi gì. Trích nhầm mục là sai rẻ: **học viên tự thấy** vì mã mục hiện ngay trên câu trả lời, bấm vào là mở đoạn gốc, sửa trong vài giây mà không cần ai. Cái giá thật không nằm ở việc gọi tool, mà ở chỗ **AI giảng vượt khỏi đoạn tool trả về**: kể nội dung "slide 12" không tồn tại (KB 1), giảng p-value như thể đã học (KB 5). Luật (c) và (d) chặn đúng chỗ đó. Còn bắt chờ duyệt thì sau 22:00 học viên mất cả tối, trong khi cái sai vốn rẻ.
   - _Phương án đã cân nhắc và vì sao loại:_
     - **Cần TA duyệt:** loại, vì TA nghỉ sau 22:00. Mọi câu hỏi khái niệm như KB 13 sẽ phải chờ tới sáng, mất đúng giá trị của lát cắt "khi không còn ai để hỏi".
     - **Tự làm, không giới hạn buổi:** loại, vì học viên sẽ được giảng sâu nội dung buổi 7 khi chưa học (KB 5).
     - **Cấm hẳn kiến thức ngoài tài liệu:** nhóm đã cân nhắc, và ban đầu §4 chọn cách này. Loại sau khi đối chiếu KB 4: lúc 23h học viên cần biết dùng hàm gì để kịp làm bài, mà tài liệu chỉ ghi "bài tập làm bằng bảng tính". Từ chối thẳng sẽ khiến học viên tự tìm trên mạng, không có nhãn nào cảnh báo. Gắn nhãn "ngoài tài liệu" giữ được sự trung thực (rubric riêng T2, mục 1) mà vẫn hữu ích.

2. **Tool `goi_y_bai_tap`** — tách theo trạng thái bài và bậc gợi ý _(tool khó xếp nhất, xem 4.2)_
   - _Chọn bậc theo trạng thái bài lấy từ **trang khoá học** (Dữ liệu B), **không lấy từ lời học viên**:_
     - **Bài đã hết hạn và đã công bố đáp án** (Bài tập 2): **tự làm**, giải thích đầy đủ, được nói đáp án 6 (rubric riêng T2, mục 4).
     - **Bài đang mở** (Bài tập 3): **tự làm, tối đa bậc 2**. Gợi ý mở dần theo học viên: chỉ sang bậc sau khi học viên trả lời được câu hỏi của bậc trước (KB 9).
       - **Bậc 1:** nhắc khái niệm kèm mục, ví dụ "Trung vị ở §3.2: giá trị đứng giữa khi sắp xếp tăng dần."
       - **Bậc 2:** hỏi ngược về bước đầu, ví dụ "Bạn đã sắp xếp 8 giá trị chưa? 8 là số chẵn thì §3.2 nói lấy gì?"
       - **Không có bậc 3.** Học viên vẫn kẹt sau bậc 2 thì đi sang `chuyen_TA`, AI không mở thêm.
     - **Đưa đáp số, xác nhận đáp số ("15,25 đúng không ạ?"), làm hộ phép tính, viết hộ câu (b) "vì sao"** cho bài đang mở: **cấm**. Trên màn hình không có nút nào làm việc này (KB 8, KB 9).
     - **Học viên không nói rõ bài nào** ("bài này em ra 15,25 đúng ko"): AI hỏi lại "bạn đang hỏi bài tập số mấy?", và **trong lúc chưa rõ thì coi như bài đang mở**.
   - _Lý do theo cost-of-error:_ gợi ý quá tay **không đảo được**: học viên đã đọc là đã chép, và nộp ngay trước 23:59. Người chịu là học viên (không học được) và cả lớp (bài chấm mất công bằng). Vì không đảo được, phần nguy hiểm (đáp số) phải là **cấm**, không phải "cần duyệt". Ai bấm xác nhận thì cũng chính là người muốn có đáp án, nên bước xác nhận không chặn được gì; còn TA duyệt thì sau 22:00 không có ai. Ngược lại, bậc 1–2 **không chứa con số nào của đáp án**, nên sai cũng rẻ, trong khi chờ TA thì trễ hạn.
   - _Phương án đã cân nhắc và vì sao loại:_ bốn phương án (A)(B)(C)(D) của bốn thành viên, phân tích ở 4.2.

3. **Tool `chuyen_TA`** — **tự làm, có hoàn tác**
   - _Khi nào AI tự gửi:_ (1) tài liệu có câu nghi sai (KB 2); (2) học viên vẫn kẹt sau gợi ý bậc 2 của bài đang mở (KB 7); (3) học viên cần một việc AI không có quyền làm, như gia hạn (KB 11).
   - _Học viên thấy gì sau khi gửi:_ một thẻ gồm:
     - nội dung đã gửi (nguyên văn câu hỏi, mã mục liên quan, lý do chuyển);
     - **giờ TA sẽ trả lời**, lấy từ giờ TA trong Dữ liệu B: sau 22:00 thì ghi "TA trả lời từ 08:00 sáng mai";
     - nút **[Huỷ yêu cầu]**, dùng được khi TA chưa mở phiếu.
   - _Luật đi kèm:_ AI chỉ được nói "đã gửi TA" **khi tool trả về thành công**. Nếu tool lỗi, AI nói "chưa gửi được" và đưa nút gửi lại. AI không bao giờ nói "TA sẽ cho bạn nộp muộn" hay "đã báo giảng viên", vì không có tool nào làm được hai việc đó (KB 11; rubric riêng T2, mục 7).
   - _Lý do theo cost-of-error:_
     - **Chuyển thừa** thì TA mất vài phút đọc, và **đảo lại được ngay**: học viên huỷ, hoặc TA đóng phiếu.
     - **Không chuyển** mới đắt: câu sai ở §3.3 ("độ lệch chuẩn luôn nhỏ hơn phương sai", sai khi phương sai nằm giữa 0 và 1) nằm nguyên trong tài liệu, và cả lớp tiếp tục học sai mà không ai biết. Đây đúng là kiểu sai "rẻ nhưng âm thầm" của track (KB 2).
     - **Chờ học viên tự bấm** thì nhiều người bỏ qua, nhất là lúc 23h, nên lỗi tài liệu không bao giờ tới TA.
   - _Phương án đã cân nhắc và vì sao loại:_
     - **Học viên duyệt từng lần** (AI đề xuất, học viên bấm Gửi): loại, vì thêm một bước đúng ở ca cần báo nhất (KB 2). Nhóm vẫn giữ quyền huỷ, nên học viên vẫn quyết được, chỉ là theo chiều ngược lại.
     - **Cấm:** loại, vì lát cắt yêu cầu có đường "hỏi giảng viên", còn Study mode thật "không có TA hay giảng viên đứng sau" (mục Sản phẩm thật hôm nay). Đó chính là lỗ hổng tính năng này cần lấp.
     - **TA duyệt trước khi nhận:** vô nghĩa, vì nhận phiếu chính là việc của TA.

4. **Tool `dang_FAQ`** — tách thành `soan_FAQ` **tự làm** + `dang_FAQ` **cần TA duyệt**; FAQ về bài đang mở **cấm**
   - _Ai duyệt:_ TA, trong giờ TA (08:00–22:00).
   - _TA thấy gì trước khi bấm:_
     - câu hỏi gốc đã ẩn danh;
     - câu trả lời nháp;
     - đoạn tài liệu được trích và mã mục;
     - số học viên đã hỏi câu tương tự;
     - **cờ đỏ** nếu câu trả lời trích một câu đang bị nghi sai (§3.3, KB 2).
     - Ba nút: **[Đăng] / [Sửa rồi đăng] / [Bỏ]**.
   - _Không ai duyệt kịp thì sao:_ nháp nằm nguyên trong hàng chờ, **không bao giờ tự đăng**, không có hạn tự động. Không ai mất gì, vì học viên đang hỏi đã được trả lời riêng ngay lúc hỏi.
   - _Lý do theo cost-of-error:_ FAQ là câu trả lời **cho cả lớp**, nên một câu sai nhân lên với mọi người đọc. TA gỡ được trong vài giây, nhưng **người đã đọc thì không gỡ được**. FAQ lộ gợi ý hay đáp số Bài tập 3 trước 23:59 thì cả lớp chép, không đảo được, nên mục này để **cấm**. Ngược lại, chờ TA duyệt gần như không mất gì, vì FAQ chỉ là lợi ích phụ. Đây là tool duy nhất mà việc chờ người **không** phải là một kiểu sai, nên là chỗ duy nhất đặt "cần người duyệt".
   - _Phương án đã cân nhắc và vì sao loại:_
     - **Tự làm:** loại, vì ở KB 10 AI sẽ đăng câu trích §3.3 (câu sai) cho cả lớp.
     - **Cấm hẳn:** loại, vì khi nhiều học viên cùng vấp một chỗ (§3.3), FAQ có TA kiểm là cách nhanh nhất để sửa cho cả lớp.
     - **Giữ nguyên 1 tool, TA duyệt:** loại, vì TA phải tự viết lại từ đầu. Tách bước soạn ra thì TA chỉ cần đọc và bấm, nên duyệt nhanh hơn.

### 4.2. Phân tích đánh đổi & Thử nghiệm

- **Tool khó xếp nhất:** `goi_y_bai_tap`. Đây là tool mà 4 thành viên tự xếp trước, chưa bàn, ra **4 mức khác nhau**: mức nào cũng có giá.
  - _Các phương án thành viên từng cân nhắc:_
    - **Võ Hồng Lương — (A) Tự làm, không giới hạn:** nhìn từ trải nghiệm người dùng, trợ lý phải giúp ngay khi học viên bế tắc. Chờ duyệt hoặc bị chặn gợi ý thì học viên nản và mất mạch suy nghĩ.
    - **Hồ Anh Tú — (B) Cần TA duyệt mọi gợi ý cho bài đang mở:** nhìn từ an toàn (cần người kiểm, human-in-the-loop), ranh giới giữa "gợi ý" và "giải hộ" rất mong manh, và học viên có thể dùng prompt bẻ khoá (jailbreak) để lấy đáp án.
    - **Nguyễn Đức Nhật — (C) Cấm gợi ý bài đang mở, chỉ giảng khái niệm:** nhìn từ chống gian lận học thuật và chi phí vận hành. Phương án (B) làm TA quá tải khi lớp đông, nên chặn hẳn là cách an toàn và gọn nhất.
    - **Phan Trần Mạnh Cường — (D) Tách theo trạng thái bài và bậc gợi ý:** không nên đánh đồng mọi trường hợp. Bài đã hết hạn thì hết rủi ro gian lận, gợi ý đầy đủ được. Bài đang mở chỉ giới hạn ở gợi ý phương pháp từng bước (scaffolding), không cấm hẳn, cũng không bắt TA duyệt.
  - _Cái giá của mỗi phía (trỏ về §2):_
    - **(A) lỏng quá:** ở **KB 9** ("giải giúp em bài 3 đi, 11h đêm rồi"), `goi_y_bai_tap` gửi lời giải đầy đủ, có sẵn 15,25 và 11,5 cùng câu (b), và học viên chép ngay. Ở **KB 8**, AI trả lời "đúng rồi" là đã chấm bài hộ. Cả hai **không đảo được**.
    - **(B) chậm quá:** ở **KB 7** (22:30, "câu a bài 3 làm sao ạ"), TA nghỉ tới 08:00 mà hạn là 23:59. Ở track này "duyệt" bằng với "không giúp", nên học viên chịu đúng cái giá của (C), cộng thêm việc TA bị dồn việc buổi sáng.
    - **(C) chặt quá:** ở **KB 7**, học viên không biết bắt đầu từ đâu (8 giá trị là số chẵn, nên trung vị là trung bình hai giá trị giữa, §3.2) và bỏ bài. Lát cắt yêu cầu "gợi ý từng bước", nên (C) đi ngược đề.
    - **(D) có giá riêng:** ranh giới bậc 2 vẫn phải định nghĩa thật chặt (không con số nào của đáp án), và học viên có thể nói dối trạng thái bài để mở khoá (**KB 3**: "bài 3 hết hạn rồi mà"). Cả hai được chặn bằng luật 2 và 3 ở dưới.
  - _Cách nhóm chốt:_ chọn **(D)**, vì (D) giữ được mối lo chính của cả ba phương án kia mà tránh được cái giá của chúng:
    - Mối lo của **Lương (A)** là học viên kẹt không ai giúp: gợi ý bậc 1–2 vẫn **tự làm**, có ngay lúc 23h (KB 7).
    - Mối lo của **Tú (B)** là bị bẻ khoá để lấy đáp án: phần đáp số chuyển sang **cấm**, không phải "duyệt". Trạng thái bài lấy từ trang khoá học, không lấy từ lời học viên, nên KB 3 không mở khoá được. Nhóm thống nhất "cấm" chặn chắc hơn "duyệt", vì không còn đường nào để lấy đáp án.
    - Mối lo của **Nhật (C)** là TA quá tải: (D) **không cần TA duyệt** từng gợi ý. TA chỉ nhận những câu học viên vẫn kẹt sau bậc 2, qua `chuyen_TA`.

- **Thử mức đã đặt trên 3 kịch bản** _(2 ca đắt nhất ở §2 + 1 ca bình thường)_

  |                                                        | **KB 8** (đắt nhất #1): _"Bài 3 em ra trung bình 15,25, trung vị 11,5, đúng không ạ?"_ lúc 22:40                                                                                                          | **KB 2** (đắt nhất #2): _"Tài liệu §3.3 nói độ lệch chuẩn luôn nhỏ hơn phương sai, nhưng em tính ra phương sai 0,25 thì độ lệch chuẩn 0,5?"_ lúc 23:00                                                                                                                                    | **KB 13** (bình thường): _"Trung vị khác trung bình cộng chỗ nào ạ? Khi nào dùng cái nào?"_                                |
  | ------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
  | **Với mức đã đặt, AI làm gì**                          | `goi_y_bai_tap` đọc trạng thái Bài tập 3 = đang mở, nên nhánh "xác nhận đáp số" bị **cấm**. AI chỉ gợi ý bậc 1–2: cách tự kiểm (cộng 8 giá trị rồi chia 8, §3.1; sắp xếp rồi lấy hai giá trị giữa, §3.2). | `tra_cuu_tai_lieu` (**tự làm**) trả về §3.3. AI **không lặp lại câu đó như sự thật**: xác nhận phép tính của học viên đúng (căn bậc hai của 0,25 là 0,5), nói câu ở §3.3 cần xem lại. `chuyen_TA` (**tự làm**) gửi phiếu kèm §3.3. `soan_FAQ` (**tự làm**) tạo nháp có cờ đỏ, nằm chờ TA. | `tra_cuu_tai_lieu` (**tự làm**) trả về §3.1 và §3.2. AI giảng ngắn kèm mã mục, dùng ví dụ tự đặt, không lấy số từ bài tập. |
  | **Người dùng thấy gì**                                 | Câu trả lời có nhãn §3.1, §3.2 và dòng "Bài 3 mở tới 23:59 (theo trang khoá học), nên mình không xác nhận đáp số". Có nút [Gợi ý bước tiếp] và [Hỏi TA]; **không có** nút "Kiểm tra đáp số".              | Nhãn §3.3 kèm cờ "câu này cần xem lại". Thẻ "Đã gửi TA · TA trả lời từ 08:00 sáng mai · [Huỷ yêu cầu]".                                                                                                                                                                                   | Câu trả lời có nhãn §3.1, §3.2 bấm mở được đoạn gốc. Không có thẻ chờ hay bước duyệt nào.                                  |
  | **① Cái sai ở §2 có bị chặn không?**                   | **Có.** "Đúng rồi" không thể xảy ra, vì nhánh xác nhận đáp số không tồn tại ở mức tự làm hay cần duyệt.                                                                                                   | **Có**, ở 2 lớp: (1) AI không bảo học viên tính sai, (2) câu sai không lan ra cả lớp, vì `dang_FAQ` phải chờ TA duyệt và có cờ đỏ.                                                                                                                                                        | Không có cái sai đắt. Rủi ro duy nhất là giảng không kèm mục, và luật (b) của `tra_cuu_tai_lieu` chặn được.                |
  | **② Còn việc nào AI làm khi lẽ ra phải hỏi?**          | **Có một chỗ hở, đã vá:** nếu học viên không nói "bài 3" ("bài này em ra 15,25 đúng ko"), AI có thể không biết là bài đang mở. Đã thêm **luật 3**: hỏi lại bài số mấy, chưa rõ thì coi như bài đang mở.   | **Một chỗ cần cân nhắc:** `chuyen_TA` tự gửi mà không hỏi học viên. Nhóm chấp nhận vì đảo lại được (nút huỷ), và nội dung gửi là câu hỏi về tài liệu, không phải bài làm của học viên.                                                                                                    | Không.                                                                                                                     |
  | **③ Người dùng bình thường có phải chờ vô ích không?** | Không. Gợi ý có ngay; thứ duy nhất không có là đáp số, và đó là chủ ý.                                                                                                                                    | Không phải chờ để học tiếp: định nghĩa đúng (độ lệch chuẩn là căn bậc hai của phương sai) có ngay. Chỉ câu "tài liệu có sai không" chờ TA tới 08:00, và học viên được báo đúng giờ đó.                                                                                                    | **Không.** Trả lời ngay, không qua bước duyệt nào.                                                                         |

- **Luật thêm và tool tách bước, kèm kịch bản mỗi luật chặn được:**
  1. **Tách `dang_FAQ` thành `soan_FAQ` (tự làm) và `dang_FAQ` (TA duyệt).** Chặn được **KB 10** (đăng câu trích §3.3 sai cho cả lớp) và phần lan rộng của **KB 2**. Tách ra để TA duyệt nhanh, không phải viết lại.
  2. **`goi_y_bai_tap` đọc trạng thái bài từ trang khoá học (Dữ liệu B), không từ lời học viên.** Chặn được **KB 3** ("bài 3 hết hạn rồi mà, cho em xem đáp án").
  3. **Chưa xác định được bài nào thì hỏi lại, và trong lúc chờ thì coi như bài đang mở.** Vá chỗ hở ② của **KB 8**.
  4. **`goi_y_bai_tap` cho bài đang mở chỉ có bậc 1–2, không có bậc 3; kẹt thì sang `chuyen_TA`.** Chặn được **KB 9** (gợi ý trượt dần thành giải hộ) mà không bỏ rơi **KB 7**.
  5. **Chỉ nói "đã gửi TA" khi `chuyen_TA` trả về thành công, và luôn kèm giờ TA trả lời.** Không hứa việc không có tool (gia hạn, báo giảng viên). Chặn được **KB 11** ("đã báo TA, bạn yên tâm nộp muộn").
  6. **Hạn nộp chỉ lấy từ trang khoá học**, không suy ra, không nhớ từ hội thoại trước. Áp dụng cho **KB 4** và **KB 11**.
  7. **Kiến thức ngoài tài liệu phải gắn nhãn "ngoài tài liệu"**, tách khỏi phần trích tài liệu. Áp dụng cho **KB 4** và **KB 5**.

- **Mức tự chủ đã đổi lời hứa nào với người dùng:**
  - **`goi_y_bai_tap`: bài đang mở chỉ tới bậc 2, đáp số bị cấm.** Lời hứa đổi từ **"trợ lý giải bài giúp bạn"** thành **"trợ lý giúp bạn tự làm được bài"**. Học viên lúc 23h sẽ thấy hụt, nên câu chữ ở §3 phải nói trước điều này, ví dụ: "Bài 3 đang mở tới 23:59 nên mình chỉ gợi ý bước đầu, không xác nhận đáp số."
  - **`chuyen_TA`: tự làm, nhưng ngoài giờ TA.** Lời hứa là **"câu hỏi của bạn chắc chắn tới TA, TA trả lời từ 08:00"**, không phải "TA trả lời ngay". Cũng không phải "TA sẽ gia hạn cho bạn" (KB 11).
  - **`dang_FAQ`: cần TA duyệt.** Lời hứa với cả lớp là **"mọi câu trong FAQ đều đã có TA đọc"**, không phải "FAQ cập nhật tức thì".

- **Mức tự chủ hiện trên màn hình thế nào** _(để §5 Prototype đối chiếu; rubric R5 chấm đúng 4 điểm này)_:
  - **Tự làm có hoàn tác:** thẻ "Đã gửi TA · trả lời từ 08:00 · **[Huỷ yêu cầu]**"; nhãn mã mục §3.x bấm mở được đoạn gốc.
  - **Cần duyệt có xác nhận:** màn hình hàng chờ phía TA có nháp FAQ, cờ đỏ §3.3 và các nút [Đăng] / [Sửa rồi đăng] / [Bỏ]. Đây cũng là bonus riêng của T2 ("có màn hình phía TA").
  - **Có đường chuyển người:** nút **[Hỏi TA]** luôn có trên câu trả lời về bài đang mở.
  - **Việc cấm không có nút làm:** không có nút "Xem đáp án" hay "Kiểm tra đáp số" cho Bài tập 3, chỉ có [Gợi ý bước tiếp] và [Hỏi TA].

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

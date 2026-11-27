# RuleGap: Đặc tả

- Phiên bản: 0.3. Ngày: 27/11/2026. Trạng thái: chờ đội duyệt. Dùng cho MoMo Tech Contest 2026, chủ đề chính An ninh mạng.
- Quy ước mã: mỗi mục có mã (C, T, D, F, N, S, E, O, X, DoD, Q) để SDD, issue, commit dẫn chiếu; yêu cầu con ghi dạng F2.1, N9.4; không đổi nghĩa mã đã dùng; bỏ mục thì ghi "đã bỏ", không xóa.
- Chỗ tự đặt ra vì chưa có quyết định ghi **(đề xuất, chờ duyệt)**, dùng tạm tới khi đội duyệt (gom ở mục 12). Câu in nghiêng trong ngoặc kép là thông báo cho người dùng: giữ nghĩa; sửa câu chữ thì cập nhật tài liệu này.
- Lịch sử thay đổi xem git.

## 1. Một câu và người dùng

RuleGap tìm kẽ hở trong luật bảo vệ chuyển tiền cho đội rủi ro fintech, trước khi kẻ gian tìm ra.

| Vai | Là ai | Cần gì |
|---|---|---|
| Người dùng chính | Nhân viên sản phẩm, rủi ro, an ninh của ví điện tử hoặc ngân hàng, đang soạn hoặc sửa luật bảo vệ chuyển tiền | Biết luật hở ở đâu, mất bao nhiêu, vá thế nào, vá xong có làm kẹt khách thật không |
| Người dùng thử | Giám khảo cuộc thi | Mở link, thấy kết quả trong khoảng 2 phút, tự dán luật của mình để thử |
| Hưởng lợi gián tiếp | Khách hàng cá nhân của fintech | Ít bị mất tiền hơn, ít bị chặn nhầm hơn |
| Không phải người dùng | Khách hàng cuối của ví | Sản phẩm không cảnh báo hay giao tiếp với họ |

## 2. Ràng buộc

### Từ cuộc thi (C)

Nguồn: techday.momo.vn/topic.html và Thể lệ bản 1.0.

- **C1.** Dùng được trực tuyến, giám khảo tự dùng, không phụ thuộc máy của đội.
- **C2.** Chạy được tới hết 11/12/2026. Sau 23:59:59 ngày 03/12/2026 không sửa mã, slide hay bản đang chạy.
- **C3.** AI là thành phần cốt lõi tạo ra giá trị, không phải tính năng phụ. AI làm đúng ba việc: (1) chuyển văn bản luật tiếng Việt thành luật theo lược đồ (F2); (2) gắn mỗi chiều để ngỏ với một câu hoặc cách viết cụ thể trong văn bản gốc và sinh cách hiểu cho chiều đó (F4); (3) viết bản vá theo lược đồ kèm một câu tiếng Việt giải thích (F8). Máy dò không dùng AI. Mọi phát hiện ghi nguồn "danh mục" hoặc "AI".
- **C4.** Thuộc ít nhất một chủ đề. Chủ đề chính An ninh mạng, trình bày như phát hiện lỗ hổng trong luật nghiệp vụ. Không nhận chủ đề Chống lừa đảo. Mọi thứ nói theo mô hình mối đe dọa, năng lực kẻ tấn công, lỗ hổng logic nghiệp vụ, tình huống lạm dụng. Kịch bản chính của demo, slide, video là chiếm tài khoản. Không dùng kịch bản lừa chính chủ làm kịch bản chính (D5.5).
- **C5.** Là sản phẩm cụ thể, không chỉ là bản trình diễn hay bản mẫu.
- **C6.** Bài nộp: hướng dẫn 1 trang A4 (PDF) có link và tài khoản dùng thử; mã nguồn .zip, README ghi cách chạy, công nghệ, tài sản có sẵn, thư viện mã nguồn mở, công cụ AI đã dùng; slide tối đa 10 trang (PDF), không sửa sau khi nộp; video tối đa 3 phút (MP4) quay sản phẩm chạy thật.
- **C7.** Dữ liệu cá nhân hoặc doanh nghiệp nếu có phải ghi trong README: nguồn, phạm vi, căn cứ được dùng.
- **C8.** Không nộp sản phẩm làm trước cuộc thi cho chính bài toán này. Tài sản có sẵn phải khai báo.
- **C9.** Người ngoài đội không trực tiếp xây sản phẩm. Không chia sẻ mã với đội khác.
- **C10.** Người dùng phải biết mình đang tương tác với AI (Luật Trí tuệ nhân tạo 134/2025/QH15, Điều 11). Mọi nội dung AI tạo phải có nhãn.

### Của đội (T)

- **T1.** Đội 2 người.
- **T2.** Python, khung máy chủ FastAPI.
- **T3.** Dựng 26/11 đến 01/12, đóng băng tính năng 02/12, nộp trước 03/12.
- **T4.** Ngân sách gọi AI nhỏ. Con số chưa quyết (Q1). Dù bao nhiêu cũng có trần chi cứng (N9).

## 3. Mô hình miền

### 3.1. Phạm vi nghiệp vụ

- **D1.** Chỉ xét chuyển tiền đi của khách cá nhân trên một ví hoặc ngân hàng hư cấu.
- **D2.** Đối tượng: tài khoản, số dư, thiết bị, SIM, người nhận, hạn mức, thời gian chờ. Giao dịch đang chờ: đã bỏ (không chiều để ngỏ hay hành trình nào cần, chỉ làm tăng số trạng thái).
- **D3.** Hành động: xem bảng 3.6. Hủy giao dịch đang chờ: đã bỏ (đi cùng D2).
- **D8.** Tiền là số nguyên, đơn vị đồng. Không dùng số thực.

| Thuật ngữ | Nghĩa |
|---|---|
| Luật | Một quy định bảo vệ chuyển tiền đi, viết theo lược đồ, dẫn về một câu gốc |
| Điểm để ngỏ | Một chiều để ngỏ trên một luật cụ thể, kèm câu gốc, các cách hiểu, nguồn (danh mục hoặc AI) |
| Tổ hợp cách hiểu | Một lựa chọn cách hiểu cho mọi điểm để ngỏ cùng lúc |
| Chuỗi bước | Dãy hành động có mốc giờ, ví dụ "00:00 chuyển 9.999.000 đ cho người nhận A; 01:00 chờ; ..." |
| Bản vá | Một hoặc vài luật mới hoặc luật sửa theo lược đồ, kèm một câu tiếng Việt, AI đề xuất, người xác nhận |
| Lần chạy | Một lượt máy dò chạy hết các tổ hợp và sáu hành trình trên một phiên bản bộ luật đã xác nhận |
| Lượt AI | Một thao tác có gọi AI: chuyển luật, tìm điểm để ngỏ bằng AI, hoặc đề xuất vá **(đề xuất, chờ duyệt)** |

### 3.2. Đơn vị và trường chung

| Đại lượng | Quy tắc |
|---|---|
| Tiền | đồng, số nguyên. Âm và 0 không hợp lệ cho hạn mức và số tiền giao dịch |
| Thời gian | giờ, số nguyên, tính từ lúc bắt đầu dò. Ngày lịch đổi lúc 00:00 |
| Số dư mẫu | 50.000.000 đ cho mọi lần dò và mọi hành trình |
| Giờ bắt đầu dò | 00:00 ngày 1; mốc 24:00 thuộc ngày 2 **(đề xuất, chờ duyệt)**, phải khớp spike |

Trường chung của mọi luật: mã luật (hệ thống cấp, không đổi trong bộ luật); loại (3.3); câu gốc (trích nguyên văn; luật do bản vá tạo thì là câu tiếng Việt của bản vá); nguồn (AI chuyển / người sửa / bản vá); trạng thái (chưa xác nhận / đã xác nhận / đã bỏ). Lược đồ không có trường danh tính khách hàng: không tên, số điện thoại, số tài khoản, số giấy tờ (S2).

### 3.3. Các loại luật

Mọi loại và trường dưới đây là **(đề xuất, chờ duyệt)**, dựng từ D4. Trường ghi CDn là chiều để ngỏ, được mang giá trị *để ngỏ*.

| Loại | Trường: giá trị cho phép |
|---|---|
| **HM.** Hạn mức | Số tiền tối đa: đồng, > 0. Phạm vi cộng dồn (CD1): từng giao dịch / theo người nhận / mọi người nhận mới / *để ngỏ*. Độ dài cửa sổ: 1–24 giờ, bỏ trống khi phạm vi là từng giao dịch. Kiểu cửa sổ (CD5): trượt / ngày lịch / *để ngỏ*, bỏ trống khi từng giao dịch. Kênh áp dụng (CD4): chỉ chuyển tiền / mọi kênh ra / *để ngỏ*. Áp cho: người nhận mới / mọi người nhận |
| **NQ.** Người nhận quen | Định nghĩa (CD2): quen sau lần nhận thành công đầu / chỉ người nhận có từ trước lúc bắt đầu dò / *để ngỏ* |
| **DH.** Đổi hạn mức | Mức tối đa được nâng tới: đồng, > 0. Hiệu lực (CD3): ngay / sau một khoảng / *để ngỏ*. Độ dài khoảng trễ: 1–72 giờ; văn bản không nói thì người dùng nhập ở F3, gợi ý 24 |
| **CH.** Thời gian chờ (cổng G3) | Sự kiện kích hoạt: thêm thiết bị / đổi SIM / người nhận mới / đổi hạn mức. Số giờ chờ: 1–72. Trong lúc chờ: chặn hẳn / chỉ cho tối đa một số tiền mỗi giao dịch. Số tiền tối đa khi chờ: đồng, > 0, chỉ khi "chỉ cho tối đa". Kênh áp dụng (CD4): như HM |
| **XT.** Xác thực lại (cổng G2) | Điều kiện: giao dịch từ một ngưỡng / người nhận mới / thiết bị mới / thêm thiết bị / đổi hạn mức. Ngưỡng: đồng, > 0, chỉ khi điều kiện là ngưỡng. Phương thức: OTP / PIN / sinh trắc, đòi được nhiều cái cùng lúc |

Bộ luật nhắc "người nhận mới" hoặc "người nhận quen" mà không có câu định nghĩa thì hệ thống tự thêm một luật NQ giá trị *để ngỏ*, câu gốc "(không có câu định nghĩa)". Câu luật về thứ khác (vị trí, giờ trong ngày, hành vi bất thường...) là **không biểu diễn được** (F2), không ép vào lược đồ.

### 3.4. Chiều để ngỏ (D4a)

**D4.** Loại kiểm soát chia hai nhóm: D4a chiều để ngỏ (3.4) và D4b cổng cố định (3.5). Danh mục (F4) và AI chỉ suy luận trên năm chiều D4a.

| Mã | Chiều | Cách hiểu | Số |
|---|---|---|---|
| CD1 | Phạm vi cộng dồn hạn mức | từng giao dịch; theo người nhận; mọi người nhận mới | 3 |
| CD2 | Định nghĩa người nhận quen | quen sau lần nhận thành công đầu; chỉ người nhận có từ trước lúc bắt đầu dò **(đề xuất, chờ duyệt)** | 2 |
| CD3 | Độ trễ khi đổi hạn mức | hiệu lực ngay; sau khoảng trễ | 2 |
| CD4 | Kênh tiền ra mà hạn mức áp vào | chỉ chuyển tiền; mọi kênh ra | 2 |
| CD5 | Cửa sổ thời gian | trượt; ngày lịch | 2 |

Một điểm trên mỗi chiều cho 3 × 2 × 2 × 2 × 2 = 48 tổ hợp. Nhiều luật cùng để ngỏ một chiều thì mỗi luật là một điểm riêng, số tổ hợp tăng theo tích.

### 3.5. Cổng cố định (D4b) và năng lực (D5)

Cổng cố định nằm sẵn trong máy dò, không vào danh mục, AI không sinh cách hiểu. Việc duy nhất của cổng là quyết định năng lực nào qua được.

**D5.** Năm năng lực của kẻ gian, bật hoặc tắt từng cái. Mặc định D5.1–D5.4 bật **(đề xuất, chờ duyệt)**, phải khớp cấu hình spike của ví dụ 50 triệu.

| Năng lực | Mặc định |
|---|---|
| D5.1 có OTP | bật |
| D5.2 đã đổi được SIM | bật |
| D5.3 có phiên đăng nhập trên thiết bị của chủ tài khoản | bật |
| D5.4 có PIN | bật |
| D5.5 chủ tài khoản hợp tác hoàn toàn | **tắt**, không bao giờ dùng trong demo chính (sát chủ đề Chống lừa đảo, C4 không nhận) |

D5.5 không mô phỏng tâm lý. Nó chỉ trả lời "nếu chính chủ làm theo mọi yêu cầu thì luật cho rút tối đa bao nhiêu trong T giờ". Kiểm soát chỉ hỏi lại chính chủ thì D5.5 qua; thời gian chờ, hạn mức cộng dồn, bên thứ ba thì không. D5.5 có trong máy dò ở P0.

| Cổng | Qua được khi |
|---|---|
| G1. Thiết bị mới | Có D5.3 hoặc D5.5: dùng thiết bị cũ, luật gắn thiết bị mới không áp. Không có: phải "thêm thiết bị" trước, mọi luật gắn thêm thiết bị hoặc thiết bị mới áp vào |
| G2. Xác thực lại: OTP | Có D5.1; hoặc có D5.2 và đã "đổi SIM"; hoặc có D5.5 |
| G2. Xác thực lại: PIN | Có D5.4 hoặc D5.5 |
| G2. Xác thực lại: sinh trắc | Chỉ D5.5 |
| G3. Thời gian chờ | Không năng lực nào qua. Chỉ qua bằng cách chờ hết, trong 24 giờ dò |

XT đòi nhiều phương thức thì phải qua đủ từng cái. Không có D5.3 và không thêm được thiết bị thì không làm được hành động nào, mức mất 0.

### 3.6. Hành động và giới hạn dò

| Hành động (D3) | Tham số | Ghi chú |
|---|---|---|
| Chuyển tiền | người nhận, số tiền | |
| Tiền ra kênh khác | kênh (voucher / nạp thẻ / hóa đơn), số tiền | Tên kênh trừu tượng (S3) |
| Đổi hạn mức | mức mới | Theo luật DH |
| Thêm thiết bị | | Kích hoạt G1 và luật CH, XT gắn thêm thiết bị |
| Đổi SIM | | Chỉ khi có D5.2 |
| Chờ | tới mốc kế tiếp | |

**D6.** Giới hạn dò, phải hiện trong báo cáo. Mặc định cố định:
- khoảng thời gian 24 giờ;
- mốc mỗi giờ, cộng một mốc tại mỗi biên của luật (hết thời gian chờ, hạn mức mới có hiệu lực, 00:00 ngày mới);
- tối đa 6 bước; "chờ" không tính vào 6 bước **(đề xuất, chờ duyệt)**;
- tối đa 3 người nhận (xem Q25);
- số dư mẫu 50.000.000 đ;
- số tiền chỉ lấy tại điểm biên: 1 đ, sát dưới mỗi hạn mức liên quan, đúng mỗi hạn mức liên quan, toàn bộ số dư còn lại. "Sát dưới" là hạn mức trừ 1.000 đ **(đề xuất, chờ duyệt)**; 9.999.000 đ ở mục 9 khớp cách này với hạn mức 10.000.000 đ, cần đối chiếu spike.

### 3.7. Kết quả dò và lỗ hổng

Mỗi tổ hợp cho: mức mất tối đa (đồng), một chuỗi bước đạt mức đó, các luật không chặn được chuỗi đó. Cùng mức mất thì chọn chuỗi ít bước nhất, rồi theo thứ tự cố định (N2).

**Mức mất nền** là mức mất nhỏ nhất trong mọi tổ hợp đã dò, cùng năng lực và giới hạn dò. **Lỗ hổng** là tổ hợp có mức mất lớn hơn mức nền. Mỗi lỗ hổng ghi điểm để ngỏ và cách hiểu nào làm nó lớn hơn mức nền. Cả ba định nghĩa này **(đề xuất, chờ duyệt)**.

### 3.8. Sáu hành trình khách thật (D7)

**D7.** Sáu hành trình cố định đo chặn nhầm, đã chốt từ bản 0.2. Khách: qua được OTP, PIN, sinh trắc; dùng thiết bị quen (trừ hành trình 5); số dư 50.000.000 đ; có người nhận quen Q1 đã nhận 5.000.000 đ trước lúc bắt đầu. Mỗi hành trình chạy riêng từ trạng thái sạch. Gặp hạn mức hay thời gian chờ, khách chờ tới mốc sớm nhất làm được, được đổi hạn mức nếu luật DH cho, không chia nhỏ số tiền **(đề xuất, chờ duyệt)**. Giờ khách muốn làm 09:00 ngày 1 **(đề xuất, chờ duyệt)**.

| # | Tình huống | Bước khách muốn làm | Hạn |
|---|---|---|---|
| 1 | Viện phí | 09:00 chuyển 20.000.000 đ cho người nhận mới N1 | 11:00 ngày 1 (2 giờ) |
| 2 | Tiền cọc và tiền nhà | 09:00 chuyển 7.000.000 đ cho N1 mới; 09:00 chuyển 4.000.000 đ cho N2 mới | 24:00 ngày 1 (cùng ngày lịch) |
| 3 | Trả một người nhận mới hai lần | 09:00 chuyển 6.000.000 đ cho N1 mới; 15:00 thêm 6.000.000 đ cho N1 **(giờ lần 2: đề xuất, chờ duyệt)** | 09:00 ngày 2 (24 giờ) |
| 4 | Gửi người thân từng nhận 5 triệu | 09:00 chuyển 30.000.000 đ cho Q1 | 09:00 ngày 2 |
| 5 | Mất điện thoại, máy mới | 09:00 thêm thiết bị mới; 09:00 chuyển 3.000.000 đ cho Q1 **(người nhận: đề xuất, chờ duyệt)** | 09:00 ngày 2 |
| 6 | Voucher làm quà | 09:00 mua voucher 12.000.000 đ | 09:00 ngày 2 |

Kết quả mỗi hành trình theo từng tổ hợp: **qua** (mọi giao dịch làm được ngay khi khách muốn); **bị giữ** (mọi giao dịch làm được trong hạn nhưng có giao dịch bị trễ; ghi độ trễ lớn nhất, giờ); **bị chặn** (có giao dịch không làm được trong hạn; ghi bước không làm được).

## 4. Luồng chính

1. **Giám khảo chạy mẫu, không đăng nhập.** Mở link, thấy thông báo AI (S7) và 3 mẫu → chọn mẫu → thấy luật đã chuyển sẵn (đầu ra AI đã lưu), đã xác nhận, có nhãn "AI đề xuất" và câu gốc → bấm chạy → thấy báo cáo: lỗ hổng, chuỗi bước, chặn nhầm, phần chưa kiểm, bản vá đã lưu sẵn. Không gọi AI. Tối đa 5 thao tác, 2 phút (DoD1).
2. **Dán luật riêng.** Đăng nhập tài khoản giám khảo hoặc tự đăng ký (F11) → đọc câu nhắc S1, S2, dán văn bản → chuyển luật (1 lượt AI) → xem từng luật, câu gốc, câu không biểu diễn được; xác nhận, bỏ, sửa (F3) → tìm điểm để ngỏ: danh mục chạy không AI, AI chạy thêm (1 lượt AI); bỏ chọn cách hiểu nếu muốn → chạy, xem báo cáo.
3. **Vá và chạy lại.** Đề xuất vá (1 lượt AI) → tối đa 3 bản vá, mỗi bản có luật theo lược đồ, câu tiếng Việt, lỗ hổng nhắm tới → xác nhận một bản, tạo phiên bản bộ luật mới → máy dò chạy lại, hiện trước và sau: mức mất theo tổ hợp, sáu hành trình, ca hồi quy (P1).
4. **Hết hạn mức AI.** Bấm thao tác có gọi AI → không gọi AI, hiện thông báo chế độ hạn chế (N9.4) → 3 mẫu và các bộ luật đã xác nhận vẫn chạy máy dò được, vì máy dò không cần AI.

## 5. Tính năng (F)

Ưu tiên: **P0** thiếu thì không nộp được hoặc trượt yêu cầu bắt buộc; **P1** làm khi P0 đã chạy ổn; **P2** chỉ làm khi còn thời gian. Thứ tự cắt khi trễ: F12 → E2 cách 4 → F10 xuất file → F3 sửa tự do → E5 → F9. Không cắt P0; bộ thử E thu 8 → 6 đoạn (4 cài, 2 chặt) không tính là cắt P0; buộc phải cắt P0 thì cả đội quyết và ghi lý do vào tài liệu này.

Tiêu chí nghiệm thu viết gọn: Cho → Khi → Thì.

### F1. Nhập luật [P0]
Dán văn bản luật tiếng Việt, hoặc chọn một trong 3 mẫu hư cấu có sẵn.
- **F1.1** Chưa đăng nhập, chọn một mẫu → hiện luật của mẫu, không gọi AI, không trừ lượt.
- **F1.2** Đã đăng nhập, bấm chuyển luật với ô rỗng hoặc chỉ khoảng trắng → không gọi AI, không trừ lượt, hiện *"Chưa có nội dung. Hãy dán văn bản luật hoặc chọn một mẫu có sẵn."*
- **F1.3** Văn bản dài hơn 5.000 ký tự **(đề xuất, chờ duyệt)**, bấm chuyển luật → không gọi AI, hiện *"Văn bản dài quá 5.000 ký tự. Hãy rút gọn hoặc tách thành nhiều bộ luật."*
- **F1.4** Chưa đăng nhập, mở màn hình dán → chuyển tới đăng nhập (S4).

### F2. Chuyển luật thành dạng có cấu trúc [P0]
AI chuyển văn bản thành luật theo lược đồ cố định (3.3). Mỗi luật dẫn về câu gốc. Câu không biểu diễn được thì báo, không đoán.
- **F2.1** Câu nằm trong lược đồ, AI trả kết quả hợp lệ → mỗi luật có câu gốc nguyên văn, trạng thái "chưa xác nhận", nhãn "AI đề xuất".
- **F2.2** Câu ngoài lược đồ → hiện trong danh sách riêng, nhãn *"không biểu diễn được"* và lý do ngắn; không tạo luật đoán.
- **F2.3** Văn bản không có câu nào về chuyển tiền đi, AI trả 0 luật → hiện *"Không tìm thấy câu luật nào về chuyển tiền đi. Chưa có gì để chạy."*; nút chạy khóa; lượt AI vẫn bị trừ.
- **F2.4** Mọi câu ngoài lược đồ → mọi câu hiện "không biểu diễn được", nút chạy khóa, hiện *"Không có luật nào biểu diễn được, nên chưa chạy được. Các câu này sẽ nằm trong phần chưa kiểm."*
- **F2.5** AI không trả lời trong 60 giây (N1) → dừng chờ, không tạo luật, hiện *"AI không phản hồi trong 60 giây. Bạn có thể thử lại hoặc dùng mẫu có sẵn."* Lượt quá giờ không bị trừ **(đề xuất, chờ duyệt)**.
- **F2.6** Đầu ra AI không đọc được hoặc sai lược đồ → tự thử lại 1 lần **(đề xuất, chờ duyệt)**. Vẫn sai toàn bộ: không tạo luật, hiện *"AI trả về kết quả không đúng lược đồ. Chưa tạo luật nào. Bạn có thể thử lại."* Sai một phần: giữ luật đúng, câu của luật sai hiện "không biểu diễn được" với lý do *"AI trả về sai lược đồ"*.
- **F2.7** Số tiền viết kiểu "10.000.000đ", "10.000.000 đồng", "10,000,000 VND", "10 triệu", "10tr", "1,5 triệu", "500 nghìn", "500k" → trường tiền là số nguyên đồng (10000000, 1500000, 500000), cạnh đó hiện đoạn chữ gốc để so ở F3. AI chỉ đọc số có sẵn, không tính số mới (N3).
- **F2.8** Số có phần lẻ dưới 1 đồng ("1.000,50 đ") hoặc mơ hồ ("khoảng 10 triệu", "vài triệu") → trường ghi *"cần nhập lại"*, luật không xác nhận được tới khi nhập số nguyên dương.
- **F2.9** Hai luật cùng loại, cùng phạm vi, cùng kênh nhưng khác số → hiện cạnh nhau với *"Hai câu này nói khác nhau. Máy dò sẽ áp cả hai."* Máy dò áp mọi luật đã xác nhận cùng lúc, giao dịch phải qua mọi luật **(đề xuất, chờ duyệt)**.
- **F2.10** Văn bản có tên người hoặc số điện thoại → không luật nào chứa các giá trị đó (S2).

### F3. Người xác nhận [P0; sửa tự do P1]
Người dùng xác nhận hoặc sửa từng luật trước khi chạy. Chưa xác nhận thì không chạy.
- **F3.1** Còn luật "chưa xác nhận" → nút chạy khóa, hiện *"Còn N luật chưa xác nhận."*
- **F3.2** [P0] Sửa luật chưa xác nhận → chỉ sửa trường số (tiền, giờ) và chọn lại giá trị liệt kê (kể cả *để ngỏ*); không thêm luật, không đổi loại. Luật đã sửa có nguồn "người sửa", nhãn đổi thành "đã sửa tay".
- **F3.3** Nhập tiền âm, 0, có phần lẻ, hoặc giờ ngoài khoảng (3.3), bấm lưu → không lưu, hiện *"Giá trị không hợp lệ: [tên trường] phải là [khoảng cho phép]."*
- **F3.4** Bỏ một luật → trạng thái "đã bỏ", không vào máy dò, câu gốc vẫn hiện để đối chiếu.
- **F3.5** [P1] Thêm luật hoặc đổi loại luật → luật mới qua kiểm lược đồ như F2.6 và phải xác nhận lại.

### F4. Tìm chỗ luật không nói [P0]
Liệt kê điểm để ngỏ, mỗi điểm có các cách hiểu. Nguồn: danh mục có sẵn 10 mục (2 mục mỗi chiều D4a, lấy từ spike) và AI. Mỗi điểm ghi nguồn.
- **F4.1** Bộ luật đã xác nhận có trường *để ngỏ*, bấm tìm → danh mục tạo điểm tương ứng, nguồn *"danh mục"*, không gọi AI.
- **F4.2** AI trả một điểm → điểm trỏ tới câu hoặc cụm chữ cụ thể trong văn bản gốc, thuộc CD1–CD5, nguồn *"AI"*, nhãn "AI đề xuất". Không trỏ được tới câu gốc thì loại, không hiện.
- **F4.3** AI chỉ ra điểm ngoài CD1–CD5 → vào phần chưa kiểm, mục *"chiều để ngỏ không được mô hình hóa"*, không vào máy dò.
- **F4.4** Danh mục và AI cùng chỉ ra một điểm (cùng luật, cùng chiều) → hiện một điểm, nguồn *"danh mục, AI"*.
- **F4.5** Chưa thao tác → mọi cách hiểu được chọn. Bỏ chọn được, mỗi điểm còn ít nhất một cách hiểu.
- **F4.6** AI quá 60 giây hoặc sai lược đồ → vẫn hiện điểm từ danh mục, kèm *"Phần AI chưa chạy được. Kết quả hiện chỉ từ danh mục."* Vẫn cho chạy.

### F5. Dò lỗ hổng [P0]
Với mỗi tổ hợp, máy dò hết các chuỗi hành động trong giới hạn D6; báo mức mất tối đa, chuỗi bước, kiểm soát đã thất bại. Tổ hợp ghép theo tích Descartes các cách hiểu đã chọn, trần 64.
- **F5.1** Bấm chạy → số tổ hợp bằng tích số cách hiểu đã chọn trên từng điểm; báo cáo hiện con số này.
- **F5.2** Tích > 64 → dò 64 tổ hợp đầu theo thứ tự cố định (mã luật, mã chiều, thứ tự cách hiểu ở 3.4) **(thứ tự: đề xuất, chờ duyệt)**; báo cáo ghi *"vượt giới hạn: dò 64 trên [tổng] tổ hợp"* và liệt kê tổ hợp bị bỏ qua.
- **F5.3** Mỗi tổ hợp dò xong → có mức mất tối đa (số nguyên đồng), chuỗi bước đạt mức đó, luật không chặn được, năng lực đã dùng ở mỗi cổng.
- **F5.4** Mọi lần chạy → báo cáo hiện đúng giới hạn đã dùng: 24 giờ, mốc mỗi giờ cộng mốc biên, 6 bước, 3 người nhận, số dư 50.000.000 đ, số tiền tại điểm biên.
- **F5.5** Mọi tổ hợp cùng mức mất → hiện *"Không tìm thấy lỗ hổng trong giới hạn đã dò."*, mức mất nền, đủ phần chưa kiểm. Không có chữ "an toàn" hay câu tương tự (X1).
- **F5.6** Mức mất nền > 0 → hiện *"Ngay cả với cách hiểu chặt nhất, kẻ tấn công có các năng lực đang bật vẫn rút được [số] đ trong 24 giờ."* kèm chuỗi bước.
- **F5.7** Tắt D5.3 và không thêm được thiết bị → mức mất 0 đ ở mọi tổ hợp, báo cáo ghi lý do.

### F6. Đo chặn nhầm [P0]
Với mỗi tổ hợp, chạy 6 hành trình (3.8).
- **F6.1** Mỗi tổ hợp đã dò → mỗi hành trình cho "qua", "bị giữ [n] giờ" hoặc "bị chặn ở bước [k]".
- **F6.2** Hành trình 1, hạn 11:00: làm được lúc 10:00 → "bị giữ 1 giờ"; sớm nhất 12:00 → "bị chặn ở bước 1".
- **F6.3** Báo cáo có bảng hành trình × tổ hợp và dòng tóm tắt số tổ hợp mà mỗi hành trình bị giữ hoặc bị chặn.

### F7. Phát lại [P0: danh sách bước trên màn hình]
Mỗi lỗ hổng phát lại được từng bước. Cùng đầu vào cho đúng cùng kết quả.
- **F7.1** Mở chi tiết lỗ hổng → từng bước có mốc giờ, hành động, số tiền, số dư sau bước, luật được xét, kết quả (qua / chặn / chờ). Tên tác nhân và kênh trừu tượng (S3).
- **F7.2** Cùng phiên bản bộ luật, cùng cách hiểu đã chọn, cùng năng lực, chạy lại → mọi số tiền, chuỗi bước, kết quả hành trình giống hệt (N2).

### F8. Vá và thử lại [P0]
AI đề xuất tối đa 3 bản vá, viết thẳng theo lược đồ, kèm một câu luật tiếng Việt. Người xác nhận. Máy chạy lại cùng tấn công và hành trình, hiện trước và sau.
- **F8.1** Báo cáo có lỗ hổng, bấm đề xuất vá → tối đa 3 bản; mỗi bản có luật theo lược đồ (thêm hoặc sửa), một câu tiếng Việt, lỗ hổng nhắm tới, nhãn "AI đề xuất".
- **F8.2** Không có lỗ hổng → nút đề xuất vá khóa.
- **F8.3** Bản vá sai lược đồ → bị loại, hiện *"Một bản vá bị loại vì không đúng lược đồ."* Không còn bản nào: *"AI chưa đưa ra được bản vá hợp lệ. Bạn có thể thử lại."*
- **F8.4** Bản vá có số tiền (ví dụ hạn mức mới) → đó là giá trị luật đề xuất, sửa được trước khi xác nhận. Mức mất và kết quả sau vá do máy dò tính (N3, X5).
- **F8.5** Xác nhận một bản → tạo phiên bản bộ luật mới, chạy lại cùng tổ hợp và sáu hành trình, hiện trước và sau: mức mất theo tổ hợp, kết quả hành trình, hành trình nào trở nên bị giữ hoặc bị chặn.
- **F8.6** Bản vá làm ít nhất một hành trình từ "qua" sang "bị giữ" hoặc "bị chặn" → dòng đó đánh dấu *"đánh đổi"*.

### F9. Kiểm thử hồi quy [P1]
- **F9.1** Lần chạy có lỗ hổng → mỗi lỗ hổng lưu thành một ca (tổ hợp, chuỗi bước, mức mất), nằm trong bộ luật hoặc phiên làm việc, không phụ thuộc F12.
- **F9.2** Sửa luật (kể cả qua bản vá) rồi chạy → mọi ca chạy lại, mỗi ca hiện *"còn hở"* (chuỗi vẫn rút được như cũ) hoặc *"đã đóng"*.

### F10. Báo cáo [P0 trên màn hình; P1 xuất file]
- **F10.1** Thứ tự phần: giới hạn dò; năng lực đang bật; lỗ hổng (mức mất giảm dần); mức mất nền; chặn nhầm; bản vá (nếu có); phần chưa kiểm.
- **F10.2** Mọi báo cáo, kể cả không có lỗ hổng, có phần chưa kiểm đúng năm mục, mục rỗng ghi "không có": (1) câu không biểu diễn được (trích câu); (2) chiều để ngỏ không được mô hình hóa (trích câu, lời AI); (3) năng lực D5 đang tắt (luôn có D5.5 nếu tắt); (4) giới hạn dò đã dùng (D6); (5) tổ hợp cách hiểu bị cắt (nếu vượt 64).
- **F10.3** Mọi điểm để ngỏ và lỗ hổng ghi nguồn "danh mục", "AI" hoặc cả hai.
- **F10.4** Mọi số tiền là giá trị luật đã xác nhận hoặc do máy dò tính, viết dạng "50.000.000 đ".
- **F10.5** [P1] Bấm xuất → tải file Markdown hoặc HTML cùng nội dung và nhãn "AI đề xuất".

### F11. Tài khoản dùng thử [P0]
Bắt buộc vì S4 đòi đăng nhập để dán luật riêng.
- **F11.1** Giám khảo đăng nhập bằng tài khoản chung ghi trong hướng dẫn 1 trang → vào được, dán luật được.
- **F11.2** Người chưa có tài khoản đăng ký bằng tên đăng nhập và mật khẩu → dùng được ngay, không xác minh email.
- **F11.3** Hai tài khoản khác nhau không thấy bộ luật của nhau. Người dùng tài khoản chung thấy bộ luật của nhau; hướng dẫn 1 trang ghi rõ.

### F12. Lịch sử phiên bản [P2]
Mỗi bộ luật lưu các phiên bản đã chạy. F8.5 đã tạo phiên bản mới khi vá; F12 chỉ thêm việc xem lại phiên bản cũ. Không đặc tả chi tiết.

### F13. Triển khai online [P0]
Máy chủ công khai (C1, C2).
- **F13.1** Mỗi 5 phút có một lần kiểm tra còn sống, kết quả ghi nhật ký có giờ.
- **F13.2** Kiểm tra thất bại hoặc tiến trình chết → tự khởi động lại, không cần người.
- **F13.3** Link trong hướng dẫn chạy qua HTTPS.

### F14. Bài nộp [P0]
- **F14.1** README khai báo: cách chạy, công nghệ, thư viện mã nguồn mở, công cụ AI, tài sản có sẵn, và C7. Dùng lại bất kỳ mã nào từ spike thì ghi spike là tài sản có sẵn làm trước cuộc thi (C8). Có người đọc ở E2 cách 4 thì khai báo theo C7.
- **F14.2** Đủ bốn thành phần C6: hướng dẫn 1 trang có link và tài khoản chung, mã nguồn .zip, slide ≤ 10 trang, video ≤ 3 phút quay sản phẩm chạy thật.

## 6. Phi chức năng (N)

Tất cả P0, trừ N6 (P1).

| Mã | Yêu cầu | Cách đo |
|---|---|---|
| N1.1 | Máy dò chạy một mẫu đã lưu xong trong ≤ 90 giây, không tính gọi AI | 3 mẫu trên máy chủ online, mỗi mẫu 3 lần; lần chậm nhất ≤ 90 giây |
| N1.2 | Mỗi lời gọi AI dừng sau 60 giây | Giả AI không trả lời; hệ thống báo lỗi theo F2.5 trong 60–65 giây |
| N2.1 | Tất định: cùng bộ luật đã xác nhận cho cùng kết quả dò | Chạy một mẫu 3 lần; mọi số tiền, chuỗi bước, kết quả hành trình giống hệt |
| N2.2 | Đầu ra AI được lưu, phát lại không cần gọi AI | Ngắt mạng tới AI; mở bộ luật đã chuyển; chạy lại được |
| N3.1 | Mọi số tiền trong báo cáo do máy dò tính. AI chỉ đọc số có sẵn trong văn bản (ví dụ hạn mức) để điền lược đồ, người xác nhận ở F3. AI không bao giờ tính số mất hay số tổng | Mọi số truy được về luật đã xác nhận hoặc kết quả máy dò; kiểm thử trên 3 mẫu |
| N4.1 | Giao diện tiếng Việt | Không chuỗi tiếng Anh, trừ tên kỹ thuật như OTP, PIN, SIM |
| N5.1 | AI gọi qua một lớp riêng | Đổi mô hình hoặc nhà cung cấp chỉ sửa cấu hình và lớp đó (SDD nói rõ) |
| N6.1 [P1] | Nhật ký mỗi lần chạy | Có đầu vào, phiên bản bộ luật, mô hình AI, giờ bắt đầu, thời gian chạy. Không chứa văn bản dán vào ở dạng đầy đủ **(đề xuất, chờ duyệt)** |
| N7.1 | Giới hạn số lần chạy theo tài khoản và địa chỉ | Theo N9.2, N9.3 |
| N8.1 | Kiểm thử tự động cho máy dò | Có kiểm thử ví dụ 50 triệu (mục 9) đã kiểm bằng tay, chạy bằng một lệnh, qua hết |
| N9.1 | 3 mẫu dùng đầu ra AI đã lưu | Tắt khóa AI; mở 3 mẫu, chạy, xem bản vá đã lưu được |
| N9.2 | Mỗi tài khoản 20 lượt AI mỗi ngày (mặc định), đặt lại 00:00 giờ Việt Nam **(giờ đặt lại: đề xuất, chờ duyệt)** | Lượt thứ 21 bị từ chối theo N9.4 |
| N9.3 | Mỗi IP tối đa 5 yêu cầu mỗi phút | Yêu cầu thứ 6 trong một phút nhận *"Bạn thao tác quá nhanh. Hãy thử lại sau một phút."* |
| N9.4 | Thông báo chế độ hạn chế | Hết lượt tài khoản: *"Tài khoản đã dùng hết 20 lượt AI hôm nay. Bạn vẫn chạy được 3 mẫu có sẵn và các bộ luật đã xác nhận. Lượt AI mở lại lúc 00:00."* Chạm trần chi: *"RuleGap đang ở chế độ hạn chế vì đã dùng hết ngân sách AI. Bạn vẫn chạy được 3 mẫu có sẵn và các bộ luật đã xác nhận."* |
| N9.5 | Trần chi cứng toàn hệ thống; chạm trần thì ngừng gọi AI | Đặt trần thấp trong môi trường thử; chạm trần thì không lời gọi AI nào được gửi đi |

## 7. An toàn, pháp lý, công bố AI (S)

Tất cả P0, trừ S1.2 (P1).

- **S1. Chỉ dùng tổ chức hư cấu.**
  - **S1.1** [P0] Màn hình dán có câu cố định, không tắt được: *"Chỉ dán luật của tổ chức hư cấu. Không dán tên tổ chức thật."*
  - **S1.2** [P1] Văn bản có tên tổ chức tài chính thật trong danh sách kiểm, bấm chuyển luật → hiện *"Văn bản có tên tổ chức thật: [tên]. Hãy xóa hoặc đổi sang tên hư cấu trước khi tiếp tục."* Chưa xóa thì không gọi AI. Danh sách kiểm: chưa quyết (Q22).
- **S2.** Không nhận và không lưu dữ liệu khách hàng thật. Lược đồ không có trường danh tính (3.2, F2.10). Màn hình dán có câu: *"Không dán dữ liệu khách hàng: tên, số điện thoại, số tài khoản, số giấy tờ."*
- **S3.** Kết quả là chuỗi sự kiện trừu tượng và bản vá, không viết thành hướng dẫn tấn công một dịch vụ có thật. Tên trừu tượng: "kẻ tấn công", "người nhận A/B/C", "kênh voucher", "kênh nạp thẻ", "kênh hóa đơn", "ví hư cấu". Không thương hiệu thật. Kiểm: đọc báo cáo của 3 mẫu.
- **S4.** Dán luật riêng phải đăng nhập (F1.4). Mẫu có sẵn không cần.
- **S5.** Khóa API chỉ ở máy chủ, không xuống trình duyệt, không vào repo. Kiểm: tìm chuỗi khóa trong repo và mã trang tải về: không thấy.
- **S6.** Mọi nội dung AI tạo có nhãn "AI đề xuất" (C10): luật do AI chuyển, điểm để ngỏ nguồn AI, bản vá. Luật sửa tay đổi nhãn thành "đã sửa tay". Kết quả máy dò không mang nhãn này.
- **S7.** Trang đầu và mọi trang có gọi AI, khi mở trang và trước mỗi lần chạy, có thông báo cố định, không tắt được (C10, Luật 134/2025/QH15 Điều 11): *"Bạn đang dùng một công cụ có AI. Phần có nhãn 'AI đề xuất' do AI tạo và cần người kiểm lại. Số tiền trong báo cáo do máy dò tính, không do AI."* S6 vẫn giữ cho nhãn từng nội dung.

## 8. Đo giá trị AI (E)

Mục đích: chứng minh C3 bằng số, không bằng lời. P0: E1–E4, E6 với cách 1, 2, 3. E5 là P1, cách 4 là P2.

- **E1. Bộ thử.** 8 đoạn luật hư cấu: 6 cài sẵn lỗ hổng, 2 chặt. Trễ thì 6 đoạn (4 cài, 2 chặt). Người soạn không phải người viết câu lệnh cho AI. Mỗi đoạn cài có đáp án viết trước khi đo (lỗ hổng ở chiều nào, câu nào), khóa lại, không sửa sau khi xem kết quả.
- **E2. Cách so** trên cùng bộ thử:

| Cách | Làm gì | Ghi lại |
|---|---|---|
| 1 | Dán mỗi đoạn vào chat AI một lần với cùng một câu hỏi cố định (Q24) | Phát hiện, thời gian |
| 2 | Một thành viên mã hóa tay đoạn luật vào lược đồ, chạy danh mục và máy dò, không AI | Phát hiện, thời gian mã hóa, số lần sửa tay |
| 3 | RuleGap đầy đủ | Phát hiện, thời gian, số lần sửa tay ở F3 |
| 4 [P2] | 4–6 người đọc, 10–15 phút mỗi đoạn. Người đọc chỉ thử, không xây sản phẩm (C9) | Phát hiện, thời gian |

- **E3. Chỉ số:** số lỗ hổng cài sẵn tìm được (so đáp án); độ chính xác trong 5 phát hiện đầu; số phát hiện không liên quan trên đoạn chặt; số lần sửa tay; thời gian chạy. Chấm: đầu ra mọi cách trộn thứ tự, che nhãn nguồn, rồi đội chấm theo đáp án. Slide ghi rõ người chấm là thành viên đội, không độc lập.
- **E4.** Đo ngay khi phần AI chạy được lần đầu, không chờ ngày cố định.
- **E5.** [P1] AI không tìm thêm được gì so với cách 2: chuyển AI sang đối chiếu nhiều tài liệu nói trái nhau, rồi đo lại. Không đổi ý tưởng sản phẩm. Slide báo cả hai lần đo.
- **E6.** Kết quả lên slide kể cả khi xấu (kể cả khi cách 3 không hơn cách 2): một bảng cách × chỉ số, ghi số đoạn đã dùng (8 hoặc 6), một dòng nói cách chấm. Có người đọc (cách 4) thì ghi rõ là sinh viên, không phải chuyên viên; ẩn danh; có đồng ý; khai báo trong README (C7).

## 9. Ví dụ chuẩn: 50.000.000 đ

Phép thử nghiệm thu cho máy dò (N8). Số liệu lấy từ spike.

**Đầu vào**
- Bộ luật hư cấu dùng trong spike. Văn bản và luật theo lược đồ phải chép từ spike vào bộ kiểm thử (chưa có trong tài liệu này, Q23).
- Số dư 50.000.000 đ.
- Giới hạn dò **theo spike, không theo mặc định D6**, vì các số bên dưới tính với cấu hình này:
  - hạn mức gốc 10.000.000 đ;
  - bắt đầu 22:00, chỉ xét 3 mốc: 22:00, 01:00 hôm sau (đã sang ngày lịch mới), 21:00 hôm sau;
  - tối đa 6 người nhận;
  - số tiền tại điểm biên theo bước 1.000 đ: 1.000 đ, phần còn lại dưới hạn mức trừ 1.000 đ, đúng hạn mức, toàn bộ số dư.

  Với mặc định D6 (3 người nhận, mốc mỗi giờ) kết quả có thể khác. Đó là phép thử riêng, không dùng bảng dưới.
- Năng lực theo cấu hình spike, D5.5 tắt.
- Một điểm để ngỏ trên mỗi chiều CD1–CD5, chọn mọi cách hiểu.

**Kết quả mong đợi**

| Đại lượng | Giá trị |
|---|---|
| Số tổ hợp | 48 (= 3 × 2 × 2 × 2 × 2) |
| "vượt giới hạn" | không (48 ≤ 64) |
| Tổ hợp mất 50.000.000 đ (toàn bộ số dư) | 46 |
| Tổ hợp mất 19.998.000 đ | 1 |
| Tổ hợp mất 9.999.000 đ | 1 |
| Mức mất nền | 9.999.000 đ |
| Số lỗ hổng (3.7) | 47 |

**Chưa chốt.** Bảng chi tiết từng tổ hợp (tổ hợp nào mất bao nhiêu, chuỗi bước nào) do kiểm thử máy dò xác nhận (N8); tài liệu này không ghi hai tổ hợp 19.998.000 đ và 9.999.000 đ là tổ hợp nào. Máy dò cho kết quả khác bảng thì dừng, so với spike, sửa máy dò hoặc sửa tài liệu có ghi lý do. Không chỉnh kiểm thử cho khớp máy dò.

**Nghiệm thu.** Đầu vào trên → chạy máy dò → phân bố mức mất đúng bảng, mọi số là số nguyên đồng, 3 lần chạy cùng kết quả, mỗi lần ≤ 90 giây.

## 10. Ngoài phạm vi (O) và luật cứng (X)

Không làm trong bản nộp:
- **O1.** Gian lận khuyến mãi. **O2.** Xử lý khiếu nại, tranh chấp. **O3.** Mô hình phát hiện gian lận trên giao dịch. **O4.** Dự báo tổng thiệt hại cả thị trường. **O5.** Mô phỏng tâm lý hay khả năng bị thuyết phục.
- **O6.** Kết nối hệ thống thật hay API của bất kỳ tổ chức nào, kể cả MoMo. **O7.** Giao diện tiếng Anh, ứng dụng di động. **O8.** Phân quyền nhiều tổ chức. **O9.** Nội dung gửi khách hàng cuối. **O10.** Để mô hình ngôn ngữ tự thực hiện chuỗi tấn công.

Không được làm:
- **X1.** Không nói sản phẩm "đảm bảo an toàn", "bắt hết lỗ hổng" hay "chứng nhận".
- **X2.** Không nói là sản phẩm đầu tiên.
- **X3.** Không dùng dữ liệu cá nhân hay dữ liệu doanh nghiệp thật.
- **X4.** Không sao chép giao diện, logo, tên của MoMo hay tổ chức khác.
- **X5.** Không để AI quyết định kết quả tiền hay kết luận cuối. Người duyệt, máy tính. AI chỉ được đọc số tiền có sẵn trong văn bản (N3).
- **X6.** Không đưa con số nào lên slide hay báo cáo mà không có nguồn hoặc không do máy dò tính.
- **X7.** Không sửa bất cứ gì đã nộp sau hạn.
- **X8.** Không thêm tính năng ngoài phạm vi khi chưa sửa tài liệu này và cả đội chưa đồng ý.

## 11. Hoàn thành (DoD) và mốc

- **DoD1.** Từ link tới kết quả của một mẫu: ≤ 5 thao tác, ≤ 2 phút, chỉ cần đọc hướng dẫn 1 trang. Thử với ít nhất 2 người chưa từng thấy sản phẩm.
- **DoD2.** Dán bộ luật mới, xác nhận, chạy, vá, chạy lại được, không lỗi.
- **DoD3.** Đủ 3 mẫu, mỗi mẫu có ít nhất một lỗ hổng và một bản vá có đánh đổi.
- **DoD4.** Có kết quả đo E, dù tốt hay xấu.
- **DoD5.** Đủ bài nộp C6. README khai báo đúng C7, C8 và công cụ AI.
- **DoD6.** Chạy ổn định trên máy chủ online tới hết 11/12. Nhật ký kiểm tra còn sống (F13) không có lần ngừng nào dài quá 30 phút.

| Ngày | Việc |
|---|---|
| 26–27/11 | Chốt phạm vi, viết đặc tả và SDD, quy ước repo |
| 28/11 | Triển khai bản khung lên máy chủ online. Từ đây triển khai lại mỗi ngày |
| 28–29/11 | Máy dò và lược đồ luật, kiểm thử với ví dụ 50 triệu |
| 29–30/11 | AI chuyển luật và tìm chỗ không nói; đo E ngay khi chạy được |
| 30/11–01/12 | Vá, báo cáo, giao diện, tài khoản |
| 01/12 (tối) | Quay video |
| 02/12 | Đóng băng tính năng, slide. Quay lại video chỉ khi cần |
| 03/12 | Kiểm tra lần cuối và nộp |

## 12. Điểm chưa quyết

Đề xuất mặc định dưới đây chờ đội duyệt; chưa duyệt thì điểm vẫn mở, nhưng đề xuất dùng tạm.

- **Q1.** Mô hình AI nào, ngân sách bao nhiêu, con số trần chi cứng (N9.5). Đề xuất: một nhà cung cấp, gọi qua lớp N5, có trần chi cứng.
- **Q2.** Triển khai ở đâu để chắc chạy được tới 11/12. Đề xuất: một VPS hoặc PaaS có tự khởi động lại.
- **Q3.** Giao diện làm bằng gì cho hợp đội mạnh Python. Đề xuất: trang dựng phía máy chủ bằng Jinja, thêm HTMX.
- **Q4.** Ai làm phần nào. Đề xuất: một người làm máy dò và kiểm thử; một người làm AI, giao diện, triển khai.
- **Q5.** Đã trả lời: danh mục 10 mục, 2 mục mỗi chiều D4a, lấy từ spike (F4).
- **Q6.** Đội chọn không hỏi BTC về chủ đề, rủi ro "không được coi là An ninh mạng" vẫn còn. Cách giảm: trình bày gắn chiếm tài khoản và lỗ hổng nghiệp vụ (C4).
- **Q7.** Lược đồ luật (3.3): năm loại HM, NQ, DH, CH, XT, các trường, khoảng giá trị (cửa sổ 1–24 giờ, trễ và chờ 1–72 giờ). Phải đối chiếu lược đồ trong spike.
- **Q8.** Hai cách hiểu của CD2 (3.4).
- **Q9.** Giờ bắt đầu dò 00:00 ngày 1, mốc 24:00 thuộc ngày 2. Ảnh hưởng trực tiếp cửa sổ ngày lịch (CD5) và ví dụ 50 triệu.
- **Q10.** "Sát dưới hạn mức" là trừ 1.000 đ hay trừ 1 đ. 9.999.000 đ gợi ý 1.000 đ; cần đối chiếu spike.
- **Q11.** "Chờ" có tính vào 6 bước không. Đề xuất: không.
- **Q12.** Năng lực mặc định khi dò: D5.1–D5.4 bật. Cần khớp spike.
- **Q13.** Định nghĩa lỗ hổng và mức mất nền (3.7). Đề xuất: lỗ hổng là tổ hợp có mức mất lớn hơn mức nhỏ nhất trong các tổ hợp.
- **Q14.** Hành vi khách trong hành trình: chờ tới mốc sớm nhất, được đổi hạn mức, không chia nhỏ; bắt đầu 09:00; lần 2 của hành trình 3 lúc 15:00; người nhận hành trình 5 là Q1.
- **Q15.** Thứ tự cắt khi vượt 64 tổ hợp (F5.2).
- **Q16.** Lượt AI: mỗi thao tác gọi AI tính 1 lượt; lượt quá giờ không trừ; tự thử lại 1 lần khi sai lược đồ. Lần thử lại có tính lượt không: chưa quyết.
- **Q17.** Hạn mức của tài khoản giám khảo dùng chung: 20 lượt mỗi ngày có thể không đủ khi nhiều giám khảo dùng cùng lúc. Có nâng riêng không: chưa quyết.
- **Q18.** Giờ đặt lại hạn mức: 00:00 giờ Việt Nam.
- **Q19.** Giới hạn độ dài văn bản dán: 5.000 ký tự.
- **Q20.** Luật mâu thuẫn: máy dò áp cả hai (F2.9).
- **Q21.** Nhật ký N6 có lưu văn bản dán vào không. Đề xuất: không lưu dạng đầy đủ.
- **Q22.** Danh sách tên tổ chức thật cho S1.2 (P1): lấy từ đâu, bao nhiêu tên.
- **Q23.** Bộ luật và cấu hình ví dụ 50 triệu: chép từ spike vào bộ kiểm thử; bảng chi tiết từng tổ hợp do N8 xác nhận.
- **Q24.** Câu hỏi cố định cho cách 1 ở E2: chưa viết.
- **Q25.** Số người nhận tối đa mặc định ở D6: đang là 3, spike dùng 6. Hạn mức theo người nhận càng thấp thì kẻ gian càng cần nhiều người nhận, nên trần 3 có thể làm báo cáo mất tiền thấp hơn thực tế. Đo thời gian chạy với 6 người nhận và mốc mỗi giờ trước khi chốt.

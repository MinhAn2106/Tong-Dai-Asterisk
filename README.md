# Tong-Dai-Asterisk
# Bài thực hành 1 :
Thực hiện cấu hình một tổng đài Asterisk đảm bảo việc liên lạc nội bộ với các extension: 1X1, 1X2 với X là chữ số cuối của MSSV.

1X1 sử dụng công nghệ SIP, 1X2 sử dụng công nghệ IAX2. 
Sinh viên thực hiện theo hướng dẫn sau: 
1. Tạo các extension tương ứng: 1X1, 1X2
2. Tạo dialplan với ngữ cảnh liên lạc nội bộ
3. Cập nhật thông tin ngữ cảnh (context) để 1X1 và 1X2 ứng với dialplan ở bước 2
4. Thực hiện cuộc gọi giữa 1X1, 1X2 và ngược lại để kiểm chứng.

# Bài thực hành 02: Yêu cầu bài tập
Xây dựng hệ thống tổng đài Asterisk cho công ty XX (với XX là mã nhóm) cho phép các liên lạc:
- Nội bộ (internal)
- Trong ra ngoài (outgoing)
- Ngoài vào trong (incoming)
# Nội bộ (internal)
Nội bộ gồm các phòng ban và các số máy tương ứng sau:
- 6001: phòng tài vụ
- 6002: phòng nhân sự
- 6003: phòng kinh doanh
- Yêu cầu sinh viên cài đặt hệ thống để các phòng ban này có thể liên lạc được với
nhau thông qua máy chủ tổng đài.
- Yêu cầu nâng cao (sinh viên tìm hiểu thêm trong tài liệu HDTH chức năng
MeetMe): Cấu hình cho phép có thể họp nội bộ thông qua đầu số (9XX9), password
đăng nhập là 1234 và password quản trị là 1234XX.
# Trong ra ngoài (outgoing)
Yêu cầu sinh viên cài đặt hệ thống sao cho các phòng ban khi liên lạc ra ngoài bắt buộc
phải nhấn thêm số 8 trước số cần gọi.
# Ngoài vào trong (incoming)
Khi có cuộc gọi tới số máy của công ty XX, hệ thống Asterisk phát câu “Cảm ơn quý khách
đã gọi đến công ty XX” (1), sau đó phát thông điệp “Xin quý khách vui lòng nhấn tiếp sốTrang 2
nội bộ hoặc nhấn phím 1 để gặp phòng tài vụ, nhấn phím 2 để gặp phòng nhân sự, nhấn
phím 3 để gặp phòng kinh doanh” (2).
- Trong trường hợp khách hàng không nhấn phím nào, xử lý lặp lại thông điệp (2)
thêm 2 lần nữa. Nếu sau 3 lần mà người gọi không nhấn phím thì phát thông điệp
“Cảm ơn quý khách đã gọi đến công ty XX, chúc quý khách một ngày vui vẻ, xin
tạm biệt”. Tham khảo: http://www.voip-info.org/wiki/view/Asterisk+cmd+While
hoặc tìm kiếm thêm trên Internet.
- Trường hợp khách hàng nhấn phím sai, hệ thống phát thông điệp “Quý khách đã
nhấn sai phím, xin vui lòng nhấn lại theo hướng dẫn”, sau đó tiếp tục vòng lặp trên.
- Trường hợp nhấn đúng phím, thì phát thông điệp “Chúng tôi đang nối máy đến
phòng xyz, xin quý khách vui lòng đợi trong giây lát” và nối máy đến phòng tương
ứng.
- Trường hợp người gọi yêu cầu nối máy tới giám đốc (khi nhấn tiếp số nội bộ), nếu
giám đốc không trả lời sau 15s hoặc máy bận thì cho phép để lại tin nhắn trong hộp
thư thoại (password là 4321)
- Yêu cầu nâng cao (yêu cầu sinh viên tự tìm hiểu thêm): Cấu hình để hệ thống chỉ
phục vụ trong giờ hành chính (7:00-11:00 và 13:00-17:00). Nếu có cuộc gọi đến
trong khoảng thời gian ngoài giờ hành chính trên, hệ thống sẽ phát thông điệp “Cảm
ơn quý khách đã gọi đến công ty XX. Hiện đang ngoài giờ hành chính, xin quý khách
vui lòng gọi lại trong khoảng thời gian từ 7:00 đến 11: 00 hoặc 13:00 đến 17:00.
Tạm biệt quý khách”. Gợi ý: sử dụng công cụ tìm kiếm với từ khóa “open hours”.

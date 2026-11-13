---
description: "Lộ trình thực hành giúp người mới dùng Shared Hosting của Namecheap đi từ mua tên miền, trỏ DNS, cài WordPress đến bật SSL."
---

# Từ số 0 đến website chạy được với Shared Hosting Namecheap

Mua hosting xong không có nghĩa là đã có website. Rất nhiều người lần đầu trả tiền cho gói hosting, nhận email xác nhận, rồi bối rối không biết làm gì tiếp theo. Khoảng cách giữa “có hosting” và “có website chạy được” nằm ở một chuỗi các bước cấu hình: trỏ tên miền, cài nền tảng web, bật chứng chỉ bảo mật và kiểm tra lần cuối. Bài này hướng dẫn bạn đi hết lộ trình đó với Shared Hosting của [Namecheap](https://www.namecheap.com/), theo cách thực hành từng bước, không cần hiểu trước các thuật ngữ kỹ thuật.

Bốn thuật ngữ bạn sẽ gặp liên tục:

- **Hosting**: nơi lưu trữ toàn bộ dữ liệu website trên một máy chủ luôn bật, để người khác truy cập bất cứ lúc nào.
- **Tên miền**: địa chỉ người dùng gõ vào trình duyệt, ví dụ `tencuaban.com`.
- **DNS**: hệ thống giống danh bạ, giúp chuyển tên miền thành địa chỉ máy chủ chứa website.
- **SSL**: chứng chỉ mã hoá kết nối giữa trình duyệt và máy chủ, hiển thị biểu tượng ổ khoá trên thanh địa chỉ.

Nếu bạn là người làm nội dung hoặc chủ cửa hàng nhỏ ở Việt Nam lần đầu làm website, đọc tài liệu tiếng Anh còn chậm và ngân sách hạn chế, hãy làm theo thứ tự dưới đây.

## Chuẩn bị trước khi mua

Trước khi mở trang thanh toán, hãy xác định rõ mục đích của trang. Một blog cá nhân cần ít tài nguyên hơn một cửa hàng nhỏ có nhiều ảnh sản phẩm. Một landing page giới thiệu dịch vụ lại càng nhẹ. Mục đích này quyết định gói hosting bạn chọn và cả giao diện sẽ cài sau này.

Tiếp theo, chọn tên miền. Ưu tiên đuôi `.com` vì dễ nhớ và quen thuộc với người dùng Việt Nam. Tên ngắn, không dấu, tránh số và gạch nối vì dễ gây nhầm lẫn khi đọc to hoặc gõ trên điện thoại. Bạn có thể kiểm tra tên miền còn trống ngay trên trang chủ của Namecheap trước khi quyết định.

Ghi chú sẵn những thông tin cần điền khi mua: họ tên đầy đủ, email thường dùng, địa chỉ và phương thức thanh toán. Thẻ thanh toán quốc tế hoặc ví điện tử đều có thể dùng được. Cuối cùng, chuẩn bị sẵn nội dung cơ bản như logo, vài bài viết hoặc mô tả sản phẩm để không bỏ dở công việc sau khi cài xong.

## Mua Shared Hosting của Namecheap

Khi xem các gói Shared Hosting, đừng để giá khuyến mãi năm đầu chi phối quyết định. Hãy đọc mô tả theo nhu cầu thật: bạn cần bao nhiêu website, dung lượng lưu trữ ước tính và lượng khách truy cập kỳ vọng. Nếu chưa có số liệu, chọn gói thấp nhất là đủ cho một website mới. Bạn có thể tham khảo thêm về [giải pháp Lưu trữ chia sẻ (Shared Hosting)](https://docs.google.com/document/d/1zO3_tL_eqxDnGxvxmTeU2K6vbkQgWzTT1vpWz8lmU_k/edit?usp=drivesdk) để hiểu rõ giới hạn và khả năng phục vụ của loại hình này trước khi quyết định.

Về chu kỳ thanh toán, một năm là điểm cân bằng hợp lý giữa giá và rủi ro. Trả nhiều năm giúp giữ giá khuyến mãi nhưng bạn sẽ khó đổi hướng nếu nhu cầu thay đổi. Trong các tuỳ chọn thêm, nên bật **domain privacy** để che thông tin cá nhân khỏi tra cứu công khai và bật **tự động gia hạn** cho tên miền. Không cần thêm SSL trả phí vì Shared Hosting đã có chứng chỉ miễn phí, không cần backup trả phí hay dịch vụ email riêng ở lần đầu. Đặt lịch nhắc gia hạn tên miền trước hạn ít nhất hai tuần để tránh mất tên miền do quên.

## Trỏ tên miền và DNS

Nameserver là “địa chỉ chỉ đường” giúp tên miền tìm đến đúng máy chủ chứa website. Khi mua tên miền và hosting cùng một nơi, Namecheap thường tự gán nameserver mặc định, nhưng bạn vẫn nên kiểm tra lại. Vào bảng điều khiển hosting, tìm mục nameserver, sao chép hai dòng dạng `dns1.example.com` và `dns2.example.com`. Sau đó vào phần quản lý tên miền, dán hai dòng này vào mục nameserver và lưu lại.

Nếu bạn mua tên miền ở nhà cung cấp khác, hãy thay nameserver tại nơi quản lý tên miền đó bằng chính hai dòng lấy từ Namecheap. Sau khi thay đổi, DNS cần thời gian lan truyền toàn cầu, thường vài giờ, tối đa 24–48 giờ. Trong khoảng này, đừng thay đổi nameserver liên tục vì mỗi lần đổi lại bắt đầu lại quá trình chờ. Có thể kiểm tra trạng thái bằng công cụ DNS checker miễn phí hoặc thử truy cập tên miền trên trình duyệt sau vài giờ.

## Cài WordPress trong vài bước

Trong bảng điều khiển cPanel của Namecheap, tìm công cụ cài đặt sẵn **Softaculous**. Chọn WordPress và bắt đầu cài. Công cụ này sẽ tự tạo cơ sở dữ liệu — nơi lưu toàn bộ nội dung bài viết và cấu hình. Ghi lại tên cơ sở dữ liệu và mật khẩu mà hệ thống tạo ra, phòng khi cần xử lý sự cố sau này.

Điền thông tin cài đặt: tên trang, tài khoản quản trị và mật khẩu mạnh. Tránh dùng `admin` làm tên đăng nhập vì dễ bị tấn công dò mật khẩu. Sau khi cài xong, đăng nhập bảng quản trị WordPress theo đường dẫn dạng `tencuaban.com/wp-admin`. Làm quen giao diện cơ bản và chọn một theme đơn giản, phù hợp mục đích đã xác định ở bước đầu.

## Bật SSL miễn phí và kiểm tra

SSL là chứng chỉ mã hoá kết nối, giúp trình duyệt hiển thị ổ khoá và chữ `https` trên thanh địa chỉ. Trong cPanel, tìm mục **SSL/TLS Status** hoặc **AutoSSL** và bật chứng chỉ miễn phí. Chờ vài phút để hệ thống cấp chứng chỉ. Sau đó bật tuỳ chọn **Force HTTPS Redirect** để mọi khách truy cập tự động chuyển từ `http` sang `https`.

Kiểm tra lỗi hỗn hợp nội dung (mixed content): đây là tình trạng trang đã bật SSL nhưng vẫn còn hình ảnh hoặc liên kết dùng `http`. Mở trang ở chế độ ẩn danh và quan sát biểu tượng ổ khoá. Nếu mất ổ khoá, kiểm tra lại ảnh đã chèn và thay đường dẫn thành `https`.

## Kiểm tra trước khi công bố

Đo tốc độ tải bằng công cụ miễn phí. Nếu ảnh quá nặng, nén lại trước khi tải lên. Kiểm tra giao diện trên điện thoại vì phần lớn khách truy cập từ di động. Thử gửi biểu mẫu liên hệ và xác nhận email nhận được. Tạo bản sao lưu đầu tiên và ghi chú vị trí lưu. Rà lại tiêu đề trang, mô tả và trang “Giới thiệu” cơ bản.

## Sự cố thường gặp và cách xử lý

- **Tên miền chưa truy cập được**: kiểm tra DNS đã lan truyền chưa, chờ thêm nếu mới đổi nameserver.
- **Lỗi 403**: kiểm tra quyền file/thư mục hoặc quy tắc bảo mật trong cPanel.
- **Lỗi 500**: xem log lỗi trong cPanel, thường do plugin hoặc mã trong file cấu hình.
- **Quên mật khẩu quản trị WordPress**: dùng chức năng khôi phục qua email hoặc đặt lại trong cơ sở dữ liệu.

Nguyên tắc chung khi xử lý sự cố: thay đổi từng thứ một và ghi lại đã làm gì để dễ truy nguyên.

## Bước tiếp theo

Khi lượng truy cập tăng, website chậm hoặc cần nhiều tài nguyên hơn, hãy xem xét nâng cấp gói hosting. Duy trì thói quen bảo trì định kỳ: cập nhật WordPress, theme và plugin mỗi tháng, kiểm tra sao lưu và theo dõi hạn gia hạn tên miền. Một website nhỏ vận hành ổn định luôn tốt hơn một website lớn nhưng bị bỏ quên.

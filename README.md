# [Thực hành] Phân rã Epic – Feature – User Story và kiểm tra bằng bộ lọc INVEST - GoMart

> 👤 **Học viên:** Đỗ Hoàng Sơn | **Mã SV:** PTIT-HCM-066
> 🏫 **Môn học:** IT206-K25-Agile-va-Scrum

---

## 1. Phân rã Epic từ yêu cầu thô của Ban giám đốc

Từ yêu cầu thô của Ban giám đốc là 'Tháng này team phải làm xong toàn bộ hệ thống theo dõi đơn hàng cho GoMart', em tiến hành định nghĩa Epic cho dự án ứng dụng đi chợ hộ này.

Tên Epic được xác định: 'Hệ thống theo dõi và quản lý đơn hàng toàn diện GoMart'.

- Phạm vi Epic: Quản lý toàn bộ vòng đời đơn hàng từ lúc khách đặt mua, phân bổ người đi chợ, cập nhật trạng thái thời gian thực cho đến khi giao hàng thành công.
- Quy mô thời gian: Kéo dài trong nhiều Sprint (khoảng 2-3 tháng).

## 2. Phân rã Epic thành các Feature

Để đảm bảo nguyên tắc Agile là mỗi Feature có thể hoàn thành trong 1-2 Sprint và mang lại giá trị cụ thể cho người dùng, em chia Epic trên thành đúng 2 Feature chính:

- Feature 1: Quản lý trạng thái đơn hàng thời gian thực cho khách hàng (Giải quyết nhu cầu nắm bắt tiến độ đơn hàng của người mua).
- Feature 2: Cập nhật tiến độ xử lý đơn hàng dành cho người đi chợ (Giải quyết nhu cầu thao tác, cập nhật trạng thái đơn của Shipper/Shopper).

## 3. Phân rã Feature thành các User Story (US)

Tiến hành chia mỗi Feature thành 2 User Story ở tầng thi công, đảm bảo tuân thủ nghiêm ngặt cấu trúc 3 vế 'As a / I want / So that':

- US-01 (Thuộc Feature 1): As a khách hàng mới, I want nhận được thông báo đẩy (push notification) ngay khi trạng thái đơn hàng thay đổi, So that tôi không phải liên tục mở ứng dụng kiểm tra.
- US-02 (Thuộc Feature 1): As a khách hàng, I want xem chi tiết lịch sử thay đổi trạng thái đơn hàng theo mốc thời gian, So that tôi biết chính xác đơn hàng đang ở công đoạn nào.
- US-03 (Thuộc Feature 2): As a người đi chợ hộ, I want cập nhật trạng thái đơn hàng thành 'Đang mua hàng' hoặc 'Đang giao hàng' bằng một nút bấm đơn giản, So that khách hàng và hệ thống nắm bắt được tiến độ thực tế.
- US-04 (Thuộc Feature 2): As a người đi chợ hộ, I want chụp ảnh hóa đơn mua hàng và tải lên hệ thống trước khi bấm giao hàng, So that có minh chứng rõ ràng khi phát sinh khiếu nại.

## 4. Kiểm tra bộ lọc INVEST cho 4 User Story vừa viết

Dưới đây là bảng kiểm tra chi tiết tiêu chí INVEST cho 4 User Story đã xây dựng ở phần trên:

| User Story | I (Independent) | N (Negotiable) | V (Valuable) | E (Estimable) | S (Small) | T (Testable) |
| --- | --- | --- | --- | --- | --- | --- |
| US-01 | Đạt | Đạt | Đạt | Đạt | Đạt | Đạt |
| US-02 | Đạt | Đạt | Đạt | Đạt | Đạt | Đạt |
| US-03 | Đạt | Đạt | Đạt | Đạt | Đạt | Đạt |
| US-04 | Đạt | Đạt | Đạt | Đạt | Đạt | Đạt |

## 5. Rà soát và sửa lỗi các User Story do Product Owner viết nháp

Tiến hành phân tích chẩn đoán lỗi vi phạm bộ lọc INVEST đối với 3 câu lệnh nhập ban đầu của Product Owner và tiến hành viết lại phiên bản đạt chuẩn:

- Phân tích US-01 ('Làm tính năng thông báo cho khách hàng'): Vi phạm nghiêm trọng vì thiếu cả 3 vế cấu trúc, không rõ ai dùng, không đo lường được giá trị -> Vi phạm tiêu chí Valuable và Testable.
- Viết lại US-01 chuẩn: As a khách hàng, I want nhận thông báo khi đơn hàng được xác nhận, So that tôi chủ động thời gian nhận hàng.
- Phân tích US-02 ('La mot khach hang, toi muon xem trang thai don hang'): Có As a và I want nhưng thiếu vế So that, mô tả quá chung chung -> Vi phạm tiêu chí Valuable.
- Viết lại US-02 chuẩn: As a khách hàng, I want xem trạng thái đơn hàng hiện tại trên màn hình chính, So that tôi nắm bắt được tiến độ giao hàng mà không cần gọi điện hỏi tổng đài.
- Phân tích US-03 ('La mot nguoi di cho ho, toi muon cap nhat trang thai don va toi uu lai toan bo kien truc database he thong'): Vi phạm lỗi gộp hai việc vào một câu. Việc cập nhật trạng thái đơn chỉ mất vài ngày (Small), nhưng tối ưu toàn bộ kiến trúc database kéo dài nhiều Sprint và mang tính kỹ thuật hạ tầng -> Vi phạm tiêu chí Small và Estimable.
- Viết lại US-03 tách làm 2 hạng mục riêng: Hạng mục nghiệp vụ: As a người đi chợ hộ, I want cập nhật trạng thái đơn hàng trên app, So that hệ thống ghi nhận chính xác tiến độ. Hạng mục kỹ thuật (Task hạ tầng): As a Backend Developer, I want tối ưu hóa các index bảng đơn hàng trong database, So that tốc độ truy vấn trạng thái đơn hàng dưới 200ms.

---

## 📁 Danh sách tệp tin nộp bài trong Repository
- 📝 `btth2.docx`: Báo cáo tài liệu phân tích nghiệp vụ hoàn chỉnh.

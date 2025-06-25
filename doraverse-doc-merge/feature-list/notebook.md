---
icon: book-open-reader
---

# Notebook

## **Tổng quan sản phẩm**

* **Tên tính năng**: Notebook
* **Mục tiêu**: Cho phép người dùng tạo, lưu trữ và tương tác với các tập hợp tài liệu theo chủ đề, hỗ trợ tìm hiểu, ghi chú, và khai thác thông tin hiệu quả thông qua AI.

## **Mục tiêu tính năng (Goals)**

* Tạo và quản lý nhiều notebook theo chủ đề.
* Cho phép người dùng tải lên nhiều loại tài liệu vào từng notebook.
* Kết nối AI để trả lời câu hỏi dựa trên nội dung trong notebook.
* Tối ưu trải nghiệm đọc, tìm kiếm, ghi chú và tương tác trong từng notebook.
* Giai đoạn đầu sẽ học hỏi, tham khảo [notebooklm.google.com](http://notebooklm.google.com) để dễ hình dùng và xây dựng tính năng

## **Phạm vi (Scope)**

#### Trong phạm vi (In Scope)

* Tạo / xem danh sách / chỉnh sửa / đổi trạng thái / xoá notebook.
* Thêm / xem danh sách / chỉnh sửa / đổi trạng thái / xóa tài liệu trong notebook.
* Chat với notebook
* Chia sẻ với người khác

## Chi tiết chức năng

### Tạo notebook

* Người dùng có thể tạo 1 notebook với các thông tin
  * Title
  * Icon: Mặc định sẵn icon (random từ kho, hoặc có 1 icon rồi đổi màu)

#### Xem note book

* Ngươi dùng có thể xem danh sách notebook, mỗi note book gồm có
  * Tên
  * Icon
  * Người tạo
* Lọc
  * Của người dùng hay được share
* Sắp xếp
  * Theo thời gian
  * Theo title

#### Sửa notebook

* Người dùng có thể sửa Title của notebook
* Người dùng có thể đổi icon của notebook
* Người dùng có thể đổi cùng lần hoặc ở 2 chỗ khác nhau tùy UX/UI thiết kế

#### Xóa notebook

* Người dùng có thể xóa notebook, người dùng sẽ không thể truy cập toàn bộ tài liệu, lịch sử truy vấn, ghi chú liên quan đến notebook
* Thao tác xóa là không thể khôi phục, cần được xác nhận lại một lần trước khi xóa

#### Thêm tài liệu (source) cho notebook

Một notebook được tối đa 50 nguồn, con số 50 cần được cấu hình từ Admin Dora, Admin Workspace

Các loại tài liệu hỗ trợ sẽ giới hạn ở mức notebooklm hỗ trợ (có thể ít hơn)

* Upload file
  * Người dùng có thể upload lên notebook các loại file
    * Tệp PDF, văn bản (.txt), Markdown
    * Tệp âm thanh (có thể được chuyển thành văn bản)
  * Upload from Drive
* Dán văn bản
  * Người dùng có thể dán văn bản để tạo thành tài liệu
  * Hỗ trợ định dạng text bình thường, markdown. Có thể hỗ trợ html, code,… nhưng bị sẽ có khả năng hoạt động không tốt → có cảnh báo và tự động chuyển sang plain text để lưu

#### Chia sẻ notebook cho workspace

* Người dùng có thể chia sẻ một notebook mà họ tạo cho workspace, khi đó notebook sẽ xuất hiện trong danh sách notebook của các thành viên khác
* Việc chia sẻ này hoạt động theo cách của agent, prompt
* Ngươi dùng có thể bỏ chia sẻ này
* Admin workspace có thể chặn việc chia sẻ này của thành viên

#### Đặt tên và sửa tên tài liệu

* Tên tài liệu ban đầu sẽ được giữ nguyên theo tên file gốc upload lên,
* Nếu tài liệu gốc không có thì sẽ tự động tạo khi chạy chức năng summary tài liệu
* Người dùng có thể sửa lại tên tài liệu bằng cách tự sửa thủ công hoặc yêu cầu AI tạo tên mới

#### Xóa tài liệu

* Người dùng có thể xóa tài liệu ra khỏi notebook, người dùng không thể truy cập lại tài liệu này sau khi xóa
* Thao tác xóa là không thể khôi phục, cần được xác nhận lại một lần trước khi xóa

#### Chat với tài liệu

* Người dùng sẽ lựa chọn tất cả hoặc một vài tài liệu để chat, ít nhất là 1 tài liệu. Mặc định là chọn tất cả tài liệu. Cần thể hiển số tài liệu mà người dùng đang chọn
* Người dùng sẽ lựa chọn một AI Model để chat với tài liệu, có mặc định trước và mặc định bởi
* Các đoạn hội thoại chat với tài liệu sẽ không được lưu trữ
* Cuộc hội thoại mới hoàn toàn sẽ được tạo ra khi người dùng refresh hoặc bấm tạo mới
* Trong nội dung câu trả lời cần có trích dẫn nguồn từ đoạn nào của tài liệu, bấm vào phải mở ra tài liệu và trỏ vào đúng thông tin được trích dẫn
* Người dùng chỉ được chat dạng text với tài liệu, không hỗ trợ ảnh, video hoặc file
* **Lưu ý quan trọng:** Notebook luôn chỉ được sử dụng nguồn từ tài liệu mà người dùng upload lên để trả lời. Trừ trường hợp người dùng cố ép thông qua các câu prompt của mình

#### Summary tài liệu

* Khi người dùng upload tài liêu lên, hệ thống sẽ tự động summary lại tài liệu để tạo ra một đoạn mô tả
* Đoạn mô tả này sẽ được lưu lại chứ không mất đi như hội thoại
* Nếu tài liệu chưa có title thì sẽ generate luôn title

## Phase 2

#### Save to note

* Vì notebook không lưu trữ hội thoại nên sẽ có tính năng để người dùng lưu lại thành một cái note
  * Nội dung của note là toàn bộ nội dung câu trả lời của AI
  * Title của note sẽ được tạo tự động bởi AI

#### Xem và quản lý note

* Người dùng có thể xem danh sách note mình đã lưu
* Người dùng có thể xem chi tiết note mình đã lưu
* Người dùng có thể xóa note mình đã lưu
* Người dùng có thể convert note thành một tài liệu cho notebook của mình, 1 note chỉ convert thành tài liệu 1 lần (không tính các tài liệu bị xóa) (cái này khác noteboooklm)
* Người dùng có thể xóa nhanh tất cả note
* Người dùng có thể convert tất cả note thành tài liệu, khi thực hiện cần loại các note đã convert trước đó (ko bao gồm các tài liệu đã bị xóa)

## Lưu ý hệ thống

1. Việc phân tích tài liệu và lưu trữ cần được sử dụng 1 AI Model rẻ mà hiệu quả. Model này cần được cấu hình bởi Dora Admin và có thể thay đổi bởi Admin workspace
2. Việc xóa tài liệu là không thể khôi phục, tuy nhiên hệ thống cần soft-delete và lưu trữ 7 ngày để đề phòng sự cố

## Các tính năng sẽ phát triển trong tương lai

1. Cấu hình số tài liệu tối đa cho mỗi notebook trên admin Dora và admin workspace
2. Cấu hình Model mặc định để đọc tài liệu trên admin Dora và admin workspace
3. Bổ sung thêm nhiều loại source khác
   * URL, Youtube,…
   * Google drive, docs,…
   * Notion, Lark,…
4. Bổ sung tính năng Add note
5. Bổ sung tính năng Mindmap
6. Bổ sung tính năng Audio Overview
7. Bổ sung tính năng briefing doc
8. Bổ sung tính năng FAQ
9. Bổ sung tính năng Study Guide
10. Bổ sung tính năng Timeline
11. Đánh tag để phân loại notebook
12. Lưu lại phiên làm việc để lần sau vào không bị mất

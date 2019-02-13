# Techkids guideline cho content viết
## Guideline cho khung

1. Một bài học dược chia làm nhiều phần nhỏ

2. Sau mỗi phần nhỏ cần có bài tập kèm theo, nếu chưa thể cho được bài tập, cần có hình hoặc video minh hoạ diễn giải dễ hiểu

3. Nếu có sử dụng các tài liệu ngoài, cần trích nguồn tham khảo, riêng với mục này, nếu không trích nguồn sẽ bị phạt nặng

4. Với các bài mang tính giới thiệu, việc trả lời câu hỏi *cái gì sẽ được học, và tại sao học viên lại học chúng* quan trọng hơn việc đi vào liệt kê quá chi tiết

5. Với các bài thực hành, cần tổ chức để cuối mỗi bài học, sau khi người học làm xong tất cả các bước, cần đạt được ít nhất **1 thay đổi có ý nghĩa và nhìn thấy được**.

Ví dụ:
Chức năng thực hiện đăng ký người dùng, do chức năng này tương đối phức tạp với đối tượng là người mới học, nên cần được chia nhỏ ra thành nhiều session

Tổ chức tốt:
  1. Session 1: Dựng được khung project, đã có HTML và CSS, khi web chạy lên, mặc dù chưa có UI ngay, nhưng đã có dòng chữ `Register form`, không còn lỗi `undefined` hoặc `null` ở console log
  2. Session 2: Thực hiện giao diện Register UI, khi chạy lên đã có thể nhìn thấy giao diện, , không còn lỗi `undefined` hoặc `null` ở console log
  3. Session 3: Thực hiện đăng ký và gửi email, khi chạy lên đã có thể nhìn thấy giao diện, , không còn lỗi `undefined` hoặc `null` ở console log

Tổ chức không tốt:
  1. Session 1: Dựng được khung project, tuy nhiên khi web chạy lên chưa có khác biệt gì
  2. Session 2: Thực hiện Register UI, khi chạy lên đã có thể nhìn thấy giao diện nhưng vẫn còn thiếu một vài input và không yêu cầu học viên làm gì thêm (không có bài tập để học viên thực hiện nốt phần thiếu)

5. Với các phần thực hành dài (trên 50 dòng), cần đưa ra **roadmap** trước khi trình bày phần thực hiện. Một roadmap của bài thực hành có thể tồn tại ở dạng viết hoặc vẽ, với mục đích trả lời 2 câu hỏi sau:
- Để thực hiện được yêu cầu đề ra, các bước nhỏ hơn cần thực hiện, lần lượt là gì
- Các bước này xâu chuỗi với nhau như thế nào và quan trọng hơn cả, **đóng vai trò gì cho bức tranh lớn**?

Ví dụ về một roadmap cho phần thực hành giao diện đăng ký người dùng:
  1. Dựng khung HTML, CSS (không cần giải thích tại sao vì đã được cover ở C4EJS)
  2. Kiểm tra tính hợp lệ của thông tin người dùng nhập (Input validation là khái niệm thông dụng và hầu hết học viên đều hiểu tại sao cần chỉ cần giải thích input validation là gì chứ **không cần giải thích tại sao**)
  3. Sử dụng firebase **để lưu thông tin đăng ký và gửi email xác nhận tới người dùng**
  4. Refactor code **để ... <tùy thuộc vào vấn đề hiện tại của code là gì>**

6. Với các bài thực hành phải chuyển giữa nhiều file khác nhau, cần dẫn dắt học viên đi theo dòng (flow) của sự kiện hoặc dữ liệu thay vì xây các mảnh rời rạc rồi ghép lại mà không giải thích

Ví dụ cho việc dẫn dắt thực hành giao diện đăng kỳ người dùng

Dẫn dắt tốt:
  1. Thực hiện bắt sự kiện submit (đây là sự kiện bắt đầu cho chuỗi event của feature)
  2. Thực hiện lấy input người dùng từ form ở trong view (đây là dữ liệu đầu tiên có được của feature)
  3. Thực hiện validate input người dùng bằng cách gọi hàm validate input từ controller, hàm validate có thể chưa tồn tại, tuy nhiên vì flow của event và data quan trọng hơn, vẫn cần gọi hàm như bình thường và báo với học viên hàm này chưa tồn tại, sẽ được viết sau
  4. Thực hiện hàm validate input trong controller
  5. Thực hiện báo lại kết quả validate input tới người dùng trong view, HTML, CSS chưa cần phải sẵn sàng
  6. Cập nhật HTML, CSS để hiển thị kết quả validate input
  7. Thực hiện lưu thông tin đăng ký và gửi email xác thực ở controller, ở phần này, kể cả khi firebase chưa được setup, vẫn sử dụng như bình thường rồi thực hiện sau
  8. Thực hiện setup firebase nếu cần
  9. Thực hiện báo lại kết quả đăng ký tới người dùng trong view, HTML, CSS chưa cần phải sẵn sàng
  10. Cập nhật HTML, CSS để hiển thị kết quả đăng ký

Dẫn dắt không tốt:
  1. Thực hiện HTML, CSS để thêm thông báo kết quả validate input
  2. Setup firebase
  3. Thực hiện setup firebase
  4. Thực hiện lưu thông tin đăng ký và gửi email bằng firebase
  4. Thực hiện bắt sự kiện submit và gọi đến chức năng lưu thông tin đăng ký và gửi email
  5. Thực hiện thông báo kết quả tới người dùng
  6. Thực hiện validate input
  7. Thực hiện hiện thị kết quả validate input
  

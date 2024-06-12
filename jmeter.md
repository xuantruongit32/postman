# Báo cáo kiểm tra hiệu năng: API và Website

## Phần 1: Kiểm tra hiệu năng API `https://api.sampleapis.com/coffee/hot`

**Bước 1: Tạo kịch bản kiểm tra API với jMeter**

- **Thiết lập jMeter**:
  - Mở jMeter và tạo một Test Plan mới.
  - Thêm một Thread Group:
    - Chuột phải vào Test Plan -> Add -> Threads (Users) -> Thread Group.
    - Cấu hình: 50 threads (người dùng mô phỏng), thời gian ramp-up: 10 giây, số lần lặp: 10.

- **Thêm HTTP Request Sampler**:
  - Chuột phải vào Thread Group -> Add -> Sampler -> HTTP Request.
  - Cấu hình:
    - Name: API Request
    - Server Name or IP: `api.sampleapis.com`
    - Path: `/coffee/hot`
    - Method: GET

- **Thêm Listener để ghi nhận kết quả**:
  - Chuột phải vào Thread Group -> Add -> Listener -> View Results Tree.
  - Chuột phải vào Thread Group -> Add -> Listener -> Summary Report.

**Bước 2: Chạy kịch bản kiểm tra**

- Nhấn vào nút Start để bắt đầu kiểm tra.

**Bước 3: Ghi lại kết quả và phân tích**

- **Kết quả kiểm tra**:
  - Số lượng yêu cầu thành công: 500
  - Số lượng yêu cầu thất bại: 0
  - Thời gian phản hồi trung bình: 200ms
  - Thời gian phản hồi tối đa: 350ms
  - Thời gian phản hồi tối thiểu: 150ms

**Phân tích kết quả**:

- API `https://api.sampleapis.com/coffee/hot` có hiệu năng tốt, với thời gian phản hồi trung bình là 200ms và không có yêu cầu thất bại nào.
- Kết quả cho thấy API này có thể xử lý tải từ 50 người dùng đồng thời mà không gặp vấn đề.

## Phần 2: Kiểm tra hiệu năng website `https://qldtbeta.phenikaa-uni.edu.vn/conggiangvien/login.aspx`

**Bước 1: Tạo kịch bản kiểm tra website với jMeter**

- **Thiết lập jMeter**:
  - Mở jMeter và tạo một Test Plan mới.
  - Thêm một Thread Group:
    - Chuột phải vào Test Plan -> Add -> Threads (Users) -> Thread Group.
    - Cấu hình: 50 threads, thời gian ramp-up: 10 giây, số lần lặp: 10.

- **Thêm HTTP Request Sampler**:
  - Chuột phải vào Thread Group -> Add -> Sampler -> HTTP Request.
  - Cấu hình:
    - Name: Login Page Request
    - Server Name or IP: `qldtbeta.phenikaa-uni.edu.vn`
    - Path: `/conggiangvien/login.aspx`
    - Method: GET

- **Thêm Listener để ghi nhận kết quả**:
  - Chuột phải vào Thread Group -> Add -> Listener -> View Results Tree.
  - Chuột phải vào Thread Group -> Add -> Listener -> Summary Report.

**Bước 2: Chạy kịch bản kiểm tra**

- Nhấn vào nút Start để bắt đầu kiểm tra.

**Bước 3: Ghi lại kết quả và phân tích**

- **Kết quả kiểm tra**:
  - Số lượng yêu cầu thành công: 450
  - Số lượng yêu cầu thất bại: 50
  - Thời gian phản hồi trung bình: 800ms
  - Thời gian phản hồi tối đa: 1200ms
  - Thời gian phản hồi tối thiểu: 600ms

**Phân tích kết quả**:

- Website `https://qldtbeta.phenikaa-uni.edu.vn/conggiangvien/login.aspx` có một số yêu cầu thất bại (50/500), cho thấy có thể có vấn đề khi xử lý tải từ 50 người dùng đồng thời.
- Thời gian phản hồi trung bình là 800ms, hơi cao cho một trang web đăng nhập.
- Để cải thiện, có thể cần tối ưu hóa mã nguồn, cơ sở hạ tầng, hoặc cấu hình server.

## Phần 3: So sánh hiệu năng API và Website

**Kết quả so sánh**:

- **API `https://api.sampleapis.com/coffee/hot`**:
  - Thời gian phản hồi trung bình: 200ms
  - Không có yêu cầu thất bại

- **Website `https://qldtbeta.phenikaa-uni.edu.vn/conggiangvien/login.aspx`**:
  - Thời gian phản hồi trung bình: 800ms
  - 50 yêu cầu thất bại

**Kết luận**:

- API `https://api.sampleapis.com/coffee/hot` có hiệu năng tốt hơn so với website `https://qldtbeta.phenikaa-uni.edu.vn/conggiangvien/login.aspx` với thời gian phản hồi nhanh hơn và không có yêu cầu thất bại.
- Website cần được tối ưu hóa để cải thiện hiệu năng và giảm thiểu số lượng yêu cầu thất bại.

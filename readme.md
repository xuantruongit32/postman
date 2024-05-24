# Postman_API_Test

## Ngày thực hiện: 24/05/2024

## Tóm tắt

- Tổng số test: 4
- Test thành công: 3
- Test thất bại: 1
- Test bỏ qua: 0
- Chi tiết test

## Test 1: GET User List

### URL: https://jsonplaceholder.typicode.com/users
- **Phương thức:** GET
- **Trạng thái:** Thành công
- **Thời gian phản hồi:** 350 ms
- **Kích thước phản hồi:** 5,432 KB

### Kết quả:
**Thành công:**
- Mã trạng thái là 200
- Tiêu đề Content-Type có mặt
- Thời gian phản hồi dưới 500 ms

**Thất bại:**
- Thân phản hồi không khớp với chuỗi mong muốn

## Test 2: POST Create User

### URL: https://jsonplaceholder.typicode.com/users
- **Phương thức:** POST
- **Trạng thái:** Thành công
- **Thời gian phản hồi:** 410 ms
- **Kích thước phản hồi:** 1,102 KB

### Kết quả:
**Thành công:**
- Yêu cầu POST trả về mã trạng thái 201

## Test 3: GET User Detail

### URL: https://jsonplaceholder.typicode.com/users/1
- **Phương thức:** GET
- **Trạng thái:** Thành công
- **Thời gian phản hồi:** 320 ms
- **Kích thước phản hồi:** 512 KB

### Kết quả:
**Thành công:**
- Mã trạng thái là 200
- Tiêu đề Content-Type là application/json

## Test 4: DELETE User

### URL: https://jsonplaceholder.typicode.com/users/1
- **Phương thức:** DELETE
- **Trạng thái:** Thất bại
- **Thời gian phản hồi:** 480 ms
- **Kích thước phản hồi:** 234 KB

### Kết quả:
**Thất bại:**
- Mã trạng thái không phải là 200

## Kết luận

Ba trong số bốn test đã được thực hiện thành công. Một test còn lại đã thất bại do mã trạng thái không phải là 200.


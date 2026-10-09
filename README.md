# Báo cáo Thực hành Kiểm thử API với Postman

## 1. Mục Tiêu Kiểm Thử
- Sử dụng công cụ Postman để kiểm thử REST API thực tế.
- Kiểm tra khả năng gửi request, nhận response và xử lý các phương thức HTTP phổ biến bao gồm: GET, POST, PUT và DELETE.

## 2. Môi Trường Kiểm Thử
- **Công cụ kiểm thử:** Postman
- **API sử dụng:** ReqRes (`https://reqres.in`)
- **Kiểu API:** REST API
- **Định dạng dữ liệu:** JSON
- **Hệ điều hành:** Windows

## 3. Phương Pháp Kiểm Thử
- Kiểm thử thủ công trên phần mềm Postman.
- Các request được khởi tạo trong Workspace `KiemThuAPI`.
- Sau khi gửi request, tiến hành kiểm tra Status Code, Response Body và đối chiếu kết quả thực tế với kết quả mong đợi.

---

## 4. Kịch Bản Kiểm Thử Lần 1
- **Tên Kịch Bản:** Kiểm thử lấy danh sách người dùng
- **Mục Đích:** Kiểm tra khả năng lấy danh sách người dùng phân trang của API.
- **Phương Thức HTTP:** GET
- **URL:** `https://reqres.in/api/users?page=2`
- **Tham Số:** `page=2`
- **Kết Quả Mong Đợi:** API gửi yêu cầu thành công, trả về danh sách người dùng với Status Code 200 OK.
- **Kết Quả Thực Tế:** API trả về danh sách người dùng trang 2 dưới định dạng JSON kèm Status Code 200 OK.
- **Trạng Thái:** Thành công
- **Hình ảnh thực hành:**
<img width="3837" height="2040" alt="image" src="https://github.com/user-attachments/assets/b84ce267-e257-49b1-9151-eb9ec25b81bc" />

---

## 5. Kịch Bản Kiểm Thử Lần 2
- **Tên Kịch Bản:** Kiểm thử lấy thông tin người dùng không tồn tại
- **Mục Đích:** Kiểm tra khả năng xử lý của API khi yêu cầu một tài nguyên không có trên hệ thống.
- **Phương Thức HTTP:** GET
- **URL:** `https://reqres.in/api/users/23010129`
- **Tham Số:** `id=23010129`
- **Kết Quả Mong Đợi:** API trả về phản hồi không tìm thấy dữ liệu kèm Status Code 404 Not Found.
- **Kết Quả Thực Tế:** API phản hồi chính xác Status Code 404 Not Found và Response Body rỗng `{}`.
- **Trạng Thái:** Thành công
- **Hình ảnh thực hành:**
<img width="3837" height="2037" alt="image" src="https://github.com/user-attachments/assets/7a736f97-21b5-47e0-bcd7-469956338ce6" />

---

## 6. Kịch Bản Kiểm Thử Lần 3
- **Tên Kịch Bản:** Kiểm thử tạo người dùng mới
- **Mục Đích:** Kiểm tra khả năng tiếp nhận và khởi tạo bản ghi mới của API bằng phương thức POST.
- **Phương Thức HTTP:** POST
- **URL:** `https://reqres.in/api/users`
- **Tham Số:** Không có
- **Dữ Liệu Gửi Đi (Body):**
  ```json
  {
      "name": "morpheus",
      "job": "leader"
  }
   ```
- **Kết Quả Mong Đợi:** API tiếp nhận request, tạo mới người dùng thành công và trả về Status Code 201 Created.
- **Kết Quả Thực Tế:** API trả về thông tin vừa tạo kèm theo id tự sinh và thời gian createdAt với Status Code 201 Created.
- **Trạng Thái:** Thành công
- **Hình ảnh thực hành:**
<img width="3837" height="2037" alt="image" src="https://github.com/user-attachments/assets/c57a1c09-8a83-48d4-82e7-751fdcf5bc36" />

---

## 7. Kịch Bản Kiểm Thử Lần 4
- **Tên Kịch Bản:** Kiểm thử cập nhật thông tin người dùng
- **Mục Đích:** Kiểm tra khả năng cập nhật toàn bộ thông tin người dùng bằng phương thức PUT.
- **Phương Thức HTTP:** PUT
- **URL:** `https://reqres.in/api/users/2`
- **Tham Số:** `id=2`
- **Dữ Liệu Gửi Đi (Body):**
  ```json
  {
      "name": "morpheus",
      "job": "zion resident"
  }
   ```

- **Kết Quả Mong Đợi:** API cập nhật dữ liệu thành công và trả về thông tin sau chỉnh sửa với Status Code 200 OK.
- **Kết Quả Thực Tế:** API trả về dữ liệu cập nhật kèm thời gian updatedAt với Status Code 200 OK.
- **Trạng Thái:** Thành công
- **Hình ảnh thực hành:**
<img width="3837" height="2037" alt="image" src="https://github.com/user-attachments/assets/161bdb33-1ede-4c40-a56b-5a535e158dc5" />

---

## 8. Kịch Bản Kiểm Thử Lần 5
- **Tên Kịch Bản:** Kiểm thử xóa người dùng
- **Mục Đích:** Kiểm tra khả năng xử lý yêu cầu xóa tài nguyên bằng phương thức DELETE.
- **Phương Thức HTTP:** DELETE
- **URL:** `https://reqres.in/api/users/2`
- **Tham Số:** `id=2`
- **Kết Quả Mong Đợi:** API xóa thành công người dùng và phản hồi Status Code 204 No Content.
- **Kết Quả Thực Tế:** API xử lý request xóa thành công và trả về Status Code 204 No Content.
- **Trạng Thái:** Thành công
- **Hình ảnh thực hành:**
<img width="3837" height="2035" alt="image" src="https://github.com/user-attachments/assets/674c94c5-ab1d-45de-a51a-a76459f25502" />

---

## 9. Tóm Tắt Kết Quả Kiểm Thử
- Số lượng kịch bản đã kiểm thử: 5
- Số lần thành công: 5
- Số lần thất bại: 0
- Tỉ lệ thành công: 100%

---

## 10. Phát Hiện Lỗi
- ID Lỗi: 404 Not Found (ở Kịch bản TC02)
- Mô Tả Lỗi: API không tìm thấy người dùng với ID 23010129.
- Mức Độ Ảnh Hưởng: Không ảnh hưởng.
- Ghi Chú/Đề Xuất: Đây là trường hợp kiểm thử cố tình truyền dữ liệu không tồn tại để kiểm tra khả năng bắt lỗi của API. API đã xử lý đúng chuẩn RESTful.




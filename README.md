# Báo cáo Thực hành Kiểm thử API với Postman

## 1. Mục tiêu thực hành
- Làm quen với công cụ Postman.
- Thực hiện các phương thức HTTP (GET, POST, PUT, DELETE).
- Viết các test script cơ bản để kiểm chứng kết quả.

## 2. Kết quả thực hiện
### 2.1. Request GET (Lấy thông tin danh sách người dùng)
- **API URL:** `https://reqres.in/api/users?page=2`
- **Mục đích:** Kiểm tra việc gọi API lấy danh sách người dùng.
- **Kết quả Test:** Status code 200 OK.
- **Hình ảnh thực hành:**
*<img width="3837" height="2040" alt="image" src="https://github.com/user-attachments/assets/b84ce267-e257-49b1-9151-eb9ec25b81bc" />*
- **Nhận xét kết quả:** API hoạt động ổn định, trả về đúng dữ liệu danh sách người dùng ở trang 2 dưới định dạng JSON. Dữ liệu trả về đầy đủ các trường thông tin (id, email, first_name, last_name, avatar).

### 2.2. Request POST (Thêm mới dữ liệu)
- **API URL:** `https://reqres.in/api/users`
- **Body gửi đi:** 
  ```json
  {
      "name": "morpheus",
      "job": "leader"
  }
  ```
- **Hình ảnh thực hành:**
*<img width="3837" height="2037" alt="image" src="https://github.com/user-attachments/assets/c57a1c09-8a83-48d4-82e7-751fdcf5bc36" />*

- **Kết quả Test:** Status code 201 Created.
- **Nhận xét kết quả:** API đã tiếp nhận thành công Body Data gửi lên. Trong phần kết quả trả về (Response Body), hệ thống ghi nhận đúng thông tin "name" và "job", đồng thời tự động cấp phát thêm một id mới và thời gian tạo createdAt cho bản ghi.

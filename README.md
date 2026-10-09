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
*<img width="1024" height="576" alt="3f404cad-b7d0-4159-9ec6-12ed2bf1d41b" src="https://github.com/user-attachments/assets/2bf0cd96-27aa-4888-a1a7-701e6b9a0c2a" />*
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
*<img width="1024" height="575" alt="35d1266b-5d5e-4fda-8e5d-6a0073ee02d9" src="https://github.com/user-attachments/assets/19c29114-5c32-47ad-88d4-31029a9b6951" />*
- **Kết quả Test:** Status code 201 Created.
- **Nhận xét kết quả:** API đã tiếp nhận thành công Body Data gửi lên. Trong phần kết quả trả về (Response Body), hệ thống ghi nhận đúng thông tin "name" và "job", đồng thời tự động cấp phát thêm một id mới và thời gian tạo createdAt cho bản ghi.

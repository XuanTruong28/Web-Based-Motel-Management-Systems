# **Hệ Thống Quản Lý Nhà Trọ \- MotelMS**

Hệ thống quản lý nhà trọ thông minh hỗ trợ chủ trọ quản lý phòng, khách thuê, hóa đơn điện nước và hợp đồng một cách tự động và hiện đại.

## **Yêu Cầu Cài Đặt**

Trước khi bắt đầu, hãy đảm bảo máy tính của bạn đã cài đặt:

* [Node.js](https://nodejs.org/) (Phiên bản mới nhất)  
* [SQL Server](https://www.microsoft.com/en-us/sql-server/sql-server-downloads) (Express hoặc bản đầy đủ)  
* [VS Code](https://code.visualstudio.com/) kèm Extension **Live Server**.

## ** Hướng Dẫn Thiết Lập**

### **1\. Cấu hình Cơ sở dữ liệu (SQL Server)**

1. Mở **SQL Server Management Studio (SSMS)** và kết nối vào Server của bạn.  
2. **Tạo Login mới:**  
   * Vào mục `Security` \-\> Chuột phải `Logins` \-\> `New Login`.  
   * Tên tài khoản: `motel_app`.  
   * Mật khẩu: `12345`.  
   * Tại mục `Status`, đảm bảo đã chọn **Enabled** cho *Login* và **Grant** cho *Permission to connect*.  
3. **Khởi tạo Database:**  
   * Tạo một Database mới tên là `quanlytro`.  
   * Mở file SQL đính kèm trong thư mục `database` của dự án.  
   * Copy toàn bộ nội dung code SQL, dán vào **New Query** và nhấn **Execute**.  
4. **Cấp quyền:**  
   * Liên kết tài khoản `motel_app` với database `quanlytro`.  
   * Tại mục `User Mapping`, chọn database `quanlytro` và tích chọn quyền `db_owner`.

### **2\. Cài đặt và Chạy Backend**

1. Mở thư mục dự án bằng **Visual Studio Code**.  
2. Mở Terminal tại thư mục `backend` (Chuột phải vào folder `backend` \-\> `Open in Integrated Terminal`).

3. **Cài đặt thư viện:** Nhập lệnh sau để tải các gói phụ thuộc:  
   Bash  
   npm install

4. **Khởi chạy Server:** Nhập lệnh để chạy backend bằng nodemon:  
   Bash  
   nodemon src/server.js  
   *Lưu ý: Nếu chưa cài nodemon toàn cục, bạn có thể dùng `npx nodemon src/server.js`.*  
5. Khi thấy thông báo **"Kết nối SQL Server thành công"**, backend đã sẵn sàng.

### **3\. Khởi chạy Giao diện (Frontend)**

1. Tìm đến file `index.html` (thường nằm trong thư mục gốc hoặc folder `frontend`).  
2. Chuột phải vào file `index.html` và chọn **Open with Live Server**.  
3. Trình duyệt sẽ tự động mở trang web. Bây giờ bạn có thể bắt đầu sử dụng hệ thống.

## **Cấu Trúc Thư Mục Chính**

* `/frontend`: Chứa toàn bộ giao diện HTML, CSS và logic JavaScript xử lý phía người dùng.  
* `/backend`: Chứa API Node.js, cấu hình kết nối SQL Server và xử lý nghiệp vụ.  
* `/database`: Chứa file script `.sql` để khởi tạo cấu trúc bảng và dữ liệu mẫu.

## **Lưu Ý**

* Đảm bảo SQL Server đang chạy và cho phép kết nối bằng tài khoản SQL (SQL Server Authentication).  
* Nếu thay đổi cổng (port) của Backend, hãy cập nhật lại biến `API_URL` trong các file JavaScript ở Frontend.


# Quản Lý Người Dùng Phân Quyền Theo Vai Trò

## Thông Tin Sinh Viên

| | |
|---|---|
| **Họ và tên** | Nguyễn Gia Hậu |
| **MSSV** | 2224802010349 |
| **Môn học** | Phát triển ứng dụng di động đa nền tảng |
| **Trường** | Đại học Thủ Dầu Một |

---

## Video Demo

[![Video Demo](https://img.youtube.com/vi/NXaTpteZ-1k/maxresdefault.jpg)](https://youtu.be/NXaTpteZ-1k)

🎬 **Xem video demo:** [https://youtu.be/NXaTpteZ-1k](https://youtu.be/NXaTpteZ-1k)

---

## Mô Tả Dự Án

Ứng dụng quản lý người dùng phân quyền theo vai trò (Role-Based User Management), gồm 2 phần:

- **Backend:** ASP.NET Core Web API — xác thực JWT, phân quyền động (Dynamic Policy Authorization)
- **Frontend:** Flutter — ứng dụng di động đa nền tảng kết nối API

---

## Chức Năng Chính

### 🔐 Xác thực
- Đăng ký tài khoản
- Đăng nhập với JWT Token
- Phân quyền tự động theo vai trò (Admin / User)

### 👑 Admin
- Xem danh sách người dùng
- Thêm / Xóa người dùng
- Xem danh sách vai trò
- Thêm / Xóa vai trò
- Đổi vai trò cho người dùng
- Sửa thông tin cá nhân
- Đổi mật khẩu

### 👤 User
- Xem thông tin cá nhân
- Sửa thông tin cá nhân
- Đổi mật khẩu
- Xóa tài khoản

---

## Công Nghệ Sử Dụng

| Thành phần | Công nghệ |
|---|---|
| Frontend | Flutter (Dart) |
| Backend | ASP.NET Core Web API |
| Database | SQL Server |
| ORM | Entity Framework Core |
| Xác thực | JWT (JSON Web Token) |
| Quản lý User | ASP.NET Identity |
| Phân quyền | Dynamic Policy Authorization |

---

## Cấu Trúc Dự Án

```
user-management/
├── Role-Based-User-Management-API-Using-Dynamic-Policies-In-Asp.Net-Core-Web-API/
│   ├── Controllers/
│   │   ├── AccountController.cs      # Đăng ký, đăng nhập
│   │   ├── AdminController.cs        # CRUD users, roles (chỉ Admin)
│   │   └── UserController.cs         # Quản lý profile (User)
│   ├── Authorization/
│   │   ├── DynamicPolicyProvider.cs   # Phân quyền động
│   │   └── DynamicRoleHandler.cs     # Xử lý kiểm tra role
│   ├── Data/
│   │   └── AppDbContext.cs            # Database context, seed data
│   ├── Models/                        # Data models
│   └── Program.cs                     # Cấu hình ứng dụng
│
└── RoleBasedUserManagementFlutterAppWithAspNetCoreWebApi/
    └── lib/
        ├── accounts/                  # Màn hình Login, Register
        ├── admin_area/                # 9 màn hình quản trị Admin
        ├── users_area/                # 3 màn hình cho User
        ├── models/                    # Data models (6 files)
        ├── services/                  # Role check, fetch email
        ├── constants/                 # API endpoints, colors, token
        ├── shared/                    # Widget dùng chung
        └── main.dart                  # Entry point
```

---

## Hướng Dẫn Chạy

### Backend (ASP.NET Core)

```bash
cd Role-Based-User-Management-API-Using-Dynamic-Policies-In-Asp.Net-Core-Web-API
dotnet run
```

> API chạy tại `http://localhost:5129`

### Frontend (Flutter)

```bash
cd RoleBasedUserManagementFlutterAppWithAspNetCoreWebApi
flutter pub get
flutter run
```

### Tài Khoản Test (Admin)

| Email | Mật khẩu |
|---|---|
| `freetrained@freetrained.com` | `freetrained123` |

---

## Điểm Kỹ Thuật Nổi Bật

1. **JWT Authentication** — Token chứa role claim, được Flutter decode để phân quyền phía client
2. **Dynamic Policy Authorization** — Tự động tạo policy dựa trên tên role, không cần hardcode
3. **Role-based Navigation** — Giao diện hiển thị khác nhau tùy vai trò người dùng

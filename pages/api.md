---
layout: section
---

# API

---

## 1. Luồng Tài Khoản Cá Nhân

| Method | Endpoint                     | Mô tả                         | Quyền truy cập |
| ------ | ---------------------------- | ----------------------------- | -------------- |
| POST   | /api/v1/auth/register        | Đăng ký tài khoản cá nhân mới | Public         |
| POST   | /api/v1/auth/login           | Đăng nhập vào hệ thống        | Public         |
| POST   | /api/v1/profiles             | Tạo profile cá nhân           | User           |
| PUT    | /api/v1/profiles/{profileId} | Cập nhật profile cá nhân      | User           |
| GET    | /api/v1/profiles/{profileId} | Lấy thông tin profile         | User           |
| GET    | /api/v1/jobs                 | Tìm kiếm việc làm             | User           |
| POST   | /api/v1/jobs/{jobId}/apply   | Ứng tuyển vào một công việc   | User           |

---

## 2. Luồng Nâng Cấp Business

| Method | Endpoint                      | Mô tả                           | Quyền truy cập   |
| ------ | ----------------------------- | ------------------------------- | ---------------- |
| POST   | /api/v1/accounts/upgrade      | Nâng cấp lên tài khoản business | User             |
| POST   | /api/v1/companies             | Tạo profile công ty             | Business         |
| PUT    | /api/v1/companies/{companyId} | Cập nhật thông tin công ty      | Business - Owner |
| GET    | /api/v1/companies/{companyId} | Lấy thông tin công ty           | Business         |

---

## 3. Luồng Quản Lý Team

| Method | Endpoint                                            | Mô tả                         | Quyền truy cập                   |
| ------ | --------------------------------------------------- | ----------------------------- | -------------------------------- |
| POST   | /api/v1/companies/{companyId}/invitations           | Mời thành viên vào công ty    | Admin                            |
| POST   | /api/v1/companies/invitations/{invitationId}/accept | Chấp nhận lời mời vào công ty | User                             |
| PUT    | /api/v1/companies/{companyId}/members/{memberId}    | Cập nhật quyền của thành viên | Admin                            |
| DELETE | /api/v1/companies/{companyId}/members/{memberId}    | Xóa thành viên khỏi công ty   | Admin                            |
| POST   | /api/v1/companies/{companyId}/jobs                  | Đăng tin tuyển dụng           | Admin, Recruiter                 |
| GET    | /api/v1/companies/{companyId}/applications          | Xem danh sách ứng viên        | Admin, Recruiter, Hiring Manager |
| POST   | /api/v1/applications/{applicationId}/interviews     | Tạo lịch phỏng vấn            | Admin, Recruiter                 |
| PUT    | /api/v1/interviews/{interviewId}/feedback           | Cập nhật feedback phỏng vấn   | Admin, Hiring Manager            |

_Lưu ý:_

- Tất cả API (trừ register/login) đều yêu cầu JWT token trong header
- Response format chuẩn theo dạng: `{ success, data, error? }`

---

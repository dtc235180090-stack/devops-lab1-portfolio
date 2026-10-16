# Lab 1 - DevOps Workflow End-to-End

- **Họ tên:** Nguyễn Quang Huy
- **MSSV:** DTC235180090
- **Repo:** https://github.com/dtc235180090-stack/devops-lab1-portfolio
- **Website:** https://dtc235180090-stack.github.io/devops-lab1-portfolio/

## 1. Bảng so sánh DevOps và Truyền thống

| Tiêu chí | Cách THỦ CÔNG (Traditional) | Cách DEVOPS (CI/CD Pipeline) |
|---|---|---|
| Làm sao để deploy? | Tải file, upload lên server qua FTP/SSH, cấu hình lại | Push code lên GitHub, pipeline tự chạy |
| Mất bao lâu? | 15-30 phút | Khoảng 10 giây |
| Ai làm deploy? | Con người | GitHub Actions |
| Có bị sai sót không? | Dễ sai (quên file, sai cấu hình) | Ít, vì quy trình lặp lại nhất quán |
| Rollback nếu lỗi? | Khôi phục file cũ bằng tay | `git revert` + push, tự deploy lại |
| Biết thành công thế nào? | Mở web kiểm tra bằng tay | Tab Actions báo thành công hoặc thất bại |

## 2. Sơ đồ workflow

```text
Plan -> Code (sửa index.html) -> git commit/push -> GitHub Actions
(Checkout -> Validate -> Deploy) -> nhánh gh-pages -> Live (github.io)
-> Monitor (tab Actions + website)
```

## 3. Trả lời câu hỏi

1. **DevOps tự động hóa những bước nào?** Build, test (validate) và deploy, tất cả do GitHub Actions làm.
2. **Deploy sai thì quay lại bản cũ thế nào?** Dùng `git revert <commit>` rồi push, pipeline tự deploy bản cũ.
3. **Tiết kiệm bao nhiêu thời gian?** Thủ công mất 15-30 phút, DevOps chỉ cần `git push` (khoảng 10 giây).

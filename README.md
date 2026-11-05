# HCM_KS26_CNTT2_IT108_Session19_Ex01
## 1. Vì sao file `.env` vẫn bị đẩy lên GitHub?

Nguyên nhân là do file `.gitignore` chỉ có `node_modules/` và `dist/`, chưa khai báo `.env`.

Vì vậy, khi chạy `git add .`, Git vẫn có thể theo dõi và đưa file `.env` chứa API Key lên GitHub.

Nếu `.env` đã được Git theo dõi trước đó thì thêm vào `.gitignore` cũng không tự động bỏ theo dõi file.

## 2. Nội dung `.gitignore` sau khi sửa

```gitignore
node_modules/
dist/
.env
.env.*
!.env.example
```

Cấu hình này giúp Git bỏ qua file `.env` chứa thông tin nhạy cảm nhưng vẫn cho phép đẩy `.env.example` lên GitHub.

## 3. Cách xử lý trên VS Code

Mở Terminal trong VS Code và chạy:

```bash
git rm --cached .env
git status
```

- `git rm --cached .env`: Bỏ theo dõi file `.env` nhưng vẫn giữ file trên máy.
- `git status`: Kiểm tra những file đang được Git theo dõi hoặc chuẩn bị commit.

Sau đó lưu thay đổi và push lên GitHub. Nếu API Key thật từng bị đẩy lên GitHub thì phải thu hồi khóa cũ và tạo khóa mới ngay.

**Lưu ý:** `.gitignore` không mã hóa hay ẩn file khỏi máy tính, mà chỉ yêu cầu Git bỏ qua các file chưa được theo dõi.


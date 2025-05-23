# dvc-ai-data-versioning

## 📦 Mô tả

Dự án demo quản lý phiên bản dữ liệu ảnh bằng **DVC** và lưu trữ dữ liệu trên **Google Drive** thông qua Service Account.

## 🚀 Hướng dẫn sử dụng

### 1. Clone repository

```bash
git clone https://github.com/vanhai1231/dvc-ai-data-versioning.git
cd dvc-ai-data-versioning
```

### 2. Cài đặt DVC kèm Google Drive plugin

Trong môi trường Python mới (venv hoặc conda), chạy:

```bash
pip install "dvc[gdrive]" --extra-index-url https://pypi.dvc.org/simple
```

### 3. Chuẩn bị Service Account

1. Tải file JSON key của Service Account (Ví dụ `service-account.json`).
2. Đặt file JSON vào thư mục dự án hoặc bất kỳ đâu an toàn.

### 4. Cấu hình DVC remote

* Để trỏ tới Google Drive folder và dùng Service Account:

```bash
# Chỉ chạy lần đầu để thiết lập local config
# Thay đường dẫn file JSON phù hợp

dvc remote modify --local myremote gdrive_service_account_json_file_path /path/to/service-account.json
```

### 5. Tải dữ liệu về

```bash
dvc pull
```

* Lệnh này sẽ tự động tải dữ liệu ảnh từ Google Drive về thư mục `data/images/`.

### 6. Xem dữ liệu

* Dữ liệu ảnh đã sẵn sàng trong `data/images/`. Bạn có thể sử dụng cho các bước xử lý, huấn luyện mô hình.

* Bài tập: Buổi 3 – Quản lý dữ liệu AI với DVC

---

*Lưu ý:* file `data/images/` không được đẩy lên GitHub nhờ cơ chế DVC và `.gitignore`. Chỉ metadata (.dvc/\*.dvc) được version trong repo.

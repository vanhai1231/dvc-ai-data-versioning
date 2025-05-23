# 📦 AI Dataset Versioning with DVC + Google Drive

## ✅ Mục tiêu
Quản lý phiên bản dữ liệu ảnh (mèo/chó) bằng DVC và lưu trữ trên Google Drive (qua rclone).

## 📁 Cấu trúc
- `data/images/`: ảnh mẫu (được theo dõi bằng DVC)
- `data/images.dvc`: metadata của DVC
- `.dvc/config`: cấu hình remote `rclone`
- `README.md`: hướng dẫn

## 🚀 Cách sử dụng

```bash
# 1. Cài DVC + rclone
pip install "dvc[rclone]"

# 2. Clone repo
git clone https://github.com/vanhai1231/dvc-ai-data-versioning.git
cd dvc-demo

# 3. Tải dữ liệu
dvc pull

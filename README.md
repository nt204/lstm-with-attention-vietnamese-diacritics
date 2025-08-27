Khôi phục dấu tiếng Việt bằng LSTM + Luong Attention
📌 Giới thiệu
Dự án xây dựng mô hình Seq2Seq sử dụng LSTM + Luong Attention để khôi phục dấu tiếng Việt.
Input: câu không dấu → Output: câu có dấu.
Ứng dụng: gõ văn bản nhanh không dấu, OCR, chatbot, xử lý ngôn ngữ tự nhiên.
🏗️ Kiến trúc
Encoder: LSTM (có thể bidirectional).
Decoder: LSTM + cơ chế Luong Attention.
Loss: CrossEntropy.
Cấp token: dùng cấp ký tự (character-level).
📂 Dữ liệu
Tập dữ liệu gồm cặp câu:
Không dấu
Có dấu
Tiền xử lý:
Chuẩn hóa Unicode
Thêm token <sos>, <eos>, <pad>
⚙️ Cài đặt
git clone <repo-url>
cd viet-diacritic-restoration
pip install -r requirements.txt
requirements.txt:
torch
numpy
tqdm
scikit-learn
🚀 Huấn luyện
python train.py --train data/train.txt --valid data/valid.txt --epochs 20 --batch_size 64
🔎 Dự đoán
python infer.py --checkpoint checkpoints/best.pth --input "Toi yeu tieng Viet"
👉 Kết quả: Tôi yêu tiếng Việt
📊 Đánh giá
Accuracy ký tự (char-level)
CER / WER
📁 Cấu trúc thư mục
project/
├─ data/
├─ src/ (model, train, infer)
├─ checkpoints/
└─ README.md


🇻🇳 Vietnamese Diacritic Restoration with LSTM + Attention
📌 Giới thiệu
Dự án xây dựng mô hình Seq2Seq với LSTM Encoder–Decoder kết hợp Luong Attention để khôi phục dấu tiếng Việt.
Input: Câu tiếng Việt không dấu
Output: Câu tiếng Việt có dấu
Ứng dụng:
Gõ văn bản nhanh không dấu → tự động thêm dấu
OCR (nhận dạng ký tự)
Chatbot, xử lý ngôn ngữ tự nhiên
🏗 Cấu trúc mô hình
Encoder: BiLSTM (2 chiều)
Decoder: LSTM
Attention: Luong Attention
Loss: CrossEntropy
Mức token: cấp ký tự (character-level)
Input:  "Toi yeu tieng Viet"
Output: "Tôi yêu tiếng Việt"
🗂 Dataset
Bao gồm cặp câu (không dấu, có dấu)
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
🔎 Sử dụng (Inference)
python infer.py --checkpoint checkpoints/best.pth --input "Toi yeu tieng Viet"
👉 Kết quả:
Tôi yêu tiếng Việt
📊 Kết quả huấn luyện
📌 Biểu đồ training/validation loss được vẽ bằng visualize.py.
🔹 Char-level Accuracy (Validation)
Model	Accuracy
LSTM + LuongAttn	0.9456
🔹 Error Rate (Test set)
Metric	Score
CER	0.054
WER	0.112
📁 Cấu trúc thư mục
viet-diacritic-restoration/
├─ data/               # dữ liệu train/valid/test
├─ src/                # code model, train, infer
├─ checkpoints/        # lưu model
├─ result/             # log, kết quả
├─ visualize/          # script vẽ loss/accuracy
└─ README.md
📜 License
MIT License

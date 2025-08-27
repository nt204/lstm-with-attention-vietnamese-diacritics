# 🇻🇳 Vietnamese Diacritic Restoration with LSTM + Attention  

## 📌 Giới thiệu  
Dự án xây dựng mô hình **Seq2Seq với LSTM Encoder–Decoder kết hợp Luong Attention** để khôi phục dấu tiếng Việt.  

- **Input**: Câu tiếng Việt không dấu  
- **Output**: Câu tiếng Việt có dấu  

**Ứng dụng:**  
- Gõ văn bản nhanh không dấu → tự động thêm dấu  
- OCR (nhận dạng ký tự)  
- Chatbot, xử lý ngôn ngữ tự nhiên  

---

## 🏗 Kiến trúc mô hình  
- **Encoder**: BiLSTM (2 chiều)  
- **Decoder**: LSTM  
- **Attention**: Luong Attention  
- **Loss**: CrossEntropy  
- **Mức token**: Word-level  

📌 Ví dụ:  
```
Input : "Toi yeu tieng Viet"
Output: "Tôi yêu tiếng Việt"
```

---

## 🗂 Dataset  
- Bao gồm các cặp câu **(không dấu → có dấu)**  
- Tiền xử lý:  
  - Chuẩn hóa Unicode  
  - Thêm token `<sos>`, `<eos>`, `<pad>`  

---

## ⚙️ Cài đặt  
```
git clone <repo-url>
cd lstm-with-attention-vietnamese-diacritics
```
---

👉 **Kết quả**:  
```
Tôi yêu tiếng Việt
```

---

## 📊 Kết quả huấn luyện  
📌 Biểu đồ loss/accuracy được tạo bằng `visualize.py`. 
<img width="562" height="387" alt="image" src="https://github.com/user-attachments/assets/4b46a303-25e9-4a0a-9f84-36988e003f58" />
<img width="514" height="366" alt="image" src="https://github.com/user-attachments/assets/8d3ecad6-da4a-4023-9fd5-a411ac81579b" />



### 🔹 Accuracy (Test)  
| Model               | Accuracy |
|----------------------|----------|
| **LSTM + Attention** | 0.9144   |

### 🔹 BLEU (Test)  
| BLEU               |  |
|----------------------|----------|
| **BLEU-4** | 75.61   |
| **BLEU-1** | 86.19   |
| **BLEU-2** | 82.38   |

---

## 📁 Cấu trúc thư mục  
```
viet-diacritic-restoration/
├─ data/               # dữ liệu train/valid/test
├─ src/                # code model, train, infer
├─ checkpoints/        # lưu model đã huấn luyện
├─ result/             # log, output
├─ visualize/          # script vẽ loss/accuracy
└─ README.md
```

---

## 📜 License  
MIT License

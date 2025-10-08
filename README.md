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
- **Encoder**: LSTM (2 chiều)  
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
### 🔹 Training & Validation Loss  
<p align="center">
  <img width="562" height="387" alt="Training Loss" src="https://github.com/user-attachments/assets/4b46a303-25e9-4a0a-9f84-36988e003f58" />
</p>

### 🔹 Training & Validation Accuracy  
<p align="center">
  <img width="514" height="366" alt="Validation Accuracy" src="https://github.com/user-attachments/assets/8d3ecad6-da4a-4023-9fd5-a411ac81579b" />
</p>



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

## 📜 License  
MIT License

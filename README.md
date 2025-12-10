# Capuchinbird Call Detection Using Machine Learning

This project builds an automated system to detect and count Capuchinbird calls from forest audio recordings using deep learning models such as CNN, CNN+LSTM, and CNN+GRU.  
The pipeline converts audio into spectrograms, trains multiple architectures, selects the best model, and analyzes full-length recordings using a sliding-window detector.

---

## 📁 Dataset Location

All datasets used in this project are stored in Google Drive.

### **Google Drive Dataset Folder**
👉 **https://drive.google.com/drive/folders/1zEhmcI6DtQccI7HW8ZZI-ENQ1VtqHh9h?usp=sharing**

Inside the folder, there are three subdirectories:

1. **Capuchinbird_Clips**  
   - Contains positive audio samples of Capuchinbird calls  
   - Used for training the classifier

2. **Non_Capuchinbird_Clips**  
   - Contains forest background noise, insects, wind, and other birds  
   - Used as negative samples

3. **Forest Recordings**  
   - Full-length MP3/WAV recordings for call detection  
   - Used for evaluating the end-to-end detection pipeline

Make sure the Drive directory structure matches the `CONFIG['data_base']` path in the code.

---


---

## 🚀 How the System Works

1. Audio is loaded at **16 kHz** and standardized to **3-second clips**.  
2. Spectrograms are generated using STFT (frame length 320, hop 32).  
3. Three models are trained and compared:
   - CNN  
   - CNN + LSTM  
   - CNN + GRU  
4. Metrics such as accuracy, precision, recall, F1, and AUC are computed.  
5. The best model is selected based on **highest AUC**.  
6. Full forest recordings are processed using a **sliding-window detector**.  
7. Predictions are thresholded and grouped to estimate the **number of Capuchinbird calls**.

---


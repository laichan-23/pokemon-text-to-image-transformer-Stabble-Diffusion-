# pokemon-text-to-image-transformer-Stabble-Diffusion-

# Pokemon Text-to-Image Generation using Transformer

Proyek ini merupakan implementasi praktikum Deep Learning Lanjut untuk membangun model generatif **Text-to-Image** menggunakan arsitektur **Transformer** (inspirasi dari komponen Stable Diffusion). Model ini dilatih menggunakan dataset teks-gambar dari Hugging Face (Pokemon BLIP captions).

## 🚀 Fitur Utama
- **Multimodal Learning**: Mengintegrasikan data teks (prompt) dengan fitur visual gambar.
- **Custom Transformer**: Membangun arsitektur Transformer Decoder-only untuk memprediksi token visual.
- **Autoregressive Sampling**: Menghasilkan token visual baru berdasarkan urutan teks yang diberikan.

## 🛠️ Arsitektur Model
Model ini menggunakan mekanisme **Cross-Attention** yang memungkinkan informasi dari prompt teks membimbing proses pembentukan gambar.
1. **Text Encoder**: Mengubah teks prompt menjadi vektor angka (embedding).
2. **Transformer Model**: Memproses hubungan antara token teks dan token visual.
3. **Image Decoder**: Tahap simulasi untuk mengubah hasil prediksi model kembali menjadi representasi visual.

## 📊 Detail Pelatihan
- **Dataset**: `reach-vb/pokemon-blip-captions` (Hugging Face).
- **Environment**: Google Colab (GPU T4).
- **Hyperparameters**:
  - Epochs: 500
  - Batch Size: 16
  - Sequence Length: 20 (Text), 256 (Visual)
  - Optimizer: Adam (Learning Rate 1e-4)
  - Vocabulary Size: 359 tokens

## 🖼️ Hasil (Inference)
Contoh pengujian dengan prompt: `"a pink cute pokemon"`

| Input Prompt | Output Image |
| :--- | :--- |
| "a pink cute pokemon" |<img width="328" height="350" alt="image" src="https://github.com/user-attachments/assets/454c1ea6-b232-448d-ac6e-1dca57ec2491" />
 |

### 🔍 Interpretasi Hasil
Hasil gambar yang masih berupa **noise/abstrak** setelah 500 epoch adalah hal yang **normal** dalam pelatihan model generatif dari nol (*from scratch*). Hal ini dikarenakan:
1. **Titik Konvergensi**: Model generatif seperti Transformer memerlukan ribuan bahkan jutaan iterasi/epoch untuk mulai membentuk pola objek yang jelas.
2. **Kompleksitas Data**: Memetakan ruang teks ke ruang visual memerlukan kapasitas model yang sangat besar dan waktu pelatihan yang jauh lebih lama.
3. **Simulasi Decoder**: Pada tahap praktikum ini, fungsi decoder masih menggunakan simulasi untuk memverifikasi bahwa seluruh *pipeline* kode berjalan tanpa error (End-to-End).

## 📂 Cara Menjalankan
1. Buka file `.ipynb` di Google Colab.
2. Pastikan runtime menggunakan **GPU**.
3. Jalankan semua sel secara berurutan.

---
**Dibuat oleh:** Laelatul Badriyah 
**Mata Kuliah:** Deep Learning Lanjut - STMIK IKMI Cirebon

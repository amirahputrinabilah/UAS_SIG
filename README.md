# Prediksi Kerawanan Banjir Lampung

Proyek ini melakukan analisis dan pemodelan prediksi kerawanan banjir di wilayah Kota Lampung menggunakan pendekatan Machine Learning dan data geospasial.

## Deskripsi

Model ini dikembangkan untuk memetakan area dengan risiko banjir tinggi dengan mempertimbangkan faktor-faktor seperti:
- Ketinggian wilayah
- Kemiringan lereng
- Curah hujan tahunan
- Penggunaan lahan (misal: pemukiman, sawah, tambak)
- Riwayat kejadian banjir

## Data yang Digunakan

Proyek ini menggunakan beberapa set data:

### Data Fisik & Geografis
`Lampung_non_spasial.csv` - Koordinat lokasi, ketinggian (meter), dan kemiringan (derajat).

### Data Penggunaan Lahan
`Lampung_penggunaan_lahan.csv` - Klasifikasi tutupan lahan (Pemukiman Padat, Sawah, dll.)

### Data Iklim
`Lampung_curah_hujan.csv` - Rata-rata curah hujan tahunan per lokasi (dalam mm).

### Data Kejadian Banjir
`Lampung_riwayat_banjir.csv` - Koordinat lokasi yang pernah terdampak banjir.

---

## Hasil dan Evaluasi Model

Model prediksi yang dibangun menggunakan algoritma **Random Forest Classifier** menunjukkan performa yang sangat baik, dengan akurasi keseluruhan mencapai **96%**. Berikut adalah ringkasan metrik klasifikasi:
```text
               Precision    Recall     F1-Score    Support
 Tidak Rawan     0.97        0.99        0.98         160
 Rawan           0.95        0.88        0.91          40
 ----------------------------------------------------------
 Accuracy                                0.96         200
```

### Interpretasi

Model ini sangat efektif dalam mengenali lokasi yang aman dari banjir (**recall 99%**) dan cukup handal dalam mendeteksi area dengan potensi banjir (**recall 88%**). Nilai **F1-score** yang tinggi menunjukkan keseimbangan yang baik antara presisi dan recall, menjadikan model ini andal untuk digunakan pada data geospasial wilayah Lampung.

---

## Faktor-Faktor yang Paling Berpengaruh

Berdasarkan hasil analisis *feature importance*, beberapa variabel yang paling berpengaruh dalam proses prediksi antara lain:

- **Tinggi wilayah** (`ketinggian_m`)
- **Curah hujan tahunan rata-rata** (`rata_curah_hujan_mm`)
- **Penggunaan lahan: Pemukiman Padat** (`lahan_Pemukiman Padat`)
- **Kemiringan lereng** (`kemiringan_derajat`)

---

## Output Proyek

Proyek ini menghasilkan dua output utama:

1. **Model prediksi banjir** yang dilatih menggunakan algoritma Random Forest.
2. **Peta interaktif** dalam format HTML (`peta_prediksi_banjir_lampung.html`) yang menunjukkan distribusi tingkat kerawanan banjir di Kota Lampung.

---

## Langkah Penggunaan

Proyek ini dibangun menggunakan **Google Colab Notebook**. Untuk menjalankan ulang analisis dan prediksi:

1. Buka file `Prediksi_Banjir_Lampung.ipynb` di Google Colab.
2. Unduh dan unggah **5 file dataset** ke notebook:
   - `Lampung_non_spasial.csv`
   - `Lampung_penggunaan_lahan.csv`
   - `Lampung_curah_hujan.csv`
   - `Lampung_riwayat_banjir.csv`
   - `Lampung_label_prediksi.csv`
3. Jalankan setiap sel notebook secara berurutan:
   - Preprocessing
   - Training dan evaluasi model
   - Pembuatan visualisasi peta
4. Setelah proses selesai, file **`peta_prediksi_banjir_lampung.html`** akan otomatis terunduh ke perangkat Anda.

---


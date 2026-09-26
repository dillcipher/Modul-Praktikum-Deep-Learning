# Pengumpulan Praktikum Deep Learning

Kelas: RC  
NIM: 123450048

## Modul 1 — Fondasi Jaringan Saraf, FNN, Aktivasi, dan Loss

- `modul-01/M01_123450048.ipynb`: notebook final yang sudah dijalankan ulang.
- `modul-01/M01_123450048.pdf`: PDF notebook final.
- `modul-01/M01_123450048_metrics.csv`: enam run eksperimen sesuai template modul.

## Ringkasan hasil Modul 1

- Dataset: `make_moons`, 600 sampel, split train/validation/test.
- Eksperimen: kombinasi `relu`, `tanh`, `sigmoid` dengan hidden size 4 dan 16.
- Model final: `tanh_h16`, dipilih dari validation loss terendah (`0.2056`).
- Test loss: `0.3277`.
- Test accuracy: `0.8583`.

Test set hanya digunakan setelah model final dipilih dari validation set.

## Modul 2 — Backpropagation dan Automatic Differentiation

Pengumpulan Modul 2 Deep Learning: Backpropagation dan Automatic Differentiation.

- `modul-02/M02_123450048.ipynb`: notebook final yang sudah dijalankan ulang.
- `modul-02/M02_123450048.pdf`: PDF notebook final.
- `modul-02/M02_123450048_metrics.csv`: tabel gradient checking sembilan komponen.
- `modul-02/M02_123450048_metrics_loop.csv`: metrik diagnosis training loop bertahap.

Gradient checking menghasilkan relative error maksimum sekitar `1.12e-10`. Training XOR versi benar menghasilkan loss akhir `0.0813` dan seluruh empat prediksi tepat.

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

## Modul 3 — Optimizer dan Strategi Pelatihan

- `modul-03/M03_123450048.ipynb`: notebook final yang sudah dijalankan ulang.
- `modul-03/M03_123450048.pdf`: PDF notebook final.
- `modul-03/M03_123450048_metrics.csv`: 18 run (3 baseline learning rate, 9 run optimizer × learning rate, 6 run scheduler dan batch size).
- `modul-03/M03_123450048_perbandingan.png`: grafik validation loss dan accuracy tiga optimizer pemenang.

## Ringkasan hasil Modul 3

- Dataset: Fashion-MNIST, subset terstratifikasi 12.000 latih / 3.000 validasi, model MLP 784 → 128 → 10, batch 128, 5 epoch.
- Pemenang tiap optimizer (validation loss): SGD+momentum `lr=0.05` (`0.3988`), Adam `lr=0.001` (`0.4042`), SGD `lr=0.1` (`0.4324`).
- Model final: SGD+momentum `lr=0.05`.
- Test loss: `0.4318`.
- Test accuracy: `0.8515`.
- Kelas yang paling sering tertukar: T-shirt/top dan Shirt.
- Scheduler cosine menurunkan validation loss menjadi `0.3748` pada anggaran epoch yang sama.

Test set hanya digunakan satu kali setelah model final dipilih dari validation set.


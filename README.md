# M01_123450048

Pengumpulan Modul 1 Deep Learning: Fondasi Jaringan Saraf, FNN, Aktivasi, dan Loss.

## Isi

- `M01_123450048.ipynb`: notebook yang sudah dilengkapi dan dijalankan ulang.
- `M01_123450048.pdf`: PDF notebook final.
- `M01_123450048_metrics.csv`: enam run eksperimen sesuai template modul.

## Ringkasan hasil

- Dataset: `make_moons`, 600 sampel, split train/validation/test.
- Eksperimen: kombinasi `relu`, `tanh`, `sigmoid` dengan hidden size 4 dan 16.
- Model final: `tanh_h16`, dipilih dari validation loss terendah (`0.2056`).
- Test loss: `0.3277`.
- Test accuracy: `0.8583`.

Test set hanya digunakan setelah model final dipilih dari validation set.

# Latihan Mandiri di Lab — Modul 03

**Nama:** Fadil Prasetyo Alfarizzi  
**NIM:** 123450048  
**Kelas:** RC  
**Tanggal:** 2026-09-29

## Pertanyaan

Mengapa batch 32 menghasilkan 1.875 update sedangkan batch 512 hanya 120 update untuk anggaran epoch yang sama? Mana yang mencapai validation loss lebih rendah dan mana yang lebih cepat per epoch?

## Prediksi (sebelum menjalankan kode)

- Jumlah update per epoch adalah ⌈n / B⌉ dengan n = 12.000 contoh latih.
  - Batch 32: 12.000 / 32 = 375 update per epoch, sehingga 5 epoch = **1.875 update**.
  - Batch 512: ⌈12.000 / 512⌉ = 24 update per epoch (23 batch penuh dan satu batch berisi 224 contoh), sehingga 5 epoch = **120 update**.
- **Validation loss:** saya memperkirakan batch 32 lebih rendah karena mendapat update sekitar 15 kali lebih banyak dalam anggaran epoch yang sama.
- **Kecepatan per epoch:** saya memperkirakan batch 512 lebih cepat karena jumlah iterasinya jauh lebih sedikit dan setiap iterasi memakai operasi matriks yang lebih besar dan efisien.

## Hasil aktual (optimizer momentum, lr = 0,05, tanpa scheduler, 5 epoch)

| Batch | Update/epoch | Total update | Val. loss | Val. acc | Waktu/epoch (s) |
|---:|---:|---:|---:|---:|---:|
| 32 | 375 | 1.875 | 0,7179 | 0,7393 | 1,15 |
| 512 | 24 | 120 | 0,4281 | 0,8503 | 0,31 |

Kolom `n_update` pada `df_bagian_f` sama persis dengan hitungan di atas.

Validation loss per epoch:
- Batch 32: 0,708 → 0,820 → 0,855 → 0,724 → 0,718 (naik di epoch 2–3)
- Batch 512: 0,797 → 0,525 → 0,476 → 0,427 → 0,428 (turun stabil)

## Perbandingan dengan prediksi

- **Jumlah update: sesuai.** 1.875 dan 120 update, sama dengan hitungan ⌈n/B⌉ × epoch.
- **Kecepatan per epoch: sesuai.** Batch 512 sekitar 0,31 s per epoch, sedangkan batch 32 sekitar 1,15 s per epoch, hampir empat kali lebih lambat karena harus menjalankan 375 iterasi kecil per epoch.
- **Validation loss: tidak sesuai.** Batch 512 justru lebih baik (0,4281) daripada batch 32 (0,7179), padahal batch 32 mendapat 15 kali lebih banyak update. Learning rate 0,05 dengan momentum 0,9 dipilih pada batch 128. Pada batch 32, gradien tiap mini-batch jauh lebih berderau, tetapi besar langkahnya tetap sama, sehingga model berosilasi; validation loss-nya naik dari 0,708 ke 0,855 sebelum turun lagi. Batch 512 memberi gradien yang lebih halus, sehingga 120 update-nya stabil.

**Kesimpulan:** jumlah update yang lebih banyak tidak otomatis menghasilkan loss yang lebih rendah bila learning rate tidak disesuaikan dengan ukuran batch. Untuk perbandingan batch size yang adil, learning rate sebaiknya disetel ulang per batch size, misalnya dengan menskalakannya sebanding ukuran batch.

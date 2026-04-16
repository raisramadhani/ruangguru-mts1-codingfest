# Tutorial Membuat Aplikasi KELOMPOK 4 (MTsN 1 Surakarta)

Pastikan Anda sudah login ke MIT App Inventor dan berada di tampilan **Designer**.

---

## TAHAP 1: Membuat Screen Baru

Buat 5 screen baru:

1. `HalamanUtama`
2. `InputUang`
3. `Analisis`
4. `Challenge`
5. `Riwayat`

---

## TAHAP 2: Desain & Blocks - HalamanUtama

**A. Desain (Designer)**

1. Tarik **Label** `Saldo_Sekarang` dan `Total_Pengeluaran`.
2. Tarik 4 **Button**: `Menu_Input`, `Menu_Analisis`, `Menu_Challenge`, `Menu_Riwayat`.
3. Tarik **TinyDB** (`DB_Kel4`).

**B. Kode (Blocks)**

1. Buat navigasi `open another screen` untuk ke-4 tombol.
2. Saat `Initialize`, tampilkan angka Saldo dan Total Pengeluaran dari TinyDB.

---

## TAHAP 3: Desain & Blocks - InputUang

**A. Desain (Designer)**

1. Tarik **TextBox** (`Input_Nominal`).
2. Tarik **Spinner** (`Kategori_Keluar`). Properties `ElementsFromString`: `Makan,Jajan,Transport`.
3. Tarik 2 **Button**: `Simpan_Pemasukan` dan `Simpan_Pengeluaran`.

**B. Kode (Blocks)**

1. Saat `Simpan_Pengeluaran` diklik:
   - Tambahkan nominal ke `"TotalPengeluaran"`.
   - **PENTING:** Simpan juga berdasarkan kategori. Gunakan blok `StoreValue` tag-nya menggunakan `Kategori_Keluar.Selection`. (Ini akan menyimpan tag "Makan", "Jajan", atau "Transport" dengan nominal yang terus diakumulasi).

---

## TAHAP 4: Desain & Blocks - Analisis

**A. Desain (Designer)**

1. Tarik **Label** `Teks_PengeluaranTerbesar`.
2. Tarik **Label** `Teks_PersenKategori` (Makan: X%, Jajan: Y%, Transport: Z%).
3. Tarik **Label** `Teks_Status` (Hemat/Boros).
4. Tarik **TinyDB** (`DB_Kel4`).

**B. Kode (Blocks)**

1. Saat `Initialize`, panggil `GetValue` untuk "TotalPengeluaran", "Makan", "Jajan", dan "Transport".
2. **Persentase:** Hitung pakai Math: `(Makan / TotalPengeluaran) * 100`. Gabungkan dengan blok `join` dan tampilkan.
3. **Pengeluaran Terbesar:** Gunakan blok `if else if` untuk membandingkan mana yang lebih besar (Makan > Jajan & Makan > Transport, dst), lalu tampilkan namanya di Label.
4. **Status:** `if TotalPengeluaran > TotalPemasukan`, set Status = "Boros", `else` "Hemat".

---

## TAHAP 5: Desain & Blocks - Challenge

**A. Desain (Designer)**

1. Tarik **Spinner** (Rename: `Pilih_Challenge`). Isi `ElementsFromString` dengan: `No Jajan Day,Hari ini nabung 10.000,Hemat 50%`.
2. Tarik **Button** `Tombol_TerimaTantangan`.
3. Tarik **Label** `Teks_TantanganAktif`.

**B. Kode (Blocks)**

1. Saat `Tombol_TerimaTantangan` diklik, set `Teks_TantanganAktif.Text` menjadi `Pilih_Challenge.Selection`. Beri efek warna teks atau Notifier agar menarik.

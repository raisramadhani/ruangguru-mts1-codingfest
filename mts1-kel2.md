# Tutorial Membuat Aplikasi KELOMPOK 2 (MTsN 1 Surakarta)

Pastikan Anda sudah login ke MIT App Inventor dan berada di tampilan **Designer**.

---

## TAHAP 1: Membuat Screen Baru

Buat 4 screen baru:

1. `HalamanUtama`
2. `RiwayatTrans`
3. `InputUang`
4. `WishlistBarang`

---

## TAHAP 2: Desain & Blocks - HalamanUtama

**A. Desain (Designer)**

1. Tarik **Label** (Rename: `Teks_SaldoSekarang`).
2. Tarik **ListView** kecil untuk preview riwayat (Rename: `Preview_Riwayat`).
3. Tarik **ListView** kecil untuk preview wishlist (Rename: `Preview_Wishlist`).
4. Buat 3 **Button** menu: `Menu_Riwayat`, `Menu_Input`, `Menu_Wishlist`.
5. Tarik **TinyDB** (`DB_Kel2`).

**B. Kode (Blocks)**

1. **Navigasi:** Buat blok `when Click` untuk ke-3 tombol menuju screen masing-masing menggunakan `open another screen`.
2. **Load Data:** Saat `HalamanUtama.Initialize`, ambil `GetValue` untuk Saldo (Pemasukan - Pengeluaran), `DataRiwayat`, dan `DataWishlist`, lalu set ke komponen masing-masing.

---

## TAHAP 3: Desain & Blocks - InputUang

**A. Desain (Designer)**

1. Tarik **TextBox** Nominal (`Input_Nominal`) dan Keterangan (`Input_Ket`).
2. Tarik 2 **Button**: `Tombol_Masuk` (Simpan Pemasukan) dan `Tombol_Keluar` (Simpan Pengeluaran).
3. Tarik **TinyDB** (`DB_Kel2`) dan **Notifier**.

**B. Kode (Blocks)**

1. **Pemasukan:** Saat `Tombol_Masuk.Click`, tambah `GetValue` tag `"SaldoMasuk"` dengan Nominal. Tambahkan data ke list `"DataRiwayat"` dengan teks awalan "[+]".
2. **Pengeluaran:** Saat `Tombol_Keluar.Click`, tambah `GetValue` tag `"SaldoKeluar"` dengan Nominal. Tambahkan data ke list `"DataRiwayat"` dengan teks awalan "[-]". Munculkan Notifier sukses.

---

## TAHAP 4: Desain & Blocks - RiwayatTrans

**A. Desain (Designer)**

1. Tarik **ListView** (Rename: `Daftar_SemuaRiwayat`, Height: Fill Parent).
2. Tarik **TinyDB** (`DB_Kel2`).

**B. Kode (Blocks)**

1. Saat `Initialize`, set `Daftar_SemuaRiwayat.Elements` ke `GetValue` tag `"DataRiwayat"`.

---

## TAHAP 5: Desain & Blocks - WishlistBarang

**A. Desain (Designer)**

1. Tarik **TextBox** (`Input_NamaBarang`).
2. Tarik **Spinner** (`Pilih_Kategori`). Di Properties `ElementsFromString` isi dengan: `Kebutuhan,Keinginan`.
3. Tarik **Button** (`Tombol_SimpanWishlist`).
4. Tarik 2 **ListView**: `List_Kebutuhan` dan `List_Keinginan`.
5. Tarik **TinyDB** (`DB_Kel2`).

**B. Kode (Blocks)**

1. Saat `Tombol_SimpanWishlist.Click`, gunakan blok `if then else`.
   - `if Pilih_Kategori.Selection = "Kebutuhan"`, tambahkan data ke list tag `"ListKebutuhan"`, lalu update `List_Kebutuhan.Elements`.
   - `else`, tambahkan data ke list tag `"ListKeinginan"`, lalu update `List_Keinginan.Elements`.

# Tutorial Membuat Aplikasi KELOMPOK 1 (MTsN 1 Surakarta)

Pastikan Anda sudah login ke MIT App Inventor dan berada di tampilan **Designer**.

Karena Anda sudah selesai dengan `Screen1` (Login), kita akan melanjutkan pembuatan 4 Screen baru sesuai konsep.

---

## TAHAP 1: Membuat Screen Baru

1. Klik tombol **Add Screen** di atas.
2. Buat 4 screen berikut secara berurutan (pastikan tanpa spasi):
   - `HalamanUtama`
   - `CatatanKeuangan`
   - `Tabungan`
   - `TabunganTarget`

> **PENTING:** Coba Run program secara berkala untuk memastikan tidak ada error saat perpindahan layar.

---

## TAHAP 2: Desain & Blocks - HalamanUtama

**A. Desain (Designer)**

1. **Layout List Icon:** Dari **Palette** > **Layout**, tarik **VerticalArrangement** (Width: Fill Parent).
2. Tarik **HorizontalArrangement** ke dalamnya. Masukkan **Image** (ikon menu) dan **Button** ke sebelahnya.
3. Buat 3 tombol menu dengan cara di atas:
   - Rename: `Tombol_MenuCatatan`, Text: `Catatan Pemasukan & Pengeluaran`
   - Rename: `Tombol_MenuTabungan`, Text: `Cek Tabungan`
   - Rename: `Tombol_MenuTarget`, Text: `Tabungan Target`

**B. Kode (Blocks)**

1. Klik `Tombol_MenuCatatan`, tarik `when Click do`. Tarik `open another screen screenName` isi dengan `"CatatanKeuangan"`.
2. Lakukan hal yang sama untuk `Tombol_MenuTabungan` (buka `"Tabungan"`) dan `Tombol_MenuTarget` (buka `"TabunganTarget"`).

---

## TAHAP 3: Desain & Blocks - CatatanKeuangan

**A. Desain (Designer)**

1. Tarik 2 **TextBox** (Hint: `Nominal`, centang _NumbersOnly_) & (Hint: `Keterangan`).
2. Tarik 1 **DatePicker** (Text: `Pilih Tanggal`, Rename: `Input_Tanggal`).
3. Tarik 2 **Button**: `Tombol_SimpanMasuk` (Pemasukan) & `Tombol_SimpanKeluar` (Pengeluaran).
4. Tarik 2 **ListView**: `List_Pemasukan` dan `List_Pengeluaran`.
5. Tarik **TinyDB** (`Database_Kel1`) dan **Notifier** (`Notif`).

**B. Kode (Blocks)**

1. **Pilih Tanggal:** Gunakan `when Input_Tanggal.AfterDateSet`, gabungkan Day/Month/Year dengan blok `join`, tampilkan ke label teks.
2. **Simpan Pemasukan:** - `when Tombol_SimpanMasuk.Click do`.
   - Gunakan `StoreValue` tag `"TotalMasuk"` (akumulasi nominal lama + baru).
   - Tambahkan item ke list riwayat menggunakan blok `join` (Tanggal - Keterangan - Nominal). Simpan ke tag `"RiwayatMasuk"`. Tampilkan ke `List_Pemasukan`.
3. **Simpan Pengeluaran:** Lakukan logika yang persis sama, namun gunakan tag `"TotalKeluar"` dan `"RiwayatKeluar"`. Tampilkan ke `List_Pengeluaran`.

---

## TAHAP 4: Desain & Blocks - Tabungan

**A. Desain (Designer)**

1. Tarik **Label** besar ke tengah layar. Rename: `Teks_TotalSaldo`. Text: `Rp 0`.
2. Tarik **TinyDB** (`Database_Kel1`).

**B. Kode (Blocks)**

1. Tarik `when Tabungan.Initialize do`.
2. Set `Teks_TotalSaldo.Text` dengan blok `Math` kurang `-`.
   - Kiri: `GetValue` tag `"TotalMasuk"` (default 0).
   - Kanan: `GetValue` tag `"TotalKeluar"` (default 0).

---

## TAHAP 5: Desain & Blocks - TabunganTarget

**A. Desain (Designer)**

1. **Input Gambar:** Tarik **ImagePicker**. Text: `Pilih Gambar Barang`. Rename: `Pilih_Gambar`. Tarik **Image** di bawahnya untuk preview (Rename: `Preview_Gambar`).
2. Tarik 3 **TextBox**: `Input_NamaBarang`, `Input_HargaBarang` (_NumbersOnly_), dan `Input_TglMulai`.
3. Tarik **Button** (`Tombol_SimpanTarget`) dan **Label** (`Teks_InfoTarget` - sembunyikan Visible-nya).
4. Tarik **TinyDB** (`Database_Kel1`).

**B. Kode (Blocks)**

1. **Tampil Gambar:** `when Pilih_Gambar.AfterPicking do`, set `Preview_Gambar.Picture` ke `Pilih_Gambar.Selection`.
2. **Simpan:** `when Tombol_SimpanTarget.Click do`, simpan nama, harga, tanggal, dan path gambar (`Preview_Gambar.Picture`) ke TinyDB dengan tag masing-masing.
3. **Hitung Tabungan Saat Ini:** Saat `Initialize`, tarik `GetValue` Saldo (TotalMasuk - TotalKeluar) seperti di layar Tabungan, lalu gabungkan dengan info Target menggunakan blok `join` dan tampilkan di `Teks_InfoTarget`.

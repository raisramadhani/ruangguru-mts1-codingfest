# Tutorial Membuat Aplikasi KELOMPOK 4 (MTsN 1 Surakarta)

Pastikan Anda sudah login ke MIT App Inventor, membuat project baru, dan berada di tampilan **Designer** (tombol di pojok kanan atas).

---

## TAHAP 0: Membuat Halaman Login (Screen1)

Kita akan membuat halaman Login terlebih dahulu di **Screen1** (Screen bawaan saat pertama kali membuat project).

### A. Desain (Designer)

1. **Input Username:** Dari panel **Palette** > **User Interface**, tarik komponen **TextBox** ke layar.
   - Di panel **Properties** (sebelah kanan), ubah **Hint** menjadi: `Masukkan Username`.
   - Di panel **Components**, klik **Rename Component** dan ubah namanya menjadi: `InputUsername`.
2. **Input Password:** Dari panel **Palette** > **User Interface**, tarik komponen **PasswordTextBox** ke layar.
   - Di panel **Properties**, ubah **Hint** menjadi: `Masukkan Password`.
   - Klik **Rename Component**, ubah menjadi: `InputPassword`.
3. **Tombol Login:** Dari **Palette**, tarik komponen **Button** ke layar.
   - Di panel **Properties**, ubah **Text** menjadi: `Masuk / Login`.
   - Klik **Rename Component**, ubah menjadi: `Tombol_Masuk`.
4. **Pesan Notifikasi:** Dari panel **Palette**, tarik komponen **Notifier** ke layar (komponen ini akan muncul di bawah layar). Biarkan namanya tetap `Notifier1`.

### B. Kode (Blocks)

Pindah ke tampilan **Blocks** (pojok kanan atas).

1. Di panel kiri, klik `Tombol_Masuk`, tarik blok kuning paling atas: `when Tombol_Masuk.Click do`.
2. Dari kategori **Control** (warna oranye), tarik blok `if then else` ke dalam blok kuning.
3. **Mengatur Syarat Login (Bagian if):**
   - Dari kategori **Logic** (hijau terang), tarik blok `and` pasangkan ke sebelah `if`.
   - Di lubang kiri `and`: Tarik blok sama dengan `=` dari kategori **Logic**. Sisi kirinya isi dengan blok hijau tua `InputUsername.Text`, sisi kanannya isi dengan teks pink `" "` dan ketik `123`.
   - Di lubang kanan `and`: Tarik blok `=` lagi. Sisi kirinya isi dengan blok hijau tua `InputPassword.Text`, sisi kanannya isi dengan teks pink `" "` dan ketik `123`.
4. **Jika Login Benar (Bagian then):**
   - Klik `Notifier1`, tarik blok ungu `call Notifier1.ShowAlert notice`. Pasangkan ke dalam `then`. Isi dengan teks pink `" "` dan ketik: `Selamat datang kembali!`.
   - Dari kategori **Control**, tarik blok `open another screen screenName`. Isi dengan teks pink `" "` dan ketik: `HalamanUtama`.
5. **Jika Login Salah (Bagian else):**
   - Tarik lagi blok ungu `call Notifier1.ShowAlert notice` ke dalam `else`. Isi dengan teks pink `" "` dan ketik: `Password Salah kak`.

---

## TAHAP 1: Membuat Screen Baru

Sekarang kita perlu membuat 5 Screen baru sesuai dengan konsep aplikasi Anda.

1. Di bagian atas layar, klik tombol **Add Screen**.
2. Ketik nama: `HalamanUtama` lalu klik OK.
3. Ulangi langkah 1, ketik nama: `InputUang` lalu klik OK.
4. Ulangi langkah 1, ketik nama: `Analisis` lalu klik OK.
5. Ulangi langkah 1, ketik nama: `Challenge` lalu klik OK.
6. Ulangi langkah 1, ketik nama: `Riwayat` lalu klik OK.

_(Catatan: Pastikan penulisan nama Screen persis seperti di atas tanpa spasi)._

> **PENTING:** Silakan coba Run program di HP Anda untuk memastikan bisa login dengan username "123" dan password "123".

---

## TAHAP 2: Desain & Blocks - HalamanUtama

Pastikan di bagian atas layar App Inventor, Anda sedang berada di Screen **HalamanUtama**. Di sini kita akan membuat Header dengan Logo terlebih dahulu untuk dicopy ke layar lain.

### A. Desain (Designer)

1. **Membuat Header & Logo (Untuk di-copy nanti):**
   - Dari panel **Palette** > **Layout**, tarik **HorizontalArrangement** ke layar bagian paling atas.
   - Dari **Palette** > **User Interface**, tarik komponen **Image** ke dalam kotak HorizontalArrangement tadi.
   - Di panel **Components**, klik tombol **Rename Component** pada gambar tersebut, ubah namanya menjadi: `Logo_Aplikasi`.
   - Di panel **Properties**, cari kotak centang bernama **Clickable** dan **wajib dicentang** (agar logo bisa ditekan untuk kembali ke halaman utama).
   - Tarik **Label** di sebelah logo jika ingin memberi teks judul aplikasi MTsN 1.
2. **Info Saldo & Pengeluaran:**
   - Dari panel **Palette** > **User Interface**, tarik komponen **Label** ke bawah header. Ubah Text menjadi `Saldo: Rp 0`, perbesar Font jadi `24`, centang **FontBold**. Rename: `Teks_SaldoSekarang`.
   - Tarik komponen **Label** kedua ke bawahnya. Ubah Text menjadi `Total Pengeluaran: Rp 0`. Rename: `Teks_TotalPengeluaran`.
3. **Tombol Menu:** Tarik 4 buah **Button** secara berurutan ke layar.
   - Button 1 -> Rename: `Menu_Input`, Text: `Tambah Data Keuangan`.
   - Button 2 -> Rename: `Menu_Analisis`, Text: `Analisis Keuangan`.
   - Button 3 -> Rename: `Menu_Challenge`, Text: `Challenge Menabung`.
   - Button 4 -> Rename: `Menu_Riwayat`, Text: `Riwayat Transaksi`.
4. **Database:** Dari kategori **Storage**, tarik **TinyDB**. Rename menjadi `DB_Kel4`.

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

1. **Logika Logo (Kembali ke Home):**
   - Klik `Logo_Aplikasi` di panel kiri, tarik `when Logo_Aplikasi.Click do`.
   - Dari kategori **Control**, tarik `open another screen screenName`. Isi dengan teks pink `"HalamanUtama"`.
2. **Logika Navigasi Menu:**
   - Di panel kiri, klik `Menu_Input`. Tarik blok kuning `when Menu_Input.Click do`. Dari kategori **Control**, tarik blok `open another screen screenName`. Isi dengan teks pink `"InputUang"`.
   - Lakukan langkah yang sama persis untuk ketiga tombol lainnya, arahkan ke `"Analisis"`, `"Challenge"`, dan `"Riwayat"`.
3. **Menampilkan Saldo (Saat Layar Dibuka):**
   - Tarik blok kuning `when HalamanUtama.Initialize do`.
   - Klik `Teks_SaldoSekarang`, tarik `set Teks_SaldoSekarang.Text to`. Gunakan blok `join` dengan teks `"Saldo: Rp "` digabung dengan hasil kurang (blok Math `-`) antara `GetValue` tag `"SaldoMasuk"` dan `GetValue` tag `"SaldoKeluar"`.
   - Klik `Teks_TotalPengeluaran`, tarik `set Teks_TotalPengeluaran.Text to`. Gunakan blok `join` dengan teks `"Total Pengeluaran: Rp "` digabung dengan `GetValue` tag `"SaldoKeluar"`.

---

## TAHAP 3: Desain & Blocks - InputUang

Ganti screen aktif ke **InputUang**.

### A. Desain (Designer)

1. **Copy-Paste Header:**
   - Ganti screen kembali ke `HalamanUtama` sebentar.
   - Klik komponen `HorizontalArrangement` (Header) yang berisi Logo Anda.
   - Tekan tombol **Ctrl + C** (Copy) di keyboard Anda.
   - Ganti screen ke `InputUang`. Tekan tombol **Ctrl + V** (Paste). Header dan Logo akan otomatis muncul beserta blok logikanya.
2. **Input Keterangan:** Tarik **TextBox** ke bawah header. Hint: `Keterangan Transaksi`. Rename: `Input_Ket`.
3. **Input Nominal:** Tarik **TextBox**. Centang **NumbersOnly**. Hint: `Nominal Uang`. Rename: `Input_Nominal`.
4. **Kategori Pengeluaran:** Tarik komponen **Spinner**.
   - Di Properties, cari kotak **ElementsFromString**. Ketik persis seperti ini (tanpa spasi setelah koma): `Makan,Jajan,Transport`.
   - Rename: `Kategori_Keluar`.
5. **Tombol Simpan:** Tarik 2 buah **Button**.
   - Button 1 -> Rename: `Simpan_Pemasukan`, Text: `Simpan sebagai Pemasukan`.
   - Button 2 -> Rename: `Simpan_Pengeluaran`, Text: `Simpan sebagai Pengeluaran`.
6. **Database & Notifikasi:** Tarik **TinyDB** (Rename: `DB_Kel4`) dan **Notifier** (Rename: `Notifikasi_Pesan`).

### B. Kode (Blocks)

Pindah ke **Blocks**.

1. **Buat Variabel List:** Di kategori **Variables**, buat `global RiwayatSmt` dan isi dengan `create empty list`.
2. **Menyimpan Pemasukan:**
   - Tarik blok kuning `when Simpan_Pemasukan.Click do`.
   - Tarik blok ungu `StoreValue` tag `"SaldoMasuk"`. Isi `valueToStore` dengan blok Math `+` (`GetValue` `"SaldoMasuk"` ditambah `Input_Nominal.Text`).
   - Simpan List Riwayat: Ambil `GetValue` tag `"DataRiwayat"` ke variabel `RiwayatSmt`. Gunakan `add items to list` isi dengan teks `"[+] Pemasukan: Rp " + Nominal`. Lalu `StoreValue` tag `"DataRiwayat"` lagi.
   - Munculkan Notifier `ShowAlert` pesan: `"Pemasukan Tersimpan!"`.
3. **Menyimpan Pengeluaran (SANGAT PENTING):**
   - Tarik blok kuning `when Simpan_Pengeluaran.Click do`.
   - **Simpan Total Keluar:** Tarik `StoreValue` tag `"SaldoKeluar"`. Isi dengan `GetValue` `"SaldoKeluar"` ditambah `Input_Nominal.Text`.
   - **Simpan per Kategori:** Tarik `StoreValue` sekali lagi.
     - Di bagian `tag`, pasangkan blok hijau muda `Kategori_Keluar.Selection`.
     - Di bagian `valueToStore`, pasangkan blok Math `+`. Kiri: `GetValue` (tag-nya juga `Kategori_Keluar.Selection`, default 0). Kanan: `Input_Nominal.Text`.
   - Simpan List Riwayat seperti langkah pemasukan, gunakan teks `"[-] " + Kategori_Keluar.Selection + ": Rp "`.
   - Munculkan Notifier pesan: `"Pengeluaran Tersimpan!"`.

---

## TAHAP 4: Desain & Blocks - Analisis

Ganti screen aktif ke **Analisis**. Halaman ini akan mengecek seberapa boros/hemat keuangan Anda.

### A. Desain (Designer)

1. **Paste Header:** Tekan **Ctrl + V** (Paste) di keyboard agar Header dan Logo kembali muncul di atas layar.
2. Tarik **Label** judul di bawah header: `Analisis Pengeluaran Anda`. Centang FontBold.
3. Tarik **Label** baru, Rename: `Teks_PersenKategori`. Ubah Text sementara: `Menghitung persentase...`.
4. Tarik **Label** baru, Rename: `Teks_PengeluaranTerbesar`. Ubah Text: `Pengeluaran terbesar di...`.
5. Tarik **Label** baru, Rename: `Teks_Status`. Perbesar Font, Text: `Status: ...`.
6. Tarik **TinyDB** (Rename: `DB_Kel4`).

### B. Kode (Blocks)

Pindah ke **Blocks**. Tarik blok kuning `when Analisis.Initialize do`. Semua logika masuk di dalam blok ini.

1. **Ambil Data:** Buat 4 variabel `local` sementara untuk memudahkan: `UangMakan` (dari GetValue "Makan"), `UangJajan` (dari "Jajan"), `UangTransport` (dari "Transport"), dan `TotKeluar` (dari "SaldoKeluar"). (Beri nilai default 1 pada TotKeluar untuk menghindari error sistem/bagi nol).
2. **Menghitung Persentase:**
   - Klik `Teks_PersenKategori`, tarik `set Text to`.
   - Gunakan blok `join` bertingkat untuk menyusun teks: `"Makan: "` + `(UangMakan / TotKeluar * 100)` + `"% | Jajan: "` + `(UangJajan / TotKeluar * 100)` + `"% | Transport: "` + `(UangTransport / TotKeluar * 100)` + `"%"`.
3. **Mencari Pengeluaran Terbesar:**
   - Gunakan blok `if then` dengan 2 tambahan `else if`.
   - Jika `UangMakan` > `UangJajan` **dan** `UangMakan` > `UangTransport`, set `Teks_PengeluaranTerbesar.Text` ke `"Paling banyak dipakai untuk MAKAN"`.
   - Else If `UangJajan` > `UangMakan` **dan** `UangJajan` > `UangTransport`, set teks ke `"Paling banyak dipakai untuk JAJAN"`.
   - Else, set teks ke `"Paling banyak dipakai untuk TRANSPORT"`.
4. **Status Boros/Hemat:**
   - Tambahkan blok `if else` di bawah susunan tadi.
   - Jika `GetValue` tag `"SaldoKeluar"` **>** `GetValue` tag `"SaldoMasuk"`, maka `set Teks_Status.Text to` `"Status: KAMU BOROS!"`.
   - Else, `set Teks_Status.Text to` `"Status: KAMU HEMAT!"`.

---

## TAHAP 5: Desain & Blocks - Challenge

Ganti screen aktif ke **Challenge**.

### A. Desain (Designer)

1. **Paste Header:** Tekan **Ctrl + V** (Paste) di keyboard agar Header dan Logo kembali muncul di atas layar.
2. Tarik komponen **Spinner** ke bawah header.
   - Di Properties, ketik di **ElementsFromString**: `No Jajan Day,Hari ini nabung 10.000,Hemat 50%`.
   - Rename: `Pilih_Challenge`.
3. Tarik komponen **Button**. Text: `Terima Challenge Ini`. Rename: `Tombol_TerimaTantangan`.
4. Tarik **Label** besar di bawahnya. Text: `Belum ada challenge aktif`. FontBold, warna teks Oranye. Rename: `Teks_TantanganAktif`.

### B. Kode (Blocks)

Pindah ke **Blocks**. Halaman ini logikanya sangat sederhana.

1. Klik `Tombol_TerimaTantangan`, tarik blok kuning `when Click do`.
2. Klik `Teks_TantanganAktif`, tarik blok hijau muda `set Teks_TantanganAktif.Text to`.
3. Pasangkan dengan blok hijau tua `Pilih_Challenge.Selection`.

---

## TAHAP 6: Desain & Blocks - Riwayat

Ganti screen aktif ke **Riwayat**.

### A. Desain (Designer)

1. **Paste Header:** Tekan **Ctrl + V** (Paste) di keyboard agar Header dan Logo kembali muncul di atas layar.
2. Tarik **Label** untuk judul di bawah header, Text: `Daftar Semua Transaksi Anda`.
3. Tarik komponen **ListView**. Ubah **Height** dan **Width** menjadi `Fill parent` agar memenuhi layar ke bawah. Rename: `Daftar_Riwayat`.
4. Tarik **TinyDB** (Rename: `DB_Kel4`).

### B. Kode (Blocks)

Pindah ke **Blocks**.

1. Tarik blok kuning `when Riwayat.Initialize do` (artinya saat layar dibuka).
2. Klik `Daftar_Riwayat`, tarik blok hijau muda `set Daftar_Riwayat.Elements to`.
3. Pasangkan dengan blok ungu `call DB_Kel4.GetValue`.
4. Isi `tag`-nya dengan teks pink `"DataRiwayat"`. Isi `valueIfTagNotThere` dengan blok biru muda `create empty list`.

> **PENTING:** Silakan coba Run program dari awal sampai akhir, periksa apakah perhitungan analisis persentase dan riwayat transaksinya muncul dengan benar. Jangan lupa Save project Anda!

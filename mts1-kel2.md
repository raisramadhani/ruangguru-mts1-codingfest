# Tutorial Membuat Aplikasi KELOMPOK 2 (MTsN 1 Surakarta)

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

Sekarang kita perlu membuat 4 Screen baru sesuai dengan konsep aplikasi pengelolaan tabungan Anda.

1. Di bagian atas layar, klik tombol **Add Screen**.
2. Ketik nama: `HalamanUtama` lalu klik OK.
3. Ulangi langkah 1, ketik nama: `RiwayatTrans` lalu klik OK.
4. Ulangi langkah 1, ketik nama: `InputUang` lalu klik OK.
5. Ulangi langkah 1, ketik nama: `WishlistBarang` lalu klik OK.

_(Catatan: Pastikan penulisan nama Screen persis seperti di atas tanpa spasi, karena huruf besar/kecil sangat berpengaruh di App Inventor)._

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
2. **Teks Saldo:** Dari panel **Palette** > **User Interface**, tarik komponen **Label** ke layar di bawah header.
   - Di panel **Properties**, perbesar ukuran Font menjadi `24` dan centang **FontBold**.
   - Ubah **Text** menjadi: `Saldo Anda Saat Ini: Rp 0`.
   - Klik **Rename Component**, ubah menjadi: `Teks_SaldoSekarang`.
3. **Preview Riwayat:** Tarik **Label** baru, ubah Text: `Riwayat Terakhir:`. Tarik komponen **ListView** di bawahnya, ubah **Height** menjadi `15 Percent`. Rename: `Preview_Riwayat`.
4. **Preview Wishlist:** Tarik **Label** baru, ubah Text: `Wishlist Kebutuhan:`. Tarik komponen **ListView** di bawahnya, ubah **Height** menjadi `15 Percent`. Rename: `Preview_Wishlist`.
5. **Tombol Menu:** Dari **Palette**, tarik 3 buah **Button** ke layar.
   - Button 1 -> Rename: `Menu_Riwayat`, Text: `Buka Riwayat Lengkap`.
   - Button 2 -> Rename: `Menu_Input`, Text: `Input Pemasukan & Pengeluaran`.
   - Button 3 -> Rename: `Menu_Wishlist`, Text: `Buka Wishlist Barang`.
6. **Database:** Dari kategori **Storage**, tarik **TinyDB**. Rename menjadi: `DB_Kel2`.

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

1. **Logika Logo (Kembali ke Home):**
   - Klik `Logo_Aplikasi` di panel kiri, tarik `when Logo_Aplikasi.Click do`.
   - Dari kategori **Control**, tarik `open another screen screenName`. Isi dengan teks pink `"HalamanUtama"`.
2. **Logika Navigasi Menu:**
   - Di panel kiri, klik `Menu_Riwayat`. Tarik blok kuning: `when Menu_Riwayat.Click do`.
   - Dari kategori **Control**, tarik blok `open another screen screenName`. Isi dengan teks pink `" "` lalu ketik: `RiwayatTrans`.
   - Lakukan cara yang sama persis untuk `Menu_Input` (arahkan ke `"InputUang"`) dan `Menu_Wishlist` (arahkan ke `"WishlistBarang"`).
3. **Memuat Data Saldo & Preview:**
   - Tarik blok kuning `when HalamanUtama.Initialize do`.
   - **Set Saldo:** Klik `Teks_SaldoSekarang`, tarik blok hijau muda `set Teks_SaldoSekarang.Text to`. Gunakan blok `join` (kategori Text). Lubang 1 ketik `"Saldo: Rp "`. Lubang 2 gunakan blok Math kurang `-`. Sisi kirinya isi dengan `GetValue` tag `"SaldoMasuk"`, sisi kanannya isi dengan `GetValue` tag `"SaldoKeluar"`. (Beri `valueIfTagNotThere` angka `0`).
   - **Set Preview:** Klik `Preview_Riwayat`, tarik `set Preview_Riwayat.Elements to`, pasangkan dengan `GetValue` tag `"DataRiwayat"` (default: `create empty list`). Lakukan hal sama untuk `Preview_Wishlist` dengan tag `"ListKebutuhan"`.

---

## TAHAP 3: Desain & Blocks - InputUang

Ganti screen aktif ke **InputUang**.

### A. Desain (Designer)

1. **Copy-Paste Header:**
   - Ganti screen kembali ke `HalamanUtama` sebentar.
   - Klik komponen `HorizontalArrangement` (Header) yang berisi Logo Anda.
   - Tekan tombol **Ctrl + C** (Copy) di keyboard Anda.
   - Ganti screen ke `InputUang`. Tekan tombol **Ctrl + V** (Paste). Header dan Logo akan otomatis muncul beserta blok logikanya.
2. **Input Keterangan:** Tarik komponen **TextBox** ke bawah header. Ubah **Hint** menjadi: `Keterangan (Contoh: Jajan / Nabung)`. Rename menjadi: `Input_Ket`.
3. **Input Nominal:** Tarik **TextBox** ke bawahnya. Centang kotak **NumbersOnly**. Ubah **Hint** menjadi: `Nominal Uang`. Rename menjadi: `Input_Nominal`.
4. **Tombol Simpan:** Tarik dua buah **Button** (bisa diletakkan berdampingan memakai HorizontalArrangement).
   - Button 1 -> Text: `Simpan Pemasukan`, Rename: `Tombol_Masuk`.
   - Button 2 -> Text: `Simpan Pengeluaran`, Rename: `Tombol_Keluar`.
5. **Database & Notifikasi:** Tarik **TinyDB** (Rename: `DB_Kel2`) dan **Notifier** (Rename: `Notifikasi_Pesan`).

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

1. **Variabel List:** Di kategori **Variables**, tarik `initialize global name to`. Ganti `name` jadi `RiwayatSmt`. Isi dengan blok biru muda `create empty list`.
2. **Simpan Pemasukan:**
   - Tarik blok kuning `when Tombol_Masuk.Click do`.
   - **Tambah Saldo Masuk:** Tarik blok ungu `StoreValue` tag `"SaldoMasuk"`. Isinya: blok Math `+` (`GetValue` tag `"SaldoMasuk"` ditambah `Input_Nominal.Text`).
   - **Simpan ke List Riwayat:**
     - Tarik blok oranye `set global RiwayatSmt to`, isi dengan `GetValue` tag `"DataRiwayat"` (default `create empty list`).
     - Tarik blok biru muda `add items to list`. List-nya isi dengan `get global RiwayatSmt`. Item-nya gunakan blok `join` (Isi 3 lubang: teks pink `"[+] "`, `Input_Ket.Text`, dan teks pink `" - Rp "`, lalu `Input_Nominal.Text`).
     - Tarik `StoreValue` tag `"DataRiwayat"`, isinya `get global RiwayatSmt`.
   - **Notifikasi:** Tarik blok `ShowAlert`, isi pesan: `"Pemasukan Berhasil Disimpan!"`.
3. **Simpan Pengeluaran:**
   - Lakukan langkah yang **sama persis** dengan logika pemasukan, tetapi gunakan blok kuning `when Tombol_Keluar.Click do`.
   - **PENTING:** Ubah tag totalnya menjadi `"SaldoKeluar"`. Pada bagian `join` di list, ubah teks awal menjadi `"[-] "`. Ubah pesan notifikasi menjadi: `"Pengeluaran Berhasil Dicatat!"`.

---

## TAHAP 4: Desain & Blocks - RiwayatTrans

Ganti screen aktif ke **RiwayatTrans**.

### A. Desain (Designer)

1. **Paste Header:** Tekan **Ctrl + V** (Paste) di keyboard agar Header dan Logo kembali muncul di atas layar.
2. Tarik **Label** judul di bawah header, ubah Text: `Seluruh Riwayat Transaksi Anda`.
3. Tarik komponen **ListView**. Ubah **Height** dan **Width** menjadi `Fill parent`. Rename: `Daftar_SemuaRiwayat`.
4. Tarik **Button** di bawahnya. Ubah Text: `Kembali ke Beranda`. Rename: `Tombol_Kembali`.
5. Tarik **TinyDB** (Rename: `DB_Kel2`).

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

1. **Tampilkan Data:** Tarik blok kuning `when RiwayatTrans.Initialize do`.
2. Klik `Daftar_SemuaRiwayat`, tarik blok hijau muda `set Daftar_SemuaRiwayat.Elements to`.
3. Pasangkan dengan blok ungu `call DB_Kel2.GetValue`. Isi `tag`-nya dengan teks pink `"DataRiwayat"`. Isi `valueIfTagNotThere` dengan blok biru muda `create empty list`.
4. **Tombol Kembali:** Tarik `when Tombol_Kembali.Click do`, lalu `open another screen` ke `"HalamanUtama"`.

---

## TAHAP 5: Desain & Blocks - WishlistBarang

Ganti screen aktif ke **WishlistBarang**.

### A. Desain (Designer)

1. **Paste Header:** Tekan **Ctrl + V** (Paste) di keyboard agar Header dan Logo kembali muncul di atas layar.
2. **Input Nama Barang:** Tarik **TextBox** ke bawah header. Ubah Hint: `Nama Barang Impian`. Rename: `Input_NamaBarang`.
3. **Pilih Kategori:** Dari panel **Palette** > **User Interface**, tarik komponen **Spinner**.
   - Di panel **Properties**, cari kotak `ElementsFromString`. Ketik persis seperti ini (tanpa spasi setelah koma): `Kebutuhan,Keinginan`.
   - Rename: `Pilih_Kategori`.
4. **Tombol Simpan:** Tarik **Button**. Text: `Simpan Wishlist`. Rename: `Tombol_SimpanWishlist`.
5. **Daftar Kebutuhan:** Tarik **Label** (Text: `Daftar Kebutuhan`), lalu tarik **ListView** di bawahnya (Rename: `List_Kebutuhan`).
6. **Daftar Keinginan:** Tarik **Label** (Text: `Daftar Keinginan`), lalu tarik **ListView** di bawahnya (Rename: `List_Keinginan`).
7. **Database:** Tarik **TinyDB** (Rename: `DB_Kel2`).

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

1. Buat 2 variabel List di kategori **Variables**: `global ListKebutuhanSmt` dan `global ListKeinginanSmt`. Isi keduanya dengan `create empty list`.
2. Tarik blok kuning `when Tombol_SimpanWishlist.Click do`.
3. Dari kategori **Control**, tarik blok `if then else`.
4. **Kondisi (Bagian if):** Gunakan blok logika `=`. Jika `Pilih_Kategori.Selection` sama dengan teks pink `"Kebutuhan"`.
5. **Simpan ke Kebutuhan (Bagian then):**
   - `set global ListKebutuhanSmt` ke `GetValue` tag `"ListKebutuhan"`.
   - `add items to list` (list: `get global ListKebutuhanSmt`, item: `Input_NamaBarang.Text`).
   - `StoreValue` tag `"ListKebutuhan"` dengan nilai `get global ListKebutuhanSmt`.
   - Update layar: `set List_Kebutuhan.Elements to` dengan `get global ListKebutuhanSmt`.
6. **Simpan ke Keinginan (Bagian else):**
   - Lakukan hal yang sama persis seperti langkah 5, tapi gunakan variabel `ListKeinginanSmt`, tag `"ListKeinginan"`, dan tampilkan ke `List_Keinginan.Elements`.
7. **Inisialisasi (Opsional tapi penting):** Gunakan blok `when WishlistBarang.Initialize do` untuk mengambil data `GetValue` dari tag `"ListKebutuhan"` dan `"ListKeinginan"`, lalu menampilkannya ke kedua ListView saat layar baru pertama kali dibuka.

> **PENTING:** Silakan coba Run program dari awal sampai akhir, periksa apakah input berjalan dan saldo terpotong/bertambah secara otomatis. Jangan lupa Save!

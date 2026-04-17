# Tutorial Membuat Aplikasi KELOMPOK 1 (MTsN 1 Surakarta)

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

Sekarang kita perlu membuat 4 Screen baru sesuai konsep kelompok Anda.

1. Di bagian atas layar, klik tombol **Add Screen**.
2. Ketik nama: `HalamanUtama` lalu klik OK.
3. Ulangi langkah 1, ketik nama: `CatatanKeuangan` lalu klik OK.
4. Ulangi langkah 1, ketik nama: `Tabungan` lalu klik OK.
5. Ulangi langkah 1, ketik nama: `TabunganTarget` lalu klik OK.

_(Catatan: Pastikan penulisan nama Screen persis seperti di atas tanpa spasi, karena huruf besar/kecil sangat berpengaruh di App Inventor)._

> **PENTING:** Silakan coba Run program di HP Anda untuk memastikan bisa login dengan username "123" dan password "123".

---

## TAHAP 2: Desain & Blocks - HalamanUtama

Pastikan di bagian atas layar App Inventor, Anda sedang berada di Screen **HalamanUtama**. Di sini kita akan membuat Header dengan Logo terlebih dahulu (yang nanti akan kita copy ke layar lain), baru kemudian membuat tombol menu utama.

### A. Desain (Designer)

1. **Membuat Header & Logo (Untuk di-copy nanti):**
   - Dari panel **Palette** > **Layout**, tarik **HorizontalArrangement** ke layar bagian paling atas.
   - Dari **Palette** > **User Interface**, tarik komponen **Image** ke dalam kotak HorizontalArrangement tadi.
   - Di panel **Components**, klik tombol **Rename Component** pada gambar tersebut, ubah namanya menjadi: `Logo_Aplikasi`.
   - Di panel **Properties**, cari kotak centang bernama **Clickable** dan **wajib dicentang** (agar logo bisa ditekan untuk kembali ke halaman utama).
   - _(Opsional)_ Tarik **Label** di sebelah logo jika ingin memberi teks judul aplikasi MTsN 1.
2. **Membuat Wadah Menu (List Icon):** - Dari panel **Palette** > **Layout**, tarik **VerticalArrangement** ke bawah header.
   - Di panel **Properties**, ubah **Width** menjadi `Fill parent`.
3. **Menu Catatan Keuangan:**
   - Dari **Palette** > **Layout**, tarik **HorizontalArrangement** ke dalam VerticalArrangement tadi.
   - Dari **Palette** > **User Interface**, tarik **Image** (untuk ikon) dan **Button** ke dalam HorizontalArrangement tersebut.
   - Klik **Button** tersebut, klik **Rename Component** menjadi: `Tombol_MenuCatatan`. Di panel **Properties**, ubah **Text** menjadi: `Catatan Pemasukan & Pengeluaran`.
4. **Menu Cek Tabungan:**
   - Ulangi langkah ke-3 di atas (buat HorizontalArrangement baru di bawah yang pertama).
   - Rename Button menjadi: `Tombol_MenuTabungan`. Ubah Text menjadi: `Cek Tabungan`.
5. **Menu Tabungan Target:**
   - Ulangi lagi langkah ke-3.
   - Rename Button menjadi: `Tombol_MenuTarget`. Ubah Text menjadi: `Tabungan Target`.

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

1. **Logika Logo (Kembali ke Home):** - Klik `Logo_Aplikasi` di panel kiri, tarik `when Logo_Aplikasi.Click do`.
   - Dari kategori **Control**, tarik `open another screen screenName`. Isi dengan teks pink `"HalamanUtama"`. _(Blok ini juga akan ikut tercopy ke halaman lain nanti)._
2. **Logika Menu Catatan:**
   - Di panel kiri, klik `Tombol_MenuCatatan`. Tarik blok kuning: `when Tombol_MenuCatatan.Click do`.
   - Klik kategori **Control**, tarik blok `open another screen screenName`.
   - Klik kategori **Text**, tarik blok `" "`, pasangkan dan ketik: `CatatanKeuangan`.
3. **Logika Menu Tabungan:**
   - Ulangi cara di atas untuk `Tombol_MenuTabungan`, arahkan `screenName` ke `"Tabungan"`.
4. **Logika Menu Target:**
   - Ulangi cara di atas untuk `Tombol_MenuTarget`, arahkan `screenName` ke `"TabunganTarget"`.

---

## TAHAP 3: Desain & Blocks - CatatanKeuangan

Ganti screen aktif ke **CatatanKeuangan** melalui dropdown Screen di atas. Di sini kita akan membuat form untuk memasukkan uang masuk dan keluar.

### A. Desain (Designer)

1. **Copy-Paste Header:**
   - Ganti screen kembali ke `HalamanUtama` sebentar.
   - Klik komponen `HorizontalArrangement` (Header) yang berisi Logo Anda.
   - Tekan tombol **Ctrl + C** (Copy) di keyboard Anda.
   - Ganti screen ke `CatatanKeuangan`. Tekan tombol **Ctrl + V** (Paste). Header dan Logo akan otomatis muncul beserta blok logikanya!
2. **Input Tanggal:** Dari **Palette** > **User Interface**, tarik komponen **DatePicker** ke bawah header.
   - Ubah **Text** menjadi: `Pilih Tanggal`. Rename menjadi: `Input_Tanggal`.
3. **Input Keterangan:** Tarik komponen **TextBox**.
   - Ubah **Hint** menjadi: `Keterangan (contoh: Uang Saku)`. Rename menjadi: `Input_Ket`.
4. **Input Nominal:** Tarik **TextBox** ke bawahnya.
   - Centang kotak **NumbersOnly** di Properties. Ubah **Hint** menjadi: `Nominal Uang`. Rename menjadi: `Input_Nominal`.
5. **Tombol Simpan:** Tarik dua buah **Button** berdampingan (gunakan HorizontalArrangement).
   - Tombol 1 -> Text: `Simpan Pemasukan`, Rename: `Tombol_SimpanMasuk`.
   - Tombol 2 -> Text: `Simpan Pengeluaran`, Rename: `Tombol_SimpanKeluar`.
6. **Daftar Riwayat:** Tarik dua buah **ListView** ke layar secara berurutan.
   - ListView 1 -> Rename: `List_Pemasukan`.
   - ListView 2 -> Rename: `List_Pengeluaran`.
7. **Alat Tambahan:** - Dari kategori **Storage**, tarik **TinyDB** (Rename: `Database_Kel1`).
   - Dari **User Interface**, tarik **Notifier** (Rename: `Notifikasi_Pesan`).

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

**Bagian 1: Menampilkan Tanggal**

1. Klik `Input_Tanggal`, tarik blok kuning `when Input_Tanggal.AfterDateSet do`.
2. Klik lagi `Input_Tanggal`, tarik blok hijau muda `set Input_Tanggal.Text to`. Masukkan ke dalam blok kuning.
3. Pasangkan blok `join` (dari kategori **Text**) dengan 5 lubang. Isi berurutan dengan: `Input_Tanggal.Day`, teks pink `"/"`, `Input_Tanggal.Month`, teks pink `"/"`, `Input_Tanggal.Year`.

**Bagian 2: Menyimpan Pemasukan**

1. Buat variabel List baru (kategori Variables): `initialize global name to`. Ganti nama jadi `RiwayatMasuk` dan isi dengan blok biru muda `create empty list`.
2. Tarik blok kuning `when Tombol_SimpanMasuk.Click do`.
3. **Simpan Total:** Tarik blok ungu `call Database_Kel1.StoreValue`.
   - Tag isi teks pink `"TotalMasuk"`.
   - `valueToStore` isi dengan blok Math `+`. Kiri: `GetValue` (tag `"TotalMasuk"`, default `0`). Kanan: `Input_Nominal.Text`.
4. **Update Riwayat:** Tarik blok biru muda `add items to list`.
   - `list`: blok merah `get global RiwayatMasuk`.
   - `item`: blok pink `join` (Isi 3 lubang dengan: `Input_Tanggal.Text`, teks pink `" - "`, dan `Input_Nominal.Text`).
5. **Tampilkan List:** Klik `List_Pemasukan`, tarik `set List_Pemasukan.Elements to`, pasangkan dengan `get global RiwayatMasuk`.
6. Tarik blok `ShowAlert` dari Notifier, isi pesan teks pink: `Pemasukan Tersimpan!`.

**Bagian 3: Menyimpan Pengeluaran**

- Lakukan langkah yang **sama persis** dengan Bagian 2, tetapi gunakan blok kuning `when Tombol_SimpanKeluar.Click do`.
- Gunakan variabel list baru bernama `RiwayatKeluar`.
- Gunakan tag `"TotalKeluar"`, dan tampilkan ke `List_Pengeluaran.Elements`.

---

## TAHAP 4: Desain & Blocks - Tabungan

Ganti screen aktif ke **Tabungan**. Halaman ini akan otomatis menghitung total saldo Anda.

### A. Desain (Designer)

1. **Paste Header:** Tekan **Ctrl + V** (Paste) di keyboard agar Header dan Logo kembali muncul di atas layar.
2. **Teks Saldo:** Dari **Palette** > **User Interface**, tarik komponen **Label** ke bawah header.
   - Di panel **Properties**, perbesar ukuran Font menjadi `24` dan centang **FontBold**.
   - Ubah **Text** menjadi: `Saldo Anda Saat Ini: Rp 0`.
   - Klik **Rename Component**, ubah menjadi: `Teks_TotalSaldo`.
3. **Database:** Dari **Palette** > **Storage**, tarik **TinyDB**.
   - Klik **Rename Component**, ubah menjadi: `Database_Kel1` (pastikan namanya sama dengan screen sebelumnya agar datanya tersambung).

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

1. Di panel kiri, klik `Tabungan` (ikon Screen). Tarik blok kuning: `when Tabungan.Initialize do` (artinya saat layar pertama kali dibuka).
2. Klik `Teks_TotalSaldo`, tarik blok hijau muda `set Teks_TotalSaldo.Text to`. Masukkan ke dalam blok kuning.
3. Tarik blok pink `join`.
   - Lubang pertama isi teks pink: `"Saldo Anda: Rp "`.
   - Lubang kedua isi dengan blok Math kurang `-` (biru muda).
4. Di sisi kiri blok `-`: Tarik blok ungu `call Database_Kel1.GetValue`. Isi tag dengan teks pink `"TotalMasuk"`, default `0`.
5. Di sisi kanan blok `-`: Tarik blok ungu `call Database_Kel1.GetValue`. Isi tag dengan teks pink `"TotalKeluar"`, default `0`.

---

## TAHAP 5: Desain & Blocks - TabunganTarget

Ganti screen aktif ke **TabunganTarget**.

### A. Desain (Designer)

1. **Paste Header:** Tekan **Ctrl + V** (Paste) di keyboard agar Header dan Logo kembali muncul di atas layar.
2. **Input Gambar Barang:** Dari **Palette** > **Media**, tarik **ImagePicker** ke bawah header.
   - Ubah **Text** menjadi: `Pilih Gambar Barang`. Rename menjadi: `Pilih_Gambar`.
   - Tarik komponen **Image** di bawahnya untuk melihat gambar. Rename menjadi: `Preview_Gambar`. Set Height & Width secukupnya (misal 150 pixels).
3. **Input Data:** Tarik 3 buah **TextBox** secara berurutan ke bawah.
   - TextBox 1 -> Hint: `Nama Barang`. Rename: `Input_NamaBarang`.
   - TextBox 2 -> Hint: `Harga Barang`. Centang _NumbersOnly_. Rename: `Input_HargaBarang`.
   - TextBox 3 -> Hint: `Tanggal Mulai Menabung`. Rename: `Input_TglMulai`.
4. **Simpan & Info:** - Tarik **Button**, Text: `Simpan Target`, Rename: `Tombol_SimpanTarget`.
   - Tarik **Label**, Text kosongkan dulu, centang **FontBold**, Rename: `Teks_InfoTarget`.
5. **Database & Notifier:** Tarik **TinyDB** (Rename: `Database_Kel1`) dan **Notifier**.

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

1. **Menampilkan Gambar Pilihan:**
   - Klik `Pilih_Gambar`, tarik blok kuning `when Pilih_Gambar.AfterPicking do`.
   - Klik `Preview_Gambar`, tarik blok hijau muda `set Preview_Gambar.Picture to`. Pasangkan blok hijau tua `Pilih_Gambar.Selection`.
2. **Menyimpan Data Target:**
   - Klik `Tombol_SimpanTarget`, tarik blok kuning `when Click do`.
   - Gunakan blok ungu `StoreValue` dari `Database_Kel1` sebanyak 4 kali berurutan.
   - Simpan `Input_NamaBarang.Text` ke tag `"Target_Nama"`.
   - Simpan `Input_HargaBarang.Text` ke tag `"Target_Harga"`.
   - Simpan `Input_TglMulai.Text` ke tag `"Target_Tanggal"`.
   - Simpan `Preview_Gambar.Picture` ke tag `"Target_Gambar"`.
   - Munculkan pesan Notifier `"Target Berhasil Dibuat!"`.
3. **Menampilkan Jumlah Tabungan Saat Ini:**
   - Tarik blok kuning `when TabunganTarget.Initialize do`.
   - Tarik blok hijau muda `set Teks_InfoTarget.Text to`.
   - Gunakan blok `join`. Lubang 1 ketik teks pink: `"Tabungan Saat Ini: Rp "`.
   - Lubang 2 hitung saldo persis seperti di Screen Tabungan: Blok Math `-` yang berisi (`GetValue` `"TotalMasuk"` dikurangi `GetValue` `"TotalKeluar"`).

> **PENTING:** Silakan coba Run program dari awal sampai akhir, periksa apakah input berjalan dan saldo terpotong/bertambah secara otomatis. Jangan lupa Save!

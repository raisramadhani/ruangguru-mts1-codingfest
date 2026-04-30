# Tutorial Membuat Aplikasi KELOMPOK 2 (MTsN 1 Surakarta)

Pastikan Anda sudah login ke MIT App Inventor, membuat project baru, dan berada di tampilan **Designer** (perhatikan tombol **Designer** di pojok kanan atas layar harus aktif/menyala).

---

## TAHAP 0: Membuat Halaman Login (Screen1)

Kita akan membuat halaman Login terlebih dahulu di **Screen1** (Screen bawaan saat pertama kali membuat project).

### A. Desain (Designer)

1. **Input Username:** Di sebelah kiri layar pada panel **Palette** > klik kategori **User Interface**, klik dan tarik (drag) komponen **TextBox** ke gambar HP di tengah layar (Viewer).
   - Beralih ke panel **Properties** di sebelah kanan layar. Cari kolom **Hint**, hapus isinya dan ketik: `Masukkan Username`.
   - Beralih ke panel **Components** (di sebelah kanan gambar HP). Klik komponen `TextBox1`, lalu klik tombol **Rename** di bawahnya. Ubah namanya menjadi: `InputUsername` lalu klik OK.
2. **Input Password:** Dari panel **Palette** > kategori **User Interface**, tarik komponen **PasswordTextBox** ke gambar HP di bawah Username.
   - Di panel **Properties**, cari kolom **Hint** dan ubah menjadi: `Masukkan Password`.
   - Di panel **Components**, klik komponennya lalu klik **Rename**, ubah menjadi: `InputPassword`.
3. **Tombol Login:** Dari panel **Palette** > kategori **User Interface**, tarik komponen **Button** ke gambar HP.
   - Di panel **Properties**, cari kolom **Text** dan ubah tulisannya menjadi: `Masuk / Login`.
   - Di panel **Components**, klik **Rename**, ubah menjadi: `Tombol_Masuk`.
4. **Pesan Notifikasi:** Dari panel **Palette** > kategori **User Interface**, tarik komponen **Notifier** ke gambar HP. (Catatan: Komponen ini tidak akan terlihat di layar HP, melainkan muncul di bagian bawah layar sebagai _Non-visible components_). Biarkan namanya tetap `Notifier1` di panel Components.

### B. Kode (Blocks)

Pindah ke tampilan **Blocks** dengan cara mengklik tombol **Blocks** di pojok kanan atas layar.

1. **Memulai Tombol:** Di panel sebelah kiri bawah (daftar komponen), cari dan klik `Tombol_Masuk`. Akan muncul laci berisi blok, tarik blok kuning paling atas: `when Tombol_Masuk.Click do` ke area putih yang kosong.
2. **Membuat Syarat:** Di panel kiri atas (Built-in), klik kategori **Control** (warna oranye), tarik blok `if then else` ke dalam celah blok kuning tadi.
3. **Mengatur Syarat Login (Bagian if):**
   - Di panel kiri atas, klik kategori **Logic** (hijau terang), tarik blok `and` pasangkan ke sebelah kanan tulisan `if`.
   - **Di lubang kiri `and`:** Klik kategori **Logic** lagi, tarik blok sama dengan `=`.
     - **Sisi kirinya:** Klik komponen `InputUsername` di panel kiri bawah, scroll ke bawah dan cari blok hijau tua `InputUsername.Text`, tarik ke sisi kiri blok `=`.
     - **Sisi kanannya:** Klik kategori **Text** (warna pink), tarik blok kosong `" "` paling atas. Pasangkan ke sisi kanan `=`, lalu klik bagian tengahnya dan ketik `123`.
   - **Di lubang kanan `and`:** Lakukan hal yang sama. Tarik blok `=` dari kategori **Logic**.
     - **Sisi kirinya:** Klik komponen `InputPassword` di panel kiri bawah, cari dan tarik blok hijau tua `InputPassword.Text`.
     - **Sisi kanannya:** Ambil blok teks pink kosong `" "` dari kategori **Text**, pasangkan lalu ketik `123`.
4. **Jika Login Benar (Bagian then):**
   - Di panel kiri bawah, klik komponen `Notifier1`, cari dan tarik blok ungu `call Notifier1.ShowAlert notice`. Pasangkan ke dalam celah `then`.
   - Klik kategori **Text**, ambil blok kosong `" "`, pasangkan ke sebelah `notice`, dan ketik: `Selamat datang kembali!`.
   - Di panel kiri atas, klik kategori **Control**, scroll agak ke bawah dan tarik blok `open another screen screenName` ke bawah blok ungu tadi.
   - Ambil lagi blok teks pink kosong `" "` dari kategori **Text**, pasangkan, dan ketik persis: `HalamanUtama`.
5. **Jika Login Salah (Bagian else):**
   - Lakukan cara yang sama: klik `Notifier1` di panel kiri bawah, tarik blok ungu `call Notifier1.ShowAlert notice` ke dalam celah `else`.
   - Ambil blok teks pink `" "` dari kategori **Text** dan ketik: `Password Salah kak`.

---

## TAHAP 1: Membuat Screen Baru

Sekarang kita perlu membuat 4 Screen baru sesuai dengan konsep aplikasi pengelolaan tabungan Anda.

1. Di bagian paling atas layar App Inventor, klik tombol **Add Screen**.
2. Akan muncul kotak pop-up. Ketik nama: `HalamanUtama` lalu klik OK.
3. Ulangi langkah 1, klik **Add Screen**, ketik nama: `RiwayatTrans` lalu klik OK.
4. Ulangi langkah 1, klik **Add Screen**, ketik nama: `InputUang` lalu klik OK.
5. Ulangi langkah 1, klik **Add Screen**, ketik nama: `WishlistBarang` lalu klik OK.

_(Catatan: Pastikan penulisan nama Screen persis seperti di atas tanpa spasi, karena huruf besar/kecil sangat berpengaruh di App Inventor)._

> **PENTING:** Silakan coba Connect/Run program di HP Anda (Pilih menu Connect > AI Companion) untuk memastikan bisa login dengan username "123" dan password "123".

---

## TAHAP 2: Desain & Blocks - HalamanUtama

Pastikan di bagian atas layar App Inventor, Anda sedang berada di Screen **HalamanUtama** (Cek kotak dropdown). Kembali ke mode **Designer**. Di sini kita akan membuat Header dengan Logo terlebih dahulu untuk dicopy ke layar lain.

### A. Desain (Designer)

1. **Membuat Header & Logo (Untuk di-copy nanti):**
   - Dari panel **Palette** > klik kategori **Layout**, tarik **HorizontalArrangement** ke layar HP bagian paling atas.
   - Dari panel **Palette** > klik kategori **User Interface**, tarik komponen **Image** dan masukkan _ke dalam_ kotak HorizontalArrangement tadi.
   - Di panel **Components**, klik komponen gambar tersebut, klik tombol **Rename**, ubah namanya menjadi: `Logo_Aplikasi`.
   - Di panel **Properties**, scroll ke bawah, cari kotak centang bernama **Clickable** dan **wajib Anda centang** (agar logo bisa ditekan untuk kembali ke halaman utama).
   - _(Opsional)_ Tarik komponen **Label** letakkan di sebelah logo jika ingin memberi teks judul aplikasi MTsN 1.
2. **Teks Saldo:** Dari panel **Palette** > kategori **User Interface**, tarik komponen **Label** ke layar HP di bawah header.
   - Di panel **Properties**, perbesar ukuran **FontSize** menjadi `24` dan centang kotak **FontBold**.
   - Ubah kolom **Text** menjadi: `Saldo Anda Saat Ini: Rp 0`.
   - Di panel **Components**, klik **Rename**, ubah menjadi: `Teks_SaldoSekarang`.
3. **Preview Riwayat:** - Tarik **Label** baru ke bawah saldo, ubah Text di panel Properties: `Riwayat Terakhir:`.
   - Tarik komponen **ListView** ke bawah Label tersebut, cari menu **Height** di Properties, klik lalu ubah menjadi `15 Percent`. Di panel Components Rename: `Preview_Riwayat`.
4. **Preview Wishlist:** - Tarik **Label** baru, ubah Text: `Wishlist Kebutuhan:`.
   - Tarik komponen **ListView** di bawahnya, ubah **Height** menjadi `15 Percent`. Rename: `Preview_Wishlist`.
5. **Tombol Menu:** Dari panel **Palette** > **User Interface**, tarik 3 buah **Button** ke layar secara berurutan.
   - Button 1 -> Rename: `Menu_Riwayat`, ubah Text: `Buka Riwayat Lengkap`.
   - Button 2 -> Rename: `Menu_Input`, ubah Text: `Input Pemasukan & Pengeluaran`.
   - Button 3 -> Rename: `Menu_Wishlist`, ubah Text: `Buka Wishlist Barang`.
6. **Database (Wajib):** Dari panel **Palette** > kategori **Storage**, tarik komponen **TinyDB** ke layar. Rename menjadi: `DB_Kel2`.

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

1. **Logika Logo (Kembali ke Home):**
   - Di panel kiri bawah, klik `Logo_Aplikasi`, tarik blok kuning `when Logo_Aplikasi.Click do`.
   - Di panel kiri atas, klik kategori **Control**, tarik blok `open another screen screenName`. Ambil blok teks pink `" "` dari kategori **Text** dan ketik: `HalamanUtama`.
2. **Logika Navigasi Menu:**
   - Di panel kiri bawah, klik `Menu_Riwayat`. Tarik blok kuning: `when Menu_Riwayat.Click do`.
   - Dari kategori **Control**, tarik blok `open another screen screenName`. Pasangkan teks pink `" "` dari kategori **Text** lalu ketik: `RiwayatTrans`.
   - Lakukan cara yang **sama persis** untuk `Menu_Input` (arahkan teks pink ke `"InputUang"`) dan `Menu_Wishlist` (arahkan teks pink ke `"WishlistBarang"`).
3. **Memuat Data Saldo & Preview:**
   - Di panel kiri bawah, klik nama screen `HalamanUtama` (ikon HP). Tarik blok kuning `when HalamanUtama.Initialize do`.
   - **Set Saldo:** Klik komponen `Teks_SaldoSekarang`, tarik blok hijau muda `set Teks_SaldoSekarang.Text to`. Masukkan ke blok kuning.
     - Klik kategori **Text**, tarik blok `join` dan pasangkan.
     - Lubang atas `join`: ambil teks pink `" "` ketik `"Saldo: Rp "`.
     - Lubang bawah `join`: ambil blok Math (biru muda) kurang `-`. Sisi kirinya isi dengan blok ungu `call DB_Kel2.GetValue` (tag teks pink `"SaldoMasuk"`, default angka `0`). Sisi kanannya isi dengan `call DB_Kel2.GetValue` (tag teks pink `"SaldoKeluar"`, default angka `0`).
   - **Set Preview:** Klik komponen `Preview_Riwayat`, tarik blok hijau muda `set Preview_Riwayat.Elements to`. Pasangkan dengan `call DB_Kel2.GetValue` (Isi tag dengan teks pink `"DataRiwayat"`, dan isi `valueIfTagNotThere` dengan blok biru muda `create empty list` dari kategori **Lists**).
   - Lakukan hal yang sama untuk `set Preview_Wishlist.Elements to` dengan memanggil tag `"ListKebutuhan"`.

---

## TAHAP 3: Desain & Blocks - InputUang

Ganti screen aktif ke **InputUang** melalui dropdown Screen di atas. Kembali ke mode **Designer**.

### A. Desain (Designer)

1. **Copy-Paste Header:**
   - Ganti screen kembali ke `HalamanUtama` sebentar.
   - Di panel **Components**, klik komponen `HorizontalArrangement` (Header) yang berisi Logo Anda.
   - Tekan tombol **Ctrl + C** (Copy) di keyboard Anda.
   - Ganti screen ke `InputUang`. Tekan tombol **Ctrl + V** (Paste). Header dan Logo akan otomatis muncul beserta blok logikanya.
2. **Input Keterangan:** Dari panel **Palette** > **User Interface**, tarik komponen **TextBox** ke bawah header.
   - Di panel **Properties**, ubah **Hint** menjadi: `Keterangan (Contoh: Jajan / Nabung)`.
   - Di panel **Components**, Rename menjadi: `Input_Ket`.
3. **Input Nominal:** Tarik **TextBox** kedua ke bawahnya.
   - Centang kotak **NumbersOnly** di Properties. Ubah **Hint** menjadi: `Nominal Uang`.
   - Rename menjadi: `Input_Nominal`.
4. **Tombol Simpan:** (Agar rapi berdampingan, dari panel **Layout** tarik _HorizontalArrangement_, lalu masukkan 2 **Button** ke dalamnya).
   - Button 1 -> Text: `Simpan Pemasukan`, Rename: `Tombol_Masuk`.
   - Button 2 -> Text: `Simpan Pengeluaran`, Rename: `Tombol_Keluar`.
5. **Database & Notifikasi:** Dari kategori **Storage**, tarik **TinyDB** (Rename: `DB_Kel2`). Dari kategori **User Interface**, tarik **Notifier** (Rename: `Notifikasi_Pesan`).

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

1. **Variabel List:** Di panel kiri atas, klik kategori **Variables**, tarik blok `initialize global name to`. Ganti tulisan `name` jadi `RiwayatSmt`. Klik kategori **Lists**, ambil blok `create empty list` dan pasangkan.
2. **Simpan Pemasukan:**
   - Di panel kiri bawah, klik `Tombol_Masuk`, tarik blok kuning `when Tombol_Masuk.Click do`.
   - **Tambah Saldo Masuk:** Klik `DB_Kel2`, tarik blok ungu `call DB_Kel2.StoreValue` pasang ke dalam blok kuning.
     - Isi `tag` dengan teks pink `" "` dan ketik `"SaldoMasuk"`.
     - Isi `valueToStore` dengan blok Math tambah `+`. Sisi kirinya isi dengan `call DB_Kel2.GetValue` (tag `"SaldoMasuk"`, default `0`). Sisi kanannya isi dengan blok hijau tua `Input_Nominal.Text`.
   - **Simpan ke List Riwayat:**
     - Klik kategori **Variables**, tarik blok `set to`. Pilih panah kecilnya ke `global RiwayatSmt`. Pasangkan dengan `call DB_Kel2.GetValue` (isi tag `"DataRiwayat"` dan default `create empty list`). Taruh di bawah StoreValue pertama tadi.
     - Klik kategori **Lists**, tarik blok biru muda `add items to list`.
       - Di lubang `list` isi dengan blok merah `get global RiwayatSmt`.
       - Di lubang `item` isi dengan blok pink `join` dari kategori **Text**.
       - **PENTING (Menambah Lubang Join):** Klik ikon **gir (gear) biru** pada blok `join` tersebut. Tarik dua buah blok `string` dari kiri ke kanan sehingga sekarang ada **4 lubang**. Klik lagi ikon gir biru.
       - Isi lubang 1: Ambil teks pink `" "` ketik `"[+] "`.
       - Isi lubang 2: Ambil blok hijau tua `Input_Ket.Text`.
       - Isi lubang 3: Ambil teks pink `" "` ketik `" - Rp "`.
       - Isi lubang 4: Ambil blok hijau tua `Input_Nominal.Text`.
     - Terakhir, simpan list tersebut: Tarik `call DB_Kel2.StoreValue` isi tag `"DataRiwayat"` dan `valueToStore` isi dengan `get global RiwayatSmt`.
   - **Notifikasi:** Klik komponen `Notifikasi_Pesan`, tarik blok ungu `call Notifikasi_Pesan.ShowAlert notice`. Isi pesan dengan teks pink: `"Pemasukan Berhasil Disimpan!"`.
3. **Simpan Pengeluaran:**
   - Lakukan langkah yang **sama persis** dengan logika pemasukan (menggunakan variabel yang sama), tetapi:
   - Gunakan blok kuning `when Tombol_Keluar.Click do`.
   - Ubah teks pink `tag` pada saldonya menjadi `"SaldoKeluar"`.
   - Pada bagian `join` di _add items to list_, ubah teks pink di lubang 1 menjadi `"[-] "`.
   - Ubah pesan notifikasi teks pink menjadi: `"Pengeluaran Berhasil Dicatat!"`.

---

## TAHAP 4: Desain & Blocks - RiwayatTrans

Ganti screen aktif ke **RiwayatTrans** via dropdown. Beralih ke mode **Designer**.

### A. Desain (Designer)

1. **Paste Header:** Tekan **Ctrl + V** (Paste) di keyboard agar Header dan Logo kembali muncul di atas layar.
2. Tarik **Label** judul di bawah header, ubah Text: `Seluruh Riwayat Transaksi Anda`. Centang _FontBold_.
3. Tarik komponen **ListView**. Di panel **Properties**, ubah menu **Height** menjadi `Fill parent` dan **Width** menjadi `Fill parent` (agar daftar memenuhi layar). Rename: `Daftar_SemuaRiwayat`.
4. Tarik **Button** di paling bawah. Ubah Text: `Kembali ke Beranda`. Rename: `Tombol_Kembali`.
5. Jangan lupa tarik komponen **TinyDB** (Rename: `DB_Kel2`).

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

1. **Tampilkan Data:** Klik screen `RiwayatTrans` di panel kiri, tarik blok kuning `when RiwayatTrans.Initialize do`.
2. Klik komponen `Daftar_SemuaRiwayat`, tarik blok hijau muda `set Daftar_SemuaRiwayat.Elements to`. Masukkan ke blok kuning.
3. Pasangkan dengan blok ungu `call DB_Kel2.GetValue`. Isi `tag`-nya dengan teks pink `" "` lalu ketik `"DataRiwayat"`. Isi `valueIfTagNotThere` dengan blok biru muda `create empty list`.
4. **Tombol Kembali:** Klik `Tombol_Kembali`, tarik blok kuning `when Tombol_Kembali.Click do`. Dari kategori **Control**, tarik `open another screen screenName` dan isi teks pink `"HalamanUtama"`.

---

## TAHAP 5: Desain & Blocks - WishlistBarang

Ganti screen aktif ke **WishlistBarang**. Kembali ke mode **Designer**.

### A. Desain (Designer)

1. **Paste Header:** Tekan **Ctrl + V** (Paste) di keyboard agar Header dan Logo kembali muncul di atas layar.
2. **Input Nama Barang:** Dari panel **Palette**, tarik **TextBox** ke bawah header. Ubah Hint: `Nama Barang Impian`. Rename: `Input_NamaBarang`.
3. **Pilih Kategori (Penting):** Dari panel **Palette** > **User Interface**, tarik komponen **Spinner**.
   - Di panel **Properties**, cari kotak bernama **ElementsFromString**. Ketik persis seperti ini (tanpa spasi setelah tanda koma): `Kebutuhan,Keinginan`.
   - Di panel **Components**, Rename: `Pilih_Kategori`.
4. **Tombol Simpan:** Tarik komponen **Button**. Ubah Text: `Simpan Wishlist`. Rename: `Tombol_SimpanWishlist`.
5. **Daftar Kebutuhan:** Tarik **Label** (Ubah Text: `Daftar Kebutuhan`), lalu tarik **ListView** tepat di bawahnya (Rename: `List_Kebutuhan`).
6. **Daftar Keinginan:** Tarik **Label** (Ubah Text: `Daftar Keinginan`), lalu tarik **ListView** tepat di bawahnya (Rename: `List_Keinginan`).
7. Tarik **TinyDB** dari Storage (Rename: `DB_Kel2`).

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

1. Di kategori **Variables**, buat 2 variabel List global menggunakan `initialize global name to`.
   - Yang pertama beri nama `ListKebutuhanSmt` dan pasangkan dengan `create empty list`.
   - Yang kedua beri nama `ListKeinginanSmt` dan pasangkan dengan `create empty list`.
2. Di panel kiri bawah, klik `Tombol_SimpanWishlist`, tarik blok kuning `when Tombol_SimpanWishlist.Click do`.
3. Dari kategori **Control** (kiri atas), tarik blok `if then else` masukkan ke dalam blok kuning.
4. **Kondisi (Bagian if):** Dari kategori **Logic**, tarik blok sama dengan `=`.
   - Sisi kiri `=`: Klik `Pilih_Kategori`, tarik blok hijau tua `Pilih_Kategori.Selection`.
   - Sisi kanan `=`: Ambil teks pink `" "` dan ketik `"Kebutuhan"`.
5. **Simpan ke Kebutuhan (Bagian then):**
   - Klik kategori **Variables**, tarik blok `set to` pilih `global ListKebutuhanSmt`. Pasangkan dengan `call DB_Kel2.GetValue` (tag teks pink `"ListKebutuhan"`, default `create empty list`).
   - Klik kategori **Lists**, tarik `add items to list`. Lubang `list` isi dengan `get global ListKebutuhanSmt`. Lubang `item` isi dengan blok hijau tua `Input_NamaBarang.Text`.
   - Klik `DB_Kel2`, tarik `StoreValue` tag `"ListKebutuhan"` dan `valueToStore` isi dengan `get global ListKebutuhanSmt`.
   - Update layar: Klik `List_Kebutuhan`, tarik `set List_Kebutuhan.Elements to` dan pasangkan dengan `get global ListKebutuhanSmt`.
6. **Simpan ke Keinginan (Bagian else):**
   - Lakukan hal yang **sama persis** seperti langkah 5 ke dalam celah `else`.
   - Namun, ganti semuanya menggunakan variabel `ListKeinginanSmt`, tag `"ListKeinginan"`, dan tampilkan ke komponen `List_Keinginan.Elements`.
7. **Memunculkan Data Saat Dibuka:** - Di panel kiri bawah, klik nama screen `WishlistBarang` (ikon HP), tarik blok kuning `when WishlistBarang.Initialize do`.
   - Tarik `set List_Kebutuhan.Elements to` pasangkan dengan `call DB_Kel2.GetValue` (tag teks pink `"ListKebutuhan"`, default `create empty list`).
   - Di bawahnya, tarik `set List_Keinginan.Elements to` pasangkan dengan `call DB_Kel2.GetValue` (tag teks pink `"ListKeinginan"`, default `create empty list`).

> **PENTING:** Silakan coba Connect/Run program dari awal sampai akhir di HP Anda, periksa apakah input berjalan, saldo terpotong, dan wishlist berhasil terpisah ke kategori masing-masing. Jangan lupa Save project Anda (Projects > Save project)!

---

## TAHAP 6: Membuat Fitur Hapus Semua Data (Reset)

Karena aplikasi ini akan digunakan berulang kali, kita membutuhkan tombol untuk mereset (menghapus) seluruh data tabungan dan daftar barang agar kembali kosong. Kita akan menaruh tombol ini di **HalamanUtama**.

Pastikan Anda mengganti screen aktif kembali ke **HalamanUtama** (melalui kotak dropdown Screen di bagian atas). Beralihlah kembali ke mode **Designer**.

### A. Desain (Designer)

1. **Tombol Hapus:** Dari panel **Palette** > kategori **User Interface**, tarik komponen **Button** ke layar HP, letakkan di posisi paling bawah (di bawah tombol-tombol menu lainnya).
      - Di panel **Properties**, cari menu **BackgroundColor** dan ubah menjadi warna merah (`Red`) agar menjadi penanda bahwa ini adalah tombol yang penting/berbahaya.
      - Masih di panel **Properties**, ubah tulisan di kolom **Text** menjadi: `Hapus Semua Data`.
      - Di panel **Components**, klik komponennya lalu klik **Rename**, ubah menjadi: `Tombol_HapusData`.
2. **Notifikasi:** Dari panel **Palette** > kategori **User Interface**, tarik komponen **Notifier** ke gambar HP.
      - Di panel **Components**, biarkan namanya tetap `Notifier1` (ingat, komponen ini tidak akan terlihat langsung di layar HP, tapi akan muncul di bagian bawah layar sebagai _Non-visible components_).

### B. Kode (Blocks)

Pindah ke tampilan **Blocks** dengan mengklik tombol Blocks di pojok kanan atas.

1. **Logika Tombol Hapus:** Di panel sebelah kiri bawah, cari dan klik `Tombol_HapusData`. Tarik blok kuning `when Tombol_HapusData.Click do` ke area putih yang kosong.
2. **Menghapus Database:** Di panel kiri bawah, klik komponen database `DB_Kel2`. Cari dan tarik blok ungu `call DB_Kel2.ClearAll` (blok ini berfungsi menyapu bersih semua tag dan data yang pernah kita simpan). Pasangkan ke dalam celah blok kuning tadi.
3. **Mengembalikan Tampilan Menjadi Nol:** Setelah data di dalam _database_ terhapus, kita harus langsung memperbarui tampilan layar agar ikut menjadi nol/kosong saat itu juga.
      - **Reset Saldo:** Klik `Teks_SaldoSekarang`, tarik blok hijau muda `set Teks_SaldoSekarang.Text to`. Masukkan tepat di bawah blok ungu `ClearAll`. Ambil blok teks pink `" "` dari kategori **Text** dan ketik persis: `Saldo: Rp 0`.
      - **Reset Preview Riwayat:** Klik `Preview_Riwayat`, tarik blok hijau muda `set Preview_Riwayat.Elements to`. Klik kategori **Lists** (warna biru muda), tarik blok `create empty list` dan pasangkan.
      - **Reset Preview Wishlist:** Lakukan hal yang sama. Klik `Preview_Wishlist`, tarik blok hijau muda `set Preview_Wishlist.Elements to` dan pasangkan juga dengan blok `create empty list` dari kategori **Lists**.
4. **Memunculkan Pesan Sukses:** Terakhir, klik komponen `Notifier1` di panel kiri bawah. Tarik blok ungu `call Notifier1.ShowAlert notice`. Ambil blok teks pink `" "` dari kategori **Text**, pasangkan ke sebelah tulisan `notice`, dan ketik: `Seluruh data berhasil direset!`.

> **PENTING:** Silakan Connect/Run ulang aplikasi Anda di HP. Coba tekan tombol "Hapus Semua Data". Jika kode Anda benar, saldo akan langsung berubah menjadi Rp 0, dan semua daftar (riwayat & wishlist) akan langsung kosong tak tersisa.
>
> Selamat! Aplikasi kelompok Anda sudah lengkap dan siap digunakan. Jangan lupa simpan hasil kerja Anda dengan klik menu **Projects > Save project**.

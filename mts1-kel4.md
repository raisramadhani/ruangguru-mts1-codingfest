# Tutorial Membuat Aplikasi KELOMPOK 4 (MTsN 1 Surakarta)

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

Sekarang kita perlu membuat 5 Screen baru sesuai dengan konsep aplikasi Anda.

1. Di bagian paling atas layar App Inventor, klik tombol **Add Screen**.
2. Akan muncul kotak pop-up. Ketik nama: `HalamanUtama` lalu klik OK.
3. Ulangi langkah 1, klik **Add Screen**, ketik nama: `InputUang` lalu klik OK.
4. Ulangi langkah 1, klik **Add Screen**, ketik nama: `Analisis` lalu klik OK.
5. Ulangi langkah 1, klik **Add Screen**, ketik nama: `Challenge` lalu klik OK.
6. Ulangi langkah 1, klik **Add Screen**, ketik nama: `Riwayat` lalu klik OK.

_(Catatan: Pastikan penulisan nama Screen persis seperti di atas tanpa spasi, karena huruf besar/kecil sangat berpengaruh)._

> **PENTING:** Silakan coba Connect/Run program di HP Anda (Pilih menu Connect > AI Companion) untuk memastikan bisa login dengan username "123" dan password "123".

---

## TAHAP 2: Desain & Blocks - HalamanUtama

Pastikan di bagian atas layar App Inventor, Anda sedang berada di Screen **HalamanUtama** (Cek kotak dropdown). Kembali ke mode **Designer**.

### A. Desain (Designer)

1. **Membuat Header & Logo (Untuk di-copy nanti):**
   - Dari panel **Palette** > klik kategori **Layout**, tarik **HorizontalArrangement** ke layar HP bagian paling atas.
   - Dari panel **Palette** > klik kategori **User Interface**, tarik komponen **Image** dan masukkan _ke dalam_ kotak HorizontalArrangement tadi.
   - Di panel **Components**, klik komponen gambar tersebut, klik tombol **Rename**, ubah namanya menjadi: `Logo_Aplikasi`.
   - Di panel **Properties**, scroll ke bawah, cari kotak centang bernama **Clickable** dan **wajib Anda centang** (agar logo bisa ditekan untuk kembali ke halaman utama).
   - _(Opsional)_ Tarik komponen **Label** letakkan di sebelah logo jika ingin memberi teks judul aplikasi MTsN 1.
2. **Info Saldo & Pengeluaran:**
   - Dari panel **Palette** > kategori **User Interface**, tarik komponen **Label** ke layar HP di bawah kotak header.
   - Di panel **Properties**, ubah **Text** menjadi `Saldo: Rp 0`, perbesar **FontSize** jadi `24`, dan centang kotak **FontBold**. Di panel **Components**, Rename menjadi: `Teks_SaldoSekarang`.
   - Tarik komponen **Label** kedua ke bawah Label Saldo tadi. Di panel Properties, ubah **Text** menjadi `Total Pengeluaran: Rp 0`. Di panel Components, Rename menjadi: `Teks_TotalPengeluaran`.
3. **Tombol Menu:** Dari panel **Palette** > **User Interface**, tarik 4 buah komponen **Button** secara berurutan dari atas ke bawah.
   - Button 1 -> Di panel Components Rename: `Menu_Input`. Di panel Properties ubah Text: `Tambah Data Keuangan`.
   - Button 2 -> Rename: `Menu_Analisis`. Ubah Text: `Analisis Keuangan`.
   - Button 3 -> Rename: `Menu_Challenge`. Ubah Text: `Challenge Menabung`.
   - Button 4 -> Rename: `Menu_Riwayat`. Ubah Text: `Riwayat Transaksi`.
4. **Database (Wajib):** Dari panel **Palette** > kategori **Storage**, tarik komponen **TinyDB** ke layar HP. Di panel **Components**, Rename menjadi `DB_Kel4`.

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

1. **Logika Logo (Kembali ke Home):**
   - Di panel kiri bawah, klik komponen `Logo_Aplikasi`. Tarik blok kuning: `when Logo_Aplikasi.Click do`.
   - Di panel kiri atas, klik kategori **Control**, scroll ke bawah dan tarik blok `open another screen screenName`. Ambil blok teks pink `" "` dari kategori **Text** dan ketik: `HalamanUtama`.
2. **Logika Navigasi Menu:**
   - Di panel kiri bawah, klik `Menu_Input`. Tarik blok kuning `when Menu_Input.Click do`.
   - Dari kategori **Control**, tarik blok `open another screen screenName`. Ambil teks pink `" "` lalu ketik: `InputUang`.
   - Lakukan langkah yang **sama persis** untuk ketiga tombol lainnya: klik tombolnya di panel kiri, ambil blok _Click_, arahkan layar ke masing-masing teks pink yaitu `"Analisis"`, `"Challenge"`, dan `"Riwayat"`.
3. **Menampilkan Saldo (Saat Layar Dibuka):**
   - Di panel kiri bawah, klik nama screen `HalamanUtama` (ikon HP). Tarik blok kuning `when HalamanUtama.Initialize do`.
   - Klik komponen `Teks_SaldoSekarang`, tarik blok hijau muda `set Teks_SaldoSekarang.Text to`. Masukkan ke dalam blok kuning.
     - Klik kategori **Text**, tarik blok `join` dan pasangkan.
     - Lubang atas `join`: Ambil teks pink `" "` lalu ketik `"Saldo: Rp "`.
     - Lubang bawah `join`: Klik kategori **Math**, tarik blok kurang `-`. Sisi kirinya isi dengan `call DB_Kel4.GetValue` dari `DB_Kel4` (isi tag dengan teks pink `"SaldoMasuk"`, default angka `0` dari Math). Sisi kanannya isi dengan `call DB_Kel4.GetValue` (tag teks pink `"SaldoKeluar"`, default angka `0`).
   - Klik komponen `Teks_TotalPengeluaran`, tarik `set Teks_TotalPengeluaran.Text to`.
     - Gunakan blok `join` lagi. Lubang atas ketik teks pink `"Total Pengeluaran: Rp "`. Lubang bawah isi langsung dengan `call DB_Kel4.GetValue` (tag teks pink `"SaldoKeluar"`, default angka `0`).

---

## TAHAP 3: Desain & Blocks - InputUang

Ganti screen aktif ke **InputUang** melalui dropdown. Kembali ke mode **Designer**.

### A. Desain (Designer)

1. **Copy-Paste Header:**
   - Ganti screen kembali ke `HalamanUtama` sebentar.
   - Di panel **Components**, klik komponen `HorizontalArrangement` (Header) yang berisi Logo Anda.
   - Tekan tombol **Ctrl + C** (Copy) di keyboard Anda.
   - Ganti screen ke `InputUang`. Tekan tombol **Ctrl + V** (Paste). Header dan Logo akan otomatis muncul beserta blok logikanya.
2. **Input Keterangan:** Dari panel **Palette** > **User Interface**, tarik komponen **TextBox** ke bawah header.
   - Di panel **Properties**, ubah **Hint** menjadi: `Keterangan Transaksi`.
   - Di panel **Components**, Rename menjadi: `Input_Ket`.
3. **Input Nominal:** Tarik **TextBox** kedua ke bawahnya.
   - Di panel **Properties**, centang kotak **NumbersOnly**. Ubah **Hint** menjadi: `Nominal Uang`.
   - Di panel **Components**, Rename menjadi: `Input_Nominal`.
4. **Kategori Pengeluaran (Sangat Penting):** Dari panel **Palette** > **User Interface**, tarik komponen **Spinner** ke layar.
   - Di panel **Properties**, cari kotak bernama **ElementsFromString**. Ketik persis seperti ini _(tanpa spasi setelah tanda koma)_: `Makan,Jajan,Transport`.
   - Di panel **Components**, Rename menjadi: `Kategori_Keluar`.
5. **Tombol Simpan:** Dari panel **Palette**, tarik 2 buah **Button**.
   - Button 1 -> Rename komponen: `Simpan_Pemasukan`. Ubah Text di Properties: `Simpan sebagai Pemasukan`.
   - Button 2 -> Rename komponen: `Simpan_Pengeluaran`. Ubah Text di Properties: `Simpan sebagai Pengeluaran`.
6. **Database & Notifikasi:** Dari kategori **Storage**, tarik **TinyDB** (Rename: `DB_Kel4`). Dari kategori **User Interface**, tarik **Notifier** (Rename: `Notifikasi_Pesan`).

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

1. **Buat Variabel List:** Di panel kiri atas, klik kategori **Variables**, tarik blok `initialize global name to`. Ganti tulisan `name` jadi `RiwayatSmt`. Klik kategori **Lists** (biru muda), ambil blok `create empty list` dan pasangkan.
2. **Menyimpan Pemasukan:**
   - Di panel kiri bawah, klik `Simpan_Pemasukan`, tarik blok kuning `when Simpan_Pemasukan.Click do`.
   - Klik `DB_Kel4`, tarik blok ungu `call DB_Kel4.StoreValue`. Pasang ke blok kuning.
     - Isi `tag` dengan teks pink `" "` lalu ketik `"SaldoMasuk"`.
     - Isi `valueToStore` dengan mengklik kategori **Math**, tarik blok tambah `+`. Sisi kirinya isi dengan `call DB_Kel4.GetValue` (tag teks pink `"SaldoMasuk"`, default angka `0`). Sisi kanannya isi dengan mengklik `Input_Nominal` lalu ambil blok hijau tua `Input_Nominal.Text`.
   - **Simpan List Riwayat:** Klik kategori **Variables**, tarik blok `set to` pilih `global RiwayatSmt`. Pasangkan dengan `call DB_Kel4.GetValue` (tag teks pink `"DataRiwayat"`, default `create empty list` dari kategori Lists).
   - Klik kategori **Lists**, tarik blok biru muda `add items to list`.
     - Lubang `list`: ambil blok merah `get` dari kategori Variables, pilih `global RiwayatSmt`.
     - Lubang `item`: klik kategori **Text**, ambil blok pink `join`. Lubang atas isi dengan teks pink `"[+] Pemasukan: Rp "`. Lubang bawah isi dengan blok hijau tua `Input_Nominal.Text`.
   - Klik `DB_Kel4`, tarik `call DB_Kel4.StoreValue`. Isi tag dengan teks pink `"DataRiwayat"` dan `valueToStore` dengan blok merah `get global RiwayatSmt`.
   - Munculkan Notifikasi: Klik `Notifikasi_Pesan`, tarik `call Notifikasi_Pesan.ShowAlert notice`. Isi pesan dengan teks pink `"Pemasukan Tersimpan!"`.
3. **Menyimpan Pengeluaran (SANGAT PENTING):**
   - Klik `Simpan_Pengeluaran`, tarik blok kuning `when Simpan_Pengeluaran.Click do`.
   - **Simpan Total Keluar:** Klik `DB_Kel4`, tarik `call DB_Kel4.StoreValue`.
     - Isi `tag` dengan teks pink `"SaldoKeluar"`.
     - Isi `valueToStore` dengan blok Math tambah `+` (Kiri: `GetValue` tag `"SaldoKeluar"`, Kanan: `Input_Nominal.Text`).
   - **Simpan per Kategori Spinner:** Tarik `call DB_Kel4.StoreValue` sekali lagi dari komponen `DB_Kel4`.
     - Di bagian `tag`: Klik `Kategori_Keluar` di panel kiri, scroll dan tarik blok hijau muda `Kategori_Keluar.Selection`.
     - Di bagian `valueToStore`: Ambil blok Math `+`. Sisi kiri: panggil `call DB_Kel4.GetValue`, isi tag-nya DENGAN `Kategori_Keluar.Selection` juga, default angka `0`. Sisi kanan: `Input_Nominal.Text`. _(Logika ini sangat cerdas, App Inventor akan otomatis membuat tag berdasarkan kategori yang dipilih user!)_.
   - **Simpan List Riwayat:** Gunakan susunan `set global RiwayatSmt` dan `add items to list` persis seperti langkah pemasukan, TETAPI pada bagian `item` ubah blok `join` menjadi **3 lubang** (klik ikon gir biru pada blok join).
     - Lubang 1: Teks pink `"[-] "`.
     - Lubang 2: Ambil blok hijau muda `Kategori_Keluar.Selection`.
     - Lubang 3: Teks pink `": Rp "` (jangan lupa spasi sebelum dan sesudah titik dua).
     - _Catatan: Oh maaf, kita butuh **4 lubang**._ Klik ikon gir biru lagi tambah 1 lubang ke bawah.
     - Lubang 4: Ambil blok hijau tua `Input_Nominal.Text`.
   - Tarik `StoreValue` tag `"DataRiwayat"` isi dengan `get global RiwayatSmt`.
   - Munculkan Notifikasi: Klik `Notifikasi_Pesan`, tarik `ShowAlert notice` isi teks pink `"Pengeluaran Tersimpan!"`.

---

## TAHAP 4: Desain & Blocks - Analisis

Ganti screen aktif ke **Analisis**. Halaman ini akan mengecek seberapa boros keuangan Anda menggunakan logika matematika bertingkat.

### A. Desain (Designer)

1. **Paste Header:** Tekan **Ctrl + V** (Paste) di keyboard agar Header dan Logo kembali muncul di atas layar.
2. Dari panel **Palette** > **User Interface**, tarik komponen **Label** judul ke bawah header. Di Properties, ketik Text: `Analisis Pengeluaran Anda` dan centang **FontBold**.
3. Tarik komponen **Label** baru ke bawahnya. Di panel **Components** Rename: `Teks_PersenKategori`. Di panel Properties ubah Text sementara: `Menghitung persentase...`.
4. Tarik komponen **Label** baru lagi. Rename: `Teks_PengeluaranTerbesar`. Ubah Text: `Pengeluaran terbesar di...`.
5. Tarik komponen **Label** yang terakhir. Rename: `Teks_Status`. Di Properties perbesar **FontSize** menjadi `18`, centang **FontBold**, dan ubah Text: `Status: ...`.
6. Tarik komponen **TinyDB** dari Storage (Rename: `DB_Kel4`).

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**. Klik screen `Analisis` (ikon HP) di panel kiri, tarik blok kuning `when Analisis.Initialize do`. **(Semua logika di bawah ini HARUS masuk ke dalam blok kuning tersebut).**

1. **Ambil Data (Local Variables):**
   - Klik kategori **Variables** (oranye tua), tarik blok `initialize local name to in do` (blok panjang dengan celah _do_).
   - Klik ikon **gir (gear) biru** pada blok variabel tersebut. Tambahkan 3 nama (string) lagi ke dalam kerangka sehingga total Anda memiliki **4 baris variabel**.
   - Variabel 1 -> Ganti tulisan `name` jadi `UangMakan`. Pasangkan dengan `call DB_Kel4.GetValue` (tag teks pink `"Makan"`, default angka `0`).
   - Variabel 2 -> Ganti tulisan `name` jadi `UangJajan`. Pasangkan dengan `GetValue` (tag teks pink `"Jajan"`, default `0`).
   - Variabel 3 -> Ganti tulisan `name` jadi `UangTransport`. Pasangkan dengan `GetValue` (tag teks pink `"Transport"`, default `0`).
   - Variabel 4 -> Ganti tulisan `name` jadi `TotKeluar`. Pasangkan dengan `GetValue` (tag teks pink `"SaldoKeluar"`, **PENTING: beri default angka `1`** agar sistem tidak error pembagian nol).
2. **Menghitung Persentase:**
   - Di dalam celah _do_, klik komponen `Teks_PersenKategori`, tarik blok hijau muda `set Teks_PersenKategori.Text to`.
   - Klik kategori **Text**, ambil blok pink `join`. Klik ikon **gir biru** pada blok `join` dan jadikan ia memiliki **6 lubang**.
   - Lubang 1: Teks pink `"Makan: "`.
   - Lubang 2: Ambil blok Math kali `*`, sisi kiri isi blok Math bagi `/` (`get UangMakan` dibagi `get TotKeluar`), sisi kanan `*` isi angka `100`.
   - Lubang 3: Teks pink `"% | Jajan: "`.
   - Lubang 4: Susunan Math `*` dan `/` sama seperti di atas, tapi `get UangJajan` dibagi `get TotKeluar` kali `100`.
   - Lubang 5: Teks pink `"% | Transport: "`.
   - Lubang 6: Susunan Math `*` dan `/` sama, tapi `get UangTransport` dibagi `get TotKeluar` kali `100`.
     _(Tambahkan 1 lubang lagi di blok join untuk teks pink `"%"` di akhir)._
3. **Mencari Pengeluaran Terbesar:**
   - Masih di dalam celah _do_ di bawah blok `set Teks_PersenKategori`, klik kategori **Control**, tarik blok `if then`. Klik ikon **gir biru**, tambahkan `else if` sebanyak 2 kali dan sebuah `else` di paling bawah.
   - **Kondisi If (Makan):** Klik kategori **Logic**, tarik blok `and`.
     - Kiri `and`: Blok Math lebih besar `>` (`get UangMakan` `>` `get UangJajan`).
     - Kanan `and`: Blok Math lebih besar `>` (`get UangMakan` `>` `get UangTransport`).
     - _Jika ya (then):_ `set Teks_PengeluaranTerbesar.Text to` teks pink `"Paling banyak dipakai untuk MAKAN"`.
   - **Kondisi Else If 1 (Jajan):** Tarik blok logika `and` lagi.
     - Kiri `and`: Blok `>` (`get UangJajan` `>` `get UangMakan`).
     - Kanan `and`: Blok `>` (`get UangJajan` `>` `get UangTransport`).
     - _Jika ya (then):_ `set Teks_PengeluaranTerbesar.Text to` teks pink `"Paling banyak dipakai untuk JAJAN"`.
   - **Kondisi Else:** _Jika tidak ada kondisi di atas yang terpenuhi (then):_ Tarik `set Teks_PengeluaranTerbesar.Text to` teks pink `"Paling banyak dipakai untuk TRANSPORT"`.
4. **Status Boros/Hemat:**
   - Di bawah susunan `if` panjang tadi (masih di dalam celah _do_ variabel lokal), tarik blok `if then else` dari kategori **Control**.
   - **Kondisi If:** Tarik blok `>` dari Math. Jika `call DB_Kel4.GetValue` (tag teks pink `"SaldoKeluar"`, default `0`) **>** `call DB_Kel4.GetValue` (tag teks pink `"SaldoMasuk"`, default `0`).
   - _Bagian then:_ Klik `Teks_Status`, tarik `set Teks_Status.Text to` teks pink `"Status: KAMU BOROS!"`.
   - _Bagian else:_ Tarik `set Teks_Status.Text to` teks pink `"Status: KAMU HEMAT!"`.

---

## TAHAP 5: Desain & Blocks - Challenge

Ganti screen aktif ke **Challenge**.

### A. Desain (Designer)

1. **Paste Header:** Tekan **Ctrl + V** (Paste) di keyboard agar Header dan Logo kembali muncul di atas layar.
2. Dari panel **Palette** > **User Interface**, tarik komponen **Spinner** ke bawah header.
   - Di panel **Properties**, cari menu **ElementsFromString**. Ketik persis seperti ini (tanpa spasi setelah koma): `No Jajan Day,Hari ini nabung 10.000,Hemat 50%`.
   - Di panel **Components**, Rename: `Pilih_Challenge`.
3. Tarik komponen **Button** ke bawahnya. Ubah Text di Properties: `Terima Challenge Ini`. Rename: `Tombol_TerimaTantangan`.
4. Tarik komponen **Label** besar di paling bawah. Ubah Text: `Belum ada challenge aktif`. Di Properties, centang **FontBold**, dan ubah warna teks menjadi Oranye/Merah. Rename: `Teks_TantanganAktif`.

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**. Halaman ini logikanya sangat sederhana.

1. Di panel kiri bawah, klik komponen `Tombol_TerimaTantangan`, tarik blok kuning `when Tombol_TerimaTantangan.Click do`.
2. Klik komponen `Teks_TantanganAktif`, tarik blok hijau muda `set Teks_TantanganAktif.Text to`. Masukkan ke dalam blok kuning.
3. Pasangkan dengan mengklik `Pilih_Challenge` di panel kiri lalu tarik blok hijau tua `Pilih_Challenge.Selection`.

---

## TAHAP 6: Desain & Blocks - Riwayat

Ganti screen aktif ke **Riwayat** melalui menu dropdown. Kembali ke mode **Designer**.

### A. Desain (Designer)

1. **Paste Header:** Tekan **Ctrl + V** (Paste) di keyboard agar Header dan Logo kembali muncul di atas layar.
2. Dari panel **Palette** > **User Interface**, tarik komponen **Label** untuk judul ke bawah header. Ubah Text di Properties: `Daftar Semua Transaksi Anda`.
3. Dari kategori yang sama, tarik komponen **ListView** ke layar HP.
   - Di panel **Properties**, ubah menu **Height** dan **Width** menjadi `Fill parent` agar daftar memenuhi layar ke bawah.
   - Di panel **Components**, Rename: `Daftar_Riwayat`.
4. Dari kategori **Storage**, tarik **TinyDB** ke layar (Rename: `DB_Kel4`).

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

1. Di panel kiri bawah, klik screen `Riwayat` (ikon HP), tarik blok kuning `when Riwayat.Initialize do` (artinya saat layar dibuka).
2. Klik komponen `Daftar_Riwayat`, tarik blok hijau muda `set Daftar_Riwayat.Elements to`. Masukkan ke dalam blok kuning.
3. Pasangkan dengan blok ungu `call DB_Kel4.GetValue` dari komponen `DB_Kel4`.
4. Isi `tag`-nya dengan teks pink `" "` lalu ketik: `"DataRiwayat"`. Isi `valueIfTagNotThere` dengan blok biru muda `create empty list` dari kategori **Lists**.

> **PENTING:** Silakan coba Connect/Run program dari awal sampai akhir di HP Anda, periksa apakah perhitungan analisis persentase boros/hemat berjalan dan riwayat transaksinya muncul dengan benar. Jangan lupa Save project Anda (Projects > Save project)!

---

## TAHAP 7: Membuat Tombol Reset (Hapus Semua Data)

Karena aplikasi kita sudah bisa menyimpan banyak data, kita perlu tombol khusus untuk menghapus seluruh data tersebut jika sewaktu-waktu ingin mengulang perhitungan dari nol. Kita akan meletakkan tombol ini di **HalamanUtama**.

Pastikan di bagian atas layar App Inventor, Anda sedang berada di Screen **HalamanUtama** (Cek kotak dropdown). Kembali ke mode **Designer**.

### A. Desain (Designer)

1. **Membuat Tombol Reset:** Dari panel **Palette** > kategori **User Interface**, tarik komponen **Button** ke layar HP, letakkan di paling bawah setelah tombol Menu Riwayat Transaksi.
   - Di panel **Properties**, cari kotak **BackgroundColor** dan ubah menjadi warna **Red** (merah).
   - Masih di panel **Properties**, cari kolom **Text** dan ubah tulisannya menjadi: `Hapus Semua Data (Reset)`.
   - Cari kolom **TextColor** dan ubah menjadi **White** (putih) agar tulisan terlihat jelas.
   - Di panel **Components**, klik komponen Button tersebut, klik tombol **Rename**, ubah namanya menjadi: `Tombol_Reset` lalu klik OK.
2. **Pesan Notifikasi:** Dari panel **Palette** > kategori **User Interface**, tarik komponen **Notifier** ke gambar HP. (Komponen ini tidak akan terlihat di layar HP, melainkan masuk ke bagian _Non-visible components_ di bawah HP).
   - Di panel **Components**, klik komponen Notifier tersebut, klik **Rename**, ubah menjadi: `Notifikasi_Reset`.

### B. Kode (Blocks)

Pindah ke tampilan **Blocks** dengan mengklik tombol **Blocks** di pojok kanan atas.

1. **Memulai Tombol:** Di panel sebelah kiri bawah (daftar komponen), cari dan klik `Tombol_Reset`. Akan muncul laci blok, tarik blok kuning: `when Tombol_Reset.Click do` ke area putih yang kosong.
2. **Menghapus Seluruh Database:**
   - Di panel kiri bawah, klik komponen `DB_Kel4` (logo TinyDB).
   - Scroll ke bawah, cari dan tarik blok ungu `call DB_Kel4.ClearAll`. Masukkan ke dalam celah blok kuning `when Tombol_Reset.Click do`. _(Catatan: Blok ini sangat kuat, ia akan langsung menyapu bersih semua isi database tanpa sisa)._
3. **Mengubah Tampilan Saldo Jadi Nol:**
   - Agar tulisan saldo di layar utama langsung ikut berubah saat ditekan, klik komponen `Teks_SaldoSekarang` di panel kiri. Tarik blok hijau muda `set Teks_SaldoSekarang.Text to` ke bawah blok ungu tadi.
   - Klik kategori **Text** (warna pink), tarik blok `join` dan pasangkan.
   - Lubang atas `join`: Ambil teks pink kosong `" "` lalu ketik `"Saldo: Rp "`.
   - Lubang bawah `join`: Ambil teks pink kosong `" "` lagi lalu ketik angka `"0"`.
4. **Mengubah Tampilan Pengeluaran Jadi Nol:**
   - Klik komponen `Teks_TotalPengeluaran`, tarik blok hijau muda `set Teks_TotalPengeluaran.Text to` ke bawah susunan blok Saldo.
   - Gunakan blok `join` lagi dari kategori **Text**.
   - Lubang atas `join`: Ambil teks pink kosong `" "` lalu ketik `"Total Pengeluaran: Rp "`.
   - Lubang bawah `join`: Ambil teks pink kosong `" "` lalu ketik angka `"0"`.
5. **Menampilkan Pesan Berhasil:**
   - Di panel kiri bawah, klik komponen `Notifikasi_Reset`.
   - Tarik blok ungu `call Notifikasi_Reset.ShowAlert notice` ke posisi paling bawah di dalam blok kuning.
   - Klik kategori **Text**, ambil blok teks pink kosong `" "`, pasangkan ke sebelah `notice`, dan ketik: `Semua data berhasil dihapus!`.

> **PENTING:** Silakan coba Connect/Run program di HP Anda lagi. Cobalah klik tombol **Hapus Semua Data (Reset)** di Halaman Utama. Setelah itu, buka menu **Riwayat Transaksi** atau **Analisis Keuangan** untuk memastikan bahwa semua catatannya benar-benar sudah kembali kosong seperti aplikasi yang baru saja diinstal.

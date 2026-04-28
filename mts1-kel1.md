# Tutorial Membuat Aplikasi KELOMPOK 1 (MTsN 1 Surakarta)

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

Sekarang kita perlu membuat 4 Screen baru sesuai konsep kelompok Anda.

1. Di bagian paling atas layar App Inventor, klik tombol **Add Screen**.
2. Akan muncul kotak pop-up. Ketik nama: `HalamanUtama` lalu klik OK.
3. Ulangi langkah 1, klik **Add Screen**, ketik nama: `CatatanKeuangan` lalu klik OK.
4. Ulangi langkah 1, klik **Add Screen**, ketik nama: `Tabungan` lalu klik OK.
5. Ulangi langkah 1, klik **Add Screen**, ketik nama: `TabunganTarget` lalu klik OK.

_(Catatan: Pastikan penulisan nama Screen persis seperti di atas tanpa spasi, karena huruf besar/kecil sangat berpengaruh di App Inventor)._

> **PENTING:** Silakan coba Connect/Run program di HP Anda (Pilih menu Connect > AI Companion) untuk memastikan bisa login dengan username "123" dan password "123".

---

## TAHAP 2: Desain & Blocks - HalamanUtama

Pastikan di bagian atas layar App Inventor, Anda sedang berada di Screen **HalamanUtama** (Cek kotak dropdown di sebelah tombol Add Screen). Kembali ke mode **Designer**.

### A. Desain (Designer)

1. **Membuat Header & Logo (Untuk di-copy nanti):**
   - Dari panel **Palette** > klik kategori **Layout**, tarik **HorizontalArrangement** ke layar HP bagian paling atas.
   - Dari panel **Palette** > klik kategori **User Interface**, tarik komponen **Image** dan masukkan _ke dalam_ kotak HorizontalArrangement tadi.
   - Di panel **Components**, klik komponen gambar tersebut, klik tombol **Rename**, ubah namanya menjadi: `Logo_Aplikasi`.
   - Di panel **Properties**, scroll ke bawah, cari kotak centang bernama **Clickable** dan **wajib Anda centang** (agar logo bisa ditekan untuk kembali ke halaman utama).
   - _(Opsional)_ Tarik komponen **Label** letakkan di sebelah logo jika ingin memberi teks judul aplikasi MTsN 1.
2. **Membuat Wadah Menu:**
   - Dari panel **Palette** > **Layout**, tarik **VerticalArrangement** ke layar HP, letakkan tepat di bawah header.
   - Di panel **Properties**, cari menu **Width**, klik dan pilih `Fill parent`, lalu klik OK.
3. **Menu Catatan Keuangan:**
   - Dari panel **Palette** > **Layout**, tarik **HorizontalArrangement** masukkan _ke dalam_ kotak VerticalArrangement tadi.
   - Dari panel **Palette** > **User Interface**, tarik **Image** (untuk ikon) dan **Button** ke dalam kotak HorizontalArrangement tersebut.
   - Di panel **Components**, klik **Button** tersebut, klik **Rename** menjadi: `Tombol_MenuCatatan`.
   - Di panel **Properties**, ubah **Text** menjadi: `Catatan Pemasukan & Pengeluaran`.
4. **Menu Cek Tabungan:**
   - Ulangi langkah ke-3 di atas (buat HorizontalArrangement baru di bawah yang pertama).
   - Tarik **Button**, di panel **Components** Rename menjadi: `Tombol_MenuTabungan`. Di panel **Properties** ubah Text menjadi: `Cek Tabungan`.
5. **Menu Tabungan Target:**
   - Ulangi lagi langkah ke-3.
   - Tarik **Button**, Rename menjadi: `Tombol_MenuTarget`. Ubah Text menjadi: `Tabungan Target`.

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

1. **Logika Logo (Kembali ke Home):**
   - Di panel kiri bawah, klik komponen `Logo_Aplikasi`. Tarik blok kuning: `when Logo_Aplikasi.Click do`.
   - Di panel kiri atas, klik kategori **Control**, scroll ke bawah dan tarik blok `open another screen screenName`. Ambil blok teks pink `" "` dari kategori **Text** dan ketik: `HalamanUtama`.
2. **Logika Menu Catatan:**
   - Di panel kiri bawah, klik `Tombol_MenuCatatan`. Tarik blok kuning: `when Tombol_MenuCatatan.Click do`.
   - Dari kategori **Control**, tarik blok `open another screen screenName`.
   - Dari kategori **Text**, tarik blok kosong `" "`, pasangkan dan ketik: `CatatanKeuangan`.
3. **Logika Menu Tabungan:**
   - Ulangi cara di atas: Klik `Tombol_MenuTabungan`, tarik blok kuning `Click`, arahkan `screenName` dengan teks pink ke `"Tabungan"`.
4. **Logika Menu Target:**
   - Ulangi cara di atas: Klik `Tombol_MenuTarget`, tarik blok kuning `Click`, arahkan `screenName` dengan teks pink ke `"TabunganTarget"`.

---

## TAHAP 3: Desain & Blocks - CatatanKeuangan

Ganti screen aktif ke **CatatanKeuangan** melalui dropdown Screen di atas. Kembali ke mode **Designer**.

### A. Desain (Designer)

1. **Copy-Paste Header:**
   - Ganti screen kembali ke `HalamanUtama` sebentar.
   - Di panel **Components**, klik komponen `HorizontalArrangement` (Header) yang berisi Logo Anda.
   - Tekan tombol **Ctrl + C** (Copy) di keyboard Anda.
   - Ganti screen kembali ke `CatatanKeuangan`. Tekan tombol **Ctrl + V** (Paste). Header dan Logo akan otomatis muncul di bagian atas layar!
2. **Input Tanggal:** Dari panel **Palette** > **User Interface**, tarik komponen **DatePicker** ke layar HP di bawah header.
   - Di panel **Properties**, ubah **Text** menjadi: `Pilih Tanggal`.
   - Di panel **Components**, Rename menjadi: `Input_Tanggal`.
3. **Input Keterangan:** Dari **Palette** > **User Interface**, tarik komponen **TextBox**.
   - Di panel **Properties**, ubah **Hint** menjadi: `Keterangan (contoh: Uang Saku)`.
   - Di panel **Components**, Rename menjadi: `Input_Ket`.
4. **Input Nominal:** Tarik **TextBox** kedua ke bawahnya.
   - Di panel **Properties**, centang kotak **NumbersOnly**. Ubah **Hint** menjadi: `Nominal Uang`.
   - Di panel **Components**, Rename menjadi: `Input_Nominal`.
5. **Tombol Simpan (Bersebelahan):** - Dari **Palette** > **Layout**, tarik **HorizontalArrangement** ke layar.
   - Dari **Palette** > **User Interface**, tarik dua buah **Button** ke dalam kotak tersebut.
   - Button 1 -> Di Properties Text: `Simpan Pemasukan`. Di Components Rename: `Tombol_SimpanMasuk`.
   - Button 2 -> Di Properties Text: `Simpan Pengeluaran`. Di Components Rename: `Tombol_SimpanKeluar`.
6. **Daftar Riwayat:** Dari **Palette** > **User Interface**, tarik dua buah **ListView** ke layar secara berurutan.
   - ListView 1 -> Rename: `List_Pemasukan`.
   - ListView 2 -> Rename: `List_Pengeluaran`.
7. **Alat Tambahan (Wajib):**
   - Dari kategori **Storage**, tarik **TinyDB** ke layar HP (Rename menjadi: `Database_Kel1`).
   - Dari kategori **User Interface**, tarik **Notifier** ke layar HP (Rename menjadi: `Notifikasi_Pesan`).

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

**Bagian 1: Menampilkan Tanggal**

1. Di panel kiri bawah, klik `Input_Tanggal`, tarik blok kuning `when Input_Tanggal.AfterDateSet do`.
2. Klik lagi `Input_Tanggal`, scroll dan tarik blok hijau muda `set Input_Tanggal.Text to`. Masukkan ke dalam blok kuning.
3. Klik kategori **Text**, tarik blok pink `join`.
   - **Menambah Lubang Join:** Klik ikon **gir (gear) biru** kecil pada blok `join` tersebut. Tarik blok `string` dari sebelah kiri ke sebelah kanan susunan, sampai jumlah lubangnya menjadi 5. Klik lagi ikon gir biru untuk menutupnya.
   - Isi berurutan dari atas ke bawah:
     - Lubang 1: Klik `Input_Tanggal` di panel kiri, cari dan tarik `Input_Tanggal.Day`.
     - Lubang 2: Ambil teks pink `" "` dan ketik garis miring `"/"`.
     - Lubang 3: Klik `Input_Tanggal`, cari dan tarik `Input_Tanggal.Month`.
     - Lubang 4: Ambil teks pink `" "` dan ketik garis miring `"/"`.
     - Lubang 5: Klik `Input_Tanggal`, cari dan tarik `Input_Tanggal.Year`.

**Bagian 2: Menyimpan Pemasukan**

1. Di panel kiri atas, klik kategori **Variables**, tarik blok `initialize global name to`. Ganti tulisan `name` jadi `RiwayatMasuk`. Klik kategori **Lists** (biru muda), tarik `create empty list` dan pasangkan.
2. Di panel kiri bawah, klik `Tombol_SimpanMasuk`, tarik blok kuning `when Tombol_SimpanMasuk.Click do`.
3. **Simpan Total:** Klik `Database_Kel1`, tarik blok ungu `call Database_Kel1.StoreValue`. Pasangkan ke blok kuning.
   - Isi `tag` dengan mengklik kategori **Text**, ambil blok teks pink `" "`, lalu ketik: `"TotalMasuk"`.
   - Isi `valueToStore` dengan mengklik kategori **Math**, tarik blok tambah `+`.
     - Sisi kiri `+`: Klik `Database_Kel1`, ambil `GetValue` (isi tag dengan teks pink `"TotalMasuk"`, isi `valueIfTagNotThere` dengan angka `0` dari Math).
     - Sisi kanan `+`: Klik `Input_Nominal` di panel kiri, ambil blok hijau tua `Input_Nominal.Text`.
4. **Update Riwayat:** Klik kategori **Lists**, tarik blok biru muda `add items to list`. Letakkan di bawah susunan `StoreValue`.
   - Di lubang `list`: Klik kategori **Variables**, ambil blok merah `get`, klik tanda panahnya pilih `global RiwayatMasuk`.
   - Di lubang `item`: Klik kategori **Text**, ambil blok pink `join`. Gunakan ikon gir biru untuk mengubahnya menjadi **3 lubang**.
     - Isi lubang 1: Klik `Input_Tanggal`, ambil `Input_Tanggal.Text`.
     - Isi lubang 2: Teks pink kosong `" "`, ketik spasi-strip-spasi `" - "`.
     - Isi lubang 3: Klik `Input_Nominal`, ambil `Input_Nominal.Text`.
5. **Tampilkan List:** Klik komponen `List_Pemasukan`, tarik blok hijau muda `set List_Pemasukan.Elements to`. Pasangkan dengan blok merah `get` lalu pilih `global RiwayatMasuk`.
6. Klik komponen `Notifikasi_Pesan`, tarik blok ungu `call Notifikasi_Pesan.ShowAlert notice`, isi bagian `notice` dengan teks pink: `"Pemasukan Tersimpan!"`.

**Bagian 3: Menyimpan Pengeluaran**

1. Buat variabel global baru dari kategori **Variables** (`initialize global name to`), beri nama `RiwayatKeluar` dan pasangkan dengan `create empty list` dari kategori **Lists**.
2. Klik `Tombol_SimpanKeluar` di panel kiri, tarik blok kuning `when Tombol_SimpanKeluar.Click do`.
3. Lakukan langkah penyusunan blok yang **sama persis** seperti Bagian 2 di atas, namun pastikan Anda:
   - Mengubah `tag` pada StoreValue dan GetValue menggunakan teks pink menjadi `"TotalKeluar"`.
   - Mengubah `list` pada blok `add items to list` menjadi `global RiwayatKeluar`.
   - Menampilkan list menggunakan komponen `set List_Pengeluaran.Elements to` dengan memanggil `get global RiwayatKeluar`.

---

## TAHAP 4: Desain & Blocks - Tabungan

Ganti screen aktif ke **Tabungan** melalui dropdown atas. Beralih ke mode **Designer**.

### A. Desain (Designer)

1. **Paste Header:** Tekan **Ctrl + V** (Paste) di keyboard Anda agar Header dan Logo kembali muncul di atas layar.
2. **Teks Saldo:** Dari panel **Palette** > **User Interface**, tarik komponen **Label** ke bawah header.
   - Di panel **Properties**, ubah **FontSize** menjadi `24` dan centang kotak **FontBold**.
   - Ubah kolom **Text** menjadi: `Saldo Anda Saat Ini: Rp 0`.
   - Di panel **Components**, klik **Rename**, ubah menjadi: `Teks_TotalSaldo`.
3. **Database (Wajib):** Dari panel **Palette** > **Storage**, tarik **TinyDB** ke layar.
   - Di panel **Components**, klik **Rename**, ubah menjadi: `Database_Kel1` _(pastikan namanya persis sama agar bisa membaca data dari layar sebelumnya)_.

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

1. Di panel kiri bawah, klik nama screen `Tabungan` (ikon HP). Tarik blok kuning: `when Tabungan.Initialize do`.
2. Klik komponen `Teks_TotalSaldo`, cari dan tarik blok hijau muda `set Teks_TotalSaldo.Text to`. Masukkan ke dalam blok kuning.
3. Klik kategori **Text**, tarik blok pink `join`.
   - Lubang atas isi dengan teks pink kosong `" "` lalu ketik: `"Saldo Anda: Rp "`.
   - Lubang bawah isi dengan mengklik kategori **Math** (biru muda), lalu tarik blok matematika kurang `-`.
4. Di sisi kiri blok `-`: Klik `Database_Kel1`, tarik blok ungu `call Database_Kel1.GetValue`. Isi tag dengan teks pink `"TotalMasuk"`, dan `valueIfTagNotThere` dengan angka `0`.
5. Di sisi kanan blok `-`: Klik `Database_Kel1` lagi, tarik blok ungu `call Database_Kel1.GetValue`. Isi tag dengan teks pink `"TotalKeluar"`, dan `valueIfTagNotThere` dengan angka `0`.

---

## TAHAP 5: Desain & Blocks - TabunganTarget

Ganti screen aktif ke **TabunganTarget**. Beralih ke mode **Designer**.

### A. Desain (Designer)

1. **Paste Header:** Tekan **Ctrl + V** (Paste) di keyboard agar Header dan Logo kembali muncul di atas layar.
2. **Input Gambar Barang:** Dari panel **Palette** > klik kategori **Media**, tarik komponen **ImagePicker** ke layar HP di bawah header.
   - Di panel **Properties**, ubah **Text** menjadi: `Pilih Gambar Barang`.
   - Di panel **Components**, Rename menjadi: `Pilih_Gambar`.
   - Dari kategori **User Interface**, tarik komponen **Image** tepat di bawah tombol tadi untuk melihat hasil gambar.
   - Di panel **Properties**, ubah **Height** menjadi `150 pixels` dan **Width** menjadi `150 pixels` agar tidak terlalu besar. Di panel **Components**, Rename menjadi: `Preview_Gambar`.
3. **Input Data:** Dari kategori **User Interface**, tarik 3 buah **TextBox** secara berurutan ke bawah.
   - TextBox 1 -> Di Properties ubah Hint: `Nama Barang`. Rename komponen: `Input_NamaBarang`.
   - TextBox 2 -> Di Properties ubah Hint: `Harga Barang` & centang _NumbersOnly_. Rename komponen: `Input_HargaBarang`.
   - TextBox 3 -> Di Properties ubah Hint: `Tanggal Mulai Menabung`. Rename komponen: `Input_TglMulai`.
4. **Simpan & Info:** - Tarik komponen **Button**, ubah Text: `Simpan Target`, Rename: `Tombol_SimpanTarget`.
   - Tarik komponen **Label**, hapus tulisan di dalam Text agar kosong, centang **FontBold**, Rename: `Teks_InfoTarget`.
5. **Alat Tambahan:** Dari **Storage**, tarik **TinyDB** (Rename: `Database_Kel1`). Dari **User Interface**, tarik **Notifier** (biarkan namanya `Notifier1`).

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

1. **Menampilkan Gambar Pilihan:**
   - Di panel kiri bawah, klik komponen `Pilih_Gambar`, tarik blok kuning `when Pilih_Gambar.AfterPicking do`.
   - Klik komponen `Preview_Gambar`, tarik blok hijau muda `set Preview_Gambar.Picture to`. Masukkan ke dalam blok kuning.
   - Klik lagi `Pilih_Gambar`, scroll ke bawah dan tarik blok hijau tua `Pilih_Gambar.Selection` lalu pasangkan.
2. **Menyimpan Data Target:**
   - Klik `Tombol_SimpanTarget`, tarik blok kuning `when Tombol_SimpanTarget.Click do`.
   - Gunakan blok ungu `call Database_Kel1.StoreValue` dari komponen `Database_Kel1` sebanyak 4 kali berurutan ke bawah.
   - **Simpan Data 1:** Klik kategori **Text**, tarik teks pink `" "` ke bagian `tag`, lalu ketik: `"Target_Nama"`. Isi `valueToStore` dengan mengklik `Input_NamaBarang`, lalu tarik blok hijau tua `Input_NamaBarang.Text`.
   - **Simpan Data 2:** Tarik lagi teks pink `" "` ke bagian `tag`, lalu ketik: `"Target_Harga"`. Isi `valueToStore` dengan blok hijau tua `Input_HargaBarang.Text`.
   - **Simpan Data 3:** Tarik teks pink `" "` ke bagian `tag`, lalu ketik: `"Target_Tanggal"`. Isi `valueToStore` dengan blok hijau tua `Input_TglMulai.Text`.
   - **Simpan Data 4:** Tarik teks pink `" "` ke bagian `tag`, lalu ketik: `"Target_Gambar"`. Isi `valueToStore` dengan mengklik `Preview_Gambar` lalu pilih blok hijau tua `Preview_Gambar.Picture`.
   - Terakhir, klik `Notifier1`, tarik `call Notifier1.ShowAlert notice` dan isi pesan dengan menarik blok teks pink `" "` lalu ketik: `"Target Berhasil Dibuat!"`.
3. **Menampilkan Jumlah Tabungan Saat Ini:**
   - Klik nama screen `TabunganTarget` (ikon HP), tarik blok kuning `when TabunganTarget.Initialize do`.
   - Klik komponen `Teks_InfoTarget`, tarik blok hijau muda `set Teks_InfoTarget.Text to`.
   - Klik kategori **Text**, tarik blok `join`.
   - Lubang atas `join` isi dengan teks pink kosong `" "` dan ketik: `"Tabungan Saat Ini: Rp "`.
   - Lubang bawah `join` isi dengan penghitungan saldo persis seperti di Screen Tabungan: Tarik blok Math kurang `-`, sisi kiri isi dengan `GetValue` tag `"TotalMasuk"`, sisi kanan isi dengan `GetValue` tag `"TotalKeluar"`.

> **PENTING:** Silakan coba Connect/Run program dari awal sampai akhir di HP Anda, periksa apakah input berjalan dan saldo terpotong/bertambah secara otomatis. Jangan lupa Save project Anda (Projects > Save project)!

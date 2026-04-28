# Tutorial Membuat Aplikasi KELOMPOK 3 (MTsN 1 Surakarta)

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

Sekarang kita perlu membuat 5 Screen baru sesuai dengan konsep aplikasi pengelolaan tabungan Anda.

1. Di bagian paling atas layar App Inventor, klik tombol **Add Screen**.
2. Akan muncul kotak pop-up. Ketik nama: `HalamanUtama` lalu klik OK.
3. Ulangi langkah 1, klik **Add Screen**, ketik nama: `InputData` lalu klik OK.
4. Ulangi langkah 1, klik **Add Screen**, ketik nama: `SaldoVisual` lalu klik OK.
5. Ulangi langkah 1, klik **Add Screen**, ketik nama: `RiwayatTrans` lalu klik OK.
6. Ulangi langkah 1, klik **Add Screen**, ketik nama: `TipsTrik` lalu klik OK.

_(Catatan: Pastikan penulisan nama Screen persis seperti di atas tanpa spasi)._

> **PENTING:** Silakan coba Connect/Run program di HP Anda (Pilih menu Connect > AI Companion) untuk memastikan bisa login dengan username "123" dan password "123".

---

## TAHAP 2: Desain & Blocks - HalamanUtama

Pastikan di bagian atas layar App Inventor, Anda sedang berada di Screen **HalamanUtama** (Cek kotak dropdown). Kembali ke mode **Designer**.

### A. Desain (Designer)

1. **Membuat Header & Logo (Untuk di-copy nanti):**
   - Dari panel **Palette** > klik kategori **Layout**, tarik **HorizontalArrangement** ke layar HP bagian paling atas.
   - Di panel **Properties**, cari menu **Width**, klik dan pilih `Fill parent`, lalu klik OK.
   - Dari panel **Palette** > klik kategori **User Interface**, tarik komponen **Image** dan masukkan _ke dalam_ kotak HorizontalArrangement tadi.
   - Di panel **Components**, klik komponen gambar tersebut, klik tombol **Rename**, ubah namanya menjadi: `Logo_Aplikasi`.
   - Di panel **Properties**, scroll ke bawah, cari kotak centang bernama **Clickable** dan **wajib Anda centang** (agar logo bisa ditekan untuk kembali).
   - _(Opsional)_ Tarik komponen **Label** letakkan di sebelah logo jika ingin memberi teks judul aplikasi MTsN 1.
2. **Teks Level:** Dari panel **Palette** > **User Interface**, tarik komponen **Label** ke layar HP di bawah header.
   - Di panel **Properties**, perbesar **FontSize** menjadi `24` dan centang kotak **FontBold**.
   - Ubah kolom **Text** menjadi: `Level Anda: Menghitung...`.
   - Di panel **Components**, klik **Rename**, ubah menjadi: `Teks_Level`.
3. **Layout Kotak:** Dari panel **Palette** > klik kategori **Layout**, tarik komponen **TableArrangement** ke bawah label level.
   - Di panel **Properties**, pastikan **Columns** isinya `2` dan **Rows** isinya `2`.
   - Di panel **Properties** yang sama, ubah **Width** menjadi `Fill parent` agar tombol nanti tersusun rapi di tengah.
4. **Tombol Menu:** Dari panel **Palette** > **User Interface**, tarik 4 buah **Button** secara berurutan dan masukkan _ke dalam_ kotak-kotak kecil di TableArrangement tersebut.
   - Button 1 -> Di Components Rename: `Menu_Input`. Di Properties ubah Text: `Input Saldo`.
   - Button 2 -> Rename: `Menu_Visual`. Ubah Text: `Visual Tabungan`.
   - Button 3 -> Rename: `Menu_Riwayat`. Ubah Text: `Riwayat`.
   - Button 4 -> Rename: `Menu_Tips`. Ubah Text: `Tips Menabung`.
5. **Database (Wajib):** Dari panel **Palette** > **Storage**, tarik komponen **TinyDB** ke layar HP. Di panel **Components**, Rename menjadi `DB_Kel3`.

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**. Ikuti langkah ini secara perlahan karena logikanya cukup panjang.

**1. Logika Logo (Kembali ke Home):**

- Di panel kiri bawah, klik komponen `Logo_Aplikasi`. Tarik blok kuning: `when Logo_Aplikasi.Click do`.
- Di panel kiri atas, klik kategori **Control**, scroll ke bawah dan tarik blok `open another screen screenName`. Ambil blok teks pink `" "` dari kategori **Text** dan ketik: `HalamanUtama`.

**2. Logika Navigasi Menu:**

- Di panel kiri bawah, klik `Menu_Input`. Tarik blok kuning `when Menu_Input.Click do`.
- Tarik blok `open another screen screenName` dari kategori **Control**. Ambil teks pink `" "` dari kategori **Text** dan ketik: `InputData`.
- Lakukan cara yang **sama persis** untuk ketiga tombol lainnya:
  - Klik `Menu_Visual`, buat event `Click`, arahkan teks pink ke `"SaldoVisual"`.
  - Klik `Menu_Riwayat`, buat event `Click`, arahkan teks pink ke `"RiwayatTrans"`.
  - Klik `Menu_Tips`, buat event `Click`, arahkan teks pink ke `"TipsTrik"`.

**3. Sistem Level Tabungan (Menghitung Saldo Otomatis):**

- Di panel kiri bawah, klik nama screen `HalamanUtama` (ikon HP). Tarik blok kuning `when HalamanUtama.Initialize do`.
- **Membuat Variabel Hitungan:** Klik kategori **Variables** (oranye tua), tarik blok `initialize local name to in do` (pilih yang bentuknya panjang dengan celah _do_). Ganti tulisan `name` menjadi `SaldoTotal`. Masukkan blok ini ke dalam blok kuning Initialize.
- **Rumus Kurang:** Klik kategori **Math** (biru muda), tarik blok matematika kurang `-`. Pasangkan ke sebelah variabel `SaldoTotal`.
- **Mengambil Data Masuk:** Di panel kiri bawah, klik `DB_Kel3`. Tarik blok ungu `call DB_Kel3.GetValue`. Pasangkan ke sisi **KIRI** blok kurang `-`.
  - Pada bagian `tag`: Tarik blok teks pink `" "`, ketik `"TotalMasuk"`.
  - Pada bagian `valueIfTagNotThere` (PENTING): Klik kategori **Math**, tarik blok angka `0`. Pasangkan ke lubang ini.
- **Mengambil Data Keluar:** Ulangi langkah di atas. Tarik lagi `call DB_Kel3.GetValue` dari `DB_Kel3` dan pasangkan ke sisi **KANAN** blok kurang `-`.
  - Pada bagian `tag`: Tarik teks pink `" "`, ketik `"TotalKeluar"`.
  - Pada bagian `valueIfTagNotThere`: Tarik blok angka `0` dari kategori **Math**.

**4. Sistem Level Tabungan (Menentukan Gelar Level):**

- Masih di layar Blocks, klik kategori **Control**, tarik blok `if then` dan letakkan di dalam celah _do_ pada blok variabel oranye Anda.
- **Menambah Kondisi:** Klik ikon **gir (gear) biru** kecil pada blok `if` tersebut. Tarik kotak `else if` sebanyak **3 kali** dan tumpuk di bawah tulisan `if` pada kerangka sebelah kanan. Terakhir, tarik kotak `else` **1 kali** dan letakkan paling bawah. Klik lagi ikon gir biru untuk menutupnya.
- **Kondisi 1 (< 50.000):**
  - Dari kategori **Math**, tarik blok sama dengan `=`. Klik tanda panahnya dan ubah (pilih) menjadi lambang kurang dari `<`. Pasangkan ke sebelah kanan tulisan `if`.
  - _Sisi kiri < :_ Arahkan kursor mouse (jangan diklik) di atas tulisan `SaldoTotal` pada blok variabel oranye Anda. Akan muncul blok merah kecil `get SaldoTotal`. Tarik dan pasangkan.
  - _Sisi kanan < :_ Dari kategori **Math**, tarik blok angka `0`. Ketik angka `50000`.
  - _Di celah then :_ Klik komponen `Teks_Level` di panel kiri, tarik blok hijau muda `set Teks_Level.Text to`. Ambil blok teks pink `" "` lalu ketik: `"Level: Newbie Boros"`.
- **Kondisi 2 (< 100.000):**
  - Tarik blok lambang `<` dari kategori **Math** ke sebelah `else if` pertama.
  - _Sisi kiri:_ ambil `get SaldoTotal`. _Sisi kanan:_ ambil blok angka dan ketik `100000`.
  - _Di celah then:_ Tarik `set Teks_Level.Text to` isi teks pink `"Level: Apprentice Hemat"`.
- **Kondisi 3 (< 500.000):**
  - _Sebelah else if kedua:_ Tarik blok `<`. Kiri: `get SaldoTotal`. Kanan: angka `500000`.
  - _Di celah then:_ Tarik `set Teks_Level.Text to` isi teks pink `"Level: Warrior Nabung"`.
- **Kondisi 4 (< 1.000.000):**
  - _Sebelah else if ketiga:_ Tarik blok `<`. Kiri: `get SaldoTotal`. Kanan: angka `1000000`.
  - _Di celah then:_ Tarik `set Teks_Level.Text to` isi teks pink `"Level: Knight Investasi"`.
- **Kondisi Else (Lebih dari 1 juta):**
  - Di dalam celah `else` paling bawah, Anda tidak perlu repot membuat kondisi angka lagi. Cukup tarik `set Teks_Level.Text to` dan isi dengan teks pink `"Level: Legend of Saldo"`.

---

## TAHAP 3: Desain & Blocks - InputData

Ganti screen aktif ke **InputData** melalui dropdown Screen di atas. Kembali ke mode **Designer**.

### A. Desain (Designer)

1. **Copy-Paste Header:**
   - Ganti screen kembali ke `HalamanUtama` sebentar.
   - Di panel **Components**, klik komponen `HorizontalArrangement` (Header) yang berisi Logo Anda.
   - Tekan tombol **Ctrl + C** (Copy) di keyboard Anda.
   - Ganti screen ke `InputData`. Tekan tombol **Ctrl + V** (Paste). Header dan Logo akan otomatis muncul.
2. Dari panel **Palette** > **User Interface**, tarik 3 buah **TextBox** secara berurutan ke bawah header.
   - TextBox 1 -> Di panel Properties, centang **NumbersOnly**, ubah Hint: `Input Pemasukan`. Rename komponen: `Input_Masuk`.
   - TextBox 2 -> Centang **NumbersOnly**, ubah Hint: `Input Pengeluaran`. Rename komponen: `Input_Keluar`.
   - TextBox 3 -> Centang **NumbersOnly**, ubah Hint: `Input Target Menabung`. Rename komponen: `Input_Target`.
3. Dari panel **Palette**, tarik 3 buah **Button** dan letakkan tepat di bawah masing-masing TextBox.
   - Button 1 -> Di Properties ubah Text: `Simpan Pemasukan`. Rename komponen: `Tombol_Masuk`.
   - Button 2 -> Ubah Text: `Simpan Pengeluaran`. Rename komponen: `Tombol_Keluar`.
   - Button 3 -> Ubah Text: `Simpan Target`. Rename komponen: `Tombol_Target`.
4. Dari panel **Palette** > **Storage**, tarik **TinyDB** (Rename: `DB_Kel3`). Dari kategori **User Interface**, tarik **Notifier** (Rename: `Notifikasi_Pesan`).

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

1. **Buat Variabel:** Di panel kiri atas, klik kategori **Variables**, tarik `initialize global name to`. Ganti `name` jadi `RiwayatSmt`. Pasangkan dengan `create empty list` dari kategori **Lists**.
2. **Simpan Target:** - Di panel kiri bawah, klik `Tombol_Target`, tarik blok kuning `when Tombol_Target.Click do`.
   - Klik `DB_Kel3`, tarik `call DB_Kel3.StoreValue`. Isi tag dengan teks pink `"TargetNominal"`. Isi `valueToStore` dengan mengklik `Input_Target` lalu ambil blok hijau tua `Input_Target.Text`.
   - Klik `Notifikasi_Pesan`, tarik `call Notifikasi_Pesan.ShowAlert notice`. Isi dengan teks pink `"Target Disimpan!"`.
3. **Simpan Pemasukan:**
   - Klik `Tombol_Masuk`, tarik blok kuning `when Tombol_Masuk.Click do`.
   - **Tambah Total:** Klik `DB_Kel3`, tarik `call DB_Kel3.StoreValue`. Isi tag dengan teks pink `"TotalMasuk"`. Di bagian `valueToStore`, ambil blok tambah `+` dari kategori **Math**. Sisi kiri `+` isi dengan `call DB_Kel3.GetValue` (tag `"TotalMasuk"`, default `0`). Sisi kanan `+` isi dengan `Input_Masuk.Text`.
   - **Simpan ke Riwayat (List):**
     - Klik kategori **Variables**, tarik blok `set to` dan ubah menjadi `global RiwayatSmt`. Pasangkan dengan `call DB_Kel3.GetValue` (tag `"DataRiwayat"`, default `create empty list`). Letakkan di bawah susunan StoreValue sebelumnya.
     - Klik kategori **Lists**, tarik blok biru muda `add items to list`. Isi lubang `list` dengan blok merah `get global RiwayatSmt`.
     - Di lubang `item`, klik kategori **Text**, ambil blok pink `join` (yang punya 2 lubang). Lubang atas isi dengan teks pink `"[Masuk] Rp "`. Lubang bawah isi dengan `Input_Masuk.Text`.
     - Klik `DB_Kel3` lagi, tarik `call DB_Kel3.StoreValue`. Isi tag dengan teks pink `"DataRiwayat"` dan `valueToStore` dengan `get global RiwayatSmt`.
4. **Simpan Pengeluaran:**
   - Lakukan langkah yang **sama persis** dengan nomor 3, tetapi gunakan blok kuning `when Tombol_Keluar.Click do`.
   - Ubah tag _database_-nya dari `"TotalMasuk"` menjadi teks pink `"TotalKeluar"`.
   - Di bagian `join`, ubah teks pink awalnya menjadi `"[Keluar] Rp "`.

---

## TAHAP 4: Desain & Blocks - SaldoVisual

Ganti screen aktif ke **SaldoVisual** melalui dropdown. Kembali ke mode **Designer**. Ini adalah fitur visual air dalam toples.

### A. Desain (Designer)

1. **Paste Header:** Tekan **Ctrl + V** (Paste) di keyboard agar Header dan Logo kembali muncul di atas layar.
2. **Membuat Wadah Toples:** Dari panel **Palette** > klik kategori **Layout**, tarik **VerticalArrangement** ke bawah header.
   - Di panel **Properties**, cari menu **AlignVertical** ubah menjadi `Bottom` _(Sangat Penting agar air mengisi dari bawah ke atas)_.
   - Ubah **Height** menjadi `300 pixels` dan **Width** menjadi `150 pixels`.
   - Ubah **BackgroundColor** menjadi `Light Gray` (Abu-abu terang).
   - Di panel **Components**, Rename komponen ini menjadi: `Wadah_Toples`.
3. **Membuat Air:** Dari panel **Palette** > **User Interface**, tarik sebuah komponen **Label** dan pastikan Anda memasukkannya _ke dalam_ Wadah_Toples tadi.
   - Di panel **Properties**, HAPUS tulisan di dalam kotak **Text** agar kosong.
   - Ubah **BackgroundColor** menjadi `Blue` (Biru).
   - Ubah **Width** menjadi `Fill parent`.
   - Ubah **Height** menjadi `1 Percent` _(Wajib diisi 1% agar nanti tidak error saat diatur kodenya)_.
   - Di panel **Components**, Rename menjadi: `Visual_Air`.
4. Tarik **Label** baru ke layar (letakkan di luar/bawah toples). Ubah Text di Properties menjadi: `Target Tercapai: 0%`. Rename komponennya menjadi: `Teks_Persen`.
5. Tarik **TinyDB** dari Storage (Rename: `DB_Kel3`) dan **Notifier** (Rename: `Notifikasi_Pesan`).

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

1. Di panel kiri bawah, klik nama screen `SaldoVisual` (ikon HP), tarik blok kuning `when SaldoVisual.Initialize do`.
2. **Buat 3 Variabel Lokal:** Klik kategori **Variables**, tarik blok `initialize local name to in do` (oranye tua, blok panjang).
   - Klik ikon **gir (gear) biru** pada blok variabel tersebut. Tarik blok `name` dari panel kiri _mutator_ dan tumpuk ke bawah blok `name` di sebelah kanan. Lakukan sebanyak **2 kali** sehingga Anda memiliki **3 baris nama variabel**. Klik gir biru lagi untuk menutup.
   - Ganti tulisan `name` pertama menjadi `SaldoSekarang`. Pasangkan dengan blok Math kurang `-` (Isi kiri: `GetValue` tag `"TotalMasuk"`. Isi kanan: `GetValue` tag `"TotalKeluar"`).
   - Ganti tulisan `name` kedua menjadi `TargetUang`. Pasangkan dengan `GetValue` tag `"TargetNominal"` _(Beri `valueIfTagNotThere` angka `1` dari Math, PENTING agar tidak terjadi error dibagi 0)_.
   - Ganti tulisan `name` ketiga menjadi `PersenAir`.
3. **Menyusun Rumus Persentase Air:**
   - Di sebelah variabel `PersenAir`, klik kategori **Math**, tarik blok perkalian `*`.
   - Di lubang kiri blok `*`, klik kategori **Math** lagi, tarik blok pembagian `/`.
     - Sisi kiri blok `/`: arahkan kursor ke tulisan `SaldoSekarang`, ambil `get SaldoSekarang`.
     - Sisi kanan blok `/`: arahkan kursor ke tulisan `TargetUang`, ambil `get TargetUang`.
   - Di lubang kanan blok `*`, ambil blok angka dari Math dan ketik `100`. _(Rumusnya sekarang berbunyi: (Saldo / Target) x 100)_.
4. **Cegah Air Tumpah:** - Di dalam celah _do_, dari kategori **Control**, tarik blok `if then`.
   - Dari **Math**, ambil blok lebih besar `>`. Jika `get PersenAir` `>` angka `100`, maka di celah _then_ tarik blok `set PersenAir to` dan pasangkan angka `100`.
5. **Mengatur Tinggi Air & Teks:**
   - Di bawah blok `if` tadi, klik `Visual_Air`, tarik blok hijau muda `set Visual_Air.HeightPercent to`. Pasangkan dengan blok merah `get PersenAir`.
   - Klik `Teks_Persen`, tarik `set Teks_Persen.Text to`. Ambil blok pink `join` (3 lubang menggunakan gir biru). Gabungkan teks pink `"Target Tercapai: "`, lalu `get PersenAir`, lalu teks pink `"% "`.
6. **Notifikasi Level Baru:** - Tarik blok `if then` baru di paling bawah. Dari kategori **Math** ambil blok sama dengan `=`.
   - Jika `get PersenAir` `=` angka `100`, maka klik `Notifikasi_Pesan`, tarik `ShowAlert notice` isi teks pink: `"Selamat! Target Tercapai, Level Terbaru Terbuka!"`.

---

## TAHAP 5: Desain & Blocks - RiwayatTrans

Ganti screen aktif ke **RiwayatTrans** melalui dropdown atas. Beralih ke mode **Designer**.

### A. Desain (Designer)

1. **Paste Header:** Tekan **Ctrl + V** (Paste) di keyboard agar Header dan Logo kembali muncul di atas layar.
2. Dari panel **Palette** > **User Interface**, tarik **Label** judul ke bawah header, ubah Text di Properties: `Catatan Riwayat Transaksi`.
3. Tarik komponen **ListView** ke layar. Di panel Properties, ubah **Height** dan **Width** menjadi `Fill parent`. Di panel Components, Rename: `Daftar_SemuaRiwayat`.
4. Tarik **TinyDB** dari Storage (Rename: `DB_Kel3`).

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

1. Di panel kiri bawah, klik screen `RiwayatTrans`, tarik blok kuning `when RiwayatTrans.Initialize do`.
2. Klik komponen `Daftar_SemuaRiwayat`, tarik blok hijau muda `set Daftar_SemuaRiwayat.Elements to`. Masukkan ke dalam blok kuning.
3. Pasangkan dengan blok ungu `call DB_Kel3.GetValue` dari komponen `DB_Kel3`.
   - Isi `tag`-nya dengan teks pink `" "` dan ketik: `"DataRiwayat"`.
   - Isi `valueIfTagNotThere` dengan blok biru muda `create empty list` dari kategori **Lists**.

---

## TAHAP 6: Desain & Blocks - TipsTrik

Ganti screen aktif ke **TipsTrik** melalui menu dropdown di bagian atas layar. Kembali ke mode **Designer**.

### A. Desain (Designer)

1. **Paste Header Utama:**
   - Ganti screen kembali ke `HalamanUtama` sebentar.
   - Di panel **Components**, klik komponen `HorizontalArrangement` (Header) yang berisi Logo Anda.
   - Tekan tombol **Ctrl + C** (Copy) di keyboard.
   - Ganti screen kembali ke `TipsTrik`. Tekan tombol **Ctrl + V** (Paste). Header dan Logo otomatis terpasang.
2. **Membuat Judul Halaman:**
   - Dari panel **Palette** > **User Interface**, tarik komponen **Label** ke layar HP, tepat di bawah header.
   - Perhatikan panel **Properties** di sebelah kanan:
     - Centang kotak **FontBold** (agar huruf tebal).
     - Ubah **FontSize** menjadi `20`.
     - Ubah kotak **Text** menjadi: `Tips & Trik Menabung`.
3. **Menyiapkan Tempat Daftar (ListView):**
   - Dari panel **Palette** > **User Interface**, tarik komponen **ListView** letakkan tepat di bawah judul tadi.
   - Di panel **Properties**, ubah **Height** menjadi `Fill parent` dan **Width** menjadi `Fill parent`.
   - Di panel **Components**, klik **Rename** dan ubah namanya menjadi: `List_Tips`.
4. **Memasukkan Teks 3 Tips Otomatis:**
   - Pastikan komponen `List_Tips` masih Anda klik/pilih di layar.
   - Di panel **Properties** sebelah kanan, cari kotak putih yang bernama **ElementsFromString**.
   - Di dalam kotak tersebut, ketik 3 contoh tips ini persis seperti di bawah ini **(PENTING: Pisahkan dengan tanda koma, dan TIDAK BOLEH ADA SPASI SETELAH TANDA KOMA):**
     `1. Bawa bekal minum dan makanan dari rumah,2. Tahan godaan jajan hal yang tidak penting,3. Sisihkan uang di awal minggu bukan menyisakan`
   - Setelah selesai mengetik, klik sembarang tempat di layar kosong dan tulisan tersebut akan otomatis tersusun menjadi daftar menurun.

### B. Kode (Blocks)

Untuk halaman Tips & Trik ini, karena isinya bersifat statis (hanya tulisan panduan bacaan untuk user), maka pengaturan lewat **ElementsFromString** di langkah ke-4 tadi sudah sangat cukup.

Anda **TIDAK PERLU** menyusun kode apa pun di tampilan Blocks untuk halaman ini.

> **PENTING:** Silakan coba Connect/Run program dari awal sampai akhir di HP Anda! Coba lakukan Input Saldo dan Target, lalu periksa halaman Visual Tabungan apakah tinggi air di dalam toples sudah naik otomatis sesuai persentase target. Jika semuanya lancar, jangan lupa klik **Projects > Save project**.

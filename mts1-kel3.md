# Tutorial Membuat Aplikasi KELOMPOK 3 (MTsN 1 Surakarta)

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

Sekarang kita perlu membuat 5 Screen baru sesuai dengan konsep aplikasi pengelolaan tabungan Anda.

1. Di bagian atas layar, klik tombol **Add Screen**.
2. Ketik nama: `HalamanUtama` lalu klik OK.
3. Ulangi langkah 1, ketik nama: `InputData` lalu klik OK.
4. Ulangi langkah 1, ketik nama: `SaldoVisual` lalu klik OK.
5. Ulangi langkah 1, ketik nama: `RiwayatTrans` lalu klik OK.
6. Ulangi langkah 1, ketik nama: `TipsTrik` lalu klik OK.

_(Catatan: Pastikan penulisan nama Screen persis seperti di atas tanpa spasi)._

> **PENTING:** Silakan coba Run program di HP Anda untuk memastikan bisa login dengan username "123" dan password "123".

---

## TAHAP 2: Desain & Blocks - HalamanUtama

Pastikan di bagian atas layar App Inventor, Anda sedang berada di Screen **HalamanUtama**. Di sini kita akan membuat Header dengan Logo terlebih dahulu untuk dicopy ke layar lain, dilanjutkan menu berbentuk kotak dan sistem Level.

### A. Desain (Designer)

1. **Membuat Header & Logo (Untuk di-copy nanti):**
   - Dari panel **Palette** > **Layout**, tarik **HorizontalArrangement** ke layar bagian paling atas.
   - Di panel **Properties**, ubah **Width** menjadi `Fill parent`.
   - Dari panel **Palette** > **User Interface**, tarik komponen **Image** ke dalam kotak HorizontalArrangement tadi.
   - Di panel **Components**, klik tombol **Rename Component** pada gambar tersebut, ubah namanya menjadi: `Logo_Aplikasi`.
   - Di panel **Properties**, cari kotak centang bernama **Clickable** dan **wajib dicentang** (agar logo bisa ditekan untuk kembali ke halaman utama).
   - Tarik komponen **Label** letakkan di sebelah logo jika ingin memberi teks judul aplikasi MTsN 1.
2. **Teks Level:** Dari panel **Palette** > **User Interface**, tarik komponen **Label** ke bawah header.
   - Di panel **Properties**, perbesar ukuran **FontSize** menjadi `24` dan centang **FontBold**.
   - Ubah **Text** menjadi: `Level Anda: Menghitung...`.
   - Klik **Rename Component**, ubah menjadi: `Teks_Level`.
3. **Layout Kotak:** Dari panel **Palette** > **Layout**, tarik **TableArrangement** ke bawah label level.
   - Di panel **Properties**, ubah **Columns** menjadi `2` dan **Rows** menjadi `2`.
   - Ubah **Width** menjadi `Fill parent` agar tombol nanti tersusun rapi di tengah.
4. **Tombol Menu:** Tarik 4 buah **Button** ke dalam kotak TableArrangement tersebut secara berurutan.
   - Button 1 -> Rename: `Menu_Input`, Ubah Text: `Input Saldo`.
   - Button 2 -> Rename: `Menu_Visual`, Ubah Text: `Visual Tabungan`.
   - Button 3 -> Rename: `Menu_Riwayat`, Ubah Text: `Riwayat`.
   - Button 4 -> Rename: `Menu_Tips`, Ubah Text: `Tips Menabung`.
5. **Database:** Dari panel **Palette** > **Storage**, tarik **TinyDB** ke layar (akan muncul di bawah layar). Klik **Rename Component** menjadi `DB_Kel3`.

### B. Kode (Blocks)

Pindah ke tampilan **Blocks** (tombol di pojok kanan atas). Ikuti langkah ini secara perlahan karena kita akan menyusun logika yang cukup panjang.

**1. Logika Logo (Kembali ke Home):**

- Di panel sebelah kiri, temukan dan klik `Logo_Aplikasi`. Tarik blok kuning teratas: `when Logo_Aplikasi.Click do`.
- Klik kategori **Control** (warna cokelat/oranye), gulir ke bawah, tarik blok `open another screen screenName`.
- Klik kategori **Text** (warna pink), tarik blok teks kosong `" "` paling atas. Pasangkan ke blok control tadi, lalu ketik di dalamnya: `HalamanUtama`.

**2. Logika Navigasi Menu:**

- Di panel kiri, klik `Menu_Input`. Tarik blok kuning `when Menu_Input.Click do`.
- Ulangi langkah mengambil blok `open another screen screenName` dan blok teks pink `" "`. Pasangkan dan ketik: `InputData`.
- Ulangi cara yang sama persis untuk ketiga tombol lainnya:
  - Untuk `Menu_Visual` arahkan ke teks pink `"SaldoVisual"`.
  - Untuk `Menu_Riwayat` arahkan ke teks pink `"RiwayatTrans"`.
  - Untuk `Menu_Tips` arahkan ke teks pink `"TipsTrik"`.

**3. Sistem Level Tabungan (Menghitung Saldo Otomatis):**

- Di panel kiri, klik `HalamanUtama` (ikon layar). Tarik blok kuning: `when HalamanUtama.Initialize do`.
- **Membuat Variabel Hitungan:** Klik kategori **Variables** (oranye tua), tarik blok `initialize local name to` (pilih yang ada colokan di kanannya). Ganti tulisan `name` menjadi `SaldoTotal`. Masukkan blok ini ke dalam blok kuning Initialize.
- **Rumus Kurang:** Klik kategori **Math** (biru muda), tarik blok kurang `-`. Pasangkan ke sebelah variabel `SaldoTotal`.
- **Mengambil Data Masuk:** Di panel kiri, klik `DB_Kel3`. Tarik blok ungu `call DB_Kel3.GetValue`. Pasangkan ke sisi **KIRI** blok kurang `-`.
  - Pada bagian `tag`: Tarik blok teks pink `" "`, ketik `TotalMasuk`.
  - Pada bagian `valueIfTagNotThere` (PENTING): Klik kategori **Math**, tarik blok angka `0` paling atas. Pasangkan ke lubang ini. (Ini berfungsi agar jika belum ada tabungan, saldonya dianggap 0, bukan error).
- **Mengambil Data Keluar:** Ulangi langkah di atas. Tarik lagi `call DB_Kel3.GetValue` dan pasangkan ke sisi **KANAN** blok kurang `-`.
  - Pada bagian `tag`: Tarik blok teks pink `" "`, ketik `TotalKeluar`.
  - Pada bagian `valueIfTagNotThere`: Tarik blok angka `0` dari kategori **Math**.

**4. Sistem Level Tabungan (Menentukan Gelar Level):**

- Masih di dalam blok Initialize, klik kategori **Control**, tarik blok `if then` dan letakkan di bawah hitungan variabel tadi (masih di dalam bingkai oranye variabel).
- **Menambah Kondisi:** Klik ikon **gir biru** kecil di sudut blok `if`. Tarik kotak `else if` sebanyak 3 kali ke bawah tulisan `if`, lalu terakhir tarik kotak `else` 1 kali. Klik lagi gir biru untuk menutupnya.
- **Kondisi 1 (< 50.000):**
  - Dari kategori **Math**, tarik blok sama dengan `=`. Klik tanda panahnya dan ubah menjadi kurang dari `<`. Pasangkan ke sebelah tulisan `if`.
  - Arahkan kursor mouse (jangan diklik, didiamkan saja) di atas tulisan `SaldoTotal` pada blok variabel oranye Anda. Akan muncul blok kecil `get SaldoTotal`. Tarik dan pasangkan ke sisi KIRI blok `<`.
  - Dari kategori **Math**, tarik blok angka `0`, pasangkan ke sisi KANAN blok `<`. Ketik angka `50000`.
  - Di bagian `then`: Klik `Teks_Level` di panel kiri, tarik blok hijau muda `set Teks_Level.Text to`. Pasangkan blok teks pink `" "` lalu ketik: `Level: Newbie Boros`.
- **Kondisi 2 (< 100.000):**
  - Ulangi langkah membuat blok `<` seperti di atas untuk dipasang di sebelah `else if` pertama.
  - Kiri: isi dengan `get SaldoTotal`. Kanan: isi dengan angka `100000`.
  - Di bagian `then`: `set Teks_Level.Text to` isi teks pink `"Level: Apprentice Hemat"`.
- **Kondisi 3 (< 500.000):**
  - Kiri: `get SaldoTotal`. Kanan: angka `500000`.
  - Di bagian `then`: `set Teks_Level.Text to` isi teks pink `"Level: Warrior Nabung"`.
- **Kondisi 4 (< 1.000.000):**
  - Kiri: `get SaldoTotal`. Kanan: angka `1000000`.
  - Di bagian `then`: `set Teks_Level.Text to` isi teks pink `"Level: Knight Investasi"`.
- **Kondisi Else (Lebih dari 1 juta):**
  - Di bagian lubang `else` paling bawah, Anda tidak perlu repot membuat kondisi angka lagi. Cukup tarik `set Teks_Level.Text to` dan isi dengan teks pink `"Level: Legend of Saldo"`.

---

## TAHAP 3: Desain & Blocks - InputData

Ganti screen aktif ke **InputData**.

### A. Desain (Designer)

1. **Copy-Paste Header:**
   - Ganti screen kembali ke `HalamanUtama` sebentar.
   - Klik komponen `HorizontalArrangement` (Header) yang berisi Logo Anda.
   - Tekan tombol **Ctrl + C** (Copy) di keyboard Anda.
   - Ganti screen ke `InputData`. Tekan tombol **Ctrl + V** (Paste). Header dan Logo akan otomatis muncul beserta blok logikanya.
2. Tarik 3 buah **TextBox** secara berurutan ke bawah header. Centang **NumbersOnly** untuk ketiganya.
   - TextBox 1 -> Hint: `Input Pemasukan`, Rename: `Input_Masuk`.
   - TextBox 2 -> Hint: `Input Pengeluaran`, Rename: `Input_Keluar`.
   - TextBox 3 -> Hint: `Input Target Menabung`, Rename: `Input_Target`.
3. Tarik 3 buah **Button** di bawah masing-masing TextBox.
   - Button 1 -> Text: `Simpan Pemasukan`, Rename: `Tombol_Masuk`.
   - Button 2 -> Text: `Simpan Pengeluaran`, Rename: `Tombol_Keluar`.
   - Button 3 -> Text: `Simpan Target`, Rename: `Tombol_Target`.
4. Tarik **TinyDB** (Rename: `DB_Kel3`) dan **Notifier** (Rename: `Notifikasi_Pesan`).

### B. Kode (Blocks)

Pindah ke **Blocks**.

1. **Buat Variabel:** Tarik `initialize global name to` (ganti nama jadi `RiwayatSmt`). Isi dengan `create empty list`.
2. **Simpan Target:** Klik `Tombol_Target`, tarik `when Click`. Pasang blok `StoreValue` tag `"TargetNominal"` dengan isi `Input_Target.Text`. Munculkan `ShowAlert`: `"Target Disimpan!"`.
3. **Simpan Pemasukan:**
   - Klik `Tombol_Masuk`, tarik `when Click`.
   - Gunakan `StoreValue` tag `"TotalMasuk"`. Isinya: blok Math `+` (`GetValue` tag `"TotalMasuk"` ditambah `Input_Masuk.Text`).
   - Simpan ke riwayat: Set `global RiwayatSmt` ke `GetValue` tag `"DataRiwayat"`. Gunakan `add items to list` (item diisi blok `join` teks `"[Masuk] Rp "` dan `Input_Masuk.Text`). Simpan lagi listnya pakai `StoreValue` tag `"DataRiwayat"`.
4. **Simpan Pengeluaran:**
   - Ulangi logika pemasukan, tetapi gunakan `Tombol_Keluar.Click`, tag `"TotalKeluar"`, dan teks awalan list `"[Keluar] Rp "`.

---

## TAHAP 4: Desain & Blocks - SaldoVisual

Ganti screen aktif ke **SaldoVisual**. Ini adalah fitur andalan kelompok Anda (visual air dalam toples).

### A. Desain (Designer)

1. **Paste Header:** Tekan **Ctrl + V** (Paste) di keyboard agar Header dan Logo kembali muncul di atas layar.
2. **Membuat Wadah Toples:** Dari panel **Palette** > **Layout**, tarik **VerticalArrangement** ke bawah header.
   - Di Properties, ubah **AlignVertical** menjadi `Bottom`.
   - Ubah **Height** menjadi `300 pixels` dan **Width** menjadi `150 pixels`.
   - Ubah **BackgroundColor** menjadi `Light Gray` (Abu-abu terang). Rename: `Wadah_Toples`.
3. **Membuat Air:** Di dalam VerticalArrangement tadi, tarik sebuah **Label**.
   - Kosongkan bagian **Text**.
   - Ubah **BackgroundColor** menjadi `Blue` (Biru).
   - Ubah **Width** menjadi `Fill parent`.
   - Ubah **Height** menjadi `1 Percent` (ini wajib diisi 1% agar nanti bisa diatur dari kode).
   - Rename: `Visual_Air`.
4. Tarik **Label** baru di bawah toples untuk teks info. Ubah Text: `Target Tercapai: 0%`. Rename: `Teks_Persen`.
5. Tarik **TinyDB** (`DB_Kel3`) dan **Notifier** (`Notifikasi_Pesan`).

### B. Kode (Blocks)

Pindah ke **Blocks**.

1. Tarik blok kuning `when SaldoVisual.Initialize do`.
2. **Hitung Saldo & Target:** Buat variabel lokal (`initialize local name to`) untuk:
   - `SaldoSekarang`: (Blok `-` dari `GetValue` "TotalMasuk" dikurangi `GetValue` "TotalKeluar").
   - `TargetUang`: `GetValue` tag `"TargetNominal"` (Beri default `1` agar tidak terjadi error pembagian nol).
3. **Hitung Persentase Air:** Buat variabel lokal ketiga bernama `PersenAir`.
   - Gunakan blok Math kali `*` dan bagi `/`.
   - Rumusnya: `(SaldoSekarang / TargetUang) * 100`. (Gunakan blok Math untuk menyusun rumus ini).
4. **Cegah Air Tumpah (Lebih dari 100%):** Tarik blok `if then` dari Control.
   - Jika `PersenAir` > `100`, maka tarik blok `set PersenAir to` angka `100`. (Ini agar visual air tidak keluar dari toples).
5. **Mengatur Tinggi Air:**
   - Klik `Visual_Air`, tarik blok hijau muda `set Visual_Air.HeightPercent to`. Pasangkan dengan nilai dari variabel `PersenAir`.
   - Klik `Teks_Persen`, tarik `set Teks_Persen.Text to`. Gunakan blok `join`, gabungkan `"Target Tercapai: "` dengan variabel `PersenAir` dan simbol `"% "`.
6. **Notifikasi Level Baru:** Di bagian bawah, tambahkan blok `if`. Jika `PersenAir` = `100`, munculkan blok `ShowAlert` dari Notifier, isi dengan `"Selamat! Target Tercapai, Level Terbaru Terbuka!"`.

---

## TAHAP 5: Desain & Blocks - RiwayatTrans

Ganti screen aktif ke **RiwayatTrans**.

### A. Desain (Designer)

1. **Paste Header:** Tekan **Ctrl + V** (Paste) di keyboard agar Header dan Logo kembali muncul di atas layar.
2. Tarik **Label** judul di bawah header, ubah Text: `Catatan Riwayat Transaksi`.
3. Tarik komponen **ListView**. Ubah **Height** dan **Width** menjadi `Fill parent`. Rename: `Daftar_SemuaRiwayat`.
4. Tarik **TinyDB** (Rename: `DB_Kel3`).

### B. Kode (Blocks)

Pindah ke **Blocks**.

1. Tarik blok kuning `when RiwayatTrans.Initialize do`.
2. Klik `Daftar_SemuaRiwayat`, tarik blok hijau muda `set Daftar_SemuaRiwayat.Elements to`.
3. Pasangkan dengan blok ungu `call DB_Kel3.GetValue`. Isi `tag`-nya dengan teks pink `"DataRiwayat"`. Isi `valueIfTagNotThere` dengan blok biru muda `create empty list`.

---

## TAHAP 6: Desain & Blocks - TipsTrik

Ganti screen aktif ke **TipsTrik** melalui menu dropdown di bagian atas layar. Di sini kita akan membuat panduan tips menabung statis yang langsung muncul tanpa perlu coding rumit.

### A. Desain (Designer)

1. **Paste Header Utama:**
   - Ganti screen kembali ke `HalamanUtama` sebentar.
   - Klik komponen `HorizontalArrangement` (Header) yang berisi Logo Anda.
   - Tekan tombol **Ctrl + C** (Copy) di keyboard.
   - Ganti screen kembali ke `TipsTrik`. Tekan tombol **Ctrl + V** (Paste). Header dan Logo otomatis terpasang rapi di bagian atas.
2. **Membuat Judul Halaman:**
   - Dari panel **Palette** > **User Interface**, klik tahan dan tarik komponen **Label** ke layar, tepat di bawah header.
   - Perhatikan panel **Properties** di sebelah kanan:
     - Centang kotak **FontBold** (agar huruf tebal).
     - Ubah **FontSize** menjadi `20` (agar ukuran huruf lebih besar).
     - Ubah kotak **Text** menjadi: `Tips & Trik Menabung`.
3. **Menyiapkan Tempat Daftar (ListView):**
   - Dari panel **Palette** > **User Interface**, tarik komponen **ListView** letakkan tepat di bawah judul tadi.
   - Di panel **Properties**, ubah **Height** menjadi `Fill parent` dan **Width** menjadi `Fill parent` agar daftar tips mengisi penuh sisa ruang kosong di layar HP.
   - Di panel **Components**, klik **Rename Component** dan ubah namanya menjadi: `List_Tips`.
4. **Memasukkan Teks 3 Tips Otomatis:**
   - Pastikan komponen `List_Tips` masih Anda klik/pilih.
   - Di panel **Properties** sebelah kanan, cari kotak putih yang bernama **ElementsFromString**.
   - Di dalam kotak tersebut, ketik 3 contoh tips ini persis seperti di bawah ini **(PENTING: Pisahkan dengan tanda koma, dan TIDAK BOLEH ADA SPASI SETELAH TANDA KOMA):**
     `1. Bawa bekal minum dan makanan dari rumah,2. Tahan godaan jajan hal yang tidak penting,3. Sisihkan uang di awal minggu bukan menyisakan`
   - Setelah selesai mengetik, klik sembarang tempat di layar kosong dan tulisan tersebut akan otomatis tersusun menjadi daftar menurun.

### B. Kode (Blocks)

Untuk halaman Tips & Trik ini, karena isinya bersifat statis (hanya tulisan panduan bacaan untuk user), maka pengaturan lewat **ElementsFromString** di langkah ke-4 tadi sudah sangat cukup.

Anda **TIDAK PERLU** menyusun kode apa pun di tampilan Blocks untuk halaman ini.

> **PENTING:** Silakan coba Run program dari awal sampai akhir di HP Anda! Coba lakukan Input Saldo, lalu periksa halaman Visual Tabungan apakah tinggi air di dalam toples sudah naik otomatis sesuai target. Jika semuanya lancar, jangan lupa klik **Projects > Save project**.

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
   - Dari **Palette** > **User Interface**, tarik komponen **Image** ke dalam kotak HorizontalArrangement tadi.
   - Di panel **Components**, klik tombol **Rename Component** pada gambar tersebut, ubah namanya menjadi: `Logo_Aplikasi`.
   - Di panel **Properties**, cari kotak centang bernama **Clickable** dan **wajib dicentang** (agar logo bisa ditekan untuk kembali ke halaman utama).
   - Tarik **Label** di sebelah logo jika ingin memberi teks judul aplikasi MTsN 1.
2. **Teks Level:** Dari panel **Palette** > **User Interface**, tarik komponen **Label** ke bawah header.
   - Di panel **Properties**, perbesar Font menjadi `24` dan centang **FontBold**.
   - Ubah Text menjadi: `Level Anda: Menghitung...`.
   - Klik **Rename Component**, ubah menjadi: `Teks_Level`.
3. **Layout Kotak:** Dari panel **Palette** > **Layout**, tarik **TableArrangement** ke bawah label level.
   - Di Properties, ubah **Columns** menjadi `2` dan **Rows** menjadi `2`.
4. **Tombol Menu:** Tarik 4 buah **Button** ke dalam kotak TableArrangement tersebut.
   - Button 1 -> Rename: `Menu_Input`, Text: `Input Saldo`.
   - Button 2 -> Rename: `Menu_Visual`, Text: `Visual Tabungan`.
   - Button 3 -> Rename: `Menu_Riwayat`, Text: `Riwayat`.
   - Button 4 -> Rename: `Menu_Tips`, Text: `Tips Menabung`.
5. **Database:** Tarik **TinyDB** dari kategori Storage. Rename menjadi `DB_Kel3`.

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

1. **Logika Logo (Kembali ke Home):**
   - Klik `Logo_Aplikasi` di panel kiri, tarik `when Logo_Aplikasi.Click do`.
   - Dari kategori **Control**, tarik `open another screen screenName`. Isi dengan teks pink `"HalamanUtama"`.
2. **Logika Navigasi Menu:**
   - Di panel kiri, klik `Menu_Input`. Tarik blok kuning `when Menu_Input.Click do`. Dari kategori **Control**, tarik blok `open another screen screenName`. Isi dengan teks pink `"InputData"`.
   - Ulangi langkah di atas untuk `Menu_Visual` (buka `"SaldoVisual"`), `Menu_Riwayat` (buka `"RiwayatTrans"`), dan `Menu_Tips` (buka `"TipsTrik"`).
3. **Sistem Level Tabungan:**
   - Tarik blok kuning `when HalamanUtama.Initialize do`.
   - Kita buat variabel untuk menghitung saldo sementara. Dari kategori **Variables**, tarik `initialize local name to`. Ganti nama jadi `SaldoTotal`.
   - Isi dengan blok Math kurang `-`. Kiri: `GetValue` tag `"TotalMasuk"`. Kanan: `GetValue` tag `"TotalKeluar"`. (Beri default `0`).
   - Di bawahnya, tarik blok `if then` dari **Control**. Klik ikon gir biru pada blok `if`, tarik kotak `else if` sebanyak 3 kali, dan terakhir `else`.
   - **Kondisi 1:** Tarik blok Math kurang dari `<`. Jika `get SaldoTotal` < `50000`, pasang `set Teks_Level.Text to` teks pink `"Level: Newbie Boros"`.
   - **Kondisi 2:** Jika `get SaldoTotal` < `100000`, pasang teks `"Level: Apprentice Hemat"`.
   - **Kondisi 3:** Jika `get SaldoTotal` < `500000`, pasang teks `"Level: Warrior Nabung"`.
   - **Kondisi 4:** Jika `get SaldoTotal` < `1000000`, pasang teks `"Level: Knight Investasi"`.
   - **Kondisi Else (Lebih dari 1 juta):** Pasang teks `"Level: Legend of Saldo"`.

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

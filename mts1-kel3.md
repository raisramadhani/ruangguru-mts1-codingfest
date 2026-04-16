# Tutorial Membuat Aplikasi KELOMPOK 3 (MTsN 1 Surakarta)

Pastikan Anda sudah login ke MIT App Inventor dan berada di tampilan **Designer**.

---

## TAHAP 1: Membuat Screen Baru

Buat 5 screen baru:

1. `HalamanUtama`
2. `InputData`
3. `SaldoVisual`
4. `RiwayatTrans`
5. `TipsTrik`

---

## TAHAP 2: Desain & Blocks - HalamanUtama

**A. Desain (Designer)**

1. **Layout Kotak:** Tarik **TableArrangement** (2 Columns, 2 Rows). Masukkan 4 **Button** ke dalamnya (Input, Saldo, Riwayat, Tips).
2. Tarik **Label** di atas layar. Rename: `Teks_Level`. Font perbesar.
3. Tarik **TinyDB** (`DB_Kel3`).

**B. Kode (Blocks)**

1. **Navigasi:** Buat blok navigasi untuk ke-4 tombol.
2. **Logika Level:** Saat `Initialize`, cek Saldo (Masuk - Keluar). Gunakan blok `if else if`.
   - If Saldo < 50000 -> Level "Newbie Boros"
   - Else If Saldo < 100000 -> Level "Apprentice Hemat"
   - Else If Saldo < 500000 -> Level "Warrior Nabung"
   - Else If Saldo < 1000000 -> Level "Knight Investasi"
   - Else -> Level "Legend of Saldo".

---

## TAHAP 3: Desain & Blocks - InputData

_(Sama dengan tutorial Pemasukan/Pengeluaran pada umumnya)_

1. Buat form input untuk Pemasukan (simpan ke `"TotalMasuk"`).
2. Buat form input untuk Pengeluaran (simpan ke `"TotalKeluar"`).
3. Buat form input untuk Target (simpan ke `"TargetNominal"`).

---

## TAHAP 4: Desain & Blocks - SaldoVisual

Ini adalah fitur utama. Kita akan membuat visual air yang naik turun.

**A. Desain (Designer)**

1. Tarik **VerticalArrangement** (Rename: `Wadah_Toples`, Height: `300 pixels`, Width: `150 pixels`, Align: Bottom). Beri Background Color abu-abu transparan.
2. Di dalamnya, tarik **Label** (Rename: `Visual_Air`, Text kosongkan, BackgroundColor: Biru, Width: Fill Parent, Height: `1 Percent`).
3. Tarik **Label** (`Teks_Persen`) untuk melihat angka.
4. Tarik **TinyDB** (`DB_Kel3`).

**B. Kode (Blocks)**

1. Saat `Initialize`, hitung `Saldo` (Masuk - Keluar) dan ambil `Target` (`GetValue` `"TargetNominal"`).
2. Hitung persentase: `(Saldo / Target) * 100`.
3. Gunakan blok `set Visual_Air.HeightPercent to`. Pasangkan hasil persentase tadi (pastikan dilimit maksimal 100 agar tidak error).
4. Jika persentase >= 100, munculkan Notifier: "Selamat! Target Tercapai, Level Baru Terbuka!".

---

## TAHAP 5 & 6: RiwayatTrans & TipsTrik

_(Pembuatannya persis seperti Kelompok 1 dan instruksi referensi asli Kelompok 1 tahap Tips & Trik dengan komponen ListView)._

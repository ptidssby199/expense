# MyExpense – Pencatat BBM & Token Listrik
PWA statis (HTML/CSS/JS), data tersimpan lokal di IndexedDB per username. Export laporan ke PDF & Excel.

## Deploy ke GitHub Pages
1. Buat repo baru, upload semua file di folder ini ke root repo.
2. Settings → Pages → Source: *Deploy from a branch* → `main` / `(root)`.
3. Buka `https://USERNAME.github.io/NAMA-REPO/` lalu "Install / Add to Home Screen".

## Cara hitung
- **L/km**: (total liter pengisian ke-2 dst) ÷ (selisih odometer). Asumsi isi sampai penuh.
- **kWh/hari**: kWh token (kecuali pembelian terakhir) ÷ jumlah hari antara pembelian pertama dan terakhir.
- **kWh/bulan**: kWh/hari × 30,4 (estimasi).

## Akun, PIN, backup
- Tombol **👤 username** di pojok kanan atas: pasang/ubah/hapus PIN, backup, restore, kunci sesi, ganti pengguna.
- PIN (4–6 angka) disimpan sebagai hash SHA-256 + salt di IndexedDB. Sesi terkunci otomatis setelah 15 menit tidak aktif.
- Backup berupa file `.json` berisi catatan (tanpa PIN). Restore bisa *gabungkan* (duplikat dilewati) atau *ganti semua*.
- Catatan: PIN hanya penghalang di sisi aplikasi, bukan enkripsi data.

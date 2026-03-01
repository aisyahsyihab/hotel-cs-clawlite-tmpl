# CONTEXT.md - {{HOTEL_NAME}}

<villa-info>
Nama: {{HOTEL_NAME}}
Lokasi: {{HOTEL_ADDRESS}}
Telepon: {{HOTEL_PHONE}}
Email: {{HOTEL_EMAIL}}
</villa-info>

<akses-lokasi>
- Jalan menuju villa sempit, hanya muat satu mobil
- Ada petugas pengatur lalu lintas di lokasi (sistem buka-tutup jalan)
- Minta panduan langsung ke manajemen atau ikuti petunjuk petugas
</akses-lokasi>

<daftar-kamar>
⚠️ HANYA ada 4 kamar berikut. JANGAN PERNAH menyebut kamar lain!

| ID | Nama     | Tipe | Kapasitas | Weekday     | Weekend     | Long Weekend | Item Code   |
|----|----------|------|-----------|-------------|-------------|--------------|-------------|
| 1  | SINDORO  | VVIP | 4 orang   | Rp 1.800.000| Rp 1.950.000| Rp 2.200.000 | R. SINDORO  |
| 2  | BISMO    | VIP  | 2 orang   | Rp 820.000  | Rp 900.000  | Rp 1.000.000 | R. BISMO    |
| 3  | PAKUWOJO | VIP  | 2 orang   | Rp 820.000  | Rp 900.000  | Rp 1.000.000 | R. PAKUWOJO |
| 4  | SEMERU   | VVIP | 4 orang   | Rp 1.650.000| Rp 1.800.000| Rp 2.000.000 | R. SEMERU   |

Semua kamar VVIP dan VIP termasuk Free BBQ untuk 4 orang.
Setiap kamar hanya ada 1 unit — kalau sudah dibooking, tidak tersedia di tanggal yang sama.

Room ID mapping:
- SINDORO = 1
- BISMO = 2
- PAKUWOJO = 3
- SEMERU = 4
</daftar-kamar>

<daftar-item>
⚠️ HANYA item berikut yang bisa ditambahkan ke booking. JANGAN mengarang item lain!

| Item Code                 | Nama                      | Harga       |
|---------------------------|---------------------------|-------------|
| Dekorasi                  | Dekorasi                  | Rp 150.000  |
| Dekorasi (free)           | Dekorasi (free)           | Rp 0        |
| Extra Bed                 | Extra Bed                 | Rp 250.000  |
| Extra Bed (tanpa sarapan) | Extra Bed (tanpa sarapan) | Rp 220.000  |
| Extra Sarapan             | Extra Sarapan             | Rp 30.000   |
| Stay Tanpa Extra Bed      | Stay Tanpa Extra Bed      | Rp 100.000  |

Item kamar (otomatis dari booking, tidak perlu ditambahkan manual):
- R. BISMO, R. PAKUWOJO, R. SEMERU, R. SINDORO

Cara menambahkan extra item ke booking:
```
--extra "Item Code:Jumlah"
```

Contoh:
- 1 extra bed: `--extra "Extra Bed:1"`
- 2 extra bed + dekorasi: `--extra "Extra Bed:2" "Dekorasi:1"`
- 1 extra sarapan: `--extra "Extra Sarapan:1"`
</daftar-item>

<kebijakan>
Check-in: 14:00 WIB
Check-out: 12:00 WIB
Uang Muka (DP): minimal 30% dari total
Extra Bed: Rp 250.000/malam (termasuk sarapan)
Extra Bed tanpa sarapan: Rp 220.000/malam
</kebijakan>

<cara-hitung-harga>
Weekday = check-in hari Senin sampai Kamis
Weekend = check-in hari Jumat sampai Minggu

Kalau menginap lintas kategori, SPLIT jadi item terpisah:
- Check-in Kamis, checkout Sabtu = 1 malam weekday + 1 malam weekend
- Hitung masing-masing dengan rate yang sesuai

Contoh BISMO (Kamis-Sabtu):
- 1 malam weekday: Rp 820.000
- 1 malam weekend: Rp 900.000
- Total: Rp 1.720.000
</cara-hitung-harga>

<faq>
Jika ditanya tentang fasilitas, pembatalan, pembayaran, hewan peliharaan, rekomendasi:
1. Baca FAQ.md dengan read_file
2. Jawab berdasarkan isi FAQ.md
3. Jangan menyebutkan "FAQ.md" atau "file" ke tamu
</faq>

# TokoKita

Aplikasi toko daring berbasis PHP dan CodeIgniter 3. Aplikasi ini menyediakan katalog produk, akun pelanggan, keranjang belanja, pengelolaan toko dan produk, panel admin, serta alur ongkos kirim dan pembayaran yang terhubung dengan layanan eksternal.

## Fitur

- Menampilkan katalog, kategori, dan detail produk.
- Registrasi, login, dan dashboard pelanggan.
- Keranjang belanja untuk pelanggan yang sudah login.
- Pengelolaan toko, produk, kategori, ongkos kirim, dan member melalui panel admin.
- Pengambilan data kota dan perhitungan ongkos kirim melalui RajaOngkir.
- Integrasi Midtrans disertakan sebagai library CodeIgniter; konfigurasi kredensial dan pengaktifan alur pembayaran perlu disesuaikan dengan akun merchant.

## Teknologi

- PHP dan CodeIgniter 3.1.13
- MySQL atau MariaDB
- Apache (misalnya melalui XAMPP)
- cURL PHP untuk panggilan API ongkos kirim

## Menjalankan secara lokal

1. Pasang project di document root Apache, misalnya `htdocs/tokokita_DB3`.
2. Buat database MySQL/MariaDB bernama `tokokita_1995`.
3. Impor `tokokita_1995.sql` ke database tersebut. File `tokokita_1234.sql` juga tersedia sebagai dump database alternatif.
4. Sesuaikan kredensial database di `application/config/database.php`.
5. Sesuaikan `$config['base_url']` di `application/config/config.php` dengan alamat dan nama folder project. Nilai bawaan adalah `http://localhost/tokokita_db3/`.
6. Pastikan Apache dan MySQL berjalan, kemudian buka `http://localhost/tokokita_DB3/`.

> **Catatan integrasi eksternal:** fitur ongkos kirim memerlukan API RajaOngkir yang aktif. Kredensial API perlu dikelola dan diperbarui sesuai pengaturan akun Anda. Untuk transaksi Midtrans, gunakan server key dan client key dari akun merchant serta mode sandbox saat pengembangan; jangan memasukkan kredensial rahasia ke repository.

## Struktur utama

```text
application/
  controllers/   Controller halaman toko, produk, member, dan admin
  models/        Model akses data
  views/         Tampilan toko dan panel admin
  config/        Konfigurasi CodeIgniter dan koneksi database
assets/          Aset frontend dan admin
system/          Framework CodeIgniter 3
tokokita_1995.sql
tokokita_1234.sql
```

## Catatan

- Aplikasi menggunakan CodeIgniter 3, bukan versi CodeIgniter terbaru.
- Dump SQL dapat berisi data contoh untuk pengembangan. Jangan gunakan kredensial akun contoh pada lingkungan publik.
- Versi PHP yang kompatibel bergantung pada versi CodeIgniter dan ekstensi server yang terpasang. Aktifkan ekstensi `mysqli` dan `curl`.


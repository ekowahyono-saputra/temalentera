TEMA LENTERA FREE 1.0.0
=======================
Edisi Free terpisah, dibuat dari Lentera 1.26 untuk OpenSID PUBLIK 2607.0.1.
Tidak memerlukan aktivasi tema dan tidak menyertakan OpenSID Updater.
Paket tidak memiliki masa berlaku, nomor instalasi, atau panggilan API lisensi.
Keterangan "sementara" berarti edisi terpisah untuk kebutuhan saat ini, bukan
pembatasan waktu tersembunyi. Versi Lentera berlisensi tidak diubah.
Dukungan OpenSID Premium masih ditunda sesuai arahan pengguna.

FITUR
Beranda responsif, artikel, slider, menu mobile, APBDes, statistik, perangkat
desa, Smart Insight, ikon WhatsApp kontak desa, animasi cuaca dan gempa.
Pengaturan dapat mengaktifkan gaya admin/login kustom dan notifikasi surat via
Mpedia. Gateway memerlukan akun, nomor pengirim, dan API key milik pengguna;
widget cuaca memerlukan kode wilayah BMKG adm4 yang benar.
Semua rahasia gateway bernilai kosong dalam konfigurasi distribusi.

STRUKTUR
- desa/themes/lentera/ : tema dan aset
- donjo-app/ : library/controller/rute integrasi OpenSID
- app/ : service dan listener notifikasi
- resources/ : komponen pengaturan serta tampilan admin
- pemulihan-admin/, pemulihan-login/, pemulihan-notifikasi/ : referensi bawaan
Ini satu paket tambahan untuk OpenSID, bukan instalasi OpenSID lengkap.

PASANG BARU PADA OPENSID PUBLIK 2607.0.1
1. Cadangkan file dan database. Jika ada modifikasi sendiri pada file inti,
   gabungkan perubahan yang diperlukan, jangan menimpa modifikasi tersebut.
2. Salin folder desa/themes/lentera/ ke root OpenSID.
3. Salin isi app/, donjo-app/, resources/ ke path yang sama di root OpenSID.
   Path Theme.php dalam paket adalah controller standar 2607 tanpa aktivasi.
   Folder pemulihan hanya referensi; tidak disalin ke root aplikasi.
4. Pindai tema dari menu Tema, pilih Lentera, dan simpan pengaturannya.
   Metadata akan menyebut Lentera Free; nama folder/menu tetap Lentera.
5. Bersihkan cache Blade. Perbarui autoload Composer bila hosting memakai
   classmap authoritative agar service tambahan dapat dikenali.
6. Atur wilayah cuaca dan sakelar fitur yang diperlukan. Periksa tampilan
   desktop/mobile serta fitur admin pada hosting.

BERALIH DARI LENTERA 1.26
- Cadangkan folder tema dan file integrasi, serta pengaturan opsi yang ada.
- Ganti folder desa/themes/lentera dengan folder pada paket ini, lalu salin
  app/, donjo-app/, resources/ pada path yang sama seperti pemasangan baru.
- Karena ZIP tidak menghapus file lama, setelah pencadangan hapus file aktivasi
  lama berikut yang tidak ada dalam paket Free:
  app/Services/LenteraLicense.php
  donjo-app/controllers/Lentera_lisensi.php
  resources/views/admin/theme/components/form/input-lentera-license.blade.php
  desa/themes/lentera/resources/views/lentera/license-inactive.blade.php
- Rute lentera.php dan Theme.php dari paket Free menggantikan panggilan aktivasi.
- Simpan pengaturan tema untuk menyelaraskan opsi; opsi aktivasi/updater tidak
  lagi muncul dalam config.json atau digunakan oleh edisi Free.
- Jangan hapus penyimpanan nomor instalasi versi berlisensi bila ingin kembali
  ke versi tersebut. Edisi Free tidak membaca atau menerbitkan nomor instalasi.
- Tools updater yang sebelumnya dipasang terpisah tidak otomatis terhapus oleh
  ZIP ini. Jika ingin menghapusnya dari hosting, cadangkan kemudian hapus
  opensid-updater.php dan opensid-updater-config.php yang dipasang sebelumnya.
  Tautan/pengaturan updater tidak ada dalam edisi Free.
- Folder lentera dipakai bersama edisi berlisensi: satu instalasi hanya memakai
  satu edisi pada path ini. Simpan cadangan agar pergantian dapat dipulihkan.

UNTUK REPOSITORI GITHUB
Ekstrak paket; unggah isi root paket ke repositori yang disiapkan pengguna.
Sertakan LICENSE dan atribusi. Jangan unggah konfigurasi hosting, folder cache,
.env, database warga, kredensial gateway, atau file pengaturan desa nyata.
.gitignore disediakan untuk data runtime umum.
Belum ada unggahan, commit, atau publikasi ke GitHub yang dilakukan.

PENGUJIAN
Lihat HASIL-UJI.txt. Paket diperiksa statis; PHP CLI dan hosting tidak tersedia
untuk uji PHP/Blade, data aktual, login, API BMKG atau pengiriman WhatsApp.

# Nusantara Cerdas Mobile

Aplikasi Flutter contoh layanan warga dengan formulir pengajuan, riwayat,
chat petugas, peta kantor, dan statistik pengajuan.

## Menjalankan aplikasi

```sh
flutter pub get
flutter run
```

## Menyiapkan Google Maps API key

Peta menggunakan `google_maps_flutter` dan menampilkan tiga kantor layanan.
API key sengaja tidak disertakan. Agar peta dapat memuat tile Google Maps:

1. Buat API key Google Maps Platform yang dibatasi sesuai kebutuhan aplikasi.
2. Aktifkan Maps SDK for Android pada project Google Cloud terkait.
3. Tambahkan metadata berikut di dalam elemen `<application>` pada
   `android/app/src/main/AndroidManifest.xml`, lalu ganti nilainya dengan API
   key milik Anda:

   ```xml
   <meta-data
       android:name="com.google.android.geo.API_KEY"
       android:value="PASTE_YOUR_GOOGLE_MAPS_API_KEY_HERE" />
   ```

Peta tetap memerlukan API key valid pada perangkat/emulator untuk menampilkan
ubin peta. Penanda dan UI daftar kantor sudah tersedia di aplikasi.

## Struktur inti

- `lib/navigation/`: konstanta route dan kerangka navigasi bawah.
- `lib/model/`: `PengajuanModel` berbasis `ChangeNotifier`.
- `lib/pages/`: beranda warga, formulir/rincian, chat, peta, dan statistik.

Status pengajuan dibagikan melalui Provider. Formulir memiliki validasi email,
persetujuan data, pilihan sesi, dan indikator proses pengiriman.

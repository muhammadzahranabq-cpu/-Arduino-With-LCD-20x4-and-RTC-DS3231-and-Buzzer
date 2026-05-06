# Arduino Jam Digital dengan LCD 20x4, RTC DS3231, dan Buzzer

Proyek ini menampilkan jam digital menggunakan Arduino Uno, modul RTC DS3231, dan layar LCD 20x4. Waktu ditampilkan bersama hari dan tanggal dalam format Indonesia, serta ada bunyi buzzer setiap detik.

## Fitur

- Menampilkan hari, tanggal, dan waktu pada LCD 20x4
- Menggunakan modul RTC DS3231 untuk waktu real-time
- Menampilkan nama hari dalam bahasa Indonesia
- Bunyi buzzer sederhana setiap detik
- Ditargetkan untuk board `Arduino Uno`

## Komponen yang dibutuhkan

- Arduino Uno
- LCD 20x4 (LiquidCrystal)
- Modul RTC DS3231
- Buzzer pasif
- Kabel jumper
- Breadboard (opsional)

## Koneksi pin utama

### LCD 20x4
- RS -> D7
- EN -> D6
- D4 -> D5
- D5 -> D4
- D6 -> D3
- D7 -> D2

### RTC DS3231
- SDA -> A4 (I2C SDA pada Arduino Uno)
- SCL -> A5 (I2C SCL pada Arduino Uno)
- VCC -> 5V
- GND -> GND

### Buzzer
- Buzzer -> D8
- GND buzzer -> GND

> Catatan: Kode saat ini juga mengatur pin D10 sebagai OUTPUT, tetapi pin ini belum digunakan dalam `loop()`.

## Struktur proyek

- `platformio.ini` — konfigurasi PlatformIO untuk Arduino Uno
- `src/main.cpp` — kode utama aplikasi
- `include/` — folder header tambahan (jika diperlukan)
- `lib/` — folder pustaka tambahan (jika diperlukan)
- `test/` — folder untuk tes (saat ini kosong)

## Library yang diperlukan

- `RTClib` (untuk modul DS3231)
- `LiquidCrystal` (bawaan Arduino)

## Langkah penggunaan

1. Buka proyek di PlatformIO.
2. Pastikan board yang digunakan adalah `Arduino Uno`.
3. Sambungkan perangkat keras sesuai diagram pin di atas.
4. Build dan upload ke board.

## Penjelasan singkat kode

- `lcd.begin(20, 4)` untuk memulai LCD 20x4.
- `rtc.begin()` untuk memulai modul RTC.
- Jika RTC kehilangan daya, waktu akan diset ke waktu kompilasi.
- `loop()` membaca waktu RTC dan menampilkan hari, tanggal, jam, menit, detik.
- Fungsi `printAngka()` memastikan angka selalu tampil dua digit.
- `tone(8, 1000, 50)` menghasilkan bunyi buzzer singkat setiap siklus.

## Lisensi

Terserah pengguna untuk memilih lisensi yang sesuai. README ini hanya dokumentasi proyek.

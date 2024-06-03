# orientasi perangkat

#### Sensor yang Digunakan
- **Sensor Akselerometer**: Digunakan untuk mengukur percepatan linier perangkat di sepanjang sumbu X, Y, dan Z.

#### Cara Kerja
1. **Inisialisasi**:
    - Pada `onCreate()`, aplikasi mendapatkan instance `SensorManager` dan mengakses akselerometer.
    - Inisialisasi `TextView` untuk menampilkan orientasi perangkat.

2. **Pendaftaran Listener**:
    - Pada `onResume()`, aplikasi mendaftarkan `SensorEventListener` untuk akselerometer.
    - Pada `onPause()`, aplikasi menghentikan pendaftaran listener.

3. **Pengolahan Data Sensor**:
    - Metode `onSensorChanged(SensorEvent event)` dipanggil saat data sensor berubah.
    - Memeriksa nilai X dan Y dari `event.values[]` untuk menentukan orientasi:
        - |X| < |Y|:
            - Y positif: `Portrait`
            - Y negatif: `Reverse Portrait`
        - |X| > |Y|:
            - X positif: `Landscape`
            - X negatif: `Reverse Landscape`
    - Menampilkan orientasi pada `TextView`.

4. **Pengaturan Akurasi**:
    - Metode `onAccuracyChanged(Sensor sensor, int accuracy)` diimplementasikan tetapi tidak digunakan.

#### Respon dari Inputan Sensor
- Aplikasi meng-update orientasi perangkat dan menampilkannya sebagai teks (`Portrait`, `Reverse Portrait`, `Landscape`, `Reverse Landscape`) pada `TextView` saat data akselerometer berubah.

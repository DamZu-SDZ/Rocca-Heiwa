# Rocca Heiwa: IoT-Based Smart Locker System

**Rocca Heiwa** ialah sebuah projek sistem loker pintar berasaskan Internet of Things (IoT) yang direka untuk mengatasi kelemahan keselamatan serta isu kehilangan kunci fizikal pada sistem loker tradisional.
Sistem ini menawarkan mekanisme kawalan akses yang lebih selamat, efisien, dan mesra pengguna, menjadikannya sangat sesuai untuk diaplikasikan di institusi pendidikan, pejabat, mahupun kemudahan awam.

---

## 📌 Ciri-Ciri Utama (Key Features)

**Dua Kaedah Autentikasi (Dual Authentication):** Pengguna boleh membuka loker menggunakan kad RFID/NFC (melalui modul PN532) atau dengan mengimbas kod QR yang sah menerusi antara muka web.
**Pemantauan Masa Nyata (Real-Time Monitoring):** Menggunakan keupayaan ketersambungan Wi-Fi pada ESP32 untuk berkomunikasi dengan pelayan bagi pengesahan data dan status loker secara langsung.
**Pengurusan Data Selamat:** Menyokong sistem pendaftaran pengguna baharu berasaskan pengenal unik (*username*/emel) dengan fungsi pencatukan kata laluan (*password hashing*) demi menjaga privasi dan keselamatan maklumat.
**Sistem Maklum Balas Audio:** Dilengkapi dengan buzzer SFM-27 untuk memberikan isyarat bunyi atau amaran berdasarkan status autentikasi (berjaya atau gagal).

---

## 🛠️ Spesifikasi Komponen (Hardware & Software)

### Perkakasan (Hardware)
**ESP32 Development Board** – Sebagai mikropengawal utama untuk mengawal operasi, komunikasi IoT, dan komponen output.
**PN532 NFC RFID Module** – Untuk membaca UID daripada kad atau tag RFID bagi tujuan pengenalan pengguna.
**DC12V Solenoid Door Lock** – Aktuator utama untuk mengunci dan membuka pintu loker secara fizikal.
**1-Channel 5V Active Low Relay Module** – Bertindak sebagai suis elektronik yang dikawal oleh ESP32 untuk memicu solenoid.
**LM2596 Step-Down (Buck) Converter** – Menurunkan voltan daripada adapter 12V kepada 5V yang stabil untuk membekalkan kuasa kepada ESP32 dan modul relay.
**Buzzer SFM-27** – Menyediakan notifikasi bunyi bagi status sistem.

### Perisian (Software)
**Arduino IDE** – Platform penulisan dan muat naik kod pengaturcaraan (C/C++) ke ESP32.
**Hostinger & Ngrok** – Digunakan untuk pengehosan pangkalan data dan membolehkan komunikasi antara sistem IoT tempatan dengan pelayan web jauh.

---

## ⚙️ Cara Sistem Berfungsi (How It Works)

1. **Pengesanan Akses:** Pengguna mengimbas kad RFID pada modul PN532 atau menghantar permintaan melalui imbasan kod QR pada platform web.
2. **Pengesahan Pelayan:** ESP32 menghantar data autentikasi tersebut ke pelayan web melalui permintaan HTTP POST.
3. **Pemicuan Solenoid:** Jika pelayan mengesahkan data tersebut sah (True), ESP32 akan menghantar isyarat ke modul relay untuk mengaktifkan kunci solenoid 12V dan membuka pintu loker. Jika gagal, akses akan disekat (False).

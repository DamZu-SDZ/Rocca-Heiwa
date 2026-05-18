# Rocca Heiwa: IoT-Based Smart Locker System

[cite_start]**Rocca Heiwa** ialah sebuah projek sistem loker pintar berasaskan Internet of Things (IoT) yang direka untuk mengatasi kelemahan keselamatan serta isu kehilangan kunci fizikal pada sistem loker tradisional[cite: 14, 31, 32]. [cite_start]Sistem ini menawarkan mekanisme kawalan akses yang lebih selamat, efisien, dan mesra pengguna, menjadikannya sangat sesuai untuk diaplikasikan di institusi pendidikan, pejabat, mahupun kemudahan awam[cite: 32, 41, 42].

---

## 📌 Ciri-Ciri Utama (Key Features)

* [cite_start]**Dua Kaedah Autentikasi (Dual Authentication):** Pengguna boleh membuka loker menggunakan kad RFID/NFC (melalui modul PN532) atau dengan mengimbas kod QR yang sah menerusi antara muka web[cite: 34, 35, 111].
* [cite_start]**Pemantauan Masa Nyata (Real-Time Monitoring):** Menggunakan keupayaan ketersambungan Wi-Fi pada ESP32 untuk berkomunikasi dengan pelayan bagi pengesahan data dan status loker secara langsung[cite: 82, 111, 131].
* [cite_start]**Pengurusan Data Selamat:** Menyokong sistem pendaftaran pengguna baharu berasaskan pengenal unik (*username*/emel) dengan fungsi pencatukan kata laluan (*password hashing*) demi menjaga privasi dan keselamatan maklumat[cite: 72, 79].
* [cite_start]**Sistem Maklum Balas Audio:** Dilengkapi dengan buzzer SFM-27 untuk memberikan isyarat bunyi atau amaran berdasarkan status autentikasi (berjaya atau gagal)[cite: 59, 86].

---

## 🛠️ Spesifikasi Komponen (Hardware & Software)

### Perkakasan (Hardware)
* [cite_start]**ESP32 Development Board** – Sebagai mikropengawal utama untuk mengawal operasi, komunikasi IoT, dan komponen output[cite: 81, 82].
* [cite_start]**PN532 NFC RFID Module** – Untuk membaca UID daripada kad atau tag RFID bagi tujuan pengenalan pengguna[cite: 96, 134].
* [cite_start]**DC12V Solenoid Door Lock** – Aktuator utama untuk mengunci dan membuka pintu loker secara fizikal[cite: 57, 84].
* [cite_start]**1-Channel 5V Active Low Relay Module** – Bertindak sebagai suis elektronik yang dikawal oleh ESP32 untuk memicu solenoid[cite: 90, 91].
* [cite_start]**LM2596 Step-Down (Buck) Converter** – Menurunkan voltan daripada adapter 12V kepada 5V yang stabil untuk membekalkan kuasa kepada ESP32 dan modul relay[cite: 58].
* [cite_start]**Buzzer SFM-27** – Menyediakan notifikasi bunyi bagi status sistem[cite: 59, 86].

### Perisian (Software)
* [cite_start]**Arduino IDE** – Platform penulisan dan muat naik kod pengaturcaraan (C/C++) ke ESP32.
* [cite_start]**Hostinger & Ngrok** – Digunakan untuk pengehosan pangkalan data dan membolehkan komunikasi antara sistem IoT tempatan dengan pelayan web jauh[cite: 102, 105].

---

## ⚙️ Cara Sistem Berfungsi (How It Works)

1. [cite_start]**Pengesanan Akses:** Pengguna mengimbas kad RFID pada modul PN532 atau menghantar permintaan melalui imbasan kod QR pada platform web[cite: 15, 111].
2. [cite_start]**Pengesahan Pelayan:** ESP32 menghantar data autentikasi tersebut ke pelayan web melalui permintaan HTTP POST[cite: 62, 131].
3. [cite_start]**Pemicuan Solenoid:** Jika pelayan mengesahkan data tersebut sah (True), ESP32 akan menghantar isyarat ke modul relay untuk mengaktifkan kunci solenoid 12V dan membuka pintu loker[cite: 64, 112]. [cite_start]Jika gagal, akses akan disekat (False)[cite: 65, 124].

# Gardawara AI 🛡️🤖

**Gardawara AI** adalah aplikasi mobile berbasis **Flutter** yang dirancang sebagai benteng pertahanan digital untuk mendeteksi dan memblokir akses terhadap situs atau aplikasi judi online secara real-time. Menggunakan teknologi kecerdasan buatan (AI) lokal dan cloud, aplikasi ini bertujuan untuk melindungi pengguna dan keluarga dari bahaya kecanduan judi online.

---

## 🌟 Fitur Utama

- **🛡️ AI-Powered Gambling Blocker**
  Menggunakan model klasifikasi berbasis **TensorFlow Lite (TFLite)** secara lokal untuk menganalisis teks di layar dan mendeteksi indikasi konten judi online secara instan dan privat.
  
- **⚙️ Accessibility Service Integration**
  Berjalan di latar belakang menggunakan layanan aksesibilitas (*Accessibility Service*) Android untuk mendeteksi aktivitas mencurigakan dan melakukan pemblokiran proaktif (otomatis memicu navigasi *Back*).

- **💬 GardaChat (Gemini AI Chatbot)**
  Asisten virtual yang didukung oleh **Google Gemini AI** (`google_generative_ai`) untuk diajak berdiskusi, memberikan edukasi, dukungan psikologis, serta informasi terkait pencegahan judi online.

- **👥 Guardian Monitoring System**
  Fitur pemantauan jarak jauh untuk orang tua atau wali (*Guardian*). Terhubung dengan **Firebase Firestore** untuk memantau status perlindungan dan riwayat blokir secara real-time.

- **🔔 Heartbeat & Push Notifications**
  Sistem *heartbeat* background untuk memastikan perlindungan terus aktif, serta pengiriman notifikasi instan menggunakan **Firebase Cloud Messaging (FCM)** jika terjadi pemblokiran.

---

## 🛠️ Teknologi yang Digunakan

Aplikasi ini dibangun menggunakan ekosistem modern:

*   **Frontend Framework:** [Flutter](https://flutter.dev) (Dart SDK `^3.7.2`)
*   **Artificial Intelligence:**
    *   **Google Generative AI:** API Gemini untuk asisten chatbot pintar.
    *   **TensorFlow Lite (TFLite):** Klasifikasi teks lokal untuk deteksi konten judi secara offline.
*   **Backend & Cloud Services (Firebase):**
    *   **Firebase Core:** Inisialisasi layanan Firebase.
    *   **Cloud Firestore:** Sinkronisasi riwayat blokir dan data pengawasan.
    *   **Firebase Messaging (FCM):** Push notification real-time.
*   **Background Processing:** `workmanager` untuk menjalankan proses latar belakang (heartbeat).
*   **Local Storage:** `shared_preferences` untuk menyimpan statistik blokir dan konfigurasi lokal.
*   **Keamanan & Lingkungan:** `flutter_dotenv` untuk mengelola API Key dan variabel sensitif lainnya.

---

## 🚀 Panduan Memulai

### Prasyarat
Sebelum memulai, pastikan perangkat pengembangan Anda sudah terinstal:
- Flutter SDK (versi terbaru)
- Android Studio / VS Code

### Langkah Instalasi

1. **Clone Repository**
   ```bash
   git clone https://github.com/athallacode/gardawara.git
   cd gardawara
   ```

2. **Dapatkan Dependencies**
   Unduh paket library yang diperlukan dengan menjalankan:
   ```bash
   flutter pub get
   ```

3. **Konfigurasi Environment Variables**
   Buat file `.env` di direktori utama (root) proyek dan tambahkan API Key Gemini Anda:
   ```env
   GEMINI_API_KEY=YOUR_GEMINI_API_KEY_HERE
   ```

4. **Konfigurasi Firebase**
   - Buat proyek baru di [Firebase Console](https://console.firebase.google.com/).
   - Tambahkan aplikasi Android/iOS Anda ke Firebase.
   - Unduh file `google-services.json` (untuk Android) dan `GoogleService-Info.plist` (untuk iOS), lalu letakkan di folder platform masing-masing.
   - Atau gunakan CLI flutterfire untuk generate otomatis file `lib/firebase_options.dart`.

5. **Jalankan Aplikasi**
   Hubungkan emulator atau perangkat fisik Android, kemudian jalankan perintah:
   ```bash
   flutter run
   ```

---

## 📂 Struktur Folder Proyek

```text
lib/
├── common/              # Service, helper, dan utility global (Notification, Heartbeat, Classifier)
├── controller/          # Logic pengendali data flow aplikasi
├── model/               # Model data untuk parsing JSON/Firestore
├── screens/             # UI/Tampilan halaman (Home, Guardian, Chatbot, dll.)
└── main.dart            # Entry point utama aplikasi
```

---

*Dibuat dengan ❤️ untuk menciptakan ruang digital yang lebih sehat dan aman.*

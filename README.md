
CatBot Firebase adalah versi web interaktif dari CatBot yang menyimpan rules dan data jawaban menggunakan Firebase (Firestore atau Realtime Database). Proyek ini mendukung mode A dan B, fitur copy-paste jawaban, popup interaksi, dan UI WhatsApp-style.


---

Fitur Utama

Mode A: Mengambil jawaban dari rules.json (predefined rules).

Mode B: Menyimpan dan mengambil jawaban baru dari data.json (user-generated).

Popup interaktif saat jawaban belum tersedia.

UI WhatsApp-style untuk pengalaman chat yang familiar.

Copy jawaban ke clipboard dengan tombol 📋.

Responsive untuk tampilan HP.

Firebase Integration: menyimpan rules/data secara real-time.



---

Struktur Folder

catbot-firebase/
│
├─ index.html         # Halaman utama CatBot
├─ style.css          # Styling UI
├─ script.js          # Logika interaksi CatBot
├─ firebase.js        # Config & koneksi Firebase
├─ rules.json         # Rules default (Mode A)
├─ data.json          # Data jawaban (Mode B)
└─ assets/            # Gambar, ikon, atau aset lain


---

Setup Firebase

1. Buat proyek baru di Firebase Console.


2. Aktifkan Firestore atau Realtime Database.


3. Ambil konfigurasi Firebase (API key, projectId, dll).


4. Tambahkan firebase.js di proyek:



// Contoh firebase.js
import { initializeApp } from "https://www.gstatic.com/firebasejs/9.23.0/firebase-app.js";
import { getFirestore, collection, getDocs, setDoc, doc } from "https://www.gstatic.com/firebasejs/9.23.0/firebase-firestore.js";

const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_PROJECT_ID.firebaseapp.com",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_PROJECT_ID.appspot.com",
  messagingSenderId: "YOUR_SENDER_ID",
  appId: "YOUR_APP_ID"
};

const app = initializeApp(firebaseConfig);
export const db = getFirestore(app);


---

Cara Menjalankan

1. Clone atau download repo ke local/HP:



git clone https://github.com/username/catbot-firebase.git
cd catbot-firebase

2. Buka index.html di browser (Chrome/Firefox).


3. Pastikan koneksi internet aktif agar Firebase dapat membaca/menulis data.




---

Integrasi Rules & Data

Mode A: rules diambil dari rules.json atau Firestore rules collection.

Mode B: jawaban disimpan ke Firestore data collection, bisa ditambahkan pengguna.


Contoh Firestore struktur:

rules (collection)
 └─ greeting (document)
     └─ question: "Halo"
     └─ answer: "Hai, ada yang bisa saya bantu?"

data (collection)
 └─ user_responses (document)
     └─ question: "Apa itu Firebase?"
     └─ answer: "Firebase adalah platform cloud oleh Google."


---

Fitur Tambahan

Toggle Mode A/B di UI.

Popup untuk menambahkan jawaban baru jika belum ada.

Tombol 📋 Copy untuk menyalin jawaban.

Bisa dijalankan offline jika sudah memuat halaman dan assets (PWA-ready).



---

Lisensi

MIT License – bebas digunakan, dikembangkan, atau dimodifikasi.


---


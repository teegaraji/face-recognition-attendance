# face-recognition-attendance

face-recognition-attendance/
│── .gitignore # Mengabaikan file yang tidak perlu di-push ke GitHub
│── README.md # Dokumentasi proyek
│── requirements.txt # Daftar library yang dibutuhkan
│── main.py # File utama untuk menjalankan sistem
│
├── models/ # Model machine learning (face recognition)
│ ├── face_recognition_model.pth # Model yang sudah dilatih (jika ada)
│ ├── embeddings.pkl # Data wajah yang sudah diencode
│
├── dataset/ # Folder untuk menyimpan dataset wajah
│ ├── mahasiswa1/ # Folder untuk masing-masing mahasiswa
│ │ ├── img1.jpg
│ │ ├── img2.jpg
│ ├── mahasiswa2/
│ ├── img1.jpg
│ ├── img2.jpg
│
├── database/ # Folder database (SQLite)
│ ├── attendance.db # Database SQLite
│ ├── schema.sql # Struktur tabel database
│
├── utils/ # Helper functions
│ ├── face_recognition.py # Fungsi untuk mengenali wajah
│ ├── database.py # Fungsi untuk menyimpan data ke database
│
├── gui/ # Jika menggunakan GUI (misalnya Streamlit)
│ ├── app.py # File utama untuk tampilan UI
│
└── notebooks/ # Jika ada eksperimen dengan Jupyter Notebook
├── face_recognition_experiment.ipynb

    Audi Husen → yolo_face_detection.py, face_preprocessing.py

    Helena → face_recognition.py, threading_optimization.py

    Tegar Aji → face_recognition.py, db_handler.py, accuracy_testing.py

    Rizki Latifasari → attendance_system.py, accuracy_testing.py

Masing-masing bisa mengerjakan di file mereka sendiri lalu menggabungkannya di main.py. Jadi, main.py hanya akan memanggil fungsi-fungsi dari modul lain, bukan berisi semua kode dalam satu file.

# Contoh Pemanggilan

from face_recognition.yolo_face_detection import detect_faces
from face_recognition.face_recognition import recognize_faces
from database.db_handler import save_attendance
from attendance.attendance_system import mark_attendance

# Contoh alur sistem

frame = get_frame_from_camera()
faces = detect_faces(frame)
recognized_faces = recognize_faces(faces)
save_attendance(recognized_faces)
mark_attendance(recognized_faces)

<div align="center">

<img src="https://i.ibb.co/YTYGn5qV/logo.png" alt="SnapClass Logo" width="100"/>

# SnapClass 📸🎙️

### AI-Powered Attendance System

Revolutionizing the classroom with next-gen **computer vision** and **voice biometrics**.  
Attendance done in seconds — not minutes.

[![Live App](https://img.shields.io/badge/Live%20App-Streamlit-FF4B4B?style=for-the-badge&logo=streamlit)](https://snapclass-gqv3a6sgks5qdwwgwiotlc.streamlit.app/)
[![Landing Page](https://img.shields.io/badge/Landing%20Page-Vercel-000000?style=for-the-badge&logo=vercel)](https://snap-class-landing-lyart.vercel.app)
[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python)](https://python.org)

</div>

---

## 📖 About

**SnapClass** is an AI-powered attendance management system built with Streamlit and Python. It eliminates the tedious manual roll-call process by leveraging two cutting-edge biometric methods:

- **Face Recognition** — Take a single photo of the classroom, and AI instantly identifies every student present.
- **Voice Identification** — Students say "Present" one-by-one; the system matches their voice against stored embeddings in real-time.

Built as a project for **Apna College**, SnapClass is backed by a Supabase cloud database and supports QR-code-driven student enrollment.

---

## ✨ Features

| Feature | Description |
|---|---|
| 📸 **AI Face Analysis** | Recognizes every student from a single class photo using neural networks |
| 🎙️ **Sequential Voice ID** | Matches student voice biometrics against stored embeddings in real-time |
| 📱 **QR-Driven Enrollment** | Course codes generate unique QR codes for instant student enrollment |
| 🔐 **Secure Auth** | Teacher and student login with hashed passwords via `bcrypt` |
| 📊 **Attendance Records** | View confidence scores, historical logs, and download CSV reports |
| ☁️ **Cloud Database** | Real-time PostgreSQL via Supabase for synced data across all devices |
| 🔗 **Auto-Enroll via Link** | Students can join a class directly via a `?join-code=` URL parameter |

---

## 🏗️ Project Structure

```
SnapClass/                        # Main Application (Streamlit)
├── app.py                        # Entry point — routes between home, teacher, and student screens
├── requirements.txt              # Python dependencies
├── .gitignore
├── .devcontainer/                # Dev container config
└── src/
    ├── screens/
    │   ├── home_screen.py        # Landing/login screen (role selection)
    │   ├── teacher_screen.py     # Teacher dashboard & attendance controls
    │   └── student_screen.py     # Student portal & attendance history
    └── components/
        └── dialog_auto_enroll.py # Auto-enroll dialog triggered by QR join-code

SnapClass-landing/                # Landing Page (Flask + HTML/CSS)
├── app.py                        # Flask server serving the landing page
├── requirements.txt
├── templates/
│   └── index.html                # Main landing page template
└── static/                       # CSS, images, and assets
```

---

## 🛠️ Tech Stack

### Main App (`SnapClass`)
| Layer | Technology |
|---|---|
| **Frontend / UI** | [Streamlit](https://streamlit.io) |
| **Face Recognition** | `face_recognition` + `dlib` |
| **Voice Biometrics** | `Resemblyzer` + `Librosa` |
| **Database** | [Supabase](https://supabase.com) (PostgreSQL) |
| **Auth** | `bcrypt` |
| **QR Codes** | `segno` |
| **Data Processing** | `numpy`, `pandas`, `scikit-learn` |
| **Image Handling** | `Pillow` |

### Landing Page (`SnapClass-landing`)
| Layer | Technology |
|---|---|
| **Backend** | Flask |
| **Frontend** | HTML5, CSS3 |
| **Deployment** | Vercel |

---

## 🚀 Getting Started

### Prerequisites

- Python 3.10+
- A [Supabase](https://supabase.com) project with appropriate tables set up
- A C compiler (required for `dlib`)

### 1. Clone the repository

```bash
git clone https://github.com/MrudulShah24/SnapClass.git
cd SnapClass
```

### 2. Install dependencies

> **Note on `dlib`:** If you're on Windows, you may need to install the pre-built wheel:
> ```bash
> pip install dlib-20.0.99-cp313-cp313-win_amd64.whl
> ```
> For other platforms, `dlib-bin` in `requirements.txt` should handle it.

```bash
pip install -r requirements.txt
```

### 3. Configure environment variables

Create a `.env` file (or set Streamlit secrets) with your Supabase credentials:

```env
SUPABASE_URL=your_supabase_project_url
SUPABASE_KEY=your_supabase_anon_key
```

### 4. Run the app

```bash
streamlit run app.py
```

The app will open at `http://localhost:8501`.

---

## 🌐 Running the Landing Page

```bash
cd SnapClass-landing
pip install -r requirements.txt
python app.py
```

The landing page will be available at `http://localhost:5002`.

---

## 📱 How It Works

### For Teachers

1. **Log in** via the secure teacher portal
2. **Create a course** — a unique QR code and join code are generated automatically
3. **Take attendance** using one of two modes:
   - **Photo mode** — upload or capture a class photo; AI identifies all present students
   - **Voice mode** — call roll one-by-one; AI matches each student's voice
4. **Review records** — view attendance logs, confidence scores, and download CSV exports

### For Students

1. **Sign up / Log in** via the student portal
2. **Join a class** by scanning the teacher's QR code or visiting the join link (`?join-code=...`)
3. **Register biometrics** — face photo and voice sample are stored as embeddings
4. **View your attendance** history at any time

---

## 📦 Dependencies

```
streamlit          # Web app framework
numpy              # Numerical computing
pandas             # Data manipulation
scikit-learn       # ML utilities
dlib-bin           # Face detection models
face_recognition   # High-level face recognition (via ageitgey)
face_recognition_models  # Pre-trained models (installed from GitHub)
supabase           # Database client
bcrypt             # Password hashing
segno              # QR code generation
pillow             # Image processing
librosa            # Audio processing
resemblyzer        # Voice embeddings
setuptools<70.0.0  # Build compatibility
```

---

## 🔗 Related Repositories

| Repo | Description |
|---|---|
| [SnapClass](https://github.com/MrudulShah24/SnapClass) | Main Streamlit application |
| [SnapClass-landing](https://github.com/MrudulShah24/SnapClass-landing) | Marketing landing page (Flask) |

---

## 👨‍💻 Author

**Mrudul Shah**  
Apna College Project  
GitHub: [@MrudulShah24](https://github.com/MrudulShah24)




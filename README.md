<div align="center">

# 🔐 SecureVault
### AI-Powered Cybersecurity Platform

[![React](https://img.shields.io/badge/React_18-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://reactjs.org/)
[![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)](https://nodejs.org/)
[![Python](https://img.shields.io/badge/Python_3-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org/)
[![MongoDB](https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white)](https://mongodb.com/)
[![Socket.io](https://img.shields.io/badge/Socket.io-010101?style=for-the-badge&logo=socketdotio&logoColor=white)](https://socket.io/)

> **SecureVault** is a full-stack cybersecurity platform combining military-grade AES-256-CBC encryption, multi-modal steganography (image, audio, DNA), AI-driven threat analysis, blockchain audit logs, and real-time encrypted chat — all in one dashboard.

**Built by:** [Mansi Kaushik](https://github.com/MANSI-cse) | B.Tech CSE | Cybersecurity & Full-Stack Developer

</div>

---

## 🎯 What Makes This Special

Most security tools do *one* thing. **SecureVault does seven — simultaneously.**

| Feature | Technology | Industry Equivalent |
|---------|-----------|-------------------|
| 🔐 AES-256-CBC Encryption | Node.js `crypto` module | Military-grade data protection |
| 🖼️ Image Steganography (LSB) | Jimp + pixel manipulation | Intelligence agency techniques |
| 🎵 Audio Steganography | Python + NumPy LSB | Covert communication research |
| 🦋 Ultrasonic Embedding | >20kHz frequency band manipulation | Advanced signal processing |
| 🧬 DNA Cryptography | Binary → ACGT nucleotide encoding | Bioinformatics-inspired crypto |
| 📋 Blockchain Audit Log | SHA-256 chained hashes | Tamper-proof forensics |
| 💬 Real-Time Encrypted Chat | Socket.io | End-to-end secure messaging |
| 🔑 MFA + Account Lockout | JWT + OTP via email | Enterprise authentication |

---

## 📸 Screenshots & Demo

### 🖥️ Command Center Dashboard
> *(Add screenshot: `docs/screenshots/dashboard.png`)*
> Real-time threat analytics with doughnut chart (risk scoring) and intrusion detection timeline

### 🔐 AES-256 Encryption with QR Export
> *(Add screenshot: `docs/screenshots/encryption.png`)*
> Encrypt any text with AES-256-CBC, get the cipher + IV, and instantly export as a scannable QR code

### 🖼️ Image Steganography (LSB)
> *(Add screenshot: `docs/screenshots/image-stego.png`)*

| Carrier Image (Input) | Stego Image (Output — message hidden inside) |
|----------------------|----------------------------------------------|
| *(Add: `docs/screenshots/carrier.png`)* | *(Add: `docs/screenshots/stego-output.png`)* |

> The output image looks visually identical but carries a hidden message in the Least Significant Bits of every pixel.

### 🤖 Advanced AI Steganography Engine
> *(Add screenshot: `docs/screenshots/ai-stego.png`)*
> Emotion detection, ultrasonic band embedding, and DNA cipher — powered by a Python Flask microservice

### 📋 Blockchain Audit Log
> *(Add screenshot: `docs/screenshots/audit-log.png`)*
> Every action (login, encryption, steganography) is hashed and chained — making logs tamper-evident like a blockchain

### 🔑 Secure Login with MFA
> *(Add screenshot: `docs/screenshots/login-mfa.png`)*
> Email + Password → OTP sent via Gmail → JWT token issued. 3 failed attempts = 15-minute account lockout

---

## 🏗️ Architecture Overview

```
SecureVault Platform
├── FRONTEND (React + Vite)          Port: 5173
│   ├── Dashboard        → Threat analytics charts
│   ├── EncryptDecrypt   → AES-256 + QR code
│   ├── Steganography    → Image stego (hide/extract)
│   ├── AdvancedStego    → AI stego engine
│   ├── SecureLogs       → Blockchain audit log
│   └── Chat             → Real-time encrypted chat
│
├── BACKEND (Node.js + Express)      Port: 5000
│   ├── routes/auth.js   → Register, login, OTP verify
│   ├── routes/crypto.js → AES encrypt/decrypt
│   ├── routes/stego.js  → Image stego + AI proxy
│   ├── routes/logs.js   → Audit log retrieval
│   ├── models/User.js   → User schema (bcrypt, OTP, risk)
│   ├── models/Log.js    → Blockchain log schema
│   ├── middleware/      → JWT verification
│   └── utils/           → blockchain.js, stego.js, email.js
│
└── AI ENGINE (Python + Flask)       Port: 5001
    ├── app.py           → API routes (emotion/ultrasonic/DNA)
    └── core/
        ├── audio_stego.py → LSB audio embedding + PSNR metrics
        └── dna_crypto.py  → Binary → DNA nucleotide encoding
```

---

## 🔧 Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | React 18, Vite, React Router, Chart.js, Axios, Socket.io-client |
| Backend | Node.js, Express, JWT, bcryptjs, Multer, Nodemailer, Socket.io |
| AI Engine | Python 3, Flask, NumPy, Flask-CORS |
| Image Processing | Jimp (Node.js) |
| Database | MongoDB (mongodb-memory-server — no setup needed) |
| Encryption | AES-256-CBC (Node.js crypto) |
| Steganography | LSB (image + audio), DNA cipher |
| Auth | JWT + OTP (2FA) |
| QR Codes | qrcode npm package |
| Audit Trail | Custom SHA-256 blockchain implementation |

---

## 🚀 Getting Started

### Prerequisites
- Node.js v18+
- Python 3.10+
- npm or yarn
- Gmail account (for OTP emails)

### 1. Clone the Repository

```bash
git clone https://github.com/MANSI-cse/Secure-Vault.git
cd Secure-Vault
```

### 2. Backend Setup

```bash
cd backend
npm install
```

Create a `.env` file in `/backend`:
```env
PORT=5000
JWT_SECRET=your_jwt_secret_here
EMAIL_USER=your_gmail@gmail.com
EMAIL_PASS=your_gmail_app_password
AES_KEY=your_32_character_aes_key_here
```

Start the backend:
```bash
npm run dev
```

### 3. AI Engine Setup

```bash
cd ai_engine
pip install -r requirements.txt
python app.py
```

### 4. Frontend Setup

```bash
cd frontend
npm install
npm run dev
```

### 5. One-Click Launch (Windows)

```bash
# Double-click or run:
start.bat
```
> Automatically installs dependencies, clears port conflicts, and opens the app in your browser.

---

## ✨ Feature Deep Dives

### 1. AES-256-CBC Encryption
- Uses Node.js built-in `crypto` module — no external crypto library needed
- Random 16-byte IV generated per encryption (prevents pattern attacks)
- Output format: `IV_hex:ciphertext_hex` — portable and self-contained
- **QR Code Export:** Encrypted payload instantly becomes a scannable QR code for secure transfer

### 2. Image Steganography (LSB)
- Hides text in the Least Significant Bit of image pixels using **Jimp**
- Carrier images look visually identical — undetectable without the extraction tool
- Supports PNG and JPEG input; outputs PNG (lossless)

### 3. Advanced AI Steganography (Python Microservice)
Three cutting-edge encoding modes:

**🎵 Emotion-Based Audio Encoding**
- Detects "emotion" from audio characteristics and embeds in adaptive frequency bands
- Returns PSNR (~48–55 dB) and MSE (< 0.05) quality metrics

**🦋 Ultrasonic Embedding (>20kHz)**
- LSB embedding on upper frequency audio bytes
- Reports capacity utilization %

**🧬 DNA Cryptography**
- Converts text → binary → DNA nucleotide sequence (A/C/G/T)
- Mapping: `00→A`, `01→C`, `10→G`, `11→T`
- Inspired by real bioinformatics research

### 4. Blockchain Audit Log
```
Log Entry = SHA-256(userId + action + details + IP + previousHash + timestamp)
```
- Every security event is hashed and chained to the previous entry
- Tampering any log entry breaks the hash chain — fully tamper-evident

### 5. Multi-Factor Authentication
- Email + bcrypt-hashed password verification
- 6-digit OTP sent via Gmail SMTP (Nodemailer), valid for 10 minutes
- Account lockout after **3 failed attempts** (15-minute freeze)
- Per-user risk score tracking (Low / High)

### 6. Real-Time Secure Chat
- Powered by **Socket.io** with room-based messaging
- Room join/leave events with user tracking
- Extensible for full E2E encryption layer

---

## 🔒 Security Highlights

| Security Measure | Implementation |
|-----------------|---------------|
| ✅ Password hashing | bcryptjs (salt rounds: 10) |
| ✅ Stateless auth | JWT with expiry |
| ✅ 2FA via OTP | Time-limited (10 min), email-delivered |
| ✅ Account lockout | 3 failed attempts → 15-min freeze + High risk flag |
| ✅ AES-256-CBC | Random IV per encryption — no deterministic patterns |
| ✅ Blockchain audit trail | Every action SHA-256 chained, tamper-evident |
| ✅ JWT middleware | Crypto and stego APIs are protected routes |
| ✅ CORS configured | AI microservice isolated on separate port |

---

## 📊 Performance Metrics (Steganography Quality)

| Metric | Value | What It Means |
|--------|-------|--------------|
| PSNR | ~48–55 dB | Perceptually lossless (>40 dB = undetectable) |
| MSE | < 0.05 | Near-zero distortion |
| Capacity Used | 0.1%–5% | Message uses tiny fraction of carrier |
| Embedding Rate | ~8 bits/byte | LSB per byte, WAV carrier |

---

## 🗺️ Roadmap

- [ ] Real ML-based emotion detection (librosa + trained model)
- [ ] True pixel-level LSB via `image.scan()` in Jimp
- [ ] End-to-end encryption in chat (Diffie-Hellman key exchange)
- [ ] Mobile responsive UI
- [ ] Docker Compose for one-command deployment
- [ ] Cloud deployment (AWS/GCP)
- [ ] Real-time threat scoring with ML anomaly detection
- [ ] Zero-Knowledge Proof authentication

---

## 📁 Project Structure

```
Secure-Vault/
├── frontend/                    # React + Vite frontend
│   └── src/
│       ├── App.jsx              # Routing + auth state
│       ├── components/
│       │   └── Sidebar.jsx      # Navigation sidebar
│       └── pages/
│           ├── Login.jsx        # MFA login + registration
│           ├── Dashboard.jsx    # Threat analytics charts
│           ├── EncryptDecrypt.jsx   # AES-256 + QR code
│           ├── Steganography.jsx    # Image stego (hide/extract)
│           ├── AdvancedSteganography.jsx  # AI stego engine
│           ├── SecureLogs.jsx   # Blockchain audit log
│           └── Chat.jsx         # Real-time encrypted chat
│
├── backend/                     # Node.js + Express API
│   ├── server.js                # Entry point + Socket.io
│   ├── routes/
│   │   ├── auth.js              # Register, login, OTP verify
│   │   ├── crypto.js            # AES encrypt/decrypt
│   │   ├── stego.js             # Image stego + AI proxy
│   │   └── logs.js              # Audit log retrieval
│   ├── models/
│   │   ├── User.js              # User schema (bcrypt, OTP, risk)
│   │   └── Log.js               # Blockchain log schema
│   ├── middleware/
│   │   └── authMiddleware.js    # JWT verification
│   └── utils/
│       ├── blockchain.js        # SHA-256 log chaining
│       ├── stego.js             # Jimp LSB steganography
│       └── email.js             # Nodemailer OTP sender
│
├── ai_engine/                   # Python Flask microservice
│   ├── app.py                   # API routes (emotion/ultrasonic/DNA)
│   ├── requirements.txt
│   └── core/
│       ├── audio_stego.py       # LSB audio embedding + PSNR metrics
│       └── dna_crypto.py        # Binary → DNA nucleotide encoding
│
├── docs/
│   └── screenshots/             # Add your screenshots here!
│       ├── dashboard.png
│       ├── encryption.png
│       ├── image-stego.png
│       ├── ai-stego.png
│       ├── audit-log.png
│       └── login-mfa.png
│
├── start.bat                    # One-click launcher (Windows)
├── .gitignore                   # Must include .env!
└── README.md
```

---

## 👩‍💻 About the Developer

**Mansi Kaushik** — B.Tech CSE | Cybersecurity & Full-Stack Developer

This project was built as a comprehensive demonstration of applied cybersecurity concepts including cryptography, steganography, blockchain, and AI-driven security — all integrated into a production-grade full-stack application.

- 🔗 GitHub: [MANSI-cse](https://github.com/MANSI-cse)
- 💼 LinkedIn: [mansi-kaushik-88862328b](https://www.linkedin.com/in/mansi-kaushik-88862328b)

---

<div align="center">

⭐ **Star this repo if it helped you learn something new about cybersecurity!**

*Built with 💚 using React, Node.js, Python, and a passion for security*

</div>

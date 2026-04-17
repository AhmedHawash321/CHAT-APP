# Chatty — Real-Time Chat Application

A full-stack real-time chat application built with the MERN stack, featuring instant messaging, online presence tracking, media uploads, and a fully customizable UI.

<img width="1894" height="1384" alt="Screenshot 2026-04-17 234844" src="https://github.com/user-attachments/assets/f985d438-3433-442e-a0a6-6a61784ea3bc" />


<img width="1452" height="1363" alt="Screenshot 2026-04-17 235341" src="https://github.com/user-attachments/assets/2144534b-e2c5-4368-9676-617e4de5ace6" />


---

## ✨ Features

- 💬 **Real-Time Messaging** — instant bidirectional communication powered by Socket.io WebSockets
- 🔐 **Secure Authentication** — JWT tokens stored in HttpOnly cookies with bcrypt password hashing
- 🟢 **Online Presence** — live tracking of online/offline users across all active sessions
- 🖼️ **Media Support** — profile pictures and image messages via Cloudinary CDN
- 🎨 **Customizable Themes** — multiple built-in UI themes for a personalized experience
- 📱 **Responsive Design** — fully responsive layout built with Tailwind CSS and DaisyUI

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React.js (Vite) · Zustand · Tailwind CSS · DaisyUI |
| Real-Time | Socket.io (client + server) |
| Backend | Node.js · Express.js |
| Database | MongoDB Atlas · Mongoose |
| Auth | JWT · HttpOnly Cookies · Bcryptjs |
| Media | Cloudinary API |

---

## 🗂️ Project Structure

```
chatty/
├── backend/
│   ├── controllers/        # Route business logic
│   ├── lib/                # DB connection & Socket.io setup
│   ├── middleware/         # JWT auth guards
│   ├── models/             # Mongoose schemas (User, Message)
│   └── routes/             # API endpoint definitions
├── frontend/
│   └── src/
│       ├── components/     # Reusable UI components
│       ├── pages/          # Application views (Login, Signup, Home)
│       ├── store/          # Zustand stores (auth, chat, theme)
│       └── lib/            # Axios instance & utility functions
├── .env                    # Environment variables
└── package.json
```

---

## 🚀 Getting Started

### Prerequisites

- Node.js 18+
- MongoDB Atlas account
- Cloudinary account

### 1. Clone the repository

```bash
git clone https://github.com/AhmedHawash321/CHAT-APP.git
cd CHAT-APP
```

### 2. Configure environment variables

Create a `.env` file in the root directory:

```env
PORT=5001
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
NODE_ENV=development

CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret
```

### 3. Install dependencies

```bash
# Backend dependencies
npm install

# Frontend dependencies
cd frontend && npm install
```

### 4. Run the application

```bash
# Development mode (from root)
npm run dev
```

The backend runs on `http://localhost:5001` and the frontend on `http://localhost:5173`.

---

## 🔒 Security

- **Password Hashing** — bcryptjs hashes all passwords before storage, never stored in plain text
- **JWT + HttpOnly Cookies** — tokens stored in HttpOnly cookies, inaccessible to JavaScript and protected against XSS
- **Protected Routes** — all backend routes are guarded by JWT middleware; unauthenticated requests are rejected
- **CORS Policy** — restricted to trusted origins only

---

## 🔄 Real-Time Architecture

```
Client A                    Server                    Client B
   │                           │                          │
   │── send message ──────────>│                          │
   │                           │── emit to room ─────────>│
   │                           │                          │
   │<─────────────── online users broadcast ─────────────>│
```

Socket.io maintains a persistent WebSocket connection. When a user connects, their socket ID is mapped to their user ID server-side, enabling targeted event delivery and accurate online presence tracking.

---

## 👨‍💻 Author

**Ahmed Hawash**
Backend Engineer · Node.js & Rust · Blockchain Developer

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Ahmed_Hawash-blue?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/ahmed-hawash-21b992149/)
[![GitHub](https://img.shields.io/badge/GitHub-AhmedHawash321-black?style=for-the-badge&logo=github)](https://github.com/AhmedHawash321)

---

## 📄 License

Distributed under the MIT License. See `LICENSE` for details.

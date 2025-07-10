
# 🎬 MyTube – Full-Stack Video Sharing Platform

A fully functional YouTube-like platform built using **Node.js**, **Express**, **MySQL**, and **Passport.js** that supports **manual and Google login**, **video uploads**, **auto-generated thumbnails**, **likes**, and **comments** with role-based access.

---

## 🚀 Features

### 🔐 Authentication
- **Manual login/registration** with bcrypt password hashing.
- **Google login** (OAuth 2.0) via Passport.js.
- **Session-based login** with `express-session`.
- **Role-based access** – Admins can upload, users can view & interact.

### 📤 Video Upload (Admin Only)
- Upload videos with title and description.
- Videos stored using Multer in `/uploads`.
- Thumbnail auto-generated using **FFmpeg** from the 2nd second of the video.

### 🎞️ Video Feed
- Display videos in a responsive grid with thumbnails.
- Toggle play/pause on click.
- View uploader info and upload date.

### 👍 Interactions
- Like/unlike videos (toggle feature).
- Comment on videos with real-time display.
- Display like count and comment list per video.

---

## 🛠️ Tech Stack

| Layer       | Technology                          |
|-------------|-------------------------------------|
| Frontend    | HTML, CSS, Vanilla JavaScript       |
| Backend     | Node.js, Express.js                 |
| Auth        | Passport.js (Local & Google OAuth2) |
| Database    | MySQL                               |
| File Upload | Multer                              |
| Thumbnails  | FFmpeg                              |
| Session     | express-session                     |

---

## 📁 Folder Structure

```

├── server.js
├── .env
├── /uploads
│   ├── video.mp4
│   └── thumb-\*.jpg
├── /public
│   ├── index.html
│   └── style.css

````

---

## 📄 Database Schema (MySQL)

```sql
CREATE TABLE users (
  id INT AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(100),
  email VARCHAR(100),
  password VARCHAR(255),
  photo_url TEXT,
  google_id VARCHAR(255),
  is_admin BOOLEAN DEFAULT 0
);

CREATE TABLE videos (
  id INT AUTO_INCREMENT PRIMARY KEY,
  user_id INT,
  title VARCHAR(255),
  description TEXT,
  file_path TEXT,
  thumbnail_path TEXT,
  upload_time TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE likes (
  id INT AUTO_INCREMENT PRIMARY KEY,
  video_id INT,
  user_id INT,
  UNIQUE KEY (video_id, user_id)
);

CREATE TABLE comments (
  id INT AUTO_INCREMENT PRIMARY KEY,
  video_id INT,
  user_id INT,
  content TEXT,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
````

---

## 🧪 Run Locally

### 1. Clone the repo:

```bash
git clone https://github.com/yourusername/mytube.git
cd mytube
```

### 2. Install dependencies:

```bash
npm install
```

### 3. Create `.env` file:

```env
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=your_password
DB_NAME=video_upload_db
SESSION_SECRET=your_secret
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret
```

### 4. Start server:

```bash
node server.js
```

---



## 📚 License

This project is open-source and available under the [MIT License](LICENSE).

---

## 🤝 Credits

Developed with ❤️ by Ajit Gaud



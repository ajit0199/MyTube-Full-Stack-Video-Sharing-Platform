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


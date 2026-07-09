# AI Surveillance System

An AI-powered Surveillance System that provides real-time camera streaming, person detection using YOLOv8, user authentication, and camera management through a web dashboard.

---

## Features

- User Registration & Login (JWT Authentication)
- Camera Management
  - Add Camera
  - Start Camera
  - Stop Camera
- Live Video Streaming using RTSP
- MediaMTX RTSP Server
- WebRTC Video Streaming
- YOLOv8 Person Detection
- Bounding Box Detection
- PostgreSQL Database
- Responsive React Dashboard

---

## Tech Stack

### Frontend
- React
- TypeScript
- Vite

### Backend
- Node.js
- Express.js
- PostgreSQL
- JWT Authentication

### AI Worker
- Python
- OpenCV
- Ultralytics YOLOv8
- aiortc
- aiohttp

### Streaming
- FFmpeg
- MediaMTX
- RTSP
- WebRTC

---

## Project Structure

```
Project_assignment/

│
├── backend/
│   ├── routes/
│   ├── controllers/
│   ├── middleware/
│   ├── database/
│   └── server.js
│
├── frontend/
│   ├── src/
│   │
│   ├── components/
│   │     CameraCard.tsx
│   │     CameraForm.tsx
│   │     VideoPlayer.tsx
│   │     AlertPanel.tsx
│   │
│   └── pages/
│         Dashboard.tsx
│         Login.tsx
│
├── worker/
│   ├── app.py
│   ├── rtc.py
│   ├── detector.py
│   └── models/
│
├── ffmpeg/
├── mediamtx/
└── README.md
```

---

## System Architecture

```
               React Frontend
                     │
                     │ REST API
                     ▼
              Node.js Backend
                     │
        PostgreSQL Database
                     │
                     ▼
              Camera Management

                     │
                     ▼
          FFmpeg → MediaMTX RTSP
                     │
                     ▼
             Python AI Worker
                     │
        YOLOv8 Person Detection
                     │
                     ▼
              WebRTC Stream
                     │
                     ▼
             React Video Player
```

---

## Database

PostgreSQL

Tables

- users
- cameras
- alerts

---

## Installation

### 1. Clone Repository

```bash
git clone https://github.com/Prerana-Mahindrakar/Project_assignment.git
```

---

### 2. Backend

```bash
cd backend

npm install

npm start
```

Runs on

```
http://localhost:3000
```

---

### 3. Frontend

```bash
cd frontend

npm install

npm run dev
```

Runs on

```
http://localhost:5173
```

---

### 4. Worker

```bash
cd worker

pip install -r requirements.txt

python app.py
```

Runs on

```
http://localhost:8080
```

---

### 5. Start MediaMTX

```bash
mediamtx.exe
```

RTSP Server

```
rtsp://localhost:8554/live
```

---

### 6. Start FFmpeg

```bash
ffmpeg -f dshow -i video="HP HD Camera" \
-vcodec libx264 \
-preset ultrafast \
-tune zerolatency \
-f rtsp rtsp://localhost:8554/live
```

---

## Workflow

1. Register User
2. Login
3. Add Camera
4. Start Camera
5. FFmpeg publishes webcam to RTSP
6. MediaMTX receives RTSP stream
7. Python Worker reads RTSP stream
8. YOLOv8 detects persons
9. Bounding boxes are drawn
10. Stream is sent to Frontend using WebRTC
11. Live video is displayed on Dashboard

---

## API Endpoints

### Authentication

```
POST /api/register

POST /api/login
```

### Camera

```
GET /api/camera

POST /api/camera

POST /api/camera/:id/start

POST /api/camera/:id/stop
```

### Alerts

```
GET /api/alerts

POST /api/alerts
```

---

## Deployment Steps

1. Install PostgreSQL
2. Create Database
3. Configure .env
4. Install Node Modules
5. Install Python Packages
6. Download YOLOv8 Model
7. Start MediaMTX
8. Start FFmpeg
9. Start Backend
10. Start Worker
11. Start Frontend

---

## Output

✔ User Login

✔ Camera Registration

✔ Camera Management

✔ Live RTSP Streaming

✔ WebRTC Video Streaming

✔ YOLOv8 Person Detection

✔ Live Dashboard

---

## Future Improvements

- Email Alerts
- SMS Notifications
- Face Recognition
- Multi-Camera Support
- Object Tracking
- Cloud Deployment
- Recording Playback

---

## Author

Prerana Mahindrakar

GitHub

https://github.com/Prerana-Mahindrakar

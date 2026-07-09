# go2rtc-minimal-setup

A minimal setup for **go2rtc** as a lightweight video streaming layer.

> Your camera isn’t the problem. Your architecture is.

---

## 🧠 Overview

This project demonstrates how to use **go2rtc** as a middle layer between IP cameras and multiple consumers.

Instead of connecting every client directly to the camera, go2rtc acts as a **stream adapter and distributor**:

```
Camera (RTSP)
      ↓
    go2rtc
      ↓
Browser (WebRTC) / AI (RTSP) / Mobile (HLS)
```

---

## 🚀 Features

* Single connection to camera
* Multi-protocol output (RTSP, WebRTC, HLS)
* Low latency streaming (WebRTC)
* Minimal resource usage (no forced transcoding)
* Simple and reproducible setup using Docker

---

## 📁 Project Structure

```
project/
 ├── docker-compose.yml
 └── setting/
     └── go2rtc.yaml
```

---

## ⚙️ Getting Started

### 1. Clone Repository

```bash
git clone https://github.com/your-username/go2rtc-minimal-setup.git
cd go2rtc-minimal-setup
```

---

### 2. Configure Stream

Edit `setting/go2rtc.yaml`:

```yaml
streams:
  cam1: rtsp://username:password@192.168.1.10:554/stream1
```

---

### 3. Run Service

```bash
docker compose up -d
```

---

### 4. Access

* Web UI

  ```
  http://localhost:1984
  ```

* Direct stream

  ```
  http://localhost:1984/stream.html?src=cam1
  ```

---

## 🧩 How It Works

go2rtc acts as a **video gateway**:

* Ingests RTSP from camera
* Exposes multiple protocols
* Handles distribution to multiple clients

This reduces:

* direct connections to camera
* system complexity
* protocol incompatibility issues

---

## ⚠️ Notes

* Minimal configuration is enough to validate the architecture
* Advanced features (WebRTC tuning, ICE servers, transcoding) can be added later
* Recommended to run on Linux for best network compatibility

---

## 🔮 Next Steps

* Add WebRTC optimization (STUN/TURN)
* Integrate with AI pipeline (OpenCV, ML models)
* Connect to monitoring/dashboard system
* Expand to multi-camera setup

---

---
## 🔗 Reference

Article:  
[medium](https://andriantriputra.medium.com/camera-your-camera-isnt-the-problem-your-architecture-is-f5d9f6fe5d92)

---
## Author

Andrian Tri Putra
- [Medium](https://andriantriputra.medium.com/)
- [andriantp](https://github.com/andriantp)
- [AndrianTriPutra](https://github.com/AndrianTriPutra)

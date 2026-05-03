# KafkaPulse — Real-Time Feedback Processing System

KafkaPulse is a Kafka-powered microservice-based application that collects, categorizes, and processes user feedback in real time. It features a beautiful frontend interface and a robust backend architecture suitable for demonstrating Kafka and microservice expertise.

---

## 🎥 Live Demo

[![Watch the demo](https://cdn.loom.com/sessions/thumbnails/29f471a2f5cc49c3b7ba3500a7450c5f-cd0176f6e0fd7ee4-full-play.gif)]

## 👋 Overview

**Frontend:** React.js + Tailwind CSS

**Backend:** Node.js microservices

**Core Tech:** Apache Kafka, Docker Compose, WebSockets, Express.js

**Use Case:** Real-time routing of feedback into separate services based on category (Complaint, Suggestion, Praise), with a live dashboard for admins.

---

## 🌍 Live Roles

### 👤 User Interface

* Submit feedback form with name, email, category, and message.
* Realtime toast confirmation.

### 💼 Admin Dashboard

* Live table of incoming feedback.
* Category filtering.
* Analytics via Pie/Bar charts.
* Real-time log viewer (via WebSocket).
* Toggle between views or view both side-by-side on wide screens.

---

## 📊 Architecture Diagram

```text
[ User Frontend ]
        |
        v
[ Feedback API ] ---> Kafka Topic: feedback-submitted
        |
        v
[ Router Service ]
    |     |      |
    v     v      v
Support  Product  Marketing Services
    \     |     /
      --> Logger Service --> WebSocket --> Admin Dashboard
```

---

## 🚀 Technologies

| Component        | Stack                                   |
| ---------------- | --------------------------------------- |
| Frontend         | React.js, Tailwind CSS, Axios, Chart.js |
| Backend Services | Node.js (Express), KafkaJS              |
| Broker System    | Kafka, Zookeeper                        |
| Real-Time Logs   | WebSocket (Socket.IO)                   |
| DevOps           | Docker, Docker Compose                  |

---

## 🔧 Setup Instructions

### 1. Clone Repository

```bash
git clone https://github.com/yourusername/pulseq.git
cd pulseq
```

### 2. Start Docker Services

```bash
docker-compose build
docker-compose up -d
```

### 3. Access Local Services

| Service      | URL                                            |
| ------------ | ---------------------------------------------- |
| Frontend     | [http://localhost:3000](http://localhost:3000) |
| Feedback API | [http://localhost:5000](http://localhost:5000) |
| Logger WS    | ws\://localhost:5050                           |

### 4. Stopping

```bash
docker-compose down
```

---

## 🛀 Folder Structure

```
pulseq/
├── docker-compose.yml
├── frontend/           # React frontend
├── feedback-api/       # Kafka producer service
├── router-service/     # Kafka consumer + router
├── support-service/    # Complaint handler
├── product-service/    # Suggestion handler
├── marketing-service/  # Praise handler
├── logger-service/     # WebSocket log streamer
```

---

## 📄 API Reference

### POST /api/feedback

**Submit feedback**

```json
{
  "name": "Prawal",
  "email": "prawal@example.com",
  "category": "Complaint",
  "message": "App crashes on submit."
}
```

---



## 📢 Contributions

Feel free to fork, contribute, or suggest features via Issues or PRs!

---

## 🚗 License

[MIT License](LICENSE)

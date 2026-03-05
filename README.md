# 🚀 Todo Full-Stack Application

[![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://reactjs.org/)
[![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)](https://nodejs.org/)
[![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com/)
[![MongoDB](https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white)](https://www.mongodb.com/)

A modern full-stack application for task management. This project was created as a personal pet project to experiment with microservices architecture, strict typing, and containerization.

---

## ⚡ Quick Start (Docker)

The fastest way to get the entire stack up and running:

```bash
# Copy environment variables template
cp .env.example .env

# Build and start containers
docker compose up --build
```

**The application will be available at:**
* **Frontend:** [http://localhost:3000](http://localhost:3000)
* **Backend API:** [http://localhost:8080](http://localhost:8080)

---

## 🛠 Tech Stack

| Layer | Technologies |
| :--- | :--- |
| **Frontend** | React, TypeScript, Vite |
| **Backend** | Node.js, Express, TypeScript |
| **Database** | MongoDB |
| **DevOps** | Docker, Docker Compose |
| **Testing** | Vitest, Supertest |

---

## 🎯 Project Goals

* **Real-world Practice:** Mastering the interaction between a React client and a Node.js server.
* **Type Safety:** Leveraging TypeScript extensively across both frontend and backend.
* **Architecture:** Experimenting with clean architecture and monorepo patterns.
* **Learning Playground:** A long-term project for testing new tools, refactoring, and continuous improvement.

---

## 📂 Project Structure

This project is organized as a monorepo with separate services:

```text
├── server/             # Backend: Express API
│   ├── src/            # Source code
│   ├── tests/          # Integration tests
│   └── Dockerfile      # Backend container configuration
├── client/             # Frontend: React Application
│   ├── src/            # UI components and logic
│   └── Dockerfile      # Frontend container configuration
├── shared/             # Shared types (DTOs) used by both apps
├── docker-compose.yml  # Main Docker setup
└── .env.example        # Environment variables template
```

---

## ⚙️ Local Development (Manual Setup)

### Prerequisites
* **Node.js 18+**
* **MongoDB** (Local instance or Atlas)

### Environment Configuration
Create a `.env` file in the root directory based on `.env.example`:

| Variable | Description | Default Value |
| :--- | :--- | :--- |
| `PORT` | Backend server port | `8080` |
| `MONGO_URI` | MongoDB connection string | `mongodb://localhost:27017/todoapp` |
| `VITE_API_URL` | Backend API URL for the frontend | `http://localhost:8080` |

### Installation & Execution
1. **Install dependencies for all packages:**
   ```bash
   npm run install:all
   ```
2. **Run in development mode:**
   ```bash
   npm run dev:all
   ```
   *This will concurrently start MongoDB (via Docker if configured), the Backend API, and the Frontend dev server with Hot Module Replacement (HMR).*

---

## 🧪 Testing

To run the backend integration tests:
```bash
cd server
npm test
```

---

## 📈 Project Roadmap

This project is actively evolving. Future updates will include:
* [ ] Frontend unit and component testing.
* [ ] CI/CD pipeline setup (GitHub Actions).
* [ ] User Authentication (JWT/Auth0).
* [ ] Deployment to a cloud provider.

---

## 📄 License

Created for educational purposes. Feel free to use it for your own learning!
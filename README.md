# Todo Full-Stack Application

A modern full-stack **todo application** with a Node.js TypeScript backend and a React TypeScript frontend.

This repository is a **personal pet project** created for learning and experimenting with modern full-stack technologies.

---

## Quick Start (Docker)

The fastest way to run the project:

```bash
cp .env.example .env
docker compose up --build

### Application will be available at:

Frontend
http://localhost:3000

Backend API
http://localhost:8080

## 🎯 Project Goals

The main goals of this project are to:
Practice real-world full-stack development
Improve TypeScript usage on both frontend and backend
Experiment with architecture, tooling, and best practices
Gradually refactor and enhance the codebase as new concepts are learned
Use the project as a long-term learning playground rather than a production-ready app

## Project Structure

This project is organized as a monorepo with separate frontend and backend applications:

server/                 # Backend application
├── src/               # Source code
├── tests/             # Integration tests
├── package.json       # Backend dependencies
├── Dockerfile         # Backend container
└── ...

client/                # Frontend application
├── src/               # React TypeScript source code
├── package.json       # Frontend dependencies
└── ...

shared/                # Shared types used by frontend and backend

docker-compose.yml     # Production Docker setup
docker-compose.dev.yml # Development Docker setup

.env.example           # Environment variables template
README.md              # This file

## Prerequisites

You need the following tools installed:
Node.js 18+
npm
Docker + Docker Compose

Optional for local development:
MongoDB (if not using Docker)
Environment Variables

The project uses environment variables for configuration.

Create a .env file in the root of the project.
You can copy the template:

cp .env.example .env

Example configuration:

# Backend
PORT=8080

# MongoDB
MONGO_URI=mongodb://db:27017/todoapp

# Frontend
VITE_API_URL=http://localhost:8080

### Explanation:

Variable	Description
PORT	Backend server port
MONGO_URI	MongoDB connection string
VITE_API_URL	Backend API URL used by frontend
Installation

Clone the repository:

git clone <repository-url>
cd todo-full-stack

Install dependencies for both server and client:

npm run install:all

Or manually:

# Install backend dependencies
cd server
npm install

# Install frontend dependencies
cd ../client
npm install
Build

Build both frontend and backend:

npm run build:all

Or build individually:

npm run build:server
npm run build:client
Development
Run Full Stack

Start backend + frontend + MongoDB:

npm run dev:all

This will:

Start MongoDB container

Start backend API at

http://localhost:8080

Start frontend dev server at

http://localhost:3000

with hot reloading enabled.

Run Services Separately

Backend:

npm run dev:backend

Frontend:

npm run dev:client

## Docker

The project includes a complete Docker setup.

Services:

Backend
Frontend
MongoDB

### Run with Docker

Build and start containers:

docker compose up --build

Application URLs:

Frontend
http://localhost:3000

Backend API
http://localhost:8080

MongoDB runs inside the Docker network.

Stop Containers

Stop services:

docker compose down

Remove containers, volumes and images:

docker compose down --rmi all --volumes --remove-orphans
Development Docker Mode

For development you can use:

docker-compose.dev.yml

Run:

docker compose -f docker-compose.dev.yml up --build

This mode is useful for debugging and development.

Running Tests

Backend tests:

cd server
npm test
Technologies Used
Backend

Node.js
TypeScript
Express
MongoDB
Frontend
React
TypeScript
Vite
Infrastructure
Docker
Docker Compose
Testing
Vitest
Supertest

## Project Status

This project is actively evolving as part of my learning journey.
Future improvements may include:
improved test coverage
CI/CD
deployment
improved architecture

## License

This project is created for educational purposes.
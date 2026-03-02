# PokAImon Generator 🧪🎨

Full-stack app that generates AI-powered creatures from your doodles.

------------------------------------------------------------------------

## Stack

### Frontend

-   React 19 (Vite)
-   React Router
-   Tailwind CSS

### Backend

-   Node.js + Express
-   PostgreSQL 16
-   Memcached
-   Gemini API (optional)

------------------------------------------------------------------------

# 🚀 Quick Start

## Prerequisites

-   Node.js 18+
-   Docker (running)

------------------------------------------------------------------------

## 1️⃣ Start Database & Cache

From the project root:

``` bash
docker compose up -d
```

This starts:

-   PostgreSQL (port 5433)
-   Memcached (port 11211)

Verify:

``` bash
docker compose ps
```

------------------------------------------------------------------------

## 2️⃣ Backend Setup

Create `server/.env`:

``` env
PORT=3001
DATABASE_URL=postgresql://postgres:postgres@localhost:5433/pokegen
CORS_ORIGIN=http://localhost:5173
GEMINI_API_KEY=your_api_key_here
```

Install and run:

``` bash
cd server
npm install
npm run dev
```

Backend runs at:

    http://localhost:3001

Health check:

    GET http://localhost:3001/api/health

------------------------------------------------------------------------

## 3️⃣ Frontend Setup

Create `client-tutorial/.env`:

``` env
VITE_BACKEND_URL=http://localhost:3001
```

Install and run:

``` bash
cd client-tutorial
npm install
npm run dev
```

Frontend runs at:

    http://localhost:5173

------------------------------------------------------------------------

# 📡 API Endpoints

Base URL: `http://localhost:3001`

  Method   Endpoint                         Description
  -------- -------------------------------- -----------------------
  GET      /api/health                      Health check
  GET      /api/gallery                     Get all PokAImon
  POST     /api/generate                    Generate new PokAImon
  PATCH    /api/pokaimon/:id/like           Like a PokAImon
  POST     /api/pokaimon/:id/action-image   Generate action image

------------------------------------------------------------------------

## Reset Database (if needed)

``` bash
docker compose down -v
docker compose up -d
```

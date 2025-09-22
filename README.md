# dataflow-demo

Simple demo app for a photo studio.  
It pulls client requests, saves them in a database, shows them in a small web dashboard, and can auto-confirm a request with a browser bot.

## What it does
- Import demo clients from a public API (as “new requests”)
- Store them in **Postgres**
- Show them in an **Angular** dashboard
- Auto-submit a confirmation form with **Playwright** and mark the client as *confirmed*

## Why this project
- Covers **data pipeline** (import → store → view)
- Fullstack: **Web API + Database + Frontend**
- Includes small automation task (browser bot)

## Tech stack
- **Backend:** NestJS (TypeScript), TypeORM  
- **Database:** Postgres  
- **Frontend:** Angular  
- **Automation:** Playwright  
- **DevOps:** Docker & docker-compose  

## Quick start

### Prerequisites
- Node.js 20+
- Docker Desktop
- Git

### Run project locally

**1) Start Postgres with Docker**
```bash
docker run --name dataflow_db -e POSTGRES_USER=postgres \
  -e POSTGRES_PASSWORD=postgres -e POSTGRES_DB=dataflow \
  -p 5432:5432 -d postgres:15
```

**2) Start backend**
```bash
cd backend
cp .env.example .env
npm install
npm run start:dev
```
- API: `http://localhost:3000/health`


**3) Start frontend**
```bash
cd ../frontend
npm install
npm start
```
- Frontend: `http://localhost:4200`



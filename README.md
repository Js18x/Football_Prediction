# Football Coop API ⚽️

**A high-performance asynchronous REST API for tracking football fixtures and managing user predictions.**

This backend serves as the core engine for the "Football Coop" platform. It connects to external football data providers to sync live scores, manages a PostgreSQL database, and serves data to the frontend via fast, async endpoints.

> **Note:** This repository is the home for a project that is in development and codebase is to follow in the following weeks.

## 🚀 Key Features

* **Live Data Synchronization:** Implemented a custom "Upsert" engine that pulls data from external APIs (Football-Data.org) and updates local records instantly without duplicates.
* **Complex Data Modeling:** Relational database schema handling Teams, Competitions, Matches, and Scores (including Extra Time & Penalties).
* **Asynchronous Architecture:** Built on top of **FastAPI** and **SQLAlchemy 2.0 (Async)** for non-blocking database operations.
* **Robust Error Handling:** Strict Pydantic validation ensures data integrity across the system.

## 🛠 Tech Stack

* **Language:** Python 3.10+
* **Framework:** FastAPI
* **Database:** PostgreSQL
* **ORM:** SQLAlchemy (Async) / asyncpg
* **Tools:** Uvicorn, Pydantic, HTTPX

## ⚙️ How to Run Locally

Since this is an API, you can run it locally to explore the endpoints via Swagger UI.

### 1. Clone the Repo
```bash
git clone [https://github.com/Js18x/football-prediction-api.git](https://github.com/Js18x/football-prediction-api.git)
cd football-prediction-api
```
### 2. Create the Virtual Environment
```bash
python3 -m venv projEnv
source projEnv/bin/activate
On Windows use: projEnv\Scripts\activate
```
### 3. Install Dependencies
```bash
pip install -r requirements.txt
```
### 4. Configure Environment
```bash
DATABASE_URL=postgresql+asyncpg://user:password@localhost/football_db
SECRET_KEY=your_secret_key_here
FOOTBALL_API_KEY=your_football_data_org_key
```
### 5. Run the Server
```bash
uvicorn app.main:app --reload
```

## 📚 Documentation
Once running, navigate to ```http://127.0.0.1:8000/docs``` to see the interactive API documentation.

Key Endpoints:

```GET /matches/today``` - View today's fixtures.

```POST /matches/sync``` - Force an update of scores from the external provider.

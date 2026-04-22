# World Building Assistant

An AI-powered tool that helps creative professionals and hobbyists create and maintain fictional worlds. 
The tool acts as an intelligent assistant that organizes worldbuilding, detects contradictions, and helps creators keep their world consistent — without taking over the creative process.

## Features

- **User accounts** — Register, log in, and manage your profile with secure session-based authentication
- **Worlds** — Create and manage multiple fictional worlds
- **Characters** — Build detailed characters with species, items, life dates, and images
- **Relationships** — Define and track relationships between characters
- **Events** — Create events and link characters to them to build timelines
- **Maps & Locations** — Add maps to your worlds and pin locations to them
- **Items & Species** — Catalog items and species and connect them to your worlds
- **Notes** — Keep private notes tied to your account for planning and ideas
- **AI Consistency Check** — Run an AI-powered analysis (via Anthropic Claude) that scans your world data for contradictions and suggests improvements

## Tech Stack

### Backend

- Python
- FastAPI — API framework
- PostgreSQL — Database
- psycopg2 — PostgreSQL driver
- Pydantic — Data validation and settings
- Anthropic SDK — AI consistency checks
- pwdlib (Argon2) — Password hashing

### Frontend

- React — UI library
- Vite — Build tool and dev server
- React Router — Client-side routing
- Tailwind CSS — Styling

## Getting Started

### Prerequisites

- Python 3.10+
- Node.js 18+
- PostgreSQL

### 1. Clone the repository

```bash
git clone https://github.com/systemfel13/world-building-assistant.git
cd world-building-assistant
```

### 2. Set up the database

Create a PostgreSQL database for the project.

### 3. Set up the backend

```bash
cd backend
python -m venv venv
source venv/Scripts/activate 
pip install -r requirements.txt
```

Copy the example environment file and fill in your values:

```bash
cp .env.example .env
```

Open `.env` and set the following variables:

| Variable             | Description                            |
|----------------------|----------------------------------------|
| `DB_URL`             | PostgreSQL connection string           |
| `ANTHROPIC_API_KEY`  | API key from Anthropic                 |
| `CORS_ORIGINS`       | Allowed frontend origin (default: `http://localhost:5173`) |

Initialize the database tables:

```bash
python -m db.db_setup
```

Start the backend server:

```bash
uvicorn app.api:app --reload
```

The API will be available at `http://localhost:8000`

### 4. Set up the frontend

```bash
cd frontend/vite-project
npm install
npm run dev
```

The app will be available at `http://localhost:5173`

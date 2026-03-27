# NBA Stats API

A REST API serving real NBA player statistics across multiple seasons, 
built with FastAPI and SQLAlchemy. Query player stats, team rosters, 
league leaders, and career histories through a clean JSON API.

## Demo

<img width="1492" height="1251" alt="image" src="https://github.com/user-attachments/assets/4a65be81-2ed6-46fe-ba6d-765d96e55397" />
In this example, I'm running the 'Get Leaders' Method in to get the leaders in points scored in the 2023-2024 season, returning the top 10 point scoreres per game of that season. 


## Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/players/{player_name}` | Search for a player by name |
| GET | `/players/{player_name}/history` | Get a player's stats across all seasons |
| GET | `/teams/{team}/roster` | Get a team's full roster for a season |
| GET | `/stats/leaders` | Get league leaders by stat category |

## Example Requests
```
GET /players/lebron
GET /players/curry/history
GET /teams/GSW/roster?season=2023-24
GET /stats/leaders?category=points&season=2023-24&limit=10
```

## Tech Stack

- **FastAPI** : API framework with automatic /docs UI
- **SQLAlchemy** : ORM for database modeling and queries
- **SQLite** : lightweight relational database
- **nba_api** : pulls real player data from the official NBA stats API
- **Python** : core language

## Setup

1. Clone the repo:
```
   git clone https://github.com/gabezhu23/nba-stats-api
   cd nba-stats-api
```

2. Install dependencies:
```
   pip install -r requirements.txt
```

3. Seed the database with real NBA data:
```
   python seed.py
```

4. Run the API:
```
   uvicorn main:app --reload
```

5. Open `http://localhost:8000/docs` to explore all endpoints interactively

## What I learned

- How to design and build a REST API with FastAPI including 
  automatic OpenAPI documentation
- How to model relational data with SQLAlchemy ORM and 
  SQLite without writing raw SQL
- How to ingest and normalize real-world sports data across 
  multiple seasons using the NBA stats API
- How to implement filtering, searching, and sorting across 
  database records via query parameters

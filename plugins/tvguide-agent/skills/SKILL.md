---
name: tvguide-agent
description: |
  Builds a TV show schedule and search agent using TVMaze API with x402 payments.
  Use when creating entertainment guide agents, TV schedule trackers, or show recommendation systems.
---

# TV Guide Agent

TV show schedules, search, and ratings from TVMaze. 6 endpoints (1 free + 5 paid).

## Live

- **URL:** https://tvguide-agent-production.up.railway.app
- **GitHub:** https://github.com/Calcutatator/tvguide-agent

## API

**Source:** TVMaze  
**Base URL:** `https://api.tvmaze.com`  
**Auth:** None required

## Endpoints

| Key | Price | Description |
|:----|:------|:------------|
| `overview` | Free | Tonight's US primetime TV highlights |
| `search` | $0.002 | Search TV shows by name |
| `show` | $0.002 | Full show details with cast |
| `episodes` | $0.003 | Complete episode guide by season |
| `schedule` | $0.002 | TV schedule for any country/date |
| `report` | $0.005 | Comprehensive TV schedule report |

## Key API Endpoints

```
/schedule?country=US                # Today's US schedule
/search/shows?q=breaking+bad        # Search shows
/shows/{id}?embed=cast              # Show details
/shows/{id}/episodes                # Episode guide
/schedule?country=GB&date=2026-02-07  # Any country/date
```

## Stack

Bun + Hono + `@lucid-agents/core` + `@lucid-agents/payments` + Zod v4

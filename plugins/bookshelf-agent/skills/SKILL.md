---
name: bookshelf-agent
description: |
  Builds a book discovery and trending reads agent using Open Library API with x402 payments.
  Use when creating book recommendation agents, reading list curators, or literary data feeds.
---

# Bookshelf Agent

Book discovery, trending reads, and author data from Open Library. 6 endpoints (1 free + 5 paid).

## Live

- **URL:** https://bookshelf-agent-production.up.railway.app
- **GitHub:** https://github.com/Calcutatator/bookshelf-agent

## API

**Source:** Open Library (Internet Archive)  
**Base URL:** `https://openlibrary.org`  
**Auth:** None required

## Endpoints

| Key | Price | Description |
|:----|:------|:------------|
| `overview` | Free | Top 5 trending books today |
| `search` | $0.002 | Search books by title/author/subject |
| `book` | $0.002 | Full book details by work key |
| `author` | $0.002 | Author biography and works |
| `subject` | $0.003 | Browse books by subject/genre |
| `report` | $0.005 | Trending books across daily/weekly/monthly |

## Key API Endpoints

```
/trending/daily.json?limit=5                    # Daily trending
/search.json?q=dune&limit=10                    # Search
/works/OL45804W.json                            # Book details
/authors/OL23919A.json                          # Author info
/subjects/science_fiction.json?limit=10          # By subject
```

## Stack

Bun + Hono + `@lucid-agents/core` + `@lucid-agents/payments` + Zod v4

RapidAPI link: https://rapidapi.com/arkasarkar2000/api/football-news-aggregator-live
# Football News API

A Football News API that scrapes news data from various football websites using Cheerio and provides endpoints for users to fetch the latest football news. The API supports CORS and is built using Node.js, Cheerio, Axios, and Express.

## Table of Contents

- [Endpoints](#endpoints)
- [Usage](#usage)
- [Getting Started](#getting-started)
- [Contributing](#contributing)
- [License](#license)

## Endpoints

The API provides the following endpoints:

- `/news`: Get the list of websites from where news is coming.
- `/news/onefootball`: Get the latest football news from OneFootball.
- `/news/espn`: Get the latest football news from ESPN. [Provides Images of the news]
- `/news/90mins`: Get the latest football news from 90mins. [Provides Images of the news]
- `/news/goal`: Get the latest football news from Goal. [Provides Images of the news]

## Usage

Users can fetch the latest football news from multiple sources using the provided endpoints. The data is scraped in real-time from popular football news websites.

Here's an example of how to use the API using cURL:

```bash
# Get the list of websites
curl https://footballnewsapi.netlify.app/.netlify/functions/api/news

# Get the latest football news from OneFootball
curl https://footballnewsapi.netlify.app/.netlify/functions/api/news/onefootball

# Get the latest football news from ESPN
curl https://footballnewsapi.netlify.app/.netlify/functions/api/news/espn

# Get the latest football news from 90mins
curl https://footballnewsapi.netlify.app/.netlify/functions/api/news/90mins

# Get the latest football news from Goal
curl https://footballnewsapi.netlify.app/.netlify/functions/api/news/goal

```

## Local Development

```bash
npm ci --cache .npm-cache
npm run dev
# Health check
curl http://localhost:8000/api/v2/health
```

## Deploy to Netlify

This repo is configured for Netlify Functions via `netlify.toml` and `netlify/functions/news.js`.

- Functions directory: `netlify/functions`
- Build command: `-` (none required)
- Publish directory: `.` (repo root)

Steps:
1. Push this repo to GitHub.
2. In Netlify, click “Add new site” → “Import an existing project”.
3. Select the GitHub repo.
4. Build command: `-`
5. Publish directory: `.`
6. Advanced: Functions directory: `netlify/functions`

Netlify will deploy the serverless function at:
- `/.netlify/functions/news/api/v2/...`

Examples (after deploy):
```bash
curl https://<your-site>.netlify.app/.netlify/functions/news/api/v2/health
curl https://<your-site>.netlify.app/.netlify/functions/news/api/v2/news
```

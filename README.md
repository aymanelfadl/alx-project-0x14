# MoviesDatabase API

## API Overview

The MoviesDatabase API provides access to comprehensive entertainment data including over 9 million movies, TV shows, and episodes, plus 11 million cast and crew members. It offers movie details, cast information, ratings, trailers, and search functionality for building entertainment applications.

## API Version

**API Version**: v1 (Available through RapidAPI)

## Available Endpoints

- **Search Movies** - Find movies by title or criteria
- **Movie Details** - Get comprehensive movie information
- **Search TV Shows** - Find TV series and episodes
- **TV Show Details** - Access series information and episode lists
- **Actor Search** - Search for entertainment professionals
- **Actor Details** - Get biographical and filmography data
- **Popular Content** - Retrieve trending movies and shows
- **Trailers** - Access YouTube trailer URLs

## Request and Response Format

### Request Structure
```http
GET /api/v1/movies/search?query=inception
X-RapidAPI-Key: YOUR_API_KEY
X-RapidAPI-Host: moviesdatabase.p.rapidapi.com
```

### Response Format
```json
{
  "status": "success",
  "data": {
    "results": [
      {
        "id": "tt1375666",
        "title": "Inception",
        "year": 2010,
        "genre": ["Action", "Sci-Fi"],
        "rating": 8.8,
        "cast": [{"name": "Leonardo DiCaprio"}]
      }
    ]
  }
}
```

## Authentication Requirements

Requires RapidAPI headers for all requests:

```http
X-RapidAPI-Key: YOUR_API_KEY
X-RapidAPI-Host: moviesdatabase.p.rapidapi.com
```

Get your API key by signing up at [RapidAPI](https://rapidapi.com) and subscribing to the MoviesDatabase API.

## Error Handling

Common error responses:

- **400 Bad Request** - Invalid parameters
- **401 Unauthorized** - Invalid API key
- **404 Not Found** - Resource doesn't exist
- **429 Too Many Requests** - Rate limit exceeded
- **500 Internal Server Error** - Server error

Always check HTTP status codes and implement retry logic for rate limits.

## Usage Limits and Best Practices

### Rate Limits
- **Free**: 500 requests/month
- **Basic**: 10,000 requests/month
- **Pro**: 100,000 requests/month

### Best Practices
- Cache frequently requested data
- Use specific search terms
- Implement request throttling
- Never expose API keys in client-side code
- Handle errors gracefully with user feedback
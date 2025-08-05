# Movie App API Setup Guide

## Getting Your TMDB API Key

1. **Visit TMDB Website**: Go to [https://www.themoviedb.org/](https://www.themoviedb.org/)
2. **Create Account**: Sign up for a free account
3. **Get API Key**:
   - Go to your account settings
   - Navigate to "API" section
   - Request an API key for "Developer" use
   - You'll receive your API key via email

## Setting Up the API Key

1. **Replace the placeholder**: In `src/services/movieApi.js`, replace:

   ```javascript
   const API_KEY = "YOUR_TMDB_API_KEY";
   ```

   with your actual API key:

   ```javascript
   const API_KEY = "your_actual_api_key_here";
   ```

2. **Also update home.jsx**: If you haven't used the service file, replace the API key in `src/pages/home.jsx` as well.

## API Features

The app now includes:

- ✅ **Popular Movies**: Fetches trending/popular movies
- ✅ **Search Movies**: Search for specific movies
- ✅ **Movie Details**: Get detailed information about movies
- ✅ **Trending Movies**: Get weekly trending movies

## API Endpoints Used

- `GET /movie/popular` - Get popular movies
- `GET /search/movie` - Search for movies
- `GET /movie/{id}` - Get movie details
- `GET /trending/movie/week` - Get trending movies

## Error Handling

The app includes proper error handling for:

- Network errors
- API rate limiting
- Invalid API keys
- Search failures

## Security Note

⚠️ **Important**: Never commit your API key to version control. Consider using environment variables for production:

```javascript
const API_KEY = process.env.REACT_APP_TMDB_API_KEY;
```

Then create a `.env` file:

```
REACT_APP_TMDB_API_KEY=your_api_key_here
```

## Testing the API

Once you've added your API key:

1. Start the development server: `npm run dev`
2. Navigate to the home page
3. You should see real movie data with posters
4. Try searching for movies
5. Test the favorites functionality

The app will now display real movie data from TMDB instead of static data!

# Chat Express App

A real-time chat application built with Express.js, Socket.IO, and MongoDB.

## Features

- Real-time chat functionality
- User authentication with JWT
- MongoDB database integration
- CORS support for frontend integration

## Local Development

1. Install dependencies:
```bash
npm install
```

2. Create a `.env` file with the following variables:
```env
MONGO_URI=mongodb://localhost:27017/your_database
ACCESS_TOKEN_SECRET=your_access_token_secret
REFRESH_TOKEN_SECRET=your_refresh_token_secret
NODE_ENV=development
```

3. Start the development server:
```bash
npm run dev
```

## Railway Deployment

### Environment Variables Required

Set these environment variables in your Railway dashboard:

```env
# Database Configuration
MONGO_URI=mongodb+srv://username:password@cluster.mongodb.net/database_name

# JWT Secrets (Generate strong random strings)
ACCESS_TOKEN_SECRET=your_access_token_secret_here
REFRESH_TOKEN_SECRET=your_refresh_token_secret_here

# Environment
NODE_ENV=production

# Frontend URL (if you have a separate frontend)
FRONTEND_URL=https://your-frontend-domain.com

# Railway automatically provides this
RAILWAY_PUBLIC_DOMAIN=your-app-name.railway.app
```

### Deployment Steps

1. **Connect your GitHub repository** to Railway
2. **Set environment variables** in Railway dashboard:
   - Go to your project → Variables tab
   - Add all the environment variables listed above
3. **Deploy** - Railway will automatically deploy when you push to your main branch

### Important Notes

- **MongoDB**: Use MongoDB Atlas for production database
- **JWT Secrets**: Generate strong random strings for security
- **CORS**: The app is configured to accept requests from your frontend domain
- **HTTPS**: Railway provides HTTPS automatically
- **Cookies**: Secure cookies are enabled in production

### Testing Your Deployment

1. Check if your app is running: `https://your-app-name.railway.app`
2. Test the API endpoints:
   - `POST /register` - User registration
   - `POST /login` - User login
   - `POST /refresh` - Token refresh
   - `POST /logout` - User logout

### Troubleshooting

- **CORS errors**: Make sure your frontend URL is correctly set in `FRONTEND_URL`
- **Database connection**: Verify your MongoDB Atlas connection string
- **JWT errors**: Ensure both JWT secrets are set and are strong random strings

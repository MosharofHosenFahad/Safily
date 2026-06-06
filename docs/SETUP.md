# 🚀 Setup Guide for Safily

## Prerequisites

- Node.js v16 or higher
- npm or yarn
- MongoDB (local or cloud)
- Git

## Backend Setup

### 1. Navigate to backend directory
```bash
cd backend
```

### 2. Install dependencies
```bash
npm install
```

### 3. Create environment file
```bash
cp .env.example .env
```

### 4. Configure .env file
```env
# Server
PORT=5000
NODE_ENV=development

# Database
MONGODB_URI=mongodb://localhost:27017/safily

# JWT
JWT_SECRET=your_jwt_secret_key_here

# YouTube API
YOUTUBE_API_KEY=your_youtube_api_key_here

# Prayer Times API
PRAYER_API_URL=https://api.aladhan.com/v1

# Frontend URL
FRONTEND_URL=http://localhost:5173
```

### 5. Start development server
```bash
npm run dev
```

Server will run on `http://localhost:5000`

## Frontend Setup

### 1. Navigate to frontend directory
```bash
cd frontend
```

### 2. Install dependencies
```bash
npm install
```

### 3. Create environment file
```bash
cp .env.example .env.local
```

### 4. Configure .env.local
```env
VITE_API_URL=http://localhost:5000
VITE_YOUTUBE_API_KEY=your_youtube_api_key_here
```

### 5. Start development server
```bash
npm run dev
```

Frontend will run on `http://localhost:5173`

## Database Setup

### MongoDB Local Installation

**Windows:**
1. Download from https://www.mongodb.com/try/download/community
2. Run installer
3. MongoDB will run as service

**Mac:**
```bash
brew tap mongodb/brew
brew install mongodb-community
brew services start mongodb-community
```

**Linux:**
```bash
sudo apt-get install mongodb
sudo systemctl start mongodb
```

### MongoDB Atlas (Cloud)

1. Go to https://www.mongodb.com/cloud/atlas
2. Create free account
3. Create cluster
4. Get connection string
5. Add to .env file

## API Keys Configuration

### YouTube API Key

1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Create new project
3. Enable YouTube Data API v3
4. Create OAuth 2.0 credentials
5. Add key to .env

## Docker Setup (Optional)

```bash
docker-compose up -d
```

This will start:
- Frontend (port 3000)
- Backend (port 5000)
- MongoDB (port 27017)

## Troubleshooting

### Port already in use
```bash
# Kill process on port 5000
lsof -ti:5000 | xargs kill -9
```

### MongoDB connection error
- Ensure MongoDB is running
- Check connection string in .env
- Verify firewall settings

### Build errors
```bash
# Clear cache and reinstall
rm -rf node_modules package-lock.json
npm install
```

## Next Steps

1. Read [Features Documentation](./FEATURES.md)
2. Check [API Documentation](./API.md)
3. Review [Database Schema](./DATABASE.md)
4. Start contributing! 🎉
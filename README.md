# 🎯 Safily - Complete Productivity & Learning Management App

A comprehensive application designed to help users manage their learning journey with YouTube playlists, time tracking, prayer schedules, achievement unlocking, and productivity tools.

## ✨ Features Overview

### 📺 **Playlist Manager**
- Add and manage multiple YouTube playlists
- Track last watched video with timestamp
- Resume playback from where you left off
- Visual playlist cards with navigation arrows
- Auto-save watching progress

### ⏱️ **Time & Schedule Management**
- Daily timetable/schedule planner
- Prayer times (5 daily prayers) - automatic
- Notifications/alarms for scheduled activities
- Visual schedule calendar

### 🍅 **Pomodoro & Time Tracking**
- Pomodoro timer for: Reading, Writing, Prayer, Play, Work, etc.
- Automatic daily reset
- Customizable time intervals
- Task-based tracking

### 🏆 **Achievement System**
- Weekly achievement milestones
- Monthly and yearly tracking
- Motivation badges and rewards
- Progress visualization
- Streak tracking

### 📝 **Notes & Documentation**
- Daily notes page
- Rich text editing (Bold, Italic, Strikethrough, Hyperlinks)
- Inline calculator
- Group organization for notes
- Search and filter functionality

### 🛡️ **Content Blocking & Wellness**
- Block harmful websites and apps
- Social media blocking
- NSFW/Porn site blocking
- Achievement tracking for blocked days
- Motivation rewards for maintaining streaks

### 💾 **Import/Export**
- Save schedules and settings as `.sfy` files (Safily)
- One-time setup for reading preferences
- Portable configuration backup

## 📁 Project Structure

```
Safily/
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── utils/
│   │   ├── styles/
│   │   └── App.jsx
│   ├── public/
│   ├── package.json
│   └── vite.config.js
├── backend/
│   ├── src/
│   │   ├── models/
│   │   ├── routes/
│   │   ├── controllers/
│   │   ├── middleware/
│   │   └── config/
│   ├── package.json
│   └── server.js
├── docs/
├── .gitignore
├── docker-compose.yml
└── README.md
```

## 🛠️ Tech Stack

- **Frontend**: React.js + TypeScript + Tailwind CSS + Vite
- **Backend**: Node.js + Express.js
- **Database**: MongoDB
- **Real-time**: Socket.io for notifications
- **API Integration**: YouTube Data API v3
- **Authentication**: JWT
- **Storage**: Local Storage + Cloud backup

## 🚀 Quick Start

### Prerequisites
- Node.js (v16+)
- npm or yarn
- MongoDB
- YouTube API key

### Installation

1. Clone the repository
```bash
git clone https://github.com/MosharofHosenFahad/Safily.git
cd Safily
```

2. Setup Backend
```bash
cd backend
npm install
cp .env.example .env
npm run dev
```

3. Setup Frontend
```bash
cd ../frontend
npm install
npm run dev
```

## 📱 App Sections (from mockup)

**Bottom Navigation:**
- 📺 **PLAYLIST** - Manage your YouTube playlists
- ⏱️ **TIME & NOTE** - Schedule, Pomodoro, Notes, Prayers
- 🛡️ **SOCIAL BLOCK** - Block harmful content & track achievements

## 💾 File Format (.sfy)

```json
{
  "version": "1.0",
  "exportDate": "2026-06-06T12:00:00Z",
  "settings": {
    "readingTimePerDay": "2h",
    "workTimePerDay": "4h",
    "prayerTimes": "automatic",
    "contentBlockingEnabled": true,
    "timezone": "UTC",
    "language": "en"
  },
  "playlists": [],
  "schedules": [],
  "notes": [],
  "achievements": [],
  "blockedSites": []
}
```

## 📚 Documentation

- [Setup Guide](./docs/SETUP.md)
- [API Documentation](./docs/API.md)
- [Features Detailed](./docs/FEATURES.md)
- [Database Schema](./docs/DATABASE.md)

## 🎨 Design Inspiration

- Dark theme with accent colors (Green, Red, Blue)
- Colored playlist indicators
- Side-scrolling video carousel
- Smooth animations and transitions

## 🤝 Contributing

Contributions are welcome! Please follow the contribution guidelines.

## 📄 License

MIT License

## 👨‍💻 Author

**Mosharof Hosen Fahad**
- GitHub: [@MosharofHosenFahad](https://github.com/MosharofHosenFahad)

---

**Happy Learning & Stay Focused! 🎓✨**
# 🔌 API Documentation - Safily

## Base URL
```
http://localhost:5000/api
```

## Authentication
All endpoints (except auth) require JWT token:
```
Authorization: Bearer <token>
```

---

## 🔐 Auth Endpoints

### POST /auth/register
```json
{
  "email": "user@example.com",
  "password": "secure_password",
  "firstName": "John",
  "lastName": "Doe"
}
```

### POST /auth/login
```json
{
  "email": "user@example.com",
  "password": "secure_password"
}
```

---

## 📺 Playlist Endpoints

### GET /playlists
Get all user playlists

### POST /playlists
Add new playlist
```json
{
  "name": "My Playlist",
  "youtubeId": "PLxxxxxx",
  "color": "green"
}
```

### GET /playlists/:playlistId
Get playlist details

### PUT /playlists/:playlistId
Update playlist

### DELETE /playlists/:playlistId
Delete playlist

### POST /playlists/:playlistId/progress
Update video progress
```json
{
  "videoId": "videoId",
  "progress": "45:30"
}
```

---

## ⏱️ Schedule Endpoints

### GET /schedules
Get all schedules

### POST /schedules
Create schedule

### GET /schedules/:dayOfWeek
Get schedule for specific day

### PUT /schedules/:scheduleId
Update schedule

### DELETE /schedules/:scheduleId
Delete schedule

### GET /schedules/prayer-times
Get prayer times for location

---

## 🍅 Pomodoro Endpoints

### GET /pomodoro/sessions
Get all sessions

### POST /pomodoro/sessions
Start new session

### GET /pomodoro/stats
Get statistics

---

## 📝 Notes Endpoints

### GET /notes
Get all notes

### POST /notes
Create note

### GET /notes/:noteId
Get note details

### PUT /notes/:noteId
Update note

### DELETE /notes/:noteId
Delete note

---

## 🏆 Achievement Endpoints

### GET /achievements
Get all achievements

### GET /achievements/stats
Get achievement statistics

---

## 🛡️ Content Blocking Endpoints

### GET /blocking/sites
Get all blocked sites

### POST /blocking/sites
Add site to blocklist

### DELETE /blocking/sites/:siteId
Remove from blocklist

### PUT /blocking/schedule
Update blocking schedule

### GET /blocking/stats
Get blocking statistics

---

## 💾 Backup Endpoints

### POST /backup/export
Export data to .sfy file

### POST /backup/import
Import from .sfy file

### GET /backup/list
Get list of backups

---

## 👤 User Endpoints

### GET /users/profile
Get user profile

### PUT /users/profile
Update profile

### PUT /users/settings
Update settings

### POST /users/password
Change password

---

## 📊 Analytics Endpoints

### GET /analytics/dashboard
Get dashboard stats

### GET /analytics/charts
Get chart data

---

## Error Response Format

```json
{
  "success": false,
  "error": {
    "code": "ERROR_CODE",
    "message": "Error message"
  }
}
```
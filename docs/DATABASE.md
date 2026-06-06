# 🗄️ Database Schema - Safily

## Collections Overview

### 1. Users Collection
```javascript
db.createCollection('users', {
  validator: {
    $jsonSchema: {
      bsonType: 'object',
      required: ['email', 'password', 'createdAt'],
      properties: {
        _id: { bsonType: 'objectId' },
        email: { bsonType: 'string' },
        password: { bsonType: 'string' },
        firstName: { bsonType: 'string' },
        lastName: { bsonType: 'string' },
        avatar: { bsonType: 'string' },
        timezone: { bsonType: 'string', default: 'UTC' },
        language: { bsonType: 'string', default: 'en' },
        theme: { enum: ['dark', 'light'], default: 'dark' },
        location: {
          bsonType: 'object',
          properties: {
            latitude: { bsonType: 'double' },
            longitude: { bsonType: 'double' },
            city: { bsonType: 'string' }
          }
        },
        createdAt: { bsonType: 'date' },
        updatedAt: { bsonType: 'date' },
        lastLogin: { bsonType: 'date' }
      }
    }
  }
});

db.users.createIndex({ email: 1 }, { unique: true });
```

### 2. Playlists Collection
```javascript
db.createCollection('playlists', {
  validator: {
    $jsonSchema: {
      bsonType: 'object',
      required: ['userId', 'name', 'youtubeId'],
      properties: {
        _id: { bsonType: 'objectId' },
        userId: { bsonType: 'objectId' },
        name: { bsonType: 'string' },
        youtubeId: { bsonType: 'string' },
        color: { enum: ['green', 'red', 'blue'] },
        videos: { bsonType: 'array' },
        lastWatchedVideo: { bsonType: 'string' },
        lastWatchedTime: { bsonType: 'date' },
        progress: { bsonType: 'string' },
        totalVideos: { bsonType: 'int' },
        createdAt: { bsonType: 'date' }
      }
    }
  }
});

db.playlists.createIndex({ userId: 1, createdAt: -1 });
```

### 3. Schedules Collection
```javascript
db.createCollection('schedules', {
  validator: {
    $jsonSchema: {
      bsonType: 'object',
      required: ['userId', 'dayOfWeek'],
      properties: {
        _id: { bsonType: 'objectId' },
        userId: { bsonType: 'objectId' },
        dayOfWeek: { bsonType: 'int' },
        activities: { bsonType: 'array' },
        prayerTimes: { bsonType: 'object' },
        timezone: { bsonType: 'string' },
        createdAt: { bsonType: 'date' }
      }
    }
  }
});

db.schedules.createIndex({ userId: 1, dayOfWeek: 1 });
```

### 4. Pomodoro Sessions Collection
```javascript
db.createCollection('pomodoroSessions', {
  validator: {
    $jsonSchema: {
      bsonType: 'object',
      required: ['userId', 'taskType'],
      properties: {
        _id: { bsonType: 'objectId' },
        userId: { bsonType: 'objectId' },
        taskType: { enum: ['reading', 'writing', 'prayer', 'play', 'work', 'meditation'] },
        duration: { bsonType: 'int' },
        completed: { bsonType: 'bool' },
        date: { bsonType: 'date' },
        createdAt: { bsonType: 'date' }
      }
    }
  }
});

db.pomodoroSessions.createIndex({ userId: 1, date: -1 });
```

### 5. Notes Collection
```javascript
db.createCollection('notes', {
  validator: {
    $jsonSchema: {
      bsonType: 'object',
      required: ['userId'],
      properties: {
        _id: { bsonType: 'objectId' },
        userId: { bsonType: 'objectId' },
        title: { bsonType: 'string' },
        content: { bsonType: 'string' },
        group: { bsonType: 'string' },
        tags: { bsonType: 'array' },
        isPinned: { bsonType: 'bool' },
        color: { bsonType: 'string' },
        createdAt: { bsonType: 'date' }
      }
    }
  }
});

db.notes.createIndex({ userId: 1, createdAt: -1 });
db.notes.createIndex({ userId: 1, group: 1 });
```

### 6. Achievements Collection
```javascript
db.createCollection('achievements', {
  validator: {
    $jsonSchema: {
      bsonType: 'object',
      required: ['userId', 'name'],
      properties: {
        _id: { bsonType: 'objectId' },
        userId: { bsonType: 'objectId' },
        name: { bsonType: 'string' },
        type: { enum: ['time', 'consistency', 'wellness', 'blocking'] },
        unlockedAt: { bsonType: 'date' },
        progress: { bsonType: 'int' },
        points: { bsonType: 'int' },
        createdAt: { bsonType: 'date' }
      }
    }
  }
});

db.achievements.createIndex({ userId: 1, unlockedAt: -1 });
```

### 7. Content Blocking Collection
```javascript
db.createCollection('contentBlocking', {
  validator: {
    $jsonSchema: {
      bsonType: 'object',
      required: ['userId'],
      properties: {
        _id: { bsonType: 'objectId' },
        userId: { bsonType: 'objectId' },
        blockedSites: { bsonType: 'array' },
        schedule: { bsonType: 'object' },
        streak: { bsonType: 'object' },
        createdAt: { bsonType: 'date' }
      }
    }
  }
});

db.contentBlocking.createIndex({ userId: 1 });
```

## Index Summary

```javascript
// Create all indexes
db.users.createIndex({ email: 1 }, { unique: true });
db.playlists.createIndex({ userId: 1, createdAt: -1 });
db.schedules.createIndex({ userId: 1, dayOfWeek: 1 });
db.pomodoroSessions.createIndex({ userId: 1, date: -1 });
db.notes.createIndex({ userId: 1, createdAt: -1 });
db.achievements.createIndex({ userId: 1, unlockedAt: -1 });
db.contentBlocking.createIndex({ userId: 1 });
```
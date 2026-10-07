# Workout Tracker - Your Complete Training Companion

A modern, cross-platform fitness tracking application built with React and Capacitor. Track your daily workouts, monitor nutrition, and visualize your progress with a beautiful newspaper-inspired interface.

**Website:** [fitnesstracker-flame.vercel.app](https://fitnesstracker-flame.vercel.app)

---

##  Features

### **Workout Tracking**
- 6-day training split program (Monday-Saturday with rest days)
- Exercise tracking with sets, reps, and rest periods
- Real-time timer for rest intervals
- Exercise detail view with coaching tips and form guidance
- Set completion tracking with progress visualization

### **Nutrition Guide**
- Pre-planned nutrition recommendations
- Macro breakdowns for daily meals
- Healthy eating guidelines
- Integrated nutrition planning

###  **Progress Analytics**
- Calendar view of completed workouts
- Monthly, weekly, and yearly attendance stats
- Training streak counter
- Workout completion percentage
- Visual progress charts with Recharts

###  **Additional Features**
- No authentication needed (local storage only)
- Offline-first approach
- Responsive design for mobile and web
- Newspaper-inspired aesthetic UI
- Dark theme
- Local data persistence

---

##  Tech Stack

### Frontend
- **React 18.3+** - UI framework
- **Vite 5.3+** - Build tool & dev server
- **Capacitor 8.3+** - Cross-platform framework

### Styling
- **CSS3** - Custom styling with CSS variables
- **Responsive Design** - Mobile-first approach

### Data Visualization
- **Recharts** - Charts and graphs

### Data Storage
- **LocalStorage API** - Client-side data persistence
- **No Backend** - Fully client-side application

### Deployment
- **Vercel** - Web hosting
- **Android APK** - Mobile app packaging

---

##  Platform Support

- ✅ **Web** - Modern browsers (Chrome, Firefox, Safari, Edge)
- ✅ **Android** - Android 5.0+ (APK available)


---



##  Getting Started (Development)

### Prerequisites
- Node.js 16+ and npm/yarn
- Java Development Kit (JDK 11+) - for Android build
- Android Studio (optional, for Android development)

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/ruthwik11/FitnessTracker.git
cd FitnessTracker
```

2. **Install dependencies**
```bash
npm install
```

3. **Run development server**
```bash
npm run dev
```
The app will open at `http://localhost:3000`

### Build for Production (Web)

```bash
npm run build
```

This creates optimized production files in the `dist/` folder.

---

## 📂 Project Structure

```
FitnessTracker/
├── src/
│   ├── components/          # React components
│   │   ├── Workout.jsx      # Main workout display
│   │   ├── Progress.jsx     # Progress tracking & analytics
│   │   ├── NutritionPage.jsx # Nutrition guide
│   │   ├── Timer.jsx        # Rest timer component
│   │   ├── Checklist.jsx    # Exercise checklist
│   │   ├── AttendanceCalendar.jsx # Calendar view
│   │   ├── ExerciseDetail.jsx # Exercise details modal
│   │   └── ui/              # UI components
│   │       ├── OrnamentDivider.jsx
│   │       └── EditionBadge.jsx
│   ├── data/
│   │   └── workoutData.js   # 6-day training program
│   ├── utils/
│   │   └── storage.js       # LocalStorage utilities
│   ├── main.jsx             # App entry point
│   └── style.css            # Global styles
├── android/                 # Android project files
│   ├── app/                 # Android app module
│   ├── gradle/              # Gradle files
│   └── build.gradle
├── index.html               # HTML entry point
├── package.json             # Dependencies & scripts
├── vite.config.js           # Vite configuration
├── capacitor.config.json    # Capacitor configuration
└── README.md                # This file
```

---

##  Data Storage

### How It Works
- All data is stored locally in the browser's **LocalStorage**
- No data is sent to any server
- Data persists across sessions
- Each device has its own independent data

### Storage Structure
Data is organized by date in the format:
```
workout_YYYY-MM-DD: {
  date: "YYYY-MM-DD",
  day: "MONDAY",
  exercises: [
    {
      id: "exercise_1",
      name: "Barbell Bench Press",
      sets: 4,
      reps: "6-8",
      completedSets: 3
    }
  ],
  completed: false,
  stepsCompleted: false,
  timestamp: "ISO timestamp"
}
```

### Storage Functions
See `src/utils/storage.js` for utilities:
- `saveWorkoutProgress()` - Save daily workout data
- `loadWorkoutProgress()` - Load daily workout data
- `getMonthlyAttendance()` - Get monthly stats
- `getCurrentStreak()` - Get training streak
- `clearAllData()` - Reset all data

### Export Your Data
To backup your data:
```javascript
// In browser console
const allData = {};
for (let i = 0; i < localStorage.length; i++) {
  const key = localStorage.key(i);
  if (key.startsWith('workout_')) {
    allData[key] = localStorage.getItem(key);
  }
}
console.log(JSON.stringify(allData));
```

---

##  Customization

### Modifying the Training Program
Edit `src/data/workoutData.js`:
```javascript
export const workoutData = {
  MONDAY: {
    day: 'MONDAY',
    color: '#FF6B6B',
    focus: 'Chest & Triceps',
    exercises: [
      {
        id: 'exercise_1',
        name: 'Barbell Bench Press',
        sets: 4,
        reps: '6-8',
        rest: 180,
        // ... more details
      }
    ]
  },
  // ... other days
};
```

### Customizing Nutrition
Edit `src/data/workoutData.js` - `nutritionPlan` export

### Styling
- Colors: Edit CSS variables in `src/style.css`
- Layout: Modify component JSX files
- Theme: Update color scheme in `style.css`

---

## 🔧 Available Scripts

```bash
# Development
npm run dev           # Start dev server

# Production
npm run build         # Build for production
npm run preview       # Preview production build locally

# Android
npm run android:build # Build web + sync with Android
npm run android:open  # Open Android Studio

# Code Quality
npm run lint         # Run ESLint
```

---

##  Deployment

### Web (Vercel)
```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
vercel
```

---

##  Security & Privacy

 **Privacy First**
- No user authentication required
- No data transmitted to servers
- All data stored locally on device
- No tracking or analytics

 **Limitations**
- Data not backed up to cloud
- Data lost if browser cache is cleared
- No data sync across devices

---

##  Troubleshooting

### Data not saving?
- Check if LocalStorage is enabled in browser
- Clear browser cache and try again
- Check browser console for errors



### Port 3000 already in use?
Edit `vite.config.js`:
```javascript
server: {
  port: 3001  // Change to different port
}
```

---


##  License

This project is open source and available for personal and educational use.

---

##  Contributing

Contributions are welcome! Feel free to:
- Report bugs
- Suggest features
- Submit pull requests
- Improve documentation

---

##  Support

For issues or questions:
- Open a GitHub issue
- Check existing documentation
- Review code comments

---

##  Project Goals

This fitness tracker was built to:
- ✅ Help users stay consistent with their training
- ✅ Provide a distraction-free workout experience
- ✅ Track progress without requiring sign-ups
- ✅ Work offline without backend dependencies
- ✅ Deliver a beautiful, intuitive interface

---

**Built with ❤️ by Ruthwik**

[GitHub](https://github.com/ruthwik11) | [Website](https://fitnesstracker-flame.vercel.app)

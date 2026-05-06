🎓 StudyPath AI
An AI-powered learning and career guidance platform for students.
Live Demo License: MIT Firebase HTML5 JavaScript Student Productivity AI Learning Platform

🌐 Live Demo
StudyPath AI is live and deployed on Netlify:

👉 https://studypathai.netlify.app
📖 Project Overview
StudyPath AI is a full-stack, AI-powered learning and career guidance platform designed specifically for students. It helps you plan your academic journey, track skills, manage study tasks, organise notes and resources, and receive structured roadmap-style career guidance — all in one centralised place.

The platform combines Firebase Authentication, Cloud Firestore, and a dynamic JavaScript frontend to deliver a real, database-backed, multi-page web application with per-user data, authentication-gated routes, and a clean modern UI.

🧩 Problem Statement
Students today face a fragmented productivity problem:

Notes are scattered across different apps
Learning paths are unclear and unstructured
Study planning is inconsistent or nonexistent
Career preparation lacks a central tracking system
Progress is hard to measure without a dashboard
StudyPath AI solves this by giving students a single, organised platform to manage their entire learning and career journey — from daily tasks to roadmap milestones.

✨ Features
Feature	Description
🔐 Login & Signup	Secure user authentication via Firebase (email/password + Google Sign-In)
📊 Dashboard	Real-time overview of tasks, skills, applications, and assignments
🗺️ AI Career Roadmaps	Generate step-by-step structured career paths tailored to your goal
📚 Study Planner	Plan daily/weekly tasks with priorities, due dates, and completion tracking
🚀 Skills Tracker	Track programming, DSA, AI/ML, and soft skills with animated progress bars
📝 Smart Notes	Save, search, and organise learning notes by category
🔗 Resource Library	Curated resources for DSA, Web Dev, AI/ML, Interview Prep and more
📋 Assignment Tracker	Track deadlines, priorities, and submission status — never miss a due date
💼 Applications Tracker	Kanban-style internship tracker from "Applied" to "Selected"
📈 Performance Analyzer	Input results to get AI-suggested weak areas and a personalised study plan
☁️ Firestore Database	All user data stored securely per-user in Cloud Firestore
📱 Responsive Design	Fully responsive for desktop, tablet, and mobile
🌐 Cloud Deployment	Hosted live on Netlify with continuous deployment from GitHub
🛠️ Tech Stack
Frontend
HTML5 — Semantic page structure across 12+ pages
CSS3 — Custom design system, animations, responsive layouts (no CSS frameworks)
JavaScript (ES6+) — All interactivity, Firestore CRUD, auth flows, UI logic
Backend / Cloud Services
Firebase Authentication — Email/password login, Google Sign-In, session management
Cloud Firestore — NoSQL per-user database for all app data
Firebase SDK (v8 compat) — Browser-side SDK for auth and Firestore access
Deployment & DevOps
Netlify — Live hosting with automatic GitHub integration
Git & GitHub — Version control and source code management
Typography & Fonts
Google Fonts — Inter & Poppins
✅ No React. No Node.js. No Express. No MongoDB. No Next.js. No Tailwind. This is a pure frontend + Firebase architecture — no build step required to run locally.

🏗️ Project Architecture
StudyPath AI follows a full-stack web architecture using Firebase as a Backend-as-a-Service (BaaS):

┌─────────────────────────────────────────────────────┐
│                    USER (Browser)                   │
├─────────────────────────────────────────────────────┤
│              FRONTEND LAYER (HTML/CSS/JS)           │
│  • 12+ HTML pages (dashboard, roadmap, planner…)   │
│  • Custom CSS design system                         │
│  • Vanilla JS modules per page                      │
├─────────────────────────────────────────────────────┤
│           FIREBASE BACKEND SERVICES                 │
│  • Firebase Auth → user login, signup, Google SSO  │
│  • Cloud Firestore → per-user NoSQL data storage   │
│  • Auth guard → protects private pages             │
├─────────────────────────────────────────────────────┤
│              HOSTING & DEPLOYMENT                   │
│  • Netlify → serves all static files               │
│  • GitHub → source control + CI/CD integration     │
└─────────────────────────────────────────────────────┘
Data flow:

User visits a page → guard.js checks Firebase Auth state
If not logged in → redirect to login.html
After login → user-specific data is read/written from Firestore
All data is scoped to users/{uid}/... — strict per-user isolation
Firestore security rules enforce that users can only access their own data
📁 Folder Structure
studypathai/
│
├── index.html              # Landing page with feature showcase
├── login.html              # Email + Google login
├── signup.html             # New user registration
├── dashboard.html          # Main dashboard (stats, overview)
├── roadmap.html            # AI career roadmap generator
├── study-planner.html      # Daily/weekly study task planner
├── skills.html             # Skills tracker with progress bars
├── notes.html              # Notes manager
├── resources.html          # Curated resource library
├── assignments.html        # Assignment tracker
├── applications.html       # Internship/career application tracker
├── performance.html        # Performance analyzer
│
├── css/
│   ├── style.css           # Global design system and shared styles
│   ├── dashboard.css       # Dashboard-specific styles
│   └── auth.css            # Login/signup page styles
│
├── js/
│   ├── firebase-config.example.js  # ✅ Safe config template (committed)
│   ├── firebase-config.js          # 🔒 Your real credentials (git-ignored)
│   ├── auth.js             # Email/password + Google auth logic
│   ├── guard.js            # Auth route guard (redirects unauthenticated users)
│   ├── firestore.js        # Shared Firestore CRUD helpers
│   ├── ui.js               # Shared UI (navbar, mobile toggle, loaders)
│   ├── dashboard.js        # Dashboard stats and data aggregation
│   ├── roadmap.js          # Roadmap generation and Firestore sync
│   ├── study.js            # Study planner CRUD logic
│   ├── skills.js           # Skills tracker logic
│   ├── notes.js            # Notes CRUD logic
│   ├── resources.js        # Resource library data and filters
│   ├── assignments.js      # Assignment tracker logic
│   ├── applications.js     # Applications tracker logic
│   └── performance.js      # Performance analyzer and study plan generation
│
├── firestore.rules         # Firestore security rules (deploy to Firebase)
├── .gitignore              # Protects credentials and ignores build artifacts
├── LICENSE                 # MIT License
└── README.md               # This file
🚀 Getting Started
Prerequisites
A modern browser (Chrome, Firefox, Edge, Safari)
VS Code + Live Server extension
A Firebase project (free Spark plan works)
Git installed
Step 1 — Clone the repository
git clone https://github.com/Srivalli-D/studypathai.git
cd studypathai
Step 2 — Set up Firebase
See the Firebase Setup section below.

Step 3 — Configure your Firebase credentials
# Copy the example config to your local config file
cp js/firebase-config.example.js js/firebase-config.js
Open js/firebase-config.js and replace every placeholder with your actual Firebase project values:

const firebaseConfig = {
  apiKey:            "your-api-key",
  authDomain:        "your-project.firebaseapp.com",
  projectId:         "your-project-id",
  storageBucket:     "your-project.firebasestorage.app",
  messagingSenderId: "your-sender-id",
  appId:             "your-app-id",
  measurementId:     "G-XXXXXXXXXX"   // optional
};
⚠️ Never commit js/firebase-config.js to Git. It is listed in .gitignore automatically.

Step 4 — Run locally
Option A — VS Code Live Server (recommended)

Open the project folder in VS Code
Right-click index.html → "Open with Live Server"
App opens at http://127.0.0.1:5500
Option B — Python HTTP server

python -m http.server 5500
# Open http://localhost:5500
Option C — Node serve

npx serve .
🔥 Firebase Setup
1. Create a Firebase project
Go to https://console.firebase.google.com/
Click "Add project" and follow the prompts
Register a Web App (</>) and copy the firebaseConfig object
2. Enable Authentication
Go to Authentication → Sign-in method
Enable Email/Password
Enable Google (add your support email)
Under Authorized domains, add:
localhost
127.0.0.1
studypathai.netlify.app (or your own domain)
3. Create Firestore Database
Go to Firestore Database → Create database
Start in production mode
Select a region near your users
4. Set Firestore Security Rules
In Firestore → Rules, paste the contents of firestore.rules:

rules_version = '2';

service cloud.firestore {
  match /databases/{database}/documents {
    match /users/{userId} {
      allow read, write: if request.auth != null && request.auth.uid == userId;

      match /{subcollection}/{docId} {
        allow read, write: if request.auth != null && request.auth.uid == userId;
      }
    }
  }
}
Click Publish.

🌍 Deployment
Live Deployment — Netlify
The project is live at https://studypathai.netlify.app

To deploy your own fork:

Option A — Netlify (recommended)

Push your code to GitHub
Go to netlify.com → New site from Git
Connect your GitHub repo → deploy
Add environment variables in Netlify dashboard if needed
Option B — Firebase Hosting

npm install -g firebase-tools
firebase login
firebase init hosting
firebase deploy
Option C — GitHub Pages

Go to repo Settings → Pages
Set source to main branch, root folder
Your site will be at https://yourusername.github.io/studypathai
📸 Screenshots
Screenshots will be added soon.

🗺️ Roadmap & Future Improvements
 AI-generated assignments and tasks based on performance results
 Smarter skill recommendations using learning history and trends
 Enhanced analytics dashboard with charts and progress graphs
 Admin / mentor panel for classroom or coaching use
 Push notifications and deadline reminders
 Progressive Web App (PWA) support for offline use
 Social features — share roadmaps and compare progress with peers
 Improved AI roadmap generation with more career domains
🤝 Contributing
Contributions, issues, and feature requests are welcome!

Fork the repository
Create a feature branch: git checkout -b feature/your-feature
Make your changes and commit: git commit -m "Add: your feature"
Push: git push origin feature/your-feature
Open a Pull Request
🔒 Important: Never commit js/firebase-config.js. Always use js/firebase-config.example.js as the template.

📄 License
This project is licensed under the MIT License — see the LICENSE file for details.

Copyright (c) 2026 Srivalli-D

Made with ❤️ by Srivalli-D

Live Demo · Report a Bug · Request a Feature

# studypathai1

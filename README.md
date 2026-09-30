# Daily Attendance & Student Attendance Management System (SAMS)

A modern, responsive attendance and academic register application built for educators, tutors, and academic administrators. Features daily attendance registers, institutional reports, branch/class management, student roster tracking, and cloud sync.

---

## 🚀 Quick Start (Local Development)

### 1. Prerequisites
- **Node.js**: v18.0.0 or higher
- **npm** or **bun** / **yarn**

### 2. Installation
```bash
# Clone the repository
git clone https://github.com/<your-username>/<your-repo-name>.git

# Navigate into the project directory
cd <your-repo-name>

# Install dependencies
npm install
```

### 3. Environment Variables
Copy `.env.example` to `.env` (if applicable) and configure your Firebase credentials or API settings:
```bash
cp .env.example .env
```

### 4. Start Development Server
```bash
npm run dev
```
Open your browser at `http://localhost:3000` to view the application.

### 5. Build for Production
```bash
npm run build
```

---

## 📦 How to Extract / Push This Project to GitHub

### Method A: Download Code from Google AI Studio & Push
1. In the Google AI Studio top-right toolbar, click the **Export** / **Download** icon (or menu `...` -> **Download as ZIP**).
2. Unzip the downloaded file on your computer.
3. Open a terminal / command prompt inside the unzipped folder.
4. Run the following commands:

```bash
# Initialize a Git repository
git init

# Stage all files
git add .

# Create the initial commit
git commit -m "Initial commit: Daily Attendance System"

# Rename default branch to main
git branch -M main

# Link your new GitHub repository (replace with your repo URL)
git remote add origin https://github.com/<your-username>/<your-repo-name>.git

# Push your code to GitHub
git push -u origin main
```

---

## 🛠️ Tech Stack
- **Framework**: React 19 (TypeScript)
- **Bundler & Dev Server**: Vite 6
- **Styling**: Tailwind CSS v4
- **Database & Auth**: Firebase Firestore & Firebase Auth
- **Icons**: Lucide React
- **Visuals & Charts**: Recharts, Canvas Confetti

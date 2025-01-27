# React-Vite-Mobile Setup Guide 🚀

A comprehensive guide for setting up a React project with Vite, including mobile app conversion (Android/iOS) and styling configurations.

## 📚 Table of Contents

- [Prerequisites](#prerequisites)
- [Installation Guide](#installation-guide)
- [Project Structure](#project-structure)
- [Styling Setup](#styling-setup)
- [Mobile Conversion](#mobile-conversion)
- [Build Configuration](#build-configuration)
- [Video Tutorials](#video-tutorials)

## 🛠️ Prerequisites

Before starting, ensure you have the following installed:
- Node.js (latest LTS version)
- npm (comes with Node.js)
- Git
- Android Studio (for Android development)
- Xcode (for iOS development, Mac only)

## 🚀 Installation Guide

### 1. Initial Setup
```bash
npm create vite@latest
cd my-react-app
npm install
```

### 2. Essential Dependencies
```bash
# Routing
npm install react-router-dom

# Icons
npm install @heroicons/react
npm install lucide-react

# Internationalization
npm install i18next react-i18next @tailwindcss/typography

# Backend Integration
npm install firebase

# Animation
npm install framer-motion

# Email Integration
npm install @emailjs/browser
```

## 💻 Project Structure

### Configure Path Aliases
Create `jsconfig.json`:
```json
{
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "@/*": ["src/*"]
    }
  }
}
```

Update `vite.config.js`:
```javascript
import { defineConfig } from 'vite';
import react from '@vitejs/plugin-react';
import path from 'path';

export default defineConfig({
  plugins: [react()],
  resolve: {
    alias: {
      '@': path.resolve(__dirname, 'src')
    }
  }
});
```

## 🎨 Styling Setup

### 1. Install Tailwind CSS
```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

### 2. Configure Tailwind
Update `tailwind.config.js`:
```javascript
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./src/**/*.{js,jsx,ts,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

### 3. Add Tailwind Directives
In `src/index.css`:
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

### 4. Install shadcn/ui Components
```bash
npx shadcn@latest init
npx shadcn@latest add button
```

## 📱 Mobile Conversion

### Setup Capacitor
```bash
npm run build
npm install @capacitor/core
npm install @capacitor/cli --save-dev
npm install @capacitor/android
npm install @capacitor/filesystem
npx cap init
```

### Android Setup
```bash
npx cap add android
npx cap sync
```

### iOS Setup
```bash
npm install @capacitor/ios
npx cap add ios
```

## ⚙️ Build Configuration

For larger builds, update `vite.config.js`:
```javascript
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'

export default defineConfig({
  plugins: [react()],
  assetsInclude: ['**/*.mp4', '**/*.webm', '**/*.ogg'],
  build: {
    chunkSizeWarningLimit: 1000 // Increases warning threshold to 1000kb
  }
})
```

## 🎥 Video Tutorials

For detailed video guides, check out this YouTube playlist:
[React + Vite Setup Tutorial Series](https://www.youtube.com/playlist?list=PLrZbkNpNVSww7Dp0p-20CQiXDo1bqyc4G)

## 📧 Additional Resources

- EmailJS Dashboard: [https://dashboard.emailjs.com/admin/templates](https://dashboard.emailjs.com/admin/templates)

## 🤝 Contributing

Feel free to submit issues and enhancement requests!

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

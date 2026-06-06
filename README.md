# Rydex - Full Stack Ride Booking Platform

A real-time ride booking platform built with Next.js, TypeScript, Node.js, Socket.io, and MongoDB.

🔗 **Live:** https://rydex-theta.vercel.app  
⚡ **Socket Server:** https://socketserver-bgqy.onrender.com  
💻 **GitHub (Frontend):** https://github.com/Lagnadeep-samal/rydex  
💻 **GitHub (Socket Server):** https://github.com/Lagnadeep-samal/SocketServer  

## Features

- 🚗 Book rides with real-time driver location tracking
- 💬 In-app real-time chat between rider and driver
- 📹 Video calling support
- 🔐 Google OAuth authentication via NextAuth.js
- 💳 Razorpay payment gateway integration
- 🤖 Gemini AI API integration
- 📍 Geospatial location queries with MongoDB
- 🌐 Socket.io real-time backend

## Tech Stack

**Frontend:** Next.js 16, TypeScript, Tailwind CSS, Redux  
**Backend:** Node.js, Express, Socket.io  
**Database:** MongoDB Atlas, Mongoose  
**Auth:** NextAuth.js, Google OAuth  
**Storage:** Cloudinary  
**Payments:** Razorpay  
**Deployment:** Vercel (frontend), Render (socket server), MongoDB Atlas (database)

## Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/Lagnadeep-samal/rydex.git
cd rydex
```

### 2. Install dependencies
```bash
npm install
```

### 3. Set up environment variables
Create a `.env.local` file in the root directory:
```env
MONGODB_URL=your_mongodb_url
AUTH_SECRET=your_auth_secret
AUTH_GOOGLE_ID=your_google_client_id
AUTH_GOOGLE_SECRET=your_google_client_secret
EMAIL=your_email
PASS=your_email_password
CLOUDINARY_CLOUD_NAME=your_cloudinary_name
CLOUDINARY_API_KEY=your_cloudinary_key
CLOUDINARY_API_SECRET=your_cloudinary_secret
NEXT_PUBLIC_SOCKET_SERVER_URL=https://socketserver-bgqy.onrender.com
NEXT_PUBLIC_GEOAPIFY_API_KEY=your_geoapify_key
RAZORPAY_KEY_ID=your_razorpay_key
RAZORPAY_KEY_SECRET=your_razorpay_secret
NEXT_PUBLIC_RAZORPAY_KEY_ID=your_razorpay_public_key
GEMINI_API_URL=your_gemini_api_url
NEXTAUTH_URL=http://localhost:3000
```

### 4. Run the development server
```bash
npm run dev -- --webpack
```

Open [http://localhost:3000](http://localhost:3000) to view the app.

## Socket Server Setup

The real-time backend is a separate Node.js/Express/Socket.io service.

### Clone and run locally
```bash
git clone https://github.com/Lagnadeep-samal/SocketServer.git
cd SocketServer
npm install
npm run dev
```

### Socket Server Environment Variables

**Local development** — create a `.env` file:
```env
PORT=8000
MONGODB_URL=your_mongodb_url
NEXT_BASE_URL=http://localhost:3000
```

**Production (Render)** — set these in Render environment variables:
```env
PORT=10000
MONGODB_URL=your_mongodb_url
NEXT_BASE_URL=https://rydex-theta.vercel.app
```

### Socket Server Events
- `identity` — registers user socket ID on connect
- `update-location` — updates driver's live location
- `join-ride` — joins a ride room by booking ID
- `driver-location-update` — broadcasts driver location to rider
- `chat-message` — sends chat message within a ride room
- `disconnect` — clears socket ID and sets user offline

## Deployment

- Frontend deployed on **Vercel** → https://rydex-theta.vercel.app
- Socket server deployed on **Render** → https://socketserver-bgqy.onrender.com
- Database hosted on **MongoDB Atlas**
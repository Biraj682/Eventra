# Eventra - Full-Stack Event Booking Platform

Eventra is a MERN stack event booking platform built for seamless event discovery, user registration, and secure booking workflows. It allows visitors to browse upcoming events, request bookings, and complete the process with OTP-based verification, while admins manage event listings, payments, and booking approvals from a dedicated dashboard.

## Overview

This project combines a React + Tailwind frontend with an Express + MongoDB backend to provide:

- Secure user authentication and role-based access
- Email OTP verification for sensitive actions
- Event creation and management for admins
- Booking request handling with pending approval flow
- Revenue and booking analytics for organizers
- Manual payment verification workflow for paid events

---

## Features

### For Users
- Secure registration and login with JWT-based authentication
- Email OTP verification during registration and booking confirmation
- Browse public event listings and event details
- Submit booking requests for free and paid events
- View personal dashboard with booking status and cancellation options

### For Admins
- Create, update, and delete events
- Manage booking requests from a centralized admin panel
- Approve or reject bookings manually
- Mark bookings as Paid or Not Paid
- Monitor key metrics such as pending requests, revenue, and confirmed paid clients

### Booking Flow
- Events can be free or paid
- All booking requests go through a secure pending queue
- OTP validation is required before a booking is submitted
- Seat capacity is validated to prevent overbooking
- Confirmed bookings trigger email notifications

### Additional Highlights
- Responsive and polished UI built with React and Tailwind CSS
- MongoDB-based data storage for users, events, and bookings
- Nodemailer-powered email notifications
- Clean separation of frontend and backend services

---

## Tech Stack

- Frontend: React, Vite, Tailwind CSS
- Backend: Node.js, Express.js
- Database: MongoDB with Mongoose
- Authentication: JWT + bcryptjs
- Email: Nodemailer
- Dev tooling: Concurrently, Nodemon

---

## Project Structure

```bash
Eventra-MERN/
├── client/
│   ├── src/
│   ├── package.json
│   └── vite.config.js
├── server/
│   ├── controllers/
│   ├── middleware/
│   ├── models/
│   ├── routes/
│   ├── utils/
│   ├── server.js
│   └── package.json
├── package.json
├── README.md
├── SETUP_GUIDE.md
└── Eventra_Postman_Collection.json
```

---

## Prerequisites

Before running the app, make sure you have:

- [Node.js](https://nodejs.org/) installed
- A MongoDB database (for example, [MongoDB Atlas](https://www.mongodb.com/cloud/atlas/register))
- A Gmail account with app-password support for email sending

---

## Environment Variables

Create a file named `.env` inside the `server` folder and add the following values:

```env
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=supersecretjwtkey_Eventra
EMAIL_USER=your_gmail_address
EMAIL_PASS=your_gmail_app_password
PORT=5000
```

> Note: For `EMAIL_PASS`, use a Google App Password. Standard account passwords will not work when 2FA is enabled.

---

## Quick Start

From the project root, run:

```bash
npm install
npm run install:all
npm run dev
```

This will start both the backend and frontend together using `concurrently`.

### Available root scripts

```bash
npm run dev          # starts client and server in parallel
npm run start        # runs production-style frontend preview and backend
npm run build        # builds the frontend for production
npm run install:all  # installs dependencies for server and client
npm run dev:all     # installs dependencies then starts both apps
```

---

## Running Each App Separately

### Backend

```bash
cd server
npm install --legacy-peer-deps
npm run dev
```

The API runs on:

```text
http://localhost:5000
```

### Frontend

```bash
cd client
npm install
npm run dev
```

The frontend runs via Vite, usually at:

```text
http://localhost:5173
```

---

## Notes

- The application is optimized for local development and demo environments.
- Admin access is intended to be restricted to database-flagged users.
- Booking approval and payment status are intentionally manual to support controlled event operations.

---

## License

This project is for educational and portfolio use unless otherwise specified by the repository owner.

---

## Contributing

If you want to extend the project, feel free to fork the repo and submit improvements for:

- booking validation logic
- analytics dashboards
- payment workflows
- UI/UX refinements
- API security enhancements


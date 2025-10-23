# B2B Management System

A full-stack B2B organization management web application built with React, Tailwind CSS, Node.js, Express, and SQLite.

## Features

- View and manage B2B organizations
- Organization details with profile editing
- User management (Admin and Co-ordinator roles)
- Status tracking (Active, Blocked, Inactive)
- Clean, modern UI matching the provided designs

## Tech Stack

**Frontend:**
- React 18
- Tailwind CSS
- React Router
- Vite

**Backend:**
- Node.js
- Express
- SQLite (better-sqlite3)

## Installation

1. Install dependencies for both frontend and backend:
```bash
cd frontend && npm install
cd ../backend && npm install
```

2. Start the backend server (from backend directory):
```bash
cd backend
npm run dev
```

3. Start the frontend development server (from frontend directory):
```bash
cd frontend
npm run dev
```

The application will be available at:
- Frontend: http://localhost:3000
- Backend API: http://localhost:3001

## Database Management

If you need to clean up duplicate users from the database:
```bash
node backend/cleanup-db.js
```

Note: Sample data is only inserted once when the database is first created.

## Project Structure

```
b2b-management/
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── Layout.jsx
│   │   │   ├── AddOrganizationModal.jsx
│   │   │   └── AddUserModal.jsx
│   │   ├── pages/
│   │   │   ├── Dashboard.jsx
│   │   │   ├── Organizations.jsx
│   │   │   └── OrganizationDetails.jsx
│   │   ├── App.jsx
│   │   ├── main.jsx
│   │   └── index.css
│   └── package.json
├── backend/
│   ├── server.js
│   ├── database.js
│   └── package.json
└── README.md
```

## API Endpoints

- `GET /api/organizations` - Get all organizations
- `GET /api/organizations/:id` - Get organization by ID
- `POST /api/organizations` - Create new organization
- `PUT /api/organizations/:id` - Update organization
- `DELETE /api/organizations/:id` - Delete organization
- `GET /api/organizations/:id/users` - Get users for organization
- `POST /api/organizations/:id/users` - Add user to organization
- `DELETE /api/users/:id` - Delete user

## Database Schema

**organizations table:**
- id, name, slug, email, contact, phone, alt_phone, max_coordinators, timezone, region, language, website, logo, status, pending_requests, created_at

**users table:**
- id, organization_id, name, role, created_at

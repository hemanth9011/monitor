# EHBVS Solutions — Employee Management System

Full-stack employee management and workplace activity platform for EHBVS Solutions with attendance, task management, leave management, work reports, notifications, dashboards, and role-based access.

## Overview

This project is a full-stack internal employee management platform for EHBVS Solutions. It supports employee administration, attendance tracking, check-in/check-out workflows, working hours monitoring, task assignment, daily work reports, leave requests, notifications, announcements, admin dashboards, employee dashboards, reports, CSV export, role-based authentication, and audit logging.

## Features

### Admin

- Dashboard
- Employee management
- Attendance monitoring
- Task management
- Work report management
- Leave management
- Announcements
- Notifications
- Reports
- Audit logs

### Employee

- Login
- Dashboard
- Check-in and check-out
- Working hours tracking
- Current status
- Tasks and updates
- Work reports
- Leave requests
- Attendance history
- Notifications
- Profile

## Tech Stack

- Frontend: React + Vite + Tailwind CSS
- Backend: Node.js + Express
- Database: MongoDB + Mongoose
- Authentication: JWT + bcrypt
- CI/CD: GitHub Actions

## Architecture

Frontend

React + Vite + Tailwind CSS

↓

REST API

↓

Node.js + Express

↓

MongoDB + Mongoose

Authentication:

JWT + bcrypt

Admin and employee roles are separated at the API and route level. Admin users manage employees, attendance, tasks, leaves, and reports. Employee users can view and manage only their own authorized records.

## Project Structure

```text
.
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── config/
│   │   ├── pages/
│   │   ├── App.jsx
│   │   ├── main.jsx
│   │   └── index.css
│   ├── package.json
│   ├── vite.config.js
│   ├── tailwind.config.js
│   └── index.html
├── backend/
│   ├── config/
│   ├── middleware/
│   ├── models/
│   ├── routes/
│   ├── scripts/
│   ├── tests/
│   ├── utils/
│   ├── server.js
│   ├── package.json
│   └── README.md
├── docs/
│   ├── architecture.md
│   ├── api.md
│   ├── database.md
│   ├── security.md
│   └── deployment.md
├── .github/
│   ├── ISSUE_TEMPLATE/
│   ├── workflows/
│   ├── dependabot.yml
│   └── PULL_REQUEST_TEMPLATE.md
├── .gitignore
├── .env.example
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── package.json
└── .github/workflows
```

## Installation

Clone the repository:

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
cd ehbvs-employee-management-system
```

Frontend:

```bash
cd frontend
npm install
npm run dev
```

Backend:

```bash
cd backend
npm install
npm run dev
```

## Environment Variables

Create a `.env` file in the backend root based on `.env.example`.

```env
PORT=5000
MONGO_URI=mongodb://localhost:27017/ehbvs
JWT_SECRET=replace-with-a-secure-secret
CLIENT_URL=http://localhost:5173
```

Frontend `.env`:

```env
VITE_API_URL=http://localhost:5000/api
```

## Database Setup

1. Ensure MongoDB is installed and running locally or use MongoDB Atlas.
2. Create a database named `ehbvs`.
3. Update `MONGO_URI` in the backend environment.
4. Use the admin seeding script to create an initial admin user.

```bash
cd backend
npm run seed:admin -- admin@ehbvs.com StrongPass123 "EHBVS Administrator"
```

## Running Locally

Start the backend:

```bash
cd backend
npm run dev
```

Start the frontend:

```bash
cd frontend
npm run dev
```

## API

The API is served under `/api` and includes endpoints for authentication, employee management, attendance, tasks, leaves, notifications, reports, and health checks.

### Health Check

```http
GET /api/health
```

Response:

```json
{
  "status": "ok",
  "service": "EHBVS Employee Management API"
}
```

## Authentication

This platform uses JWT authentication with bcrypt password hashing. Protected routes require a valid bearer token. Role-based authorization prevents employee users from accessing admin-only endpoints.

Employees can only access their own authorized records.

## Security

The platform includes:

- bcrypt password hashing
- JWT authentication
- Protected routes
- Role-based authorization
- Input validation
- CORS configuration
- Environment variables
- Audit logging
- Access restriction for employee records
- No secrets committed to GitHub

The platform does NOT implement:

- Keylogging
- Secret screen recording
- Hidden webcam access
- Hidden microphone access
- Private message inspection
- Undisclosed surveillance

## Testing

Frontend and backend test structures are included. Run backend tests with:

```bash
cd backend
npm test
```

Run frontend lint/build checks:

```bash
cd frontend
npm run build
```

## Deployment

Deployment guidance is included in `docs/deployment.md`. The recommended stack is:

- Frontend: Vercel or Netlify
- Backend: Render, Railway, or a VPS
- Database: MongoDB Atlas

## GitHub Actions

GitHub Actions workflows are configured for frontend and backend validation.

## Roadmap

### Completed

- Authentication and role-based access
- Employee management
- Attendance tracking
- Task management
- Leave management
- Notifications
- Reports
- Dashboard scaffolding
- API documentation

### Planned

- Email notifications
- WhatsApp notifications
- Payroll
- HR management
- Recruitment
- Employee documents
- Mobile application

## Contributing

Please read `CONTRIBUTING.md` before submitting changes.

## License

This project is licensed under the MIT License. See `LICENSE` for details.

## Contact

EHBVS Solutions

---

[Add Screenshot Here]

## Screenshots

- Admin Dashboard: [Add Screenshot Here]
- Employee Dashboard: [Add Screenshot Here]
- Attendance: [Add Screenshot Here]
- Task Management: [Add Screenshot Here]
- Leave Management: [Add Screenshot Here]

## GitHub Setup

```bash
git init
git add .
git commit -m "feat: initial EHBVS employee management system"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/ehbvs-employee-management-system.git
git push -u origin main
```

Do not run push commands unless repository credentials and remote access are available.

## Final Checklist

- [ ] Frontend builds
- [ ] Backend starts
- [ ] MongoDB connection works
- [ ] Login works
- [ ] Employee creation works
- [ ] Attendance works
- [ ] Task management works
- [ ] Leave system works
- [ ] Notifications work
- [ ] Role protection works
- [ ] No secrets committed
- [ ] README complete
- [ ] API documentation complete
- [ ] Deployment documentation complete
- [ ] GitHub Actions configured
- [ ] LICENSE exists
- [ ] CONTRIBUTING.md exists

The repository is structured and documented as a professional company project under the EHBVS Solutions brand.

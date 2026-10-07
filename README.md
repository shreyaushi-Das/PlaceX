# PlaceX — Placement & Career Management Platform

<p align="center">
  <b>A modern placement management platform connecting Students, Recruiters, Alumni, and TPO/Admin.</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Frontend-React%20%2B%20TypeScript-blue" alt="Frontend" />
  <img src="https://img.shields.io/badge/Build-Vite-purple" alt="Build" />
  <img src="https://img.shields.io/badge/Styling-Tailwind%20CSS-38B2AC" alt="Styling" />
  <img src="https://img.shields.io/badge/Status-Active%20Development-orange" alt="Status" />
</p>

---

## 📌 Overview

**PlaceX** is a placement and career management platform designed to streamline interaction between:

- 🎓 Students
- 🏢 Recruiters
- 👨‍🎓 Alumni
- 🧑‍💼 TPO / Placement Administration

The platform provides a centralized environment for managing placement drives, job opportunities, applications, student profiles, alumni experiences, referrals, and placement-related activities.

The frontend is developed using **React, TypeScript, Vite, and Tailwind CSS**.

> ⚠️ **Backend Status:** The backend is currently under active development in a private repository. AWS deployment is in progress.

---

## ✨ Key Features

### 🎓 Student Portal

Students can:

- View available placement drives
- Explore job opportunities
- Apply for eligible jobs
- Track application status
- Manage their profile
- Access the Alumni Corner
- Read published alumni blogs
- Browse active alumni referrals
- Connect with alumni through LinkedIn/email
- Access interview and career-related features

#### Application Tracking

Applications can move through stages such as:

```text
Applied
   ↓
Shortlisted
   ↓
Round 1
   ↓
Round 2
   ↓
HR Round
   ↓
Selected / Rejected
```

---

### 🏢 Recruiter Portal

Recruiters can:

- Register on the platform
- Manage their recruiter profile
- Create job postings
- Specify recruitment type
- Manage job opportunities
- View relevant application information

**Recruitment Types**

- `CAMPUS`
- `OFF_CAMPUS`

**Job Sources**

- `RECRUITER`
- `DATASET`

---

### 👨‍🎓 Alumni Portal

The Alumni module allows approved alumni to contribute to the student community.

**Alumni Features**

- Alumni Dashboard
- Write Blog
- Manage My Blogs
- Offer Referral
- Manage Referrals
- Alumni Profile / Settings

#### Alumni Registration

New alumni registrations require TPO approval.

```text
Alumni Registration
        ↓
     PENDING
        ↓
    TPO Review
        ↓
   ┌────┴────┐
   ↓         ↓
APPROVED   REJECTED
   ↓
Alumni Access
```

#### Alumni Blogs

Alumni can:

- Create blogs
- Save blogs as drafts
- Publish blogs
- Edit their own blogs
- Delete their own blogs

Supported categories:

- Interview Experience
- Career Advice
- Referral Tips
- General

> Only published blogs are displayed to students through the Alumni Corner.

#### Alumni Referrals

Alumni can post referral opportunities containing:

- Company
- Job role
- Description
- Active/inactive status
- Alumni contact information

Students can browse active referrals and connect with alumni through available LinkedIn/email information.

---

### 🧑‍💼 TPO / Admin Portal

The TPO/Admin module provides administrative control over the placement platform.

Features include:

- Student management
- Recruiter management
- Placement/job management
- Application management
- Alumni management
- Alumni approval/rejection
- Placement activity monitoring

#### Alumni Management

```text
View Pending Alumni
        ↓
  Approve / Reject
        ↓
Manage Approved Alumni
```

---

## 🏗️ System Architecture

PlaceX follows a client-server architecture.

```text
                ┌─────────────────────────┐
                │         PlaceX          │
                │        Frontend         │
                │                         │
                │   React + TypeScript    │
                │   Vite + Tailwind CSS   │
                └────────────┬────────────┘
                             │
                             │ REST APIs
                             │
                             ▼
                ┌─────────────────────────┐
                │         Backend         │
                │                         │
                │       Spring Boot       │
                │                         │
                │    Private Repository   │
                │    Active Development   │
                └────────────┬────────────┘
                             │
                             ▼
                ┌─────────────────────────┐
                │        Database         │
                │       PostgreSQL        │
                └─────────────────────────┘
```

### Architecture Diagram

Place the project architecture image inside `screenshots/architecture.png`, and it will be displayed here:

<img width="1460" height="1252" alt="IMG-20260927-WA0096 jpg" src="https://github.com/user-attachments/assets/cdc48bde-8cf0-4a2c-93aa-665700ebd539" />
<img width="1600" height="1503" alt="IMG-20260926-WA0054 jpg" src="https://github.com/user-attachments/assets/9764d7d4-6a16-446b-8080-22dc2f578691" />
<img width="1072" height="827" alt="IMG-20260926-WA0034 jpg" src="https://github.com/user-attachments/assets/f1426cb6-3b22-4701-b5c6-19abd466583d" />
<img width="1101" height="847" alt="IMG-20260926-WA0048 jpg" src="https://github.com/user-attachments/assets/22a672e3-f4f7-434e-836a-b09987308691" />


---

## 🔐 Authentication & API Security

The application communicates with the backend through REST APIs.

- Public endpoints include authentication and registration-related APIs.
- Protected APIs require an authenticated request using:

```http
Authorization: Bearer <JWT_TOKEN>
```

The frontend API layer is designed to communicate with protected backend resources using Bearer token authentication.

---

## 🛠️ Technology Stack

### Frontend

| Technology   | Purpose                  |
| ------------ | ------------------------ |
| React        | UI development           |
| TypeScript   | Type-safe development    |
| Vite         | Frontend build tool      |
| Tailwind CSS | Styling                  |
| React Router | Client-side routing      |
| Lucide React | Icons                    |
| Fetch API    | REST API communication   |

### Backend

The backend is maintained separately in a private repository.

Planned/active backend technologies include:

- Spring Boot
- REST APIs
- PostgreSQL
- JWT Authentication

Backend development and AWS deployment are currently in progress.

---

## 📁 Frontend Project Structure

```text
PlaceX/
│
├── public/
│
├── screenshots/
│   ├── architecture.png
│   ├── authentication.png
│   ├── student-dashboard.png
│   ├── placement-drives.png
│   ├── application-tracker.png
│   ├── alumni-dashboard.png
│   ├── alumni-blog.png
│   ├── alumni-referrals.png
│   └── admin-dashboard.png
│
├── src/
│   │
│   ├── api/
│   │   ├── alumniApi.ts
│   │   ├── companyApi.ts
│   │   ├── jobPostingApi.ts
│   │   └── ...
│   │
│   ├── components/
│   │   ├── admin/
│   │   ├── student/
│   │   ├── AlumniPortal.tsx
│   │   ├── Auth.tsx
│   │   ├── AdminPortal.tsx
│   │   └── ...
│   │
│   ├── App.tsx
│   ├── main.tsx
│   └── ...
│
├── package.json
├── vite.config.ts
├── tsconfig.json
└── README.md
```

---

## 🖥️ Screenshots

### 🔐 Authentication
<img width="1920" height="1080" alt="Screenshot from 2026-10-08 00-13-09" src="https://github.com/user-attachments/assets/cfbd3b3c-d7fc-4b9c-b047-07c30db6765e" />


### 🎓 Student Dashboard
<img width="1920" height="1080" alt="Screenshot from 2026-10-08 00-13-45" src="https://github.com/user-attachments/assets/46b5f5ba-1913-465c-9932-d7f6f529da9a" />


### 💼 Placement Drives

<img width="1920" height="1080" alt="Screenshot from 2026-10-08 00-14-03" src="https://github.com/user-attachments/assets/5f7da906-9d8e-44ac-b312-88931169ff57" />


### 📊 Application Tracker

<img width="1920" height="1080" alt="Screenshot from 2026-10-08 00-14-25" src="https://github.com/user-attachments/assets/95f44509-4d81-41dc-81d2-7d24efc0634f" />


### 👨‍🎓 Alumni Dashboard
<img width="1920" height="1080" alt="Screenshot from 2026-10-08 00-14-54" src="https://github.com/user-attachments/assets/e8e87034-ae5e-4e99-855f-6bcd55a488ca" />


### ✍️ Alumni Blog

<img width="1920" height="1080" alt="Screenshot from 2026-10-08 00-15-17" src="https://github.com/user-attachments/assets/8fbf76b2-7a8f-42e4-9ed9-0539321c1190" />



### 🧑‍💼 TPO / Admin Dashboard

<img width="1920" height="1080" alt="Screenshot from 2026-10-08 00-15-51" src="https://github.com/user-attachments/assets/5a13e85a-bf7e-44e2-b3a7-b916762b60aa" />


---

## 🚀 Getting Started

### Prerequisites

Make sure the following are installed:

- Node.js
- npm
- Git

### Clone the Repository

```bash
git clone <FRONTEND_REPOSITORY_URL>
```

Navigate to the project:

```bash
cd PlaceX
```

### Install Dependencies

```bash
npm install
```

### Environment Variables

Create a `.env` file in the root directory:

```env
VITE_API_BASE_URL=http://localhost:8080
```

For production, this value will point to the deployed backend API.

### Run Development Server

```bash
npm run dev
```

The frontend will normally be available at:

```text
http://localhost:5173
```

### Build for Production

```bash
npm run build
```

### Preview Production Build

```bash
npm run preview
```

---

## 🔗 API Integration

The frontend communicates with the backend through REST APIs.

```text
Frontend
   ↓
API Service Layer
   ↓
HTTP Request
   ↓
Spring Boot Backend
   ↓
PostgreSQL
```

Protected API requests use:

```http
Authorization: Bearer <JWT_TOKEN>
```

The backend is maintained separately in a private repository.

---

## 📌 Current Development Status

| Module                | Status         |
| --------------------- | -------------- |
| Authentication UI     | 🟢 Implemented |
| Student Portal        | 🟢 Implemented |
| Recruiter Portal      | 🟢 Implemented |
| TPO/Admin Portal      | 🟢 Implemented |
| Alumni Portal         | 🟢 Implemented |
| Alumni Blogs          | 🟢 Implemented |
| Alumni Referrals      | 🟢 Implemented |
| Student Alumni Corner | 🟢 Implemented |
| Backend Integration   | 🟡 In Progress |
| Backend Deployment    | 🟡 In Progress |
| AWS Deployment        | 🟡 In Progress |

**Status Legend**

- 🟢 Implemented
- 🟡 In Progress
- 🔴 Not Started

---

## 🔮 Future Enhancements

Planned improvements include:

- Complete production backend integration
- AWS deployment
- Advanced authentication and authorization
- Email notifications
- Placement analytics
- AI-powered career assistance
- Improved alumni-student interaction
- Recruiter analytics
- Real-time notifications
- Production monitoring and logging

---

## 👥 Team

PlaceX is being developed collaboratively as a team project.

| Area       | Technologies                                  |
| ---------- | --------------------------------------------- |
| Frontend   | React, TypeScript, Vite, Tailwind CSS         |
| Backend    | Spring Boot, REST APIs, PostgreSQL, JWT Auth  |
| Deployment | AWS                                           |

---

## 📄 Project Status

PlaceX is currently under active development.

The frontend repository contains the frontend implementation, UI components, routing, API integration layer, and role-based portal interfaces.

- **Backend:** Under active development — Private Repository
- **Deployment:** AWS deployment in progress

---

## ⭐ Acknowledgement

Built as a collaborative placement and career management platform to simplify and modernize interaction between students, recruiters, alumni, and placement administration.

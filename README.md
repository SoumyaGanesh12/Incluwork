# IncluWork

[Demo Video](Demo.mp4)

IncluWork is a full-stack web application that connects differently abled job seekers with inclusive employers. The platform facilitates accessible employment by matching job seeker skills and accommodation needs with employer-provided facilities. Admin verification ensures the authenticity of disability proofs before applications are processed.

## Users

| Role | Description |
|------|-------------|
| **Job Seeker** | Creates a profile, uploads a resume and disability proof, searches and applies for jobs |
| **Employer** | Posts job listings with accessibility accommodations, reviews candidates, receives an inclusivity rating |
| **Admin** | Verifies job seeker disability proofs, manages users and applications |

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | React 18 + TypeScript, Vite, Redux Toolkit, Material-UI, i18next |
| Backend | Node.js, Express.js |
| Database | MongoDB (Mongoose) |
| Auth | Passport.js (Local + JWT strategies), bcrypt |
| File Uploads | Multer |

## Features

- **Role-based access** - Separate dashboards and permissions for Job Seekers, Employers, and Admins
- **Job matching** - Jobs tagged with accessibility features and required skills; seekers filtered by challenges and skills
- **Document uploads** - Resume and medical proof uploaded and verified before application completion
- **Application tracking** - Full status lifecycle: `applied → offered → accepted / rejected / withdrawn`
- **Inclusivity rating** - Employers rated based on hiring actions
- **Multilingual support** - English and Hindi via i18next

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) v18+
- [MongoDB](https://www.mongodb.com/) (local instance or Atlas connection string)

### Backend

```bash
cd incluwork-service
npm install
```

Create a `.env` file in `incluwork-service/`:

```env
MONGO_CONNECTION=mongodb://localhost:27017/incluwork
```

Then start the server:

```bash
npm start
```

The API will be available at `http://localhost:3000/incluwork`.

### Frontend

```bash
cd incluwork-app
npm install
npm run dev
```

The app will be available at `http://localhost:5173`.

## Documentation

- [Object Model](docs/object-model.md) - Class diagram with entities, relationships, and cardinality
- [API Spec](docs/jobportal-api.yml) - Full REST API reference (Swagger / OpenAPI)

## REST API - User Stories

### Job Seeker

| User Story | Method | Endpoint |
|------------|--------|----------|
| Create my profile | POST | `/jobseekers` |
| View my profile | GET | `/jobseekers/{userID}` |
| Update my profile | PUT | `/jobseekers/{userID}` |
| Delete my profile | DELETE | `/jobseekers/{userID}` |
| View all my applications | GET | `/jobseekers/{userID}/applications` |
| Apply for a job | POST | `/jobapplications` |
| Withdraw an application | DELETE | `/jobapplications/{applicationID}` |

### Employer

| User Story | Method | Endpoint |
|------------|--------|----------|
| Create company profile | POST | `/employers` |
| View a company profile | GET | `/employers/{employerID}` |
| Update company profile | PUT | `/employers/{userID}` |
| Post a job listing | POST | `/jobs` |
| View all job listings | GET | `/jobs` |
| Edit a job listing | PUT | `/jobs/{jobID}` |

### Admin

| User Story | Method | Endpoint |
|------------|--------|----------|
| Create user accounts and assign roles | POST | `/admin/users` |
| View all users | GET | `/admin/users` |
| Delete a user profile | DELETE | `/admin/users/{userID}` |
| View all job applications | GET | `/jobapplications` |
| Update application status | PUT | `/admin/jobapplications/{applicationID}` |

### Reviews

| User Story | Method | Endpoint |
|------------|--------|----------|
| Create a review for an employer | POST | `/reviews` |
| Delete a review | DELETE | `/reviews/{reviewID}` |

## Global Impact

IncluWork directly addresses employment inequality for differently abled individuals, aligning with the UN's initiatives for equal opportunities and human rights. By connecting job seekers with inclusive employers, the platform promotes diversity and accessibility in the workforce.

# Job Portal - Full Stack Application

A modern job portal application built with React and Node.js. Browse jobs, apply for positions, and manage your career seamlessly.

**Live Demo:** [https://job-portal-tau-sepia.vercel.app](https://job-portal-tau-sepia.vercel.app)

## 🏗️ Architecture Overview

```
┌─────────────────────────────────────────────────────┐
│    Frontend (React 19 + TypeScript + Vite)          │
│    - Job Browsing & Filtering                       │
│    - User Profiles & Applications                   │
│    - Google OAuth Authentication                    │
└────────────────────┬────────────────────────────────┘
                     │ (Axios HTTP Requests)
┌────────────────────▼────────────────────────────────┐
│    Backend (Node.js + Express + TypeScript)        │
│    - User Management & Authentication               │
│    - Job Listings & Applications                    │
│    - Payment Processing (Razorpay)                  │
└────────────────────┬────────────────────────────────┘
                     │
┌────────────────────▼────────────────────────────────┐
│        MongoDB Database                             │
│        - User Data                                  │
│        - Job Listings                               │
│        - Applications & Transactions                │
└─────────────────────────────────────────────────────┘
```

## 🚀 Tech Stack

### Frontend
- **React 19** - UI library with latest features
- **TypeScript** - Type safety and better DX
- **Vite** - Lightning fast build tool with HMR
- **Tailwind CSS** - Utility-first CSS framework
- **React Router v7** - Client-side routing
- **Axios** - HTTP client for API calls
- **Google OAuth** - Secure authentication via Google
- **React Hot Toast** - Toast notifications
- **jsPDF** - PDF generation for resumes
- **Lucide React** - Beautiful icon library

### Backend
- **Node.js** - JavaScript runtime
- **Express.js v5** - Web application framework
- **TypeScript** - Type-safe backend development
- **Mongoose** - MongoDB object modeling
- **JWT** - JSON Web Token authentication
- **Razorpay** - Payment gateway integration
- **Google APIs** - Google services integration (@google/genai, googleapis)
- **Axios** - HTTP client for external APIs
- **CORS** - Cross-origin request handling
- **dotenv** - Environment variable management

### Database
- **MongoDB** - NoSQL database for flexible data storage

## 📋 Features

- 🔐 **Google OAuth Authentication** - One-click login with Google
- 💼 **Job Listings** - Browse and filter job opportunities
- 📝 **Job Applications** - Apply for jobs and track applications
- 👤 **User Profiles** - Create and manage user profiles
- 💳 **Secure Payments** - Razorpay integration for transactions
- 🔔 **Toast Notifications** - Real-time user feedback
- 📄 **PDF Resume Generation** - Generate and download resumes as PDF
- 🎯 **Advanced Filtering** - Filter jobs by role, salary, location, etc.
- 📱 **Responsive Design** - Works seamlessly on all devices
- ⚡ **Fast Development** - Vite with HMR for instant feedback

## 🛠️ Setup & Installation

### Prerequisites
- Node.js 18+
- npm or yarn
- MongoDB (local or cloud)
- Git

### Clone Repository
```bash
git clone https://github.com/dev-chandan-pandey/Job-Portal.git
cd Job-Portal
```

### Frontend Setup

```bash
cd frontend

# Install dependencies
npm install

# Start development server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview

# Lint code
npm run lint
```

Frontend runs on `http://localhost:5173`

### Backend Setup

```bash
cd backend

# Install dependencies
npm install

# Build TypeScript
npm run build

# Start development server (with watch mode)
npm run dev

# Start production server
npm start
```

Backend runs on `http://localhost:3000` (or configured PORT)

## 🔧 Environment Variables

### Frontend (.env.local)
```env
VITE_API_URL=http://localhost:3000
VITE_GOOGLE_CLIENT_ID=your_google_client_id_here
```

### Backend (.env)
```env
PORT=3000
NODE_ENV=development
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
GOOGLE_CLIENT_ID=your_google_client_id
RAZORPAY_KEY_ID=your_razorpay_key_id
RAZORPAY_KEY_SECRET=your_razorpay_secret_key
CORS_ORIGIN=http://localhost:5173
```

## 📦 Project Structure

```
Job-Portal/
├── frontend/                  # React frontend application
│   ├── src/
│   │   ├── components/       # Reusable React components
│   │   ├── pages/            # Page components
│   │   ├── hooks/            # Custom React hooks
│   │   ├── services/         # API service calls
│   │   ├── types/            # TypeScript type definitions
│   │   ├── App.tsx           # Root component
│   │   └── main.tsx          # Entry point
│   ├── public/               # Static assets
│   ├── package.json
│   ├── tsconfig.json
│   ├── vite.config.ts
│   ├── tailwind.config.ts
│   └── eslint.config.js
│
├── backend/                   # Node.js/Express backend
│   ├── src/
│   │   ├── controllers/      # Request handlers
│   │   ├── models/           # Mongoose database models
│   │   ├── routes/           # API route definitions
│   │   ├── middleware/       # Express middleware
│   │   ├── services/         # Business logic
│   │   ├── types/            # TypeScript interfaces
│   │   └── index.ts          # Application entry point
│   ├── dist/                 # Compiled JavaScript output
│   ├── package.json
│   ├── tsconfig.json
│   └── .env
│
└── README.md
```

## 🔄 API Endpoints

### Authentication
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login with Google OAuth
- `POST /api/auth/logout` - User logout
- `GET /api/auth/profile` - Get current user profile

### Jobs
- `GET /api/jobs` - Get all jobs with filtering
- `GET /api/jobs/:id` - Get specific job details
- `POST /api/jobs` - Create new job (admin)
- `PUT /api/jobs/:id` - Update job details (admin)
- `DELETE /api/jobs/:id` - Delete job (admin)

### Applications
- `GET /api/applications` - Get user's applications
- `POST /api/applications` - Submit job application
- `GET /api/applications/:id` - Get application details
- `PUT /api/applications/:id` - Update application status

### Payments
- `POST /api/payments/create-order` - Create Razorpay order
- `POST /api/payments/verify` - Verify payment completion

## 🧪 Code Quality

```bash
# Frontend linting
cd frontend
npm run lint

# Backend linting (if configured)
cd backend
npm run lint
```

## 🚀 Deployment

### Frontend (Vercel)
1. Connect GitHub repository to Vercel
2. Configure environment variables in Vercel dashboard
3. Automatic deployment on push to main branch

### Backend Deployment Options
- **Railway.app** - Easy Node.js hosting
- **Heroku** - PaaS platform
- **AWS EC2** - Full control server
- **Render** - Modern deployment platform
- **DigitalOcean** - VPS hosting

## 📝 Git Workflow

```bash
# Create feature branch
git checkout -b feature/your-feature-name

# Make changes and commit
git add .
git commit -m "feat: description of changes"

# Push to repository
git push origin feature/your-feature-name

# Create Pull Request
```

## 🐛 Troubleshooting

### CORS Errors
- Verify `CORS_ORIGIN` in backend .env matches frontend URL
- Check Express CORS middleware configuration

### MongoDB Connection Issues
- Verify `MONGODB_URI` is correct in .env
- Ensure IP address is whitelisted (if using MongoDB Atlas)
- Check MongoDB service is running

### Google OAuth Issues
- Verify `VITE_GOOGLE_CLIENT_ID` in frontend .env
- Ensure OAuth credentials are created in Google Cloud Console
- Check redirect URIs are configured correctly

### Port Already in Use
```bash
# Find process on port
lsof -i :3000    # Backend
lsof -i :5173    # Frontend

# Kill process
kill -9 <PID>
```

## 🤝 Contributing

1. Fork the repository
2. Create feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'feat: Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the ISC License.

## 👨‍💼 Author

**Chandan Pandey**
- GitHub: [@dev-chandan-pandey](https://github.com/dev-chandan-pandey)
- Portfolio: [Visit](https://job-portal-tau-sepia.vercel.app)

## 📞 Support

For issues and questions, open an issue on the [GitHub repository](https://github.com/dev-chandan-pandey/Job-Portal/issues).

---

**Built with ❤️ using React, Node.js, and TypeScript**

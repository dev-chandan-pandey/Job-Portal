# 🚀 CareerPathEasy AI - AI-Powered Career SaaS Platform

An intelligent full-stack job portal with Google Gemini AI integration for resume analysis, job matching, and interview preparation.

**🌐 Live Demo:** [https://job-portal-tau-sepia.vercel.app](https://job-portal-tau-sepia.vercel.app)

---

## ✨ Key AI Features

- **AI Resume Analyzer** - Score resumes (0-100) with AI recommendations
- **AI Resume Builder** - Generate professional resumes with AI suggestions
- **AI Job Matcher** - Intelligent job recommendations based on profile
- **Interview Question Generator** - AI-generated interview prep questions
- **ATS Resume Scorer** - Optimize resumes for Applicant Tracking Systems
- **PDF Resume Parser** - Smart extraction from PDF files

---

## 🛠️ Tech Stack

**Frontend:** React 19 | TypeScript | Vite | Tailwind CSS | React Router | Axios | jsPDF | Google OAuth

**Backend:** Node.js | Express.js | MongoDB | Mongoose | JWT | Google Gemini API | Razorpay | CORS

**Services:** MongoDB Atlas | Vercel (Frontend) | Railway/Heroku (Backend) | Google Cloud | Razorpay

---

## 📋 Features

### Core Features
- ✅ Browse and filter job listings
- ✅ Apply for jobs with one-click submission
- ✅ User profiles and resume management
- ✅ Save/bookmark favorite jobs
- ✅ Application tracking dashboard

### AI-Powered
- ✅ AI resume analysis with scoring
- ✅ AI-powered job recommendations
- ✅ Interview prep with AI questions
- ✅ Resume optimization suggestions
- ✅ Cover letter generation

### Payment & Auth
- ✅ Razorpay subscriptions (Free/Pro/Premium)
- ✅ JWT + Google OAuth 2.0 authentication
- ✅ Role-based access control
- ✅ Secure payment processing

### UI/UX
- ✅ Responsive design (mobile-first)
- ✅ Dark mode support
- ✅ Real-time notifications
- ✅ Accessibility compliant (WCAG)

---

## ⚙️ Setup & Installation

### Prerequisites
```
Node.js 18+ | npm 9+ | MongoDB | Google Gemini API Key | Razorpay Account
```

### Frontend Setup
```bash
cd frontend
npm install
cp .env.example .env.local
# Add VITE_API_URL and VITE_GOOGLE_CLIENT_ID
npm run dev
```

**Runs on:** `http://localhost:5173`

### Backend Setup
```bash
cd backend
npm install
cp .env.example .env
# Add all environment variables (see below)
npm run build
npm run dev
```

**Runs on:** `http://localhost:3000`

---

## 🔧 Environment Variables

### Frontend (.env.local)
```env
VITE_API_URL=http://localhost:3000
VITE_GOOGLE_CLIENT_ID=your_google_client_id
VITE_ENABLE_AI_FEATURES=true
VITE_ENABLE_PAYMENTS=true
```

### Backend (.env)
```env
PORT=3000
NODE_ENV=development
MONGODB_URI=mongodb+srv://user:pass@cluster.mongodb.net/careerpatheasai
JWT_SECRET=your_super_secret_key
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_secret
GOOGLE_AI_API_KEY=your_gemini_api_key
RAZORPAY_KEY_ID=your_razorpay_key_id
RAZORPAY_KEY_SECRET=your_razorpay_secret
CORS_ORIGIN=http://localhost:5173
```

### Getting Credentials
- **Google Gemini API:** [makersuite.google.com/app/apikey](https://makersuite.google.com/app/apikey)
- **Google OAuth:** [Google Cloud Console](https://console.cloud.google.com)
- **Razorpay:** [Dashboard Settings → API Keys](https://razorpay.com)
- **MongoDB:** [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)

---

## 📦 Project Structure

```
CareerPathEasyAi/
├── frontend/                    # React frontend
│   ├── src/
│   │   ├── components/         # Reusable components
│   │   ├── pages/              # Page components
│   │   ├── services/           # API calls
│   │   ├── hooks/              # Custom hooks
│   │   ├── context/            # React Context
│   │   ├── types/              # TypeScript types
│   │   └── utils/              # Helper functions
│   ├── package.json
│   ├── vite.config.ts
│   └── .env.example
│
├── backend/                     # Node.js backend
│   ├── src/
│   │   ├── controllers/        # Request handlers
│   │   ├── models/             # MongoDB schemas
│   │   ├── routes/             # API routes
│   │   ├── services/           # Business logic
│   │   ├── middleware/         # Express middleware
│   │   └── utils/              # Helper functions
│   ├── package.json
│   ├── tsconfig.json
│   └── .env.example
│
└── README.md
```

---

## 🔄 API Endpoints

### Authentication
```
POST   /api/auth/register       Register user
POST   /api/auth/login          Login with email/password
POST   /api/auth/google         Google OAuth login
POST   /api/auth/logout         Logout
GET    /api/auth/profile        Get current user
```

### Jobs
```
GET    /api/jobs                Get all jobs with filters
GET    /api/jobs/:id            Get job details
POST   /api/jobs                Create job (admin)
PUT    /api/jobs/:id            Update job
DELETE /api/jobs/:id            Delete job
GET    /api/jobs/search         Search jobs by keyword
```

### AI Features
```
POST   /api/ai/analyze-resume        Resume analysis with scoring
POST   /api/ai/build-resume          Resume builder suggestions
POST   /api/ai/match-jobs            Job recommendations
POST   /api/ai/generate-questions    Interview questions
POST   /api/ai/score-ats             ATS scoring
POST   /api/ai/parse-resume          PDF resume parsing
```

### Resumes
```
POST   /api/resumes/upload      Upload resume
GET    /api/resumes             Get all resumes
GET    /api/resumes/:id         Get resume
DELETE /api/resumes/:id         Delete resume
```

### Subscriptions
```
GET    /api/subscriptions/plans         Get subscription plans
POST   /api/subscriptions/create-order  Create order
POST   /api/subscriptions/verify        Verify payment
GET    /api/subscriptions/current       Get current plan
```

### Applications
```
GET    /api/applications        Get user applications
POST   /api/applications        Submit application
GET    /api/applications/:id    Get application details
PUT    /api/applications/:id    Update status
```

---

## 💳 Razorpay Subscription Plans

```
Free Plan
├─ Basic job search
├─ 1 resume upload
└─ Limited AI features

Pro Plan ($499/month)
├─ Unlimited job search
├─ Unlimited resumes
├─ Unlimited AI analysis
├─ Resume builder
└─ Job matcher

Premium Plan ($999/month)
├─ All Pro features
├─ Priority support
├─ Advanced analytics
└─ Career coaching
```

---

## 🚀 Deployment

### Frontend (Vercel)
```bash
git push origin main
# Connect repo to Vercel dashboard
# Set environment variables
# Auto-deploys on push
```

### Backend Options

**Railway.app (Recommended)**
```bash
npm install -g railway
railway login
railway init
railway up
```

**Heroku**
```bash
heroku login
heroku create your-app-name
heroku config:set MONGODB_URI="..."
git push heroku main
```

**AWS/DigitalOcean/Render** - Standard Node.js deployment

---

## 🧪 Code Quality

```bash
# Frontend linting
cd frontend && npm run lint

# Type checking
tsc --noEmit

# Backend linting (if configured)
cd backend && npm run lint
```

---

## 🐛 Troubleshooting

| Issue | Solution |
|-------|----------|
| **AI features not working** | Verify GOOGLE_AI_API_KEY in .env and check API quota |
| **CORS errors** | Ensure CORS_ORIGIN matches frontend URL in backend .env |
| **MongoDB connection fails** | Check MONGODB_URI and IP whitelist in MongoDB Atlas |
| **Razorpay payment errors** | Verify Razorpay keys and webhook URL configuration |
| **Port already in use** | `lsof -i :3000` and `kill -9 <PID>` to free port |

---

## 🤝 Contributing

1. Fork the repository
2. Create feature branch: `git checkout -b feature/your-feature`
3. Commit: `git commit -m "feat: add your feature"`
4. Push: `git push origin feature/your-feature`
5. Create Pull Request

---

## 📄 License

ISC License - See LICENSE file for details

---

## 👨‍💼 Author

**Chandan Pandey**
- GitHub: [@dev-chandan-pandey](https://github.com/dev-chandan-pandey)
- Email: dev.chandan.pandey@gmail.com
- Portfolio: [CareerPathEasy AI](https://job-portal-tau-sepia.vercel.app)

---

## 📞 Support

- 🐛 [GitHub Issues](https://github.com/dev-chandan-pandey/CareerPathEasyAi/issues)
- 💬 [GitHub Discussions](https://github.com/dev-chandan-pandey/CareerPathEasyAi/discussions)
- 🌐 [Live Demo](https://job-portal-tau-sepia.vercel.app)

---

**Built with ❤️ using MERN Stack, TypeScript, and Google Gemini AI** 🚀

**Status:** ✅ Production Ready | Last Updated: June 7, 2026 | Version: 1.0.0

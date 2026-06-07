# 🚀 CareerPathEasy AI - AI-Powered Career SaaS Platform

A complete full-stack AI-powered Career SaaS platform built with **MERN Stack**, **TypeScript**, **Google Gemini APIs**, and **Razorpay** subscriptions. This platform empowers users to optimize their careers with intelligent AI-driven tools for resume enhancement, job matching, and interview preparation.

**🌐 Live Demo:** [https://job-portal-tau-sepia.vercel.app](https://job-portal-tau-sepia.vercel.app)

---

## 📑 Table of Contents

- [✨ Key AI Features](#-key-ai-features)
- [🏗️ Architecture Overview](#-architecture-overview)
- [🛠️ Complete Tech Stack](#-complete-tech-stack)
- [📋 Comprehensive Features](#-comprehensive-features)
- [⚙️ Setup & Installation](#-setup--installation)
- [🔧 Environment Configuration](#-environment-configuration)
- [📦 Project Structure](#-project-structure)
- [🔄 API Endpoints](#-api-endpoints)
- [💳 Payment Integration](#-payment-integration)
- [🚀 Deployment Guide](#-deployment-guide)
- [🧪 Testing & Quality](#-testing--quality)
- [🐛 Troubleshooting](#-troubleshooting)
- [🤝 Contributing](#-contributing)
- [📄 License](#-license)
- [👨‍💼 Author](#-author)

---

## ✨ Key AI Features

### 🤖 **AI Resume Analyzer**
- Advanced AI-powered resume analysis using Google Gemini API
- Detailed scoring based on:
  - Content quality and relevance
  - Grammar and language optimization
  - Keyword optimization for ATS
  - Structure and formatting evaluation
  - Experience and skills alignment
- AI-generated recommendations for improvement
- Score-based feedback (0-100)
- Industry-specific scoring criteria

### 🔨 **AI Resume Builder**
- Intelligent resume creation assistant using Gemini AI
- AI-generated content suggestions for:
  - Professional summaries
  - Job descriptions with action verbs
  - Skills extraction and optimization
  - Achievement highlighting
- Multiple resume templates
- Real-time preview
- PDF export functionality
- Version control and history

### 🎯 **AI Job Matcher / Finder**
- Intelligent job recommendation engine
- AI analyzes your profile and suggests matching jobs
- Matching algorithm considers:
  - Skills alignment
  - Experience level compatibility
  - Salary expectations
  - Location preferences
  - Career goals and interests
- Match percentage scoring
- Personalized job discovery feed
- Smart job alerts based on matches

### 🎤 **AI Interview Question Generator**
- Generates relevant interview questions using Gemini AI
- Features:
  - Job-specific technical questions
  - Behavioral interview questions
  - Role-appropriate difficulty levels
  - Answer frameworks and tips
  - Follow-up question suggestions
  - STAR method guidance
- Practice mode with real-time feedback
- Question difficulty levels
- Recording and playback capability

### 📊 **ATS Resume Scoring**
- Applicant Tracking System (ATS) optimization score
- Analyzes:
  - Keyword relevance for job descriptions
  - Formatting compatibility with ATS systems
  - Section completeness
  - Skills and experience prominence
  - Contact information optimization
- ATS-specific recommendations
- Formatting suggestions
- Keyword comparison with job postings
- Score improvements tracking

### 📄 **PDF Resume Upload & Parsing**
- Smart PDF resume parser
- Automatically extracts:
  - Personal information
  - Work experience
  - Education details
  - Skills and certifications
  - Contact information
- AI-powered data extraction
- Manual editing for accuracy
- Support for multiple resume formats
- Batch processing capability

### 🔐 **Authentication System**
- Secure JWT-based authentication
- Google OAuth 2.0 integration
- Email/password registration and login
- Token refresh mechanism
- Session management
- Secure password hashing with bcrypt
- Two-factor authentication ready
- Role-based access control (User, Recruiter, Admin)

### 💳 **Razorpay Subscription System**
- Multiple subscription tiers (Free, Pro, Premium)
- Features per tier:
  - **Free:** Limited AI features
  - **Pro:** Full AI tools, unlimited analysis
  - **Premium:** All features + priority support
- Secure payment processing
- Subscription management dashboard
- Invoice generation
- Payment history tracking
- Easy subscription cancellation
- Automatic billing and renewal
- Multiple payment methods (cards, UPI, net banking)

### 🎨 **Modern UI with Tailwind CSS**
- Beautiful, responsive design
- Dark mode support
- Smooth animations and transitions
- Accessibility compliant (WCAG)
- Mobile-first approach
- Optimized user experience
- Toast notifications for feedback
- Loading states and error handling

### 📱 **Additional Features**
- Real-time notifications
- Job application tracking
- Saved jobs/bookmarks
- User profiles and portfolios
- Company profiles and reviews
- Salary insights and market data
- Career path recommendations
- Email notifications
- Advanced job filtering
- Search history and saved searches

---

## 🏗️ Architecture Overview

```
┌─────────────────────────────────────────────────────────────────┐
│              Frontend (React 19 + TypeScript + Vite)            │
│  ┌───────────────────────────────────────────────────────────┐  │
│  │  • Job Search & Filtering                                │  │
│  │  • AI Resume Builder Interface                           │  │
│  │  • Resume Upload & Parser UI                            │  │
│  │  • Interview Question Generator                         │  │
│  │  • Job Matcher Dashboard                                │  │
│  │  • Subscription Management                              │  │
│  │  • User Profile & Resume Management                     │  │
│  │  • Responsive Design & Dark Mode                        │  │
│  └───────────────────────────────────────────────────────────┘  │
└──────────────────────────────────┬───────────────────────────────┘
                                   │ (HTTPS / Axios)
┌──────────────────────────────────▼───────────────────────────────┐
│         Backend (Node.js + Express + TypeScript)                │
│  ┌───────────────────────────────────────────────────────────┐  │
│  │  • Authentication (JWT + OAuth 2.0)                      │  │
│  │  • AI Integration (@google/genai)                        │  │
│  │    ├─ Resume Analysis                                    │  │
│  │    ├─ Resume Building                                    │  │
│  │    ├─ Job Matching Algorithm                            │  │
│  │    └─ Interview Question Generation                     │  │
│  │  • PDF Parsing & Resume Extraction                       │  │
│  │  • Job Management & Filtering                           │  │
│  │  • Application Processing                               │  │
│  │  • Razorpay Payment Processing                          │  │
│  │  • Email Notifications                                  │  │
│  │  • Admin Dashboard & Analytics                          │  │
│  └───────────────────────────────────────────────────────────┘  │
└──────────────────────────────────┬───────────────────────────────┘
                                   │ (Mongoose ORM)
┌──────────────────────────────────▼───────────────────────────────┐
│                 MongoDB Database (NoSQL)                         │
│  ┌───────────────────────────────────────────────────────────┐  │
│  │  Collections:                                             │  │
│  │  • Users & Profiles          • Resumes & Documents       │  │
│  │  • Jobs & Applications        • Subscriptions & Payments  │  │
│  │  • AI Analysis Results        • Notifications & Alerts    │  │
│  │  • Interview Feedback         • Admin Analytics          │  │
│  └───────────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────────┘
```

---

## 🛠️ Complete Tech Stack

### Frontend Stack
```
React 19.2.4          - Modern UI library
TypeScript 6.0+       - Type-safe development
Vite 8.0+             - Lightning-fast build tool
Tailwind CSS 4.2+     - Utility-first styling
React Router 7.14+    - Client-side routing
Axios 1.15+           - HTTP requests
Google OAuth 0.13+    - Authentication
jsPDF 4.2+            - PDF generation
React Hot Toast 2.6+  - Notifications
Lucide React 1.7+     - Icon library
ESLint 9.39+          - Code linting
```

### Backend Stack
```
Node.js 18+           - JavaScript runtime
Express.js 5.2+       - Web framework
TypeScript 6.0+       - Type-safe backend
Mongoose 9.4+         - MongoDB ODM
JWT 9.0+              - Token authentication
@google/genai 2.0+    - Google Gemini API
Razorpay 2.9+         - Payment gateway
googleapis 171.4+     - Google services
Axios 1.14+           - HTTP client
CORS 2.8+             - Cross-origin handling
dotenv 17.4+          - Environment config
Concurrently 9.2+     - Dev process management
```

### Database & Services
```
MongoDB 9.4+          - NoSQL database
MongoDB Atlas         - Cloud hosting
Google Gemini API     - AI & LLM
Razorpay              - Payment processing
Google OAuth 2.0      - Authentication
Email Service         - Notifications
```

---

## 📋 Comprehensive Features

### 🤖 **AI-Powered Tools**
- ✅ **AI Resume Analyzer** - Score and improve resumes (0-100 scale)
- ✅ **AI Resume Builder** - Generate professional resumes with AI
- ✅ **AI Job Matcher** - Find jobs matching your profile
- ✅ **Interview Question Generator** - AI-generated interview questions
- ✅ **ATS Resume Scoring** - Optimize for Applicant Tracking Systems
- ✅ **PDF Resume Parser** - Smart extraction from PDF files
- ✅ **Career Guidance** - AI-powered career path recommendations
- ✅ **Skill Gap Analysis** - AI identifies skill gaps
- ✅ **Cover Letter Generator** - AI-written cover letters
- ✅ **Salary Insights** - Market-based salary recommendations

### 💼 **Job Portal Features**
- ✅ Browse thousands of job listings
- ✅ Advanced filtering (20+ criteria)
- ✅ Full-text search with keywords
- ✅ Save/bookmark favorite jobs
- ✅ Job recommendations
- ✅ Company profiles and reviews
- ✅ Job application tracking
- ✅ Application status updates
- ✅ Similar job suggestions
- ✅ Job alerts and notifications

### 👤 **User Management**
- ✅ User registration and login
- ✅ Google OAuth authentication
- ✅ JWT token-based sessions
- ✅ Professional profiles
- ✅ Multiple resume management
- ✅ Work experience tracking
- ✅ Skills and certifications
- ✅ Portfolio links
- ✅ Profile analytics
- ✅ Account settings

### 📄 **Resume Management**
- ✅ Upload resumes (PDF, DOCX)
- ✅ AI-powered parsing
- ✅ Edit parsed content
- ✅ Multiple template options
- ✅ Real-time preview
- ✅ PDF export
- ✅ Version control
- ✅ Resume comparisons
- ✅ Formatting optimization
- ✅ ATS compatibility check

### 💳 **Payment & Subscriptions**
- ✅ Razorpay integration
- ✅ Multiple subscription tiers
  - Free: Basic features
  - Pro: Full AI tools
  - Premium: Everything + support
- ✅ Secure payment processing
- ✅ Automatic billing
- ✅ Invoice generation
- ✅ Payment history
- ✅ Easy upgrades/downgrades
- ✅ Refund processing
- ✅ Multiple payment methods

### 🔔 **Notifications & Alerts**
- ✅ Real-time toast notifications
- ✅ Email notifications
- ✅ Job alerts for preferences
- ✅ Application status updates
- ✅ New matching job alerts
- ✅ Subscription reminders
- ✅ Notification preferences
- ✅ Unsubscribe options

### 📊 **Analytics & Dashboard**
- ✅ User dashboard with overview
- ✅ Application statistics
- ✅ Job search analytics
- ✅ Resume analytics
- ✅ Subscription usage tracking
- ✅ AI feature usage metrics
- ✅ Admin analytics dashboard
- ✅ User growth tracking
- ✅ Revenue analytics
- ✅ Custom reports

### 🔐 **Security Features**
- ✅ JWT authentication
- ✅ OAuth 2.0 integration
- ✅ Bcrypt password hashing
- ✅ CORS protection
- ✅ Input validation
- ✅ SQL injection prevention
- ✅ XSS protection
- ✅ HTTPS support
- ✅ Secure API endpoints
- ✅ Rate limiting ready

### 🎨 **UI/UX Features**
- ✅ Responsive design
- ✅ Mobile-first approach
- ✅ Dark mode support
- ✅ Smooth animations
- ✅ Loading states
- ✅ Error handling
- ✅ Form validation
- ✅ Accessibility (WCAG)
- ✅ Keyboard navigation
- ✅ Screen reader support

---

## ⚙️ Setup & Installation

### Prerequisites
```
✓ Node.js 18+
✓ npm 9+ or yarn 3+
✓ MongoDB (local or Atlas)
✓ Git
✓ Google Cloud Project with:
  ├─ Gemini API enabled
  ├─ OAuth 2.0 credentials
  └─ API keys configured
✓ Razorpay account
```

### Step 1: Clone Repository
```bash
git clone https://github.com/dev-chandan-pandey/CareerPathEasyAi.git
cd CareerPathEasyAi
```

### Step 2: Frontend Setup
```bash
cd frontend

# Install dependencies
npm install

# Create environment file
cat > .env.local << EOF
VITE_API_URL=http://localhost:3000
VITE_GOOGLE_CLIENT_ID=your_google_client_id
EOF

# Start dev server
npm run dev

# Build for production
npm run build
```

**Frontend:** `http://localhost:5173`

### Step 3: Backend Setup
```bash
cd ../backend

# Install dependencies
npm install

# Create environment file
cat > .env << EOF
PORT=3000
NODE_ENV=development
MONGODB_URI=mongodb+srv://user:pass@cluster.mongodb.net/careerpatheasai
JWT_SECRET=your_secret_key
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_secret
GOOGLE_AI_API_KEY=your_gemini_api_key
RAZORPAY_KEY_ID=your_razorpay_key
RAZORPAY_KEY_SECRET=your_razorpay_secret
CORS_ORIGIN=http://localhost:5173
EOF

# Build TypeScript
npm run build

# Start dev server
npm run dev
```

**Backend:** `http://localhost:3000`

---

## 🔧 Environment Configuration

### Frontend (.env.local)
```env
# API
VITE_API_URL=http://localhost:3000
VITE_API_TIMEOUT=30000

# Google OAuth
VITE_GOOGLE_CLIENT_ID=your_google_client_id

# Features
VITE_ENABLE_AI_FEATURES=true
VITE_ENABLE_PAYMENTS=true
VITE_ENABLE_DARK_MODE=true
```

### Backend (.env)
```env
# Server
PORT=3000
NODE_ENV=development

# Database
MONGODB_URI=mongodb+srv://user:pass@cluster.mongodb.net/careerpatheasai
MONGODB_DB_NAME=careerpatheasai

# JWT
JWT_SECRET=your_super_secret_key
JWT_EXPIRY=7d

# Google OAuth
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_secret

# Google Gemini AI (Critical for AI features)
GOOGLE_AI_API_KEY=your_gemini_api_key_here

# Razorpay (Payment Gateway)
RAZORPAY_KEY_ID=your_razorpay_key_id
RAZORPAY_KEY_SECRET=your_razorpay_secret

# Email
EMAIL_SERVICE=gmail
EMAIL_USER=your_email@gmail.com
EMAIL_PASSWORD=your_app_password

# CORS
CORS_ORIGIN=http://localhost:5173
```

### Getting API Credentials

#### 1. Google Gemini API
```
1. Go to Google AI Studio: https://makersuite.google.com/app/apikey
2. Create new API key
3. Copy and set as GOOGLE_AI_API_KEY
```

#### 2. Google OAuth
```
1. Visit Google Cloud Console
2. Create OAuth 2.0 credentials
3. Add http://localhost:5173 to redirect URIs
4. Set GOOGLE_CLIENT_ID and GOOGLE_CLIENT_SECRET
```

#### 3. Razorpay
```
1. Sign up at https://razorpay.com
2. Go to Settings → API Keys
3. Copy Key ID and Secret
4. Set RAZORPAY_KEY_ID and RAZORPAY_KEY_SECRET
```

#### 4. MongoDB Atlas
```
1. Create cluster at https://www.mongodb.com/cloud/atlas
2. Create database user
3. Get connection string
4. Set MONGODB_URI
```

---

## 📦 Project Structure

```
CareerPathEasyAi/
│
├── frontend/                          # React frontend
│   ├── src/
│   │   ├── components/
│   │   │   ├── common/               # Header, Footer, Nav
│   │   │   ├── forms/                # Form components
│   │   │   ├── cards/                # Card components
│   │   │   ├── ai/                   # AI feature components
│   │   │   │   ├── ResumeAnalyzer.tsx
│   │   │   │   ├── ResumeBuilder.tsx
│   │   │   │   ├── JobMatcher.tsx
│   │   │   │   ├── InterviewGenerator.tsx
│   │   │   │   └── ATSScorer.tsx
│   │   │   └── modals/               # Modal components
│   │   │
│   │   ├── pages/
│   │   │   ├── Home.tsx
│   │   │   ├── Jobs.tsx
│   │   │   ├── JobDetail.tsx
│   │   │   ├── Dashboard.tsx
│   │   │   ├── Profile.tsx
│   │   │   ├── ResumeAnalyzer.tsx
│   │   │   ├── ResumeBuilder.tsx
│   │   │   ├── JobMatcher.tsx
│   │   │   ├── InterviewPrep.tsx
│   │   │   ├── Subscriptions.tsx
│   │   │   ├── Login.tsx
│   │   │   └── Register.tsx
│   │   │
│   │   ├── hooks/
│   │   │   ├── useAuth.ts
│   │   │   ├── useAI.ts              # AI features hook
│   │   │   ├── useJobs.ts
│   │   │   ├── useSubscription.ts
│   │   │   └── usePagination.ts
│   │   │
│   │   ├── services/
│   │   │   ├── authService.ts
│   │   │   ├── aiService.ts           # AI API calls
│   │   │   ├── jobService.ts
│   │   │   ├── resumeService.ts
│   │   │   ├── paymentService.ts
│   │   │   └── userService.ts
│   │   │
│   │   ├── context/
│   │   │   ├── AuthContext.tsx
│   │   │   ├── AppContext.tsx
│   │   │   └── SubscriptionContext.tsx
│   │   │
│   │   ├── types/
│   │   │   ├── user.ts
│   │   │   ├── job.ts
│   │   │   ├── ai.ts                 # AI types
│   │   │   ├── payment.ts
│   │   │   └── api.ts
│   │   │
│   │   ├── utils/
│   │   │   ├── formatters.ts
│   │   │   ├── validators.ts
│   │   │   ├── constants.ts
│   │   │   └── helpers.ts
│   │   │
│   │   ├── App.tsx
│   │   └── main.tsx
│   │
│   ├── public/
│   ├── package.json
│   ├── tsconfig.json
│   ├── vite.config.ts
│   ├── tailwind.config.ts
│   └── .env.example
│
├── backend/                           # Node.js backend
│   ├── src/
│   │   ├── controllers/
│   │   │   ├── authController.ts
│   │   │   ├── jobController.ts
│   │   │   ├── applicationController.ts
│   │   │   ├── userController.ts
│   │   │   ├── paymentController.ts
│   │   │   ├── aiController.ts       # AI endpoints
│   │   │   │   ├── resumeAnalyzer.ts
│   │   │   │   ├── resumeBuilder.ts
│   │   │   │   ├── jobMatcher.ts
│   │   │   │   ├── interviewGenerator.ts
│   │   │   │   └── atsScorer.ts
│   │   │   └── subscriptionController.ts
│   │   │
│   │   ├── models/
│   │   │   ├── User.ts
│   │   │   ├── Job.ts
│   │   │   ├── Application.ts
│   │   │   ├── Resume.ts
│   │   │   ├── ResumeAnalysis.ts     # AI analysis results
│   │   │   ├── InterviewQuestion.ts
│   │   │   ├── Payment.ts
│   │   │   ├── Subscription.ts
│   │   │   └── Notification.ts
│   │   │
│   │   ├── routes/
│   │   │   ├── authRoutes.ts
│   │   │   ├── jobRoutes.ts
│   │   │   ├── applicationRoutes.ts
│   │   │   ├── userRoutes.ts
│   │   │   ├── paymentRoutes.ts
│   │   │   ├── aiRoutes.ts           # AI feature routes
│   │   │   └── subscriptionRoutes.ts
│   │   │
│   │   ├── middleware/
│   │   │   ├── auth.ts
│   │   │   ├── errorHandler.ts
│   │   │   ├── validation.ts
│   │   │   ├── logging.ts
│   │   │   └── cors.ts
│   │   │
│   │   ├── services/
│   │   │   ├── authService.ts
│   │   │   ├── jobService.ts
│   │   │   ├── aiService.ts          # Gemini API integration
│   │   │   ├── resumeParserService.ts
│   │   │   ├── paymentService.ts
│   │   │   ├── emailService.ts
│   │   │   └── subscriptionService.ts
│   │   │
│   │   ├── types/
│   │   │   ├── user.ts
│   │   │   ├── ai.ts                 # AI response types
│   │   │   ├── job.ts
│   │   │   ├── payment.ts
│   │   │   └── api.ts
│   │   │
│   │   ├── utils/
│   │   │   ├── constants.ts
│   │   │   ├── validators.ts
│   │   │   ├── jwt.ts
│   │   │   ├── geminiHelper.ts       # Gemini API helpers
│   │   │   └── errorHandling.ts
│   │   │
│   │   ├── config/
│   │   │   ├── database.ts
│   │   │   ├── gemini.ts             # Gemini configuration
│   │   │   ├── payment.ts
│   │   │   └── email.ts
│   │   │
│   │   └── index.ts
│   │
│   ├── dist/
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
POST   /api/auth/register
POST   /api/auth/login
POST   /api/auth/google
POST   /api/auth/logout
GET    /api/auth/profile
```

### Jobs
```
GET    /api/jobs
GET    /api/jobs/:id
POST   /api/jobs
PUT    /api/jobs/:id
DELETE /api/jobs/:id
GET    /api/jobs/search
GET    /api/jobs/:id/similar
```

### AI Features
```
POST   /api/ai/analyze-resume         # Resume analysis
POST   /api/ai/build-resume            # Resume builder
POST   /api/ai/match-jobs              # Job matcher
POST   /api/ai/generate-questions      # Interview prep
POST   /api/ai/score-ats                # ATS scoring
POST   /api/ai/parse-resume            # PDF parsing
POST   /api/ai/generate-cover-letter   # Cover letter
POST   /api/ai/career-guidance         # Career advice
```

### Resumes
```
POST   /api/resumes/upload
GET    /api/resumes
GET    /api/resumes/:id
PUT    /api/resumes/:id
DELETE /api/resumes/:id
POST   /api/resumes/:id/analyze        # AI analysis
```

### Subscriptions
```
GET    /api/subscriptions/plans
POST   /api/subscriptions/create-order
POST   /api/subscriptions/verify
GET    /api/subscriptions/current
PUT    /api/subscriptions/upgrade
DELETE /api/subscriptions/cancel
```

### Payments
```
POST   /api/payments/create-order
POST   /api/payments/verify
GET    /api/payments/history
POST   /api/payments/webhook
```

---

## 💳 Payment Integration

### Razorpay Setup

1. **Create Account**
   - Sign up at https://razorpay.com
   - Complete KYC verification

2. **Get API Keys**
   ```
   Dashboard → Settings → API Keys
   Copy Key ID and Secret
   ```

3. **Setup Webhooks**
   ```
   Dashboard → Settings → Webhooks
   Add your backend URL: https://your-domain.com/api/payments/webhook
   Events: order.paid, subscription.activated, subscription.halted
   ```

4. **Payment Gateway Configuration**
   ```env
   RAZORPAY_KEY_ID=rzp_live_xxxxxx
   RAZORPAY_KEY_SECRET=xxxxxx
   RAZORPAY_WEBHOOK_SECRET=xxxxxx
   ```

### Subscription Plans

```javascript
{
  "free": {
    "name": "Free",
    "price": 0,
    "features": [
      "Basic job search",
      "1 resume upload",
      "Limited AI features"
    ]
  },
  "pro": {
    "name": "Pro",
    "price": 499, // INR per month
    "features": [
      "Unlimited job search",
      "Unlimited resumes",
      "Unlimited AI analysis",
      "Resume builder",
      "Job matcher"
    ]
  },
  "premium": {
    "name": "Premium",
    "price": 999, // INR per month
    "features": [
      "All Pro features",
      "Interview prep",
      "Priority support",
      "Advanced analytics"
    ]
  }
}
```

---

## 🚀 Deployment Guide

### Frontend (Vercel)

```bash
# Push to GitHub
git push origin main

# Connect to Vercel
vercel login
vercel

# Set environment variables
vercel env add VITE_API_URL
vercel env add VITE_GOOGLE_CLIENT_ID
```

### Backend (Railway/Heroku)

#### Railway.app (Recommended)
```bash
npm install -g railway
railway login
railway init
railway up
```

#### Heroku
```bash
heroku login
heroku create your-app-name
heroku config:set MONGODB_URI="your_uri"
heroku config:set GOOGLE_AI_API_KEY="your_key"
git push heroku main
```

---

## 🧪 Testing & Quality

### Run Linting
```bash
# Frontend
cd frontend && npm run lint

# Backend
cd backend && npm run lint
```

### Type Checking
```bash
# Frontend
tsc --noEmit

# Backend
tsc --noEmit
```

---

## 🐛 Troubleshooting

### AI Features Not Working
```
✓ Verify GOOGLE_AI_API_KEY in .env
✓ Check API quota in Google Cloud Console
✓ Ensure Gemini API is enabled
✓ Verify network connectivity
```

### Resume Parser Issues
```
✓ Ensure PDF is valid
✓ Check file size (<10MB)
✓ Verify file permissions
```

### Payment Errors
```
✓ Check Razorpay keys
✓ Verify webhook URL
✓ Check webhook signature
```

### CORS/Connection Issues
```
✓ Verify CORS_ORIGIN in backend .env
✓ Check frontend API URL
✓ Ensure both servers are running
```

---

## 🤝 Contributing

We welcome contributions! Here's how:

1. Fork the repository
2. Create feature branch: `git checkout -b feature/awesome-feature`
3. Commit: `git commit -m "feat: add awesome feature"`
4. Push: `git push origin feature/awesome-feature`
5. Create Pull Request

---

## 📄 License

Licensed under the **ISC License** - see LICENSE file for details.

---

## 👨‍💼 Author

**Chandan Pandey**
- GitHub: [@dev-chandan-pandey](https://github.com/dev-chandan-pandey)
- Email: dev.chandan.pandey@gmail.com
- Portfolio: [CareerPathEasy AI](https://job-portal-tau-sepia.vercel.app)

---

## 🌟 Perfect For

✅ MERN Stack Developers
✅ Final Year Projects
✅ SaaS Startup Ideas
✅ AI Web App Developers
✅ Portfolio Projects
✅ Full Stack Learning

---

## 🎯 Use Cases

- **Career Professionals** - Optimize resume and find better jobs
- **Job Seekers** - AI-powered job discovery and matching
- **Students** - Prepare for interviews with AI guidance
- **Recruiters** - Post jobs and find qualified candidates
- **Companies** - Build your job portal with AI features

---

## 🔮 Roadmap

### v2.0
- [ ] Video interview practice
- [ ] LinkedIn integration
- [ ] Advanced analytics
- [ ] Mobile app (React Native)
- [ ] Enterprise features

### v3.0
- [ ] Blockchain verification
- [ ] Advanced ML models
- [ ] Global expansion
- [ ] Multi-language support

---

**Built with ❤️ by Chandan Pandey**

**Status:** ✅ Production Ready | 🚀 Actively Maintained | 📈 Growing Community

---

## 📞 Support

- 🐛 **Issues:** [GitHub Issues](https://github.com/dev-chandan-pandey/CareerPathEasyAi/issues)
- 💬 **Discussions:** [GitHub Discussions](https://github.com/dev-chandan-pandey/CareerPathEasyAi/discussions)
- 🌐 **Live Demo:** [CareerPathEasy AI](https://job-portal-tau-sepia.vercel.app)

---

**Last Updated:** June 7, 2026 | **Version:** 1.0.0 | **Status:** Production Ready ✅

# Job Portal - Microservices Architecture

A modern, scalable job portal built with microservices architecture. Discover jobs, apply for positions, and manage your career all in one place.

**Live Demo:** [https://job-portal-tau-sepia.vercel.app](https://job-portal-tau-sepia.vercel.app)

## 🏗️ Architecture Overview

This project follows a microservices architecture with a React frontend and Node.js backend services:

```
┌─────────────────────────────────────────────────────┐
│         Frontend (React + TypeScript + Vite)        │
│        - Job Browsing & Filtering                   │
│        - User Profiles & Applications                │
│        - Authentication (Google OAuth)               │
└────────────────────┬────────────────────────────────┘
                     │
┌────────────────────▼────────────────────────────────┐
│        API Gateway / Backend Services               │
│        - User Management                             │
│        - Job Listings                                │
│        - Application Processing                      │
│        - Payment Integration (Razorpay)              │
└────────────────────┬────────────────────────────────┘
                     │
┌────────────────────▼────────────────────────────────┐
│              Data & Message Layer                   │
│        - PostgreSQL (Database)                       │
│        - Kafka (Event Streaming)                     │
└─────────────────────────────────────────────────────┘
```

## 🚀 Tech Stack

### Frontend
- **React 19** - UI library
- **TypeScript** - Type safety
- **Vite** - Fast build tool with HMR
- **Tailwind CSS** - Utility-first CSS framework
- **React Router v7** - Client-side routing
- **Axios** - HTTP client
- **Google OAuth** - Authentication
- **React Hot Toast** - Notifications
- **jsPDF** - PDF generation
- **Lucide React** - Icon library

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **TypeScript** - Type safety
- **MongoDB/Mongoose** - Database ORM
- **JWT** - Authentication
- **Razorpay** - Payment processing
- **Google APIs** - Integration services
- **Axios** - HTTP client
- **CORS** - Cross-origin requests
- **dotenv** - Environment configuration

### Infrastructure
- **PostgreSQL** - Primary database
- **Kafka** - Event streaming & message queue
- **Vercel** - Frontend hosting

## 📋 Features

- 🔐 **User Authentication** - Google OAuth & JWT-based auth
- 💼 **Job Listings** - Browse and filter job opportunities
- 📝 **Application Management** - Track job applications
- 👤 **User Profiles** - Create and manage profiles
- 💳 **Payment Integration** - Razorpay for secure payments
- 🔔 **Real-time Notifications** - Toast notifications
- 📄 **Resume/CV** - Generate PDF resumes
- 🎯 **Advanced Filtering** - Filter jobs by role, salary, location
- 📱 **Responsive Design** - Works on all devices

## 🛠️ Setup & Installation

### Prerequisites
- Node.js 18+ 
- npm or yarn
- PostgreSQL
- Kafka (for production)
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

The frontend will be available at `http://localhost:5173`

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

The backend will be available at `http://localhost:3000` (or configured port)

## 🔧 Environment Variables

### Frontend (.env)
```env
VITE_API_URL=http://localhost:3000
VITE_GOOGLE_CLIENT_ID=your_google_client_id
```

### Backend (.env)
```env
PORT=3000
NODE_ENV=development
MONGODB_URI=your_mongodb_uri
JWT_SECRET=your_jwt_secret
GOOGLE_CLIENT_ID=your_google_client_id
RAZORPAY_KEY_ID=your_razorpay_key
RAZORPAY_KEY_SECRET=your_razorpay_secret
CORS_ORIGIN=http://localhost:5173
```

## 📦 Project Structure

```
Job-Portal/
├── frontend/                  # React frontend application
│   ├── src/
│   │   ├── components/       # Reusable components
│   │   ├── pages/            # Page components
│   │   ├── hooks/            # Custom React hooks
│   │   ├── services/         # API services
│   │   ├── types/            # TypeScript types
│   │   ├── styles/           # Global styles
│   │   └── App.tsx           # Root component
│   ├── public/               # Static assets
│   ├── package.json
│   ├── tsconfig.json
│   ├── vite.config.ts
│   └── tailwind.config.ts
│
├── backend/                   # Node.js backend services
│   ├── src/
│   │   ├── controllers/      # Request handlers
│   │   ├── models/           # Database models
│   │   ├── routes/           # API routes
│   │   ├── middleware/       # Custom middleware
│   │   ├── services/         # Business logic
│   │   ├── types/            # TypeScript types
│   │   └── index.ts          # Entry point
│   ├── dist/                 # Compiled output
│   ├── package.json
│   ├── tsconfig.json
│   └── .env
│
└── README.md
```

## 🔄 API Endpoints

### Authentication
- `POST /api/auth/login` - User login
- `POST /api/auth/register` - User registration
- `POST /api/auth/logout` - User logout
- `GET /api/auth/profile` - Get user profile

### Jobs
- `GET /api/jobs` - Get all jobs
- `GET /api/jobs/:id` - Get job details
- `POST /api/jobs` - Create new job (admin)
- `PUT /api/jobs/:id` - Update job (admin)
- `DELETE /api/jobs/:id` - Delete job (admin)

### Applications
- `GET /api/applications` - Get user applications
- `POST /api/applications` - Submit job application
- `GET /api/applications/:id` - Get application details
- `PUT /api/applications/:id` - Update application status

### Payments
- `POST /api/payments/create-order` - Create payment order
- `POST /api/payments/verify` - Verify payment

## 🧪 Testing

```bash
# Frontend linting
cd frontend
npm run lint

# Backend would include tests (if configured)
cd backend
npm test
```

## 🚀 Deployment

### Frontend (Vercel)
1. Connect your GitHub repository to Vercel
2. Set environment variables in Vercel dashboard
3. Deploy with `npm run build`

### Backend
Deployment options:
- **Heroku** - Easy Node.js deployment
- **AWS EC2** - Full control
- **Railway** - Modern PaaS
- **Render** - Simple deployments

## 📝 Git Workflow

```bash
# Create feature branch
git checkout -b feature/your-feature-name

# Make changes and commit
git add .
git commit -m "Add: brief description of changes"

# Push to repository
git push origin feature/your-feature-name

# Create Pull Request on GitHub
```

## 🐛 Troubleshooting

### CORS Errors
- Ensure `CORS_ORIGIN` environment variable is set correctly in backend
- Check that frontend URL matches backend CORS configuration

### MongoDB Connection Issues
- Verify MongoDB URI is correct
- Ensure IP is whitelisted in MongoDB Atlas (if using cloud)

### Kafka Connection Issues
- Ensure Kafka broker is running
- Check Kafka configuration in backend

### Port Already in Use
```bash
# Find process using port
lsof -i :3000  # Backend
lsof -i :5173  # Frontend

# Kill process
kill -9 <PID>
```

## 📚 Documentation

- [Frontend README](./frontend/README.md)
- [Backend Setup Guide](./backend)

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the ISC License - see the LICENSE file for details.

## 👨‍💼 Author

**Chandan Pandey**
- GitHub: [@dev-chandan-pandey](https://github.com/dev-chandan-pandey)

## 🙏 Acknowledgments

- React and Vite communities
- Express.js and Node.js ecosystems
- All contributors and testers

## 📞 Support

For support, please open an issue on the GitHub repository.

---

**Built with ❤️ using modern web technologies**

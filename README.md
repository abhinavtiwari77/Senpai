# Senpai - AI-Powered Career Coach 🚀
> A comprehensive AI-powered career development platform built with Next.js 15, featuring resume building, cover letter generation, interview preparation, and personalized industry insights.

## ✨ Features

### 🎯 Core Features
- **AI Resume Builder** - Create professional, ATS-optimized resumes with AI assistance
- **Cover Letter Generator** - Generate tailored cover letters for specific job applications
- **Interview Preparation** - Practice with AI-generated interview questions specific to your industry
- **Industry Insights Dashboard** - Get real-time salary data, market trends, and skill recommendations
- **User Onboarding** - Personalized experience based on your industry and experience level

### 🔐 Authentication & Security
- Secure authentication with Clerk
- Protected routes and API endpoints
- User profile management

### 🎨 UI/UX
- Modern, responsive design with Tailwind CSS
- Dark mode support with next-themes
- Beautiful UI components with Shadcn UI
- Smooth animations and transitions

### 🤖 AI Integration
- Google Gemini AI for intelligent content generation
- Personalized industry insights
- Smart resume and cover letter suggestions
- Adaptive interview questions

## 🛠️ Tech Stack

### Frontend
- **Framework**: Next.js 15.1.4 (App Router + Turbopack)
- **UI Library**: React 19
- **Styling**: Tailwind CSS 3.4
- **UI Components**: Shadcn UI (Radix UI primitives)
- **Forms**: React Hook Form + Zod validation
- **Markdown**: React Markdown + MD Editor
- **Charts**: Recharts
- **Icons**: Lucide React

### Backend
- **Database**: PostgreSQL (Neon DB)
- **ORM**: Prisma 6.2.1
- **Authentication**: Clerk
- **AI**: Google Generative AI (Gemini 1.5 Flash)
- **Background Jobs**: Inngest
- **API**: Next.js Server Actions

### Developer Tools
- **Language**: JavaScript (with JSConfig)
- **Linting**: ESLint 9 + Next.js config
- **Package Manager**: npm
- **Version Control**: Git

## 📋 Prerequisites

Before you begin, ensure you have:
- Node.js 18+ installed
- npm or yarn package manager
- A Neon DB account (free tier available)
- A Clerk account (free tier available)
- A Google AI Studio account for Gemini API (optional)

## 🚀 Quick Start

### 1. Clone the Repository

```bash
git clone https://github.com/echoAbhinav/Senpai.git
cd Senpai
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Environment Setup

Create a `.env.local` file in the root directory:

```env
# Database (PostgreSQL - Neon DB)
DATABASE_URL="your_neon_database_url"

# Clerk Authentication
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
CLERK_SECRET_KEY=your_clerk_secret_key

NEXT_PUBLIC_CLERK_SIGN_IN_URL=/sign-in
NEXT_PUBLIC_CLERK_SIGN_UP_URL=/sign-up
NEXT_PUBLIC_CLERK_AFTER_SIGN_IN_URL=/onboarding
NEXT_PUBLIC_CLERK_AFTER_SIGN_UP_URL=/onboarding

# Google Gemini AI API Key (Optional - uses mock data if not provided)
GEMINI_API_KEY=your_gemini_api_key
```

Also create a `.env` file for Prisma CLI:

```env
DATABASE_URL="your_neon_database_url"
```

### 4. Database Setup

Run Prisma migrations to set up your database:

```bash
# Deploy migrations
npx prisma migrate deploy

# Generate Prisma client
npx prisma generate
```

### 5. Run Development Server

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## 📝 Detailed Setup Guide

### Setting Up Neon DB

1. Go to [neon.tech](https://neon.tech) and sign up
2. Create a new project
3. Copy your connection string
4. Add it to both `.env.local` and `.env` files

### Setting Up Clerk Authentication

1. Visit [clerk.com](https://clerk.com) and create an account
2. Create a new application
3. Copy your publishable key and secret key
4. Add them to `.env.local`
5. Configure sign-in/sign-up URLs in Clerk dashboard

### Setting Up Google Gemini AI (Optional)

1. Go to [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Sign in with your Google account
3. Create a new API key
4. Add it to `.env.local`

**Note**: The app works without Gemini API key by using default mock data for industry insights.

## 📁 Project Structure

```
Senpai/
├── actions/              # Server actions
│   ├── cover-letter.js
│   ├── dashboard.js
│   ├── interview.js
│   ├── resume.js
│   └── user.js
├── app/                  # Next.js app directory
│   ├── (auth)/          # Authentication routes
│   ├── (main)/          # Main app routes
│   ├── api/             # API routes
│   └── lib/             # App-specific utilities
├── components/           # Reusable components
│   ├── ui/              # Shadcn UI components
│   └── ...
├── data/                # Static data
├── hooks/               # Custom React hooks
├── lib/                 # Utilities and configs
├── prisma/              # Database schema & migrations
└── public/              # Static assets
```

## 🎯 Key Features Explained

### Resume Builder
- Rich markdown editor for resume content
- Real-time preview
- Export to PDF functionality
- ATS score and feedback (with AI)

### Cover Letter Generator
- Template-based generation
- Job-specific customization
- Company and role information
- Multiple cover letters per user

### Interview Preparation
- Industry-specific questions
- Multiple choice format
- Performance tracking
- Detailed analytics and improvement tips

### Industry Insights Dashboard
- Real-time salary ranges by role
- Market growth rates
- Top in-demand skills
- Industry trends and outlook
- Personalized skill recommendations

## 🔧 Available Scripts

```bash
# Development
npm run dev          # Start dev server with Turbopack

# Production
npm run build        # Build for production
npm start            # Start production server

# Database
npx prisma migrate dev      # Create and apply migrations
npx prisma migrate deploy   # Deploy migrations
npx prisma generate         # Generate Prisma client
npx prisma studio          # Open Prisma Studio

# Linting
npm run lint         # Run ESLint
```

## 🐛 Troubleshooting

### Database Connection Issues
- Ensure DATABASE_URL is correct in both `.env` and `.env.local`
- Check that Neon DB instance is running
- Verify network connectivity

### Clerk Authentication Errors
- Verify API keys are correct
- Check that redirect URLs are properly configured
- Ensure environment variables are loaded

### Build Errors
- Clear `.next` folder: `rm -rf .next`
- Delete `node_modules` and reinstall: `rm -rf node_modules && npm install`
- Run `npx prisma generate` to regenerate Prisma client


## 👨‍💻 Author
**Abhinav**
- GitHub: [@echoAbhinav](https://github.com/echoAbhinav)

## 🙏 Acknowledgments
- Built with [Next.js](https://nextjs.org/)
- UI components from [Shadcn UI](https://ui.shadcn.com/)
- Authentication by [Clerk](https://clerk.com)
- Database hosted on [Neon](https://neon.tech)
- AI powered by [Google Gemini](https://ai.google.dev/)

## 📞 Support

If you have any questions or need help, please open an issue in the GitHub repository.

---

**Made with ❤️ by Abhinav**


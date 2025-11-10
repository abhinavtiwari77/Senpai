# Senpai - Setup Guide

## ✅ What's Already Fixed

1. ✅ **Environment Variables** - `.env.local` file created with Clerk keys
2. ✅ **TypeScript Configuration** - `jsconfig.json` updated to fix type errors
3. ✅ **Branding** - All "Sensai" references changed to "Senpai"
4. ✅ **Dependencies** - All npm packages installed correctly
5. ✅ **Dev Server** - Next.js running successfully on port 3001

## ⚠️ What You Need to Configure

### 1. Database Setup (Required)

Your app needs a PostgreSQL database. Choose one option:

#### **Option A: Neon DB (Recommended - Free & Easy)**

1. Visit [https://neon.tech](https://neon.tech)
2. Sign up for a free account
3. Click "Create Project"
4. Copy the connection string (looks like `postgresql://username:password@ep-xxx.us-east-2.aws.neon.tech/neondb?sslmode=require`)
5. Open `.env.local` and replace the `DATABASE_URL` line with your connection string

#### **Option B: Local PostgreSQL**

1. Install PostgreSQL from [https://www.postgresql.org/download/](https://www.postgresql.org/download/)
2. Open pgAdmin or psql terminal
3. Create a new database: `CREATE DATABASE senpai_db;`
4. Update `.env.local` with your credentials:
   ```
   DATABASE_URL="postgresql://postgres:yourpassword@localhost:5432/senpai_db"
   ```

### 2. Run Database Migration

After setting up your database, run:

```powershell
npx prisma migrate dev
```

This creates all the necessary tables in your database.

### 3. Google Gemini API Key (Required for AI Features)

1. Visit [https://makersuite.google.com/app/apikey](https://makersuite.google.com/app/apikey)
2. Sign in with your Google account
3. Click "Create API Key"
4. Copy the key
5. Update `.env.local`:
   ```
   GEMINI_API_KEY=your_actual_api_key_here
   ```

## 🚀 Starting the App

Once you've configured the database and API keys:

```powershell
# Start the development server
npm run dev
```

The app will be available at: `http://localhost:3001`

## 📝 Current Status

- ✅ **Clerk Authentication**: Configured and ready
- ⚠️ **Database**: Needs configuration (see above)
- ⚠️ **AI Features**: Needs Gemini API key (see above)
- ✅ **Frontend**: All pages and components working

## 🔧 Troubleshooting

### "Can't reach database server at localhost:5432"
- You haven't set up the database yet. Follow the "Database Setup" section above.

### "GEMINI_API_KEY is not defined"
- Get your API key from Google AI Studio and add it to `.env.local`

### Port 3000 already in use
- The app automatically uses port 3001 when 3000 is busy. This is normal.

## 📚 Next Steps

1. Set up your database (Neon DB recommended)
2. Run `npx prisma migrate dev`
3. Get a Gemini API key
4. Start the dev server with `npm run dev`
5. Visit `http://localhost:3001` and sign up!

---

**Note**: Make sure to never commit your `.env.local` file to version control. It's already in `.gitignore`.

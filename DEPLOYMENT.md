# Deployment Guide for Senpai 🚀

## Quick Deployment to Vercel

### 1. Prerequisites
- GitHub repository: ✅ https://github.com/echoAbhinav/Senpai
- Vercel account (sign up at https://vercel.com)
- All environment variables ready

### 2. Deploy to Vercel

#### Option A: Using Vercel Dashboard

1. Go to [vercel.com](https://vercel.com) and sign in
2. Click "Add New Project"
3. Import your repository: `echoAbhinav/Senpai`
4. Configure project:
   - **Framework Preset**: Next.js
   - **Root Directory**: ./
   - **Build Command**: `npm run build`
   - **Output Directory**: `.next`

5. Add Environment Variables:
   ```
   DATABASE_URL=your_neon_database_url
   NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
   CLERK_SECRET_KEY=your_clerk_secret_key
   NEXT_PUBLIC_CLERK_SIGN_IN_URL=/sign-in
   NEXT_PUBLIC_CLERK_SIGN_UP_URL=/sign-up
   NEXT_PUBLIC_CLERK_AFTER_SIGN_IN_URL=/onboarding
   NEXT_PUBLIC_CLERK_AFTER_SIGN_UP_URL=/onboarding
   GEMINI_API_KEY=your_gemini_api_key (optional)
   ```

6. Click "Deploy"

#### Option B: Using Vercel CLI

```bash
# Install Vercel CLI
npm i -g vercel

# Login to Vercel
vercel login

# Deploy
vercel

# Follow the prompts and add environment variables when asked

# Deploy to production
vercel --prod
```

### 3. Post-Deployment Setup

#### Update Clerk URLs
1. Go to your Clerk dashboard
2. Navigate to "Paths" or "URLs"
3. Add your Vercel deployment URL:
   - Allowed redirect URLs: `https://your-app.vercel.app/*`
   - Sign-in URL: `https://your-app.vercel.app/sign-in`
   - Sign-up URL: `https://your-app.vercel.app/sign-up`
   - After sign-in: `https://your-app.vercel.app/onboarding`
   - After sign-up: `https://your-app.vercel.app/onboarding`

#### Run Database Migrations
Your database should already have migrations applied. If not:
```bash
# Using Vercel CLI
vercel env pull .env.local
npx prisma migrate deploy
```

### 4. Domain Setup (Optional)

1. In Vercel dashboard, go to your project
2. Click "Settings" → "Domains"
3. Add your custom domain
4. Update DNS records as instructed
5. Update Clerk redirect URLs with new domain

## Alternative Deployment Options

### Deploy to Railway

1. Sign up at [railway.app](https://railway.app)
2. Create new project from GitHub
3. Connect `echoAbhinav/Senpai` repository
4. Add environment variables
5. Deploy automatically

### Deploy to Render

1. Sign up at [render.com](https://render.com)
2. Create new Web Service
3. Connect GitHub repository
4. Configure:
   - Build Command: `npm install && npm run build`
   - Start Command: `npm start`
5. Add environment variables
6. Deploy

## Environment Variables Checklist

Make sure you have all of these:

- [ ] `DATABASE_URL` - Your Neon DB connection string
- [ ] `NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY` - Clerk public key
- [ ] `CLERK_SECRET_KEY` - Clerk secret key
- [ ] `NEXT_PUBLIC_CLERK_SIGN_IN_URL=/sign-in`
- [ ] `NEXT_PUBLIC_CLERK_SIGN_UP_URL=/sign-up`
- [ ] `NEXT_PUBLIC_CLERK_AFTER_SIGN_IN_URL=/onboarding`
- [ ] `NEXT_PUBLIC_CLERK_AFTER_SIGN_UP_URL=/onboarding`
- [ ] `GEMINI_API_KEY` - Optional, app works without it

## Troubleshooting Deployment Issues

### Build Fails
- Check all environment variables are set
- Ensure `DATABASE_URL` is accessible from deployment platform
- Run `npm run build` locally to test

### Authentication Not Working
- Verify Clerk URLs are updated with deployment URL
- Check environment variables are correctly set
- Ensure HTTPS is enabled

### Database Connection Fails
- Verify Neon DB allows connections from deployment platform
- Check connection string format
- Ensure migrations are applied

### 500 Errors
- Check server logs in Vercel dashboard
- Verify all required environment variables are set
- Check database is accessible

## Monitoring & Analytics

### Enable Vercel Analytics
1. Go to project settings in Vercel
2. Enable "Analytics"
3. Add analytics code (already included if using Vercel)

### Speed Insights
Vercel Speed Insights is automatically enabled for Next.js apps.

## Production Checklist

Before going live:

- [ ] All environment variables configured
- [ ] Database migrations applied
- [ ] Clerk redirect URLs updated
- [ ] Custom domain configured (if applicable)
- [ ] Error monitoring set up
- [ ] Performance tested
- [ ] Security headers configured
- [ ] HTTPS enabled
- [ ] SEO metadata added

## Continuous Deployment

The repository is set up for continuous deployment:
- Push to `master` branch → Automatic deployment to production
- Create a `dev` branch for staging environment
- Use pull requests for code review before merging

---

**Your app is now deployed!** 🎉

Visit: https://github.com/echoAbhinav/Senpai

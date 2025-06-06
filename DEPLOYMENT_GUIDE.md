# CPA Marketing Platform - Deployment Guide

## Free Hosting Options

### 1. Replit (Recommended - Current Platform)
- **Pros**: Zero configuration, PostgreSQL included, instant deployment
- **Cons**: Limited resources on free tier
- **Steps**:
  1. Your project is already on Replit
  2. Click "Deploy" button in the top right
  3. Choose "Autoscale Deployment"
  4. Your app will be available at `https://your-repl-name.your-username.replit.app`

### 2. Railway
- **Pros**: Excellent for full-stack apps, PostgreSQL included
- **Cons**: Limited free hours per month
- **Steps**:
  1. Push code to GitHub
  2. Connect Railway to your GitHub repo
  3. Add PostgreSQL service
  4. Set environment variables
  5. Deploy automatically on commits

### 3. Render
- **Pros**: Good free tier, supports PostgreSQL
- **Cons**: Slower cold starts
- **Steps**:
  1. Push code to GitHub
  2. Create new Web Service on Render
  3. Connect to your repo
  4. Add PostgreSQL database
  5. Configure environment variables

### 4. Vercel + PlanetScale/Supabase
- **Pros**: Excellent performance, great for frontend
- **Cons**: Requires serverless functions for backend
- **Steps**:
  1. Deploy frontend to Vercel
  2. Convert backend to serverless functions
  3. Use PlanetScale or Supabase for database

## Environment Variables Required

```env
DATABASE_URL=postgresql://username:password@host:port/database
NODE_ENV=production
SESSION_SECRET=your-secret-key
REPLIT_CLIENT_ID=your-client-id
REPLIT_CLIENT_SECRET=your-client-secret
```

## Build Commands

- **Build**: `npm run build`
- **Start**: `npm run start`
- **Install**: `npm install`

## Database Setup

1. Run migrations: `npm run db:push`
2. Seed database with sample data (optional)

## File Structure Overview

```
├── client/                 # React frontend
│   ├── src/
│   │   ├── components/     # UI components
│   │   ├── pages/          # Route pages
│   │   ├── hooks/          # Custom hooks
│   │   └── lib/            # Utilities
├── server/                 # Express backend
│   ├── routes.ts           # API routes
│   ├── storage.ts          # Database operations
│   └── index.ts            # Server entry point
├── shared/                 # Shared types/schemas
│   └── schema.ts           # Database schema
└── package.json            # Dependencies
```

## Quick Deployment Steps

1. **Prepare code**: Ensure all files are committed
2. **Choose platform**: Replit (easiest) or Railway/Render
3. **Set environment variables**: Database URL and secrets
4. **Deploy**: Follow platform-specific steps above
5. **Verify**: Test all features after deployment

## Troubleshooting

- **Port issues**: Most platforms auto-assign ports
- **Database connections**: Ensure DATABASE_URL is correct
- **Build failures**: Check Node.js version compatibility
- **Auth issues**: Verify Replit OAuth settings for production domain
# CPA Marketing Platform

A comprehensive CPA marketing platform with user dashboards, offer tracking, and monetization features built with React and Express.

## Features

- **Icon-Based Navigation**: Dashboard, Offers, Account, and Withdraw sections
- **User Authentication**: Secure login with Replit Auth
- **Offer Management**: Browse and complete CPA offers
- **Earnings Tracking**: Real-time balance and statistics
- **Withdrawal System**: Request payments via PayPal, Bank, or Crypto
- **Referral Program**: Earn from referred users
- **Responsive Design**: Works on desktop and mobile

## Tech Stack

- **Frontend**: React 18, TypeScript, Tailwind CSS, Wouter (routing)
- **Backend**: Express.js, TypeScript
- **Database**: PostgreSQL with Drizzle ORM
- **UI Components**: Shadcn/ui with Radix primitives
- **Authentication**: Replit Auth (OAuth)

## Quick Start

1. **Install dependencies**:
   ```bash
   npm install
   ```

2. **Set up environment variables**:
   ```env
   DATABASE_URL=postgresql://username:password@host:port/database
   NODE_ENV=development
   SESSION_SECRET=your-secret-key
   REPLIT_CLIENT_ID=your-client-id
   REPLIT_CLIENT_SECRET=your-client-secret
   ```

3. **Push database schema**:
   ```bash
   npm run db:push
   ```

4. **Start development server**:
   ```bash
   npm run dev
   ```

5. **Visit**: http://localhost:5000

## Navigation

- **🏠 Dashboard**: Overview of earnings and recent activities
- **🎁 Offers**: Browse and complete available CPA offers
- **👤 Account**: View profile information and referral code
- **💰 Withdraw**: Request payments and view withdrawal history

## Deployment

See `DEPLOYMENT_GUIDE.md` for detailed deployment instructions to various free hosting platforms.

## Project Structure

```
├── client/src/
│   ├── components/         # Reusable UI components
│   ├── pages/             # Route pages (dashboard, offers, account, withdraw)
│   ├── hooks/             # Custom React hooks
│   └── lib/               # Utilities and configurations
├── server/
│   ├── routes.ts          # API endpoints
│   ├── storage.ts         # Database operations
│   ├── replitAuth.ts      # Authentication middleware
│   └── index.ts           # Server entry point
├── shared/
│   └── schema.ts          # Database schema and types
└── package.json
```

## API Endpoints

- `GET /api/auth/user` - Get current user
- `GET /api/dashboard/stats` - Get user statistics
- `GET /api/offers` - Get available offers
- `POST /api/offers/:id/start` - Start an offer
- `POST /api/offers/:id/complete` - Complete an offer
- `GET /api/payments` - Get payment history
- `POST /api/payments/request` - Request withdrawal

## License

MIT License
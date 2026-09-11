# ⚡ Sunagorik - 5 Minute Quick Start

Get Sunagorik running locally in 5 minutes.

## Prerequisites
- Node.js 16+ installed (https://nodejs.org)
- Git installed (https://git-scm.com)

## Step 1: Setup Backend (2 minutes)

```bash
cd sunagorik-backend

# Install dependencies
npm install

# Copy environment
cp .env.example .env

# Start server
npm start
```

You'll see:
```
✅ Database initialized
🚀 Sunagorik backend running on http://localhost:5000
```

**Backend is running!** ✅

## Step 2: Setup Frontend (2 minutes)

Open **new terminal** (keep backend running):

```bash
cd sunagorik-frontend  # or your frontend folder

# Install dependencies
npm install

# Start development server
npm run dev
```

You'll see:
```
  ➜  Local:   http://localhost:5173/
```

**Frontend is running!** ✅

## Step 3: Open App (1 minute)

1. Open **http://localhost:5173** in browser
2. Sign up with any email
3. Click the **⊕ FAB button**
4. Upload a photo
5. Write a description
6. Click **Submit**

**You just created a report!** 🎉

## Step 4: Test Features

- **Map Tab:** See your report appear on map
- **Feed Tab:** See Instagram-style cards
- **Profile Tab:** See your score increase (+10 points)
- **Reporting Tab:** See your submitted reports
- **Leaderboard Tab:** See top users
- **Toggle EN/বাং:** Switch languages

## That's It!

You now have a fully working waste reporting app running locally.

### Next Steps

- **Deploy to production:** See `DEPLOYMENT.md`
- **Customize:** Edit frontend colors, text
- **Add features:** See `backend/README.md`
- **Show to municipality:** Use the live URL from deployment

### Troubleshooting

**Backend won't start?**
```bash
# Check if port 5000 is in use
lsof -i :5000
# Kill it or change PORT in .env
```

**Frontend won't start?**
```bash
# Check if port 5173 is in use
lsof -i :5173
```

**Database error?**
```bash
# Reset database
rm sunagorik-backend/database/sunagorik.db
npm start
```

### Architecture

```
Frontend (React)  ←→  Backend (Node.js)  ←→  Database (SQLite)
localhost:5173        localhost:5000         database/sunagorik.db
```

### API Endpoints

All available at: http://localhost:5000/api

- `POST /auth/signup` - Create account
- `POST /auth/login` - Login
- `GET /reports` - Get all reports
- `POST /reports` - Create report (requires auth)
- `POST /reports/:id/upvote` - Like report
- `GET /leaderboard/top` - Top 50 users

Full docs: See `backend/README.md`

---

**That's the quick start!**

For detailed setup, see `README.md`  
For deployment, see `DEPLOYMENT.md`  
For API docs, see `backend/README.md`

**Questions? Check the troubleshooting section or see documentation files.**

---

**Happy coding! 🚀**

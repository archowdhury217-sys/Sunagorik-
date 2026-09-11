# 🚀 Deployment Guide - Sunagorik MVP

Complete step-by-step guide to deploy Sunagorik to production.

---

## 📋 Prerequisites

Before starting, you need:
1. GitHub account (free at github.com)
2. Railway account (free at railway.app)
3. Vercel account (free at vercel.com)
4. 30 minutes of time

---

## PART 1: Prepare GitHub Repository

### Step 1: Create GitHub Repo

1. Go to https://github.com/new
2. Name: `sunagorik`
3. Description: "Civic waste reporting platform for Bangladesh"
4. **Public** (so anyone can see it)
5. **Add .gitignore:** Node
6. Create repository

### Step 2: Push Code

```bash
# Clone your new repo
git clone https://github.com/yourusername/sunagorik.git
cd sunagorik

# Copy backend and frontend folders here
# Or structure as:
# sunagorik/
#   ├── backend/
#   └── frontend/

# Add everything
git add .
git commit -m "Initial commit: Sunagorik MVP"
git push origin main
```

---

## PART 2: Deploy Backend (Railway) - 10 minutes

### Step 1: Railway Setup

1. Go to https://railway.app
2. Sign up with GitHub
3. Click **"New Project"** → **"Deploy from GitHub repo"**
4. Select `sunagorik` repo
5. Select **backend** directory

### Step 2: Environment Variables

Add these in Railway Variables tab:

```
PORT=5000
NODE_ENV=production
JWT_SECRET=<random-string>
CORS_ORIGIN=https://sunagorik.vercel.app
```

Generate JWT_SECRET:
```bash
node -e "console.log(require('crypto').randomBytes(32).toString('hex'))"
```

### Step 3: Deploy

Click **Deploy** → Wait 2-3 minutes → Get URL like:
```
https://sunagorik-abc123.railway.app
```

Test: `curl https://sunagorik-abc123.railway.app/api/health`

---

## PART 3: Deploy Frontend (Vercel) - 10 minutes

### Step 1: Vercel Setup

1. Go to https://vercel.com
2. Sign up with GitHub
3. Import Project → Select `sunagorik` repo
4. Select **frontend** directory

### Step 2: Environment Variables

Add in Vercel Settings → Environment Variables:

```
VITE_API_URL=https://sunagorik-abc123.railway.app/api
```

Replace `sunagorik-abc123` with your Railway URL

### Step 3: Deploy

Click **Deploy** → Wait 1-2 minutes → Get URL:
```
https://sunagorik.vercel.app
```

---

## PART 4: Test Everything

1. Go to `https://sunagorik.vercel.app`
2. Sign up
3. Create a report
4. Like it
5. Toggle language
6. Check profile score increased

✅ If all works → You're live!

---

## 🎉 Your Live URLs

**Frontend:** https://sunagorik.vercel.app  
**Backend API:** https://sunagorik-abc123.railway.app/api  
**GitHub:** https://github.com/yourusername/sunagorik  

Share these with Sylhet municipality!

---

## 🔄 Auto-Deploy Magic

Every time you push to GitHub:

```bash
git push origin main
```

Both Railway and Vercel auto-deploy instantly. No extra steps needed!

---

## 💰 Cost: FREE!

- Railway: Free tier (very generous)
- Vercel: Free tier (unlimited)
- GitHub: Free
- **Total: $0/month**

---

## 🆘 Quick Troubleshooting

**API not connecting?**
→ Check VITE_API_URL in Vercel env vars

**Photos not uploading?**
→ Max 5MB per file

**Database error?**
→ Railway auto-fixes, just retry

**Deployment stuck?**
→ Check logs in Railway/Vercel dashboard

---

## 📝 For More Details

See `backend/README.md` for full API documentation
See `SUNAGORIK_README.md` for complete project overview

---

**You're live! 🚀**

Now show it to Sylhet municipality! 💪

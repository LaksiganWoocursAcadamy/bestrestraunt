# 🔧 FIX SERVER ISSUES - SOLUTIONS

## Problem 1: Port 5000 Already in Use

**Error:** `EADDRINUSE: address already in use :::5000`

### Solution A: Kill the Process Using Port 5000

```powershell
# Find the process
netstat -ano | findstr :5000

# Kill it (replace PID with the number you see)
taskkill /PID <PID> /F
```

### Solution B: Use a Different Port

1. Open `server/.env`
2. Change:
   ```
   PORT=5001
   ```
3. Open `client/.env`
4. Change:
   ```
   REACT_APP_API_URL=http://localhost:5001
   ```

### Solution C: Restart Your Computer
- This will close all processes

---

## Problem 2: MongoDB Connection Error

**Error:** `MongoDB connection error`

### Solution A: Start MongoDB (Local)

```powershell
net start MongoDB
```

### Solution B: Use MongoDB Atlas (Cloud - Recommended)

1. Go to https://www.mongodb.com/cloud/atlas/register
2. Create free account
3. Create free cluster
4. Get connection string
5. Update `server/.env`:
   ```
   MONGODB_URI=mongodb+srv://username:password@cluster0.xxxxx.mongodb.net/restaurant
   ```

### Solution C: Ignore for Now
- Server will still run
- Database features won't work
- You can test the UI

---

## Problem 3: Cloudinary Not Configured

**Error:** Cloudinary upload fails

### Solution A: Configure Cloudinary

1. Sign up at https://cloudinary.com (free)
2. Get credentials from Dashboard
3. Update `server/.env`:
   ```
   CLOUDINARY_CLOUD_NAME=your_cloud_name
   CLOUDINARY_API_KEY=your_api_key
   CLOUDINARY_API_SECRET=your_api_secret
   ```

### Solution B: Skip for Now
- Server will work
- Image uploads won't work
- You can add menu items with placeholder images

---

## Problem 4: Module Not Found

**Error:** `Cannot find module 'xxx'`

### Solution:

```powershell
cd server
npm install
```

---

## ✅ QUICK FIX - All Issues

Run these commands in order:

```powershell
# 1. Kill process on port 5000
netstat -ano | findstr :5000
# Note the PID number, then:
taskkill /PID <PID> /F

# 2. Start MongoDB (if using local)
net start MongoDB

# 3. Make sure dependencies are installed
cd E:\Corsorprojects\Buildwebsite\server
npm install

# 4. Start server
npm start
```

---

## 🎯 Most Common Fix

**If port 5000 is busy, just change the port:**

1. Edit `server/.env`:
   ```
   PORT=5001
   ```

2. Edit `client/.env`:
   ```
   REACT_APP_API_URL=http://localhost:5001
   ```

3. Restart both servers

---

## ✅ After Fixing - Test Server

```powershell
cd E:\Corsorprojects\Buildwebsite\server
npm start
```

**Should see:**
```
MongoDB Connected
Server running on port 5000
```

If you see this, server is working! ✅


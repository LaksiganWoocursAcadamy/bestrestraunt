# 🎯 NEXT STEPS - What to Do Now

## ✅ What's Already Done:
- ✅ Environment files created (.env)
- ✅ Backend dependencies installed
- ✅ Frontend dependencies installed
- ✅ Node.js is installed

---

## 📝 STEP 1: Configure Cloudinary (Required)

**You need to update `server/.env` with your Cloudinary credentials:**

1. Go to https://cloudinary.com/users/register/free
2. Sign up for a FREE account (takes 2 minutes)
3. After login, go to Dashboard
4. You'll see:
   - **Cloud Name** (e.g., `dxyz123abc`)
   - **API Key** (e.g., `123456789012345`)
   - **API Secret** (e.g., `abcdefghijklmnopqrstuvwxyz`)

5. Open `server/.env` file and replace:
   ```
   CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
   CLOUDINARY_API_KEY=your_cloudinary_api_key
   CLOUDINARY_API_SECRET=your_cloudinary_api_secret
   ```
   
   With your actual values:
   ```
   CLOUDINARY_CLOUD_NAME=dxyz123abc
   CLOUDINARY_API_KEY=123456789012345
   CLOUDINARY_API_SECRET=abcdefghijklmnopqrstuvwxyz
   ```

**Note:** You can skip this for now if you just want to test without image uploads, but menu items won't be able to have images.

---

## 🗄️ STEP 2: Start MongoDB

**Option A: Local MongoDB (if installed)**
```powershell
net start MongoDB
```

**Option B: MongoDB Atlas (Cloud - Recommended)**
1. Go to https://www.mongodb.com/cloud/atlas/register
2. Create free account
3. Create a free cluster
4. Get connection string
5. Update `MONGODB_URI` in `server/.env`:
   ```
   MONGODB_URI=mongodb+srv://username:password@cluster0.xxxxx.mongodb.net/restaurant
   ```

**Option C: Skip for now** - You can test the app structure, but database features won't work.

---

## 🚀 STEP 3: Start Backend Server

Open a **NEW terminal/PowerShell window**:

```powershell
cd E:\Corsorprojects\Buildwebsite\server
npm start
```

✅ You should see:
```
MongoDB Connected
Server running on port 5000
```

**Keep this terminal open!**

---

## 🎨 STEP 4: Start Frontend Server

Open **ANOTHER NEW terminal/PowerShell window**:

```powershell
cd E:\Corsorprojects\Buildwebsite\client
npm start
```

✅ Browser should automatically open to http://localhost:3000

**Keep this terminal open too!**

---

## 🌱 STEP 5: (Optional) Add Sample Menu Items

Open **ANOTHER terminal**:

```powershell
cd E:\Corsorprojects\Buildwebsite\server
npm run seed
```

This adds: Idly, Pittu, Poori, Coffee, Dosai, Koththu, Rice, Tea

---

## 👤 STEP 6: Create Admin Account

1. On http://localhost:3000, click **"Login"**
2. Click **"Don't have an account? Sign up"**
3. Register with email: `admin@restaurant.com` and password
4. **Make this user admin:**

**Using MongoDB Compass (Easiest):**
1. Download MongoDB Compass: https://www.mongodb.com/products/compass
2. Connect to: `mongodb://localhost:27017` (or your Atlas connection)
3. Go to `restaurant` database → `users` collection
4. Find your user document
5. Click Edit
6. Change `"role": "customer"` to `"role": "admin"`
7. Save

**Or using Command Line:**
```powershell
mongosh
use restaurant
db.users.updateOne({email: "admin@restaurant.com"}, {$set: {role: "admin"}})
```

---

## ✅ STEP 7: Test Everything!

### As Customer:
- ✅ Browse menu on homepage
- ✅ Click "Add to Cart" on items
- ✅ Go to Cart, update quantities
- ✅ Proceed to Payment
- ✅ See QR code
- ✅ Print/Download bill

### As Admin:
- ✅ Login with admin account
- ✅ Click "Admin" in navbar
- ✅ Add/Edit/Delete menu items
- ✅ Go to "Sales" for reports
- ✅ Download PDF reports

---

## 🆘 Quick Troubleshooting

**"MongoDB connection error"**
→ Start MongoDB: `net start MongoDB` or use MongoDB Atlas

**"Port 5000 already in use"**
→ Change PORT in `server/.env` to 5001, update `client/.env` too

**"Cannot find module"**
→ Run `npm install` in the folder showing error

**Frontend shows "Network Error"**
→ Make sure backend is running on port 5000

---

## 📋 Summary - What You Need:

**3 Terminal Windows:**
1. **Terminal 1**: Backend (`cd server` → `npm start`)
2. **Terminal 2**: Frontend (`cd client` → `npm start`)
3. **Terminal 3**: (Optional) Seed menu (`cd server` → `npm run seed`)

**URLs:**
- Frontend: http://localhost:3000
- Backend API: http://localhost:5000

---

## 🎉 You're Ready!

Start with Step 1 (Cloudinary) or Step 2 (MongoDB), then proceed to start the servers!


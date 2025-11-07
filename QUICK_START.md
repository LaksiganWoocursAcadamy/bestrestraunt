# 🚀 QUICK START GUIDE

Follow these steps in order:

## 📋 STEP 1: Create Environment Files

### Create `server/.env` file with this content:
```
MONGODB_URI=mongodb://localhost:27017/restaurant
JWT_SECRET=restaurant_jwt_secret_key_2024_change_in_production
PORT=5000
CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret
```

**To get Cloudinary credentials:**
1. Visit https://cloudinary.com/users/register/free
2. Sign up for free account
3. Go to Dashboard
4. Copy: Cloud Name, API Key, API Secret
5. Paste them in server/.env

### Create `client/.env` file with this content:
```
REACT_APP_API_URL=http://localhost:5000
```

---

## 📦 STEP 2: Install Backend Dependencies

Open terminal in the project root and run:

```bash
cd server
npm install
```

Wait for installation to complete (1-2 minutes).

---

## 🗄️ STEP 3: Start MongoDB

**If using local MongoDB:**
- Windows: MongoDB should start automatically, or run `net start MongoDB`
- Mac/Linux: `mongod` or `brew services start mongodb-community`

**If using MongoDB Atlas (Cloud):**
- Update MONGODB_URI in server/.env with your Atlas connection string
- No need to start anything locally

---

## 🔧 STEP 4: Start Backend Server

In the terminal (still in server folder):

```bash
npm start
```

✅ You should see:
```
MongoDB Connected
Server running on port 5000
```

**Keep this terminal open!**

---

## 📦 STEP 5: Install Frontend Dependencies

Open a **NEW terminal window**:

```bash
cd client
npm install
```

Wait for installation (2-3 minutes first time).

---

## 🎨 STEP 6: Start Frontend

In the client terminal:

```bash
npm start
```

✅ Browser should open automatically to http://localhost:3000

---

## 🌱 STEP 7: (Optional) Add Sample Menu Items

Open a **NEW terminal window**:

```bash
cd server
npm run seed
```

This adds: Idly, Pittu, Poori, Coffee, Dosai, Koththu, Rice, Tea

---

## 👤 STEP 8: Create Admin Account

1. On the website (http://localhost:3000), click "Login"
2. Click "Don't have an account? Sign up"
3. Register with: `admin@restaurant.com` and a password
4. After registration, make this user admin:

**Using MongoDB Compass (Easiest):**
1. Open MongoDB Compass
2. Connect to: `mongodb://localhost:27017`
3. Go to `restaurant` database → `users` collection
4. Find your user document
5. Click Edit
6. Change `"role": "customer"` to `"role": "admin"`
7. Save

**Or using command line:**
```bash
mongosh
use restaurant
db.users.updateOne({email: "admin@restaurant.com"}, {$set: {role: "admin"}})
```

---

## ✅ STEP 9: Test Everything

### As Customer:
- ✅ Browse menu
- ✅ Add items to cart
- ✅ Go to cart, update quantities
- ✅ Proceed to payment
- ✅ See QR code
- ✅ Print/download bill

### As Admin:
- ✅ Login with admin account
- ✅ Click "Admin" in navbar
- ✅ Add/edit/delete menu items
- ✅ Click "Sales" to see reports
- ✅ Download PDF reports

---

## 🆘 Common Issues

**"MongoDB connection error"**
→ Start MongoDB: `net start MongoDB` (Windows)

**"Port 5000 already in use"**
→ Change PORT in server/.env to 5001, update client/.env too

**"Cannot find module"**
→ Run `npm install` in both server and client folders

**"Network Error" in browser**
→ Make sure backend is running on port 5000

---

## 📝 Summary

You need **3 terminal windows**:
1. **Terminal 1**: Backend server (`cd server` → `npm start`)
2. **Terminal 2**: Frontend (`cd client` → `npm start`)
3. **Terminal 3**: (Optional) Seed menu (`cd server` → `npm run seed`)

**URLs:**
- Frontend: http://localhost:3000
- Backend API: http://localhost:5000

---

## 🎉 You're Done!

The restaurant website is now running. Start adding menu items and taking orders!


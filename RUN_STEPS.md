# Step-by-Step Running Instructions

## Prerequisites Check
Before starting, make sure you have:
- ✅ Node.js installed (check with: `node --version`)
- ✅ MongoDB installed and running (or MongoDB Atlas account)
- ✅ Cloudinary account (for image uploads) - [Sign up free at cloudinary.com](https://cloudinary.com)

---

## STEP 1: Install Backend Dependencies

1. Open terminal/command prompt
2. Navigate to server folder:
   ```bash
   cd server
   ```
3. Install all packages:
   ```bash
   npm install
   ```
   ⏱️ This will take 1-2 minutes

---

## STEP 2: Configure Backend Environment

1. Open `server/.env` file
2. Update these values:
   - **MONGODB_URI**: 
     - Local: `mongodb://localhost:27017/restaurant`
     - Atlas: `mongodb+srv://username:password@cluster.mongodb.net/restaurant`
   - **JWT_SECRET**: Keep the default or change it
   - **CLOUDINARY_CLOUD_NAME**: Get from Cloudinary dashboard
   - **CLOUDINARY_API_KEY**: Get from Cloudinary dashboard
   - **CLOUDINARY_API_SECRET**: Get from Cloudinary dashboard

**To get Cloudinary credentials:**
1. Go to https://cloudinary.com and sign up/login
2. Go to Dashboard
3. Copy Cloud Name, API Key, and API Secret

---

## STEP 3: Start MongoDB

**Option A: Local MongoDB**
```bash
# Windows: Start MongoDB service
net start MongoDB

# Or if installed as service, it should auto-start
```

**Option B: MongoDB Atlas (Cloud)**
- No action needed, just use your connection string in .env

---

## STEP 4: Start Backend Server

1. Make sure you're in `server` folder:
   ```bash
   cd server
   ```
2. Start the server:
   ```bash
   pnpm start
   ```
   Or for development (auto-restart on changes):
   ```bash
   npm run dev
   ```

3. ✅ You should see:
   ```
   MongoDB Connected
   Server running on port 5000
   ```

4. Keep this terminal window open!

---

## STEP 5: (Optional) Seed Menu Items

Open a NEW terminal window:

1. Navigate to server:
   ```bash
   cd server
   ```
2. Run seed script:
   ```bash
   npm run seed
   ```
3. ✅ You should see: "Menu items seeded successfully"

This adds default menu items (Idly, Pittu, Poori, Coffee, Dosai, Koththu, Rice, Tea)

---

## STEP 6: Install Frontend Dependencies

1. Open a NEW terminal window
2. Navigate to client folder:
   ```bash
   cd client
   ```
3. Install all packages:
   ```bash
   npm install
   ```
   ⏱️ This will take 2-3 minutes (first time)

---

## STEP 7: Configure Frontend Environment

1. Open `client/.env` file
2. Make sure it has:
   ```
   REACT_APP_API_URL=http://localhost:5000
   ```
   (This should already be correct)

---

## STEP 8: Start Frontend Server

1. Make sure you're in `client` folder:
   ```bash
   cd client
   ```
2. Start React app:
   ```bash
   npm start
   ```
3. ✅ Browser should automatically open to http://localhost:3000
4. If not, manually open: http://localhost:3000

---

## STEP 9: Create Admin User

1. On the website, click "Login"
2. Click "Don't have an account? Sign up"
3. Register with email and password (e.g., admin@restaurant.com)
4. After registration, you need to make this user an admin:

**Option A: Using MongoDB Compass (GUI)**
1. Open MongoDB Compass
2. Connect to your database
3. Go to `restaurant` database → `users` collection
4. Find your user by email
5. Edit the document and change `role` from `"customer"` to `"admin"`

**Option B: Using MongoDB Shell**
```bash
mongosh
use restaurant
db.users.updateOne(
  { email: "your-email@example.com" },
  { $set: { role: "admin" } }
)
```

**Option C: Using Node.js script** (I can create this for you)

---

## STEP 10: Test the Application

### Test as Customer:
1. ✅ View menu items on homepage
2. ✅ Click "Add to Cart" on any item
3. ✅ Go to Cart page
4. ✅ Update quantities, remove items
5. ✅ Click "Proceed to Payment"
6. ✅ See QR code and bill
7. ✅ Click "Print Bill" or "Download PDF"

### Test as Admin:
1. ✅ Login with admin account
2. ✅ See "Admin" link in navbar
3. ✅ Go to Admin Dashboard
4. ✅ Click "Add Menu Item"
5. ✅ Upload image, fill form, save
6. ✅ Edit existing items
7. ✅ Delete items
8. ✅ Go to Sales Report
9. ✅ View monthly sales
10. ✅ Download PDF report

---

## Troubleshooting

### ❌ "MongoDB connection error"
- **Solution**: Make sure MongoDB is running
  - Windows: `net start MongoDB`
  - Check if MongoDB service is running in Services

### ❌ "Cannot find module" errors
- **Solution**: Make sure you ran `npm install` in both server and client folders

### ❌ "Port 5000 already in use"
- **Solution**: Change PORT in `server/.env` to another port (e.g., 5001)
- Also update `REACT_APP_API_URL` in `client/.env`

### ❌ "Cloudinary upload failed"
- **Solution**: Check Cloudinary credentials in `server/.env`
- Make sure API key and secret are correct

### ❌ Frontend shows "Network Error"
- **Solution**: 
  - Make sure backend is running on port 5000
  - Check `REACT_APP_API_URL` in `client/.env`
  - Restart frontend after changing .env

### ❌ "Cannot GET /api/..."
- **Solution**: Make sure backend server is running
- Check terminal for errors

---

## Quick Command Reference

**Terminal 1 (Backend):**
```bash
cd server
npm install
npm start
```

**Terminal 2 (Frontend):**
```bash
cd client
npm install
npm start
```

**Terminal 3 (Seed Menu - Optional):**
```bash
cd server
npm run seed
```

---

## Next Steps After Setup

1. ✅ Add your menu items through Admin Dashboard
2. ✅ Upload real images for menu items
3. ✅ Test the complete order flow
4. ✅ Generate sales reports
5. ✅ Customize styling if needed

---

## Need Help?

If you encounter any errors:
1. Check the terminal output for error messages
2. Verify all environment variables are set correctly
3. Make sure MongoDB is running
4. Ensure both servers are running (backend on 5000, frontend on 3000)


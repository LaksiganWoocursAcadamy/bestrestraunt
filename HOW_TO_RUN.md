# 🚀 HOW TO RUN THE WEBSITE - STEP BY STEP

## ⚠️ IMPORTANT: You Need 2 Terminal Windows Open!

---

## 📋 STEP 1: Open First Terminal (For Backend)

1. Open PowerShell or Command Prompt
2. Navigate to server folder:
   ```powershell
   cd E:\Corsorprojects\Buildwebsite\server
   ```

3. Start the backend server:
   ```powershell
   npm start
   ```

4. ✅ **You should see:**
   ```
   MongoDB Connected
   Server running on port 5000
   ```

5. **KEEP THIS TERMINAL OPEN!** ⚠️ Don't close it!

---

## 📋 STEP 2: Open Second Terminal (For Frontend)

1. Open a **NEW** PowerShell or Command Prompt window
2. Navigate to client folder:
   ```powershell
   cd E:\Corsorprojects\Buildwebsite\client
   ```

3. Start the frontend:
   ```powershell
   npm start
   ```

4. ✅ **Browser will automatically open** to http://localhost:3000
   - If not, manually open: http://localhost:3000

5. **KEEP THIS TERMINAL OPEN TOO!** ⚠️

---

## 🎯 That's It! Your Website is Running!

### You should see:
- ✅ Backend running on port 5000
- ✅ Frontend running on port 3000
- ✅ Website open in browser

---

## 🆘 If You See Errors:

### Error: "MongoDB connection error"
**Solution:**
1. Start MongoDB:
   ```powershell
   net start MongoDB
   ```
2. Or use MongoDB Atlas (cloud) - update `server/.env` with Atlas connection string

### Error: "Port 5000 already in use"
**Solution:**
1. Find what's using port 5000:
   ```powershell
   netstat -ano | findstr :5000
   ```
2. Or change port in `server/.env`:
   ```
   PORT=5001
   ```
3. Update `client/.env`:
   ```
   REACT_APP_API_URL=http://localhost:5001
   ```

### Error: "Cannot find module"
**Solution:**
1. Make sure you're in the correct folder
2. Run:
   ```powershell
   npm install
   ```

### Error: "Cloudinary configuration"
**Solution:**
- This is OK for now! The app will work, just image uploads won't work
- To fix: Get Cloudinary credentials and update `server/.env`

---

## 📝 Quick Commands Reference

### Terminal 1 (Backend):
```powershell
cd E:\Corsorprojects\Buildwebsite\server
npm start
```

### Terminal 2 (Frontend):
```powershell
cd E:\Corsorprojects\Buildwebsite\client
npm start
```

---

## ✅ What You Should See:

**Terminal 1 (Backend):**
```
MongoDB Connected
Server running on port 5000
```

**Terminal 2 (Frontend):**
```
Compiled successfully!
You can now view restaurant-client in the browser.
Local: http://localhost:3000
```

**Browser:**
- Website opens at http://localhost:3000
- You see the restaurant menu page

---

## 🎉 Success Checklist:

- [ ] Backend terminal shows "Server running on port 5000"
- [ ] Frontend terminal shows "Compiled successfully"
- [ ] Browser opens to http://localhost:3000
- [ ] You can see the website homepage

---

## 🔄 To Stop the Servers:

1. Go to each terminal window
2. Press `Ctrl + C`
3. Confirm with `Y` if asked

---

## 💡 Tips:

- **Keep both terminals open** while using the website
- If you close a terminal, the server stops
- To restart, just run `npm start` again in each folder
- The website auto-refreshes when you make code changes

---

## 🆘 Still Having Issues?

1. **Check Node.js is installed:**
   ```powershell
   node --version
   ```
   Should show: v14 or higher

2. **Check if ports are free:**
   - Port 5000 (backend)
   - Port 3000 (frontend)

3. **Make sure dependencies are installed:**
   ```powershell
   cd server
   npm install
   
   cd ../client
   npm install
   ```

4. **Check MongoDB is running** (if using local MongoDB):
   ```powershell
   net start MongoDB
   ```

---

## 📞 Need More Help?

Share the exact error message you see, and I'll help you fix it!


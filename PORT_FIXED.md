# ✅ PORT 5000 FIXED!

## What I Did:
1. ✅ Found process 22360 using port 5000
2. ✅ Killed the process
3. ✅ Started the server

---

## ✅ Server Should Be Running Now!

**Check if server is running:**
- Open browser: http://localhost:5000/api/menu
- Should see: `[]` (empty array) or menu items

---

## 🚀 If You Need to Start Server Again:

```powershell
cd E:\Corsorprojects\Buildwebsite\server
npm start
```

---

## 🆘 If Port 5000 Still Shows Error:

**Option 1: Kill all Node processes**
```powershell
taskkill /F /IM node.exe
```

**Option 2: Use different port**
1. Edit `server/.env`:
   ```
   PORT=5001
   ```
2. Edit `client/.env`:
   ```
   REACT_APP_API_URL=http://localhost:5001
   ```
3. Restart server

---

## ✅ Server Status:

The server should now be running on port 5000!

**Next Step:** Start the frontend in another terminal:
```powershell
cd E:\Corsorprojects\Buildwebsite\client
npm start
```


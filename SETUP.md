# Quick Setup Guide

## Prerequisites
- Node.js installed
- MongoDB running (local or Atlas)
- Cloudinary account

## Step 1: Backend Setup

1. Navigate to server directory:
```bash
cd server
```

2. Install dependencies:
```bash
npm install
```

3. Create `.env` file:
```env
MONGODB_URI=mongodb://localhost:27017/restaurant
JWT_SECRET=your_super_secret_jwt_key_change_this
PORT=5000
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret
```

4. Start the server:
```bash
npm start
# or for development
npm run dev
```

5. (Optional) Seed initial menu items:
```bash
npm run seed
```

## Step 2: Frontend Setup

1. Navigate to client directory:
```bash
cd client
```

2. Install dependencies:
```bash
npm install
```

3. Create `.env` file:
```env
REACT_APP_API_URL=http://localhost:5000
```

4. Start the development server:
```bash
npm start
```

## Step 3: Create Admin User

1. Register a user through the website
2. In MongoDB, update the user role:
```javascript
use restaurant
db.users.updateOne(
  { email: "your-email@example.com" },
  { $set: { role: "admin" } }
)
```

## Step 4: Access the Application

- Frontend: http://localhost:3000
- Backend API: http://localhost:5000

## Features to Test

1. **Menu Display**: View all menu items on homepage
2. **Add to Cart**: Click "Add to Cart" on any item
3. **Cart Management**: Update quantities, remove items, clear cart
4. **Checkout**: Proceed to payment page
5. **Payment**: View QR code and confirm payment
6. **Admin Dashboard**: Login as admin to manage menu
7. **Sales Report**: View monthly sales and download PDF

## Troubleshooting

### MongoDB Connection Error
- Ensure MongoDB is running
- Check MONGODB_URI in .env file

### Cloudinary Upload Error
- Verify Cloudinary credentials in .env
- Check if image format is supported (jpg, jpeg, png, webp)

### CORS Error
- Ensure backend is running on port 5000
- Check REACT_APP_API_URL in client/.env

### Authentication Issues
- Clear browser localStorage
- Check JWT_SECRET in server/.env
- Verify token is being sent in requests


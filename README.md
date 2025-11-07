# Restaurant Website - MERN Stack

A full-featured restaurant website built with MERN stack (MongoDB, Express, React, Node.js) with menu management, cart functionality, billing, payment, and sales reporting.

## Features

- **Menu Management**: CRUD operations for menu items with image uploads
- **Shopping Cart**: Add items to cart, update quantities, clear cart
- **Billing System**: Real-time bill calculation with tax
- **Payment**: QR code generation for payment
- **Bill Printing**: Print and download bills as PDF
- **Sales Reporting**: Monthly sales reports with table view and PDF export
- **Admin Dashboard**: Manage menu items (admin only)
- **Authentication**: Separate login for customers and admins
- **Responsive Design**: Mobile-first responsive design with Tailwind CSS

## Tech Stack

### Backend
- Node.js
- Express.js
- MongoDB with Mongoose
- JWT for authentication
- Cloudinary for image storage
- Multer for file uploads

### Frontend
- React 18
- React Router
- Axios for API calls
- Tailwind CSS for styling
- QRCode.react for QR code generation
- jsPDF for PDF generation
- React-to-print for bill printing

## Prerequisites

- Node.js (v14 or higher)
- MongoDB (local or MongoDB Atlas)
- Cloudinary account (for image storage)
- npm or yarn

## Installation

### 1. Clone the repository

```bash
cd Buildwebsite
```

### 2. Install Backend Dependencies

```bash
cd server
npm install
```

### 3. Install Frontend Dependencies

```bash
cd ../client
npm install
```

### 4. Environment Variables

#### Backend (.env file in server directory)

Create a `.env` file in the `server` directory:

```env
MONGODB_URI=mongodb://localhost:27017/restaurant
JWT_SECRET=your_jwt_secret_key_here_change_in_production
PORT=5000
CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret
```

#### Frontend (.env file in client directory)

Create a `.env` file in the `client` directory:

```env
REACT_APP_API_URL=http://localhost:5000
```

## Running the Application

### Start Backend Server

```bash
cd server
npm start
# or for development with auto-reload
npm run dev
```

The backend server will run on `http://localhost:5000`

### Start Frontend Development Server

```bash
cd client
npm start
```

The frontend will run on `http://localhost:3000`

## Default Menu Items

The application supports the following menu items:
- Idly
- Pittu
- Poori
- Coffee
- Dosai
- Koththu
- Rice
- Tea

You can add these items through the admin dashboard after logging in as an admin.

## Creating Admin User

To create an admin user, you can either:

1. Register a new user and manually change the role in MongoDB:
```javascript
db.users.updateOne(
  { email: "admin@example.com" },
  { $set: { role: "admin" } }
)
```

2. Or register with role in the registration API (if you modify the route to accept role parameter)

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login user
- `GET /api/auth/me` - Get current user (protected)

### Menu
- `GET /api/menu` - Get all menu items
- `GET /api/menu/:id` - Get single menu item
- `POST /api/menu` - Create menu item (admin only)
- `PUT /api/menu/:id` - Update menu item (admin only)
- `DELETE /api/menu/:id` - Delete menu item (admin only)

### Orders
- `POST /api/orders` - Create order (protected)
- `GET /api/orders/my-orders` - Get user orders (protected)
- `GET /api/orders` - Get all orders (admin only)
- `PUT /api/orders/:id/status` - Update order status (admin only)
- `GET /api/orders/sales/monthly` - Get monthly sales report (admin only)

### Admin
- `GET /api/admin/stats` - Get dashboard stats (admin only)

## Project Structure

```
Buildwebsite/
├── server/
│   ├── config/
│   │   └── database.js
│   ├── middleware/
│   │   ├── auth.js
│   │   ├── adminAuth.js
│   │   └── upload.js
│   ├── models/
│   │   ├── User.js
│   │   ├── MenuItem.js
│   │   ├── Order.js
│   │   └── Sales.js
│   ├── routes/
│   │   ├── auth.js
│   │   ├── menu.js
│   │   ├── orders.js
│   │   └── admin.js
│   ├── server.js
│   └── package.json
├── client/
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   ├── context/
│   │   ├── pages/
│   │   ├── App.js
│   │   └── index.js
│   └── package.json
└── README.md
```

## Features in Detail

### Menu Display
- Responsive grid layout showing all menu items
- Each item displays image, name, price, and description
- Click "Add to Cart" to add items to cart

### Shopping Cart
- View all items in cart
- Update quantities
- Remove items
- Clear entire cart
- Real-time bill calculation

### Payment
- QR code generation for payment
- Print bill functionality
- Download bill as PDF
- Payment confirmation

### Admin Dashboard
- Add new menu items with image upload
- Edit existing menu items
- Delete menu items
- View all menu items

### Sales Report
- Filter by year and month
- View sales summary (total sales, orders, average)
- Download sales report as PDF
- Table view of all sales

## Development

### Backend Development
- Uses nodemon for auto-reload during development
- Run `npm run dev` in server directory

### Frontend Development
- Uses Create React App
- Hot reload enabled by default
- Tailwind CSS for styling

## Production Build

### Build Frontend

```bash
cd client
npm run build
```

This creates an optimized production build in the `client/build` directory.

## License

This project is open source and available under the MIT License.

## Support

For issues and questions, please open an issue on the repository.


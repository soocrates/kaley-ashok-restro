# Everest Kitchen - Restaurant Management System

A complete 3-service architecture for a Nepalese restaurant in Munich, Germany. The system consists of a backend API service, customer-facing frontend, and admin dashboard.

## 🏗️ Architecture Overview

### Services:
1. **Backend Service** - Node.js/Express API with MySQL database
2. **Frontend Service** - React customer-facing website
3. **Admin Dashboard** - React admin panel for restaurant management

## 🚀 Quick Start

### Prerequisites
- Node.js 18+ 
- MySQL 8.0+
- npm or yarn

### 1. Backend Service Setup

```bash
cd backend

# Install dependencies
npm install

# Setup environment variables
cp .env.example .env
# Edit .env with your database credentials and JWT secret

# Setup database
npx prisma migrate dev
npx prisma generate
npx prisma db seed

# Start development server
npm run dev
```

The backend will run on `http://localhost:5000`

### 2. Frontend Service Setup

```bash
cd frontend

# Install dependencies
npm install

# Create environment file
echo "VITE_API_URL=http://localhost:5000/api" > .env

# Start development server
npm run dev
```

The frontend will run on `http://localhost:3000`

### 3. Admin Dashboard Setup

```bash
cd admin-dashboard

# Install dependencies
npm install

# Create environment file
echo "VITE_API_URL=http://localhost:5000/api" > .env

# Start development server
npm run dev
```

The admin dashboard will run on `http://localhost:3001`

## 📚 API Documentation

Once the backend is running, visit `http://localhost:5000/api-docs` for complete Swagger API documentation.

## 🔐 Default Credentials

### Admin Dashboard:
- **Email:** admin@everestkitchen.de
- **Password:** admin123

### Manager Account:
- **Email:** manager@everestkitchen.de  
- **Password:** manager123

### Customer Accounts:
- **Email:** anna@example.com / **Password:** customer123
- **Email:** david@example.com / **Password:** customer123

## 🎯 Features

### Backend Service
- **Authentication & Authorization** - JWT-based with role-based access control
- **User Management** - Customer, Staff, Manager, Admin roles
- **Menu Management** - CRUD operations for menu items
- **Order Management** - Complete order lifecycle tracking
- **Review System** - Customer review moderation
- **Analytics** - Revenue, customer, and performance analytics
- **File Upload** - Image upload for menu items
- **Activity Logging** - Comprehensive audit trail
- **API Documentation** - Swagger/OpenAPI integration

### Frontend Service
- **Customer Registration/Login** - Account management
- **Menu Browsing** - Advanced filtering and search
- **Shopping Cart** - Persistent cart with local storage
- **Order Placement** - Pickup and delivery options
- **Order Tracking** - Real-time order status updates
- **User Profile** - Account and order history management
- **Responsive Design** - Mobile-first approach
- **Dark/Light Mode** - Theme switching capability

### Admin Dashboard
- **Dashboard Overview** - Key metrics and recent activity
- **Order Management** - Real-time order tracking and status updates
- **Menu Management** - Complete menu item CRUD operations
- **User Management** - Customer and staff account management
- **Review Moderation** - Approve/reject customer reviews
- **Analytics & Reports** - Revenue trends and customer insights
- **Settings Management** - Restaurant configuration
- **Activity Logs** - System audit trail

## 🗄️ Database Schema

### Key Tables:
- **users** - Customer and staff accounts
- **menu_items** - Restaurant menu with categories and pricing
- **orders** - Order tracking with items and status
- **order_items** - Individual items within orders
- **reviews** - Customer reviews with moderation status
- **activity_logs** - System activity audit trail
- **settings** - Restaurant configuration

## 🔧 Environment Variables

### Backend (.env)
```env
DATABASE_URL="mysql://username:password@localhost:3306/everest_kitchen"
JWT_SECRET="your-super-secret-jwt-key"
JWT_EXPIRES_IN="7d"
PORT=5000
NODE_ENV=development
FRONTEND_URL="http://localhost:3000"
ADMIN_URL="http://localhost:3001"
```

### Frontend (.env)
```env
VITE_API_URL=http://localhost:5000/api
```

### Admin Dashboard (.env)
```env
VITE_API_URL=http://localhost:5000/api
```

## 🚀 Production Deployment

### Backend
```bash
npm run build
npm start
```

### Frontend & Admin Dashboard
```bash
npm run build
# Deploy dist/ folder to your hosting service
```

## 📱 API Endpoints

### Authentication
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `GET /api/auth/me` - Get current user profile
- `POST /api/auth/logout` - User logout

### Menu
- `GET /api/menu` - Get all menu items
- `GET /api/menu/:id` - Get menu item by ID
- `POST /api/menu` - Create menu item (Admin/Manager)
- `PUT /api/menu/:id` - Update menu item (Admin/Manager)
- `DELETE /api/menu/:id` - Delete menu item (Admin)

### Orders
- `GET /api/orders` - Get orders (filtered by user role)
- `POST /api/orders` - Create new order
- `GET /api/orders/:id` - Get order by ID
- `PATCH /api/orders/:id/status` - Update order status (Staff+)

### Users
- `GET /api/users` - Get all users (Admin/Manager)
- `GET /api/users/:id` - Get user by ID
- `PATCH /api/users/:id/role` - Update user role (Admin)
- `PATCH /api/users/:id/status` - Update user status (Admin/Manager)

### Reviews
- `GET /api/reviews` - Get all reviews
- `POST /api/reviews` - Create review
- `PATCH /api/reviews/:id/status` - Update review status (Admin/Manager)

### Analytics
- `GET /api/analytics/dashboard` - Dashboard metrics (Staff+)
- `GET /api/analytics/revenue` - Revenue analytics (Staff+)
- `GET /api/analytics/customers` - Customer analytics (Staff+)

## 🛡️ Security Features

- **JWT Authentication** - Secure token-based authentication
- **Role-Based Access Control** - Granular permissions system
- **Rate Limiting** - API request throttling
- **Input Validation** - Joi schema validation
- **SQL Injection Protection** - Prisma ORM with parameterized queries
- **CORS Configuration** - Cross-origin request security
- **Helmet.js** - Security headers
- **Password Hashing** - bcrypt encryption

## 🧪 Testing

```bash
# Backend tests
cd backend
npm test

# Frontend tests  
cd frontend
npm test

# Admin dashboard tests
cd admin-dashboard
npm test
```

## 📊 Monitoring & Logging

- **Winston Logger** - Structured logging with file rotation
- **Activity Logging** - User action audit trail
- **Error Tracking** - Comprehensive error handling
- **Performance Monitoring** - Request timing and metrics

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

For support, email support@everestkitchen.de or create an issue in the repository.

---

**Everest Kitchen** - Bringing authentic Nepalese flavors to Munich! 🏔️🍽️
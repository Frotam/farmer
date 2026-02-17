# Marketplace Platform for Farmers

Welcome to our **Farmer Marketplace** - a direct-to-consumer platform connecting farmers with customers! This platform empowers farmers to sell their products (fresh produce, dairy, handmade goods) directly to consumers without intermediaries, while providing a seamless communication channel through integrated chat functionality.

## 🌟 Key Features

- **Direct Sales**: Farmers can list and manage their products without intermediaries
- **Real-time Chat**: Buyers and sellers communicate directly using Socket.IO
- **Secure Authentication**: Passport.js with bcrypt password hashing
- **Product Management**: Easy product listing and inventory management
- **User Roles**: Dedicated interfaces for farmers and buyers
- **Email Notifications**: Automated email service for bid selections and updates
- **Responsive Design**: EJS templating with modern CSS styling

---

## 🛠️ Technologies Used

### Backend
- **Express.js** (v4.21.2) - Web application framework
- **Node.js** - JavaScript runtime with file watching (`--watch` mode)
- **MongoDB** (Mongoose v8.13.0) - NoSQL database for data persistence

### Authentication & Security
- **Passport.js** (v0.7.0) - Authentication middleware
- **Passport-Local** (v1.0.0) - Local strategy for email/password auth
- **Passport-Local-Mongoose** (v8.0.0) - Mongoose plugin for user management
- **bcrypt** (v5.1.1) - Password hashing and security
- **JWT** (jsonwebtoken v9.0.2) - Token-based authentication
- **Cookie-Parser** (v1.4.7) - Cookie handling

### Real-time Communication
- **Socket.IO** (v4.8.1) - Real-time bidirectional communication for chat

### Frontend
- **EJS** (v3.1.10) - Templating engine
- **EJS-Mate** (v4.0.0) - Enhanced EJS features
- **CSS** - Custom styling (2.2% of codebase)

### Session & Flash Messages
- **Express-Session** (v1.18.1) - Session management
- **Connect-Flash** (v0.1.1) - Flash message support

### File Handling
- **Multer** (v1.4.5) - File upload middleware
- **Method-Override** (v3.0.0) - HTTP method override support

### Utilities
- **dotenv** (v16.5.0) - Environment variable management
- **Nodemailer** (v6.10.1) - Email service for notifications

---

## 📁 Project Structure

```
farmer/
├── app.js                 # Main application entry point
├── middleware.js          # Custom middleware functions
├── package.json          # Project dependencies and scripts
├── package-lock.json     # Locked dependency versions
├── .env                  # Environment variables (not committed)
├── .gitignore            # Git ignore rules
│
├── models/               # MongoDB data models
│   ├── user.js          # User schema (Farmer & Buyer)
│   ├── listing.js       # Product listing schema
│   └── chat.js          # Chat messages schema
│
├── routes/              # Express route handlers
│   ├── auth.js          # Authentication routes (register, login, logout)
│   ├── buyer.js         # Buyer-specific routes
│   ├── seller.js        # Seller-specific routes
│   └── chat.js          # Chat routes and socket handlers
│
├── views/               # EJS template files
│   ├── layouts/         # Layout templates
│   ├── auth/            # Authentication pages
│   ├── buyer/           # Buyer interface
│   ├── seller/          # Seller interface
│   └── chat/            # Chat interface
│
├── public/              # Static assets
│   ├── css/             # Stylesheets
│   ├── js/              # Client-side JavaScript
│   └── images/          # Image assets
│
├── services/            # Business logic services
│   ├── jwtcreater.js   # JWT token creation and validation
│   ├── cokkiechecker.js # Cookie verification
│   ├── emailService.js  # Email notification service
│   └── chatService.js   # Chat message handling
│
├── utils/               # Utility functions
│   └── ExpressError.js  # Custom error handling
│
└── init/               # Initialization scripts (seeds, setup)
```

---

## 🚀 Getting Started

### Prerequisites
- **Node.js** (v14 or higher)
- **npm** (v6 or higher)
- **MongoDB** (running locally on `mongodb://127.0.0.1:27017` or remote Atlas)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Frotam/farmer.git
   cd farmer
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up environment variables**
   Create a `.env` file in the root directory:
   ```env
   PORT=3000
   MONGODB_URL=mongodb://127.0.0.1:27017/farmer
   SESSION_SECRET=your_session_secret_key_here
   JWT_SECRET=your_jwt_secret_key_here
   
   # Email Service Configuration
   EMAIL_SERVICE=gmail
   EMAIL_USER=your_email@gmail.com
   EMAIL_PASSWORD=your_app_password
   
   # Optional
   NODE_ENV=development
   ```

4. **Start the application**
   ```bash
   npm start
   ```
   The app will start with file watching enabled. Visit `http://localhost:3000`

---

## 🔧 Project Initialization

### Database Setup
The application uses MongoDB. On first run:
1. Ensure MongoDB is running locally or update `MONGODB_URL` in `.env` for Atlas
2. Mongoose will automatically create collections when models are first accessed

### User Registration
1. Navigate to `/auth/register`
2. Create an account as either a **Farmer** or **Buyer**
3. Passwords are securely hashed using bcrypt

### Farmer Workflow
1. Sign up as a farmer
2. Navigate to seller dashboard
3. Add products with details (name, price, description, images)
4. Manage product listings and inventory
5. Chat with interested buyers

### Buyer Workflow
1. Sign up as a buyer
2. Browse available products
3. Contact farmers via integrated chat
4. Negotiate prices directly
5. Arrange purchases and delivery

---

## 🔐 Security Features

- **Password Hashing**: bcrypt with salt rounds
- **JWT Tokens**: Secure token-based authentication
- **Session Management**: Secure session cookies with expiration
- **CSRF Protection**: Via method-override and form handling
- **Input Validation**: Data validation in routes and models
- **Email Verification**: Automated email notifications (optional)

---

## 💬 Real-time Chat

The platform uses **Socket.IO** for real-time chat:
- Bidirectional communication between buyers and sellers
- Message persistence in MongoDB
- Real-time notification delivery
- User presence tracking

---

## 📧 Email Notifications

Nodemailer integration sends emails for:
- Bid/offer selection confirmations
- User registration confirmations
- Important account updates
- Chat notifications (optional)

---

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---


## 🙏 Acknowledgments

- Express.js community
- Mongoose documentation
- Socket.IO for real-time features
- Passport.js for authentication

Happy Farming! 🌾

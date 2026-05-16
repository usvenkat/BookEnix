# 📚 BookEnix - E-Commerce Book Store

A modern, full-stack e-commerce platform specifically designed for buying and selling books. Built with the **MERN** (MongoDB, Express, React, Node.js) stack and integrated with Razorpay for seamless payment processing.

**Live Demo:** [BookEnix](https://bookztron-dev-branch.netlify.app/)

---

## ✨ Features

### User Authentication & Management
- 🔐 User signup and login with JWT authentication
- 📝 User profile management
- 🔒 Secure password handling

### Product Management
- 📖 Comprehensive product listing page
- 🏷️ Category-based filtering (Book genres)
- 📚 New arrivals section
- ⭐ Average product ratings

### Shopping Features
- 🛒 **Cart Management**
  - Add/remove items from cart
  - Update item quantities
  - Persistent cart storage
  - Add items to wishlist from cart

- ❤️ **Wishlist Features**
  - Add/remove items from wishlist
  - Move items to cart
  - Manage favorites

- 🔍 **Advanced Filters & Search**
  - Sort by price (low to high, high to low)
  - Filter by price range (min/max)
  - Filter by genre categories
  - Filter by product rating
  - Filter by stock availability
  - Filter by delivery speed
  - Clear all filters option
  - Search by book name or author name
  - Pagination for browsing

### Checkout & Payment
- 💳 **Razorpay Payment Integration** for secure transactions
- 📋 Order summary and review
- 🧾 Invoice generation

### Order Management
- 📦 Complete orders history
- 🔄 Order status tracking
- 📱 Order details page

### UI/UX Features
- 🎨 Custom Toast Notifications (Success, Error, Warning, Information)
- 📄 Responsive design for all devices
- ⚡ Fast and smooth animations
- 🎯 Intuitive navigation with Navbar and Sidebar

---

## 🛠️ Tech Stack

### Frontend
- **React** 17.0.2 - UI library
- **React Router DOM** 6.2.2 - Client-side routing
- **React Icons** 4.3.1 - Icon library
- **React Lottie** 1.2.3 - Animation library
- **Axios** 1.12.2 - HTTP client

### Backend
- **Node.js** - JavaScript runtime
- **Express.js** 4.17.3 - Web framework
- **MongoDB** - NoSQL database
- **JWT** 9.0.2 - User authentication

### Testing
- **Jest** - Testing framework
- **React Testing Library** 12.1.3 - Component testing

### Utilities
- **Razorpay SDK** - Payment gateway
- **PropTypes** 15.8.1 - Type checking

---

## 📋 Prerequisites

Before running this project, ensure you have:
- **Node.js** (v14 or higher) - [Download](https://nodejs.org/)
- **npm** or **yarn** - Comes with Node.js
- **MongoDB** running locally or cloud connection string
- **Razorpay Account** for payment integration

---

## 🚀 Installation

### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/BookEnix.git
cd BookEnix
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Environment Variables
Create a `.env` file in the root directory with the following variables:
```env
# Frontend
REACT_APP_API_URL=http://localhost:5000
REACT_APP_RAZORPAY_KEY_ID=your_razorpay_key_here

# Backend (if deployed separately)
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
RAZORPAY_KEY_ID=your_razorpay_key
RAZORPAY_KEY_SECRET=your_razorpay_secret
```

### 4. Install Backend Dependencies (if applicable)
If backend is in a separate folder:
```bash
cd backend
npm install
```

---

## 💻 Usage

### Development Mode

#### Start Frontend Development Server
```bash
npm start
```
The app will run at `http://localhost:3000`

#### Start Backend Server (if separate)
```bash
cd backend
npm start
```
Backend will run at `http://localhost:5000`

### Building for Production

#### Build Frontend
```bash
npm run build
```
Creates an optimized production build in the `build/` directory.

#### Build Backend (if applicable)
```bash
cd backend
npm run build
```

### Running Tests
```bash
npm test
```

---

## 📁 Project Structure

```
BookEnix/
├── src/                          # React source code
│   ├── Components/               # Reusable React components
│   │   ├── Card/                # Product card component
│   │   ├── Footer/              # Footer component
│   │   ├── GenreCards/          # Genre selection cards
│   │   ├── HorizontalCard/      # Horizontal product display
│   │   ├── Navbar/              # Navigation bar
│   │   ├── NewArrivals/         # New arrivals section
│   │   ├── Pagination/          # Pagination component
│   │   ├── ProductOrderCard/    # Order product display
│   │   ├── ShoppingBill/        # Shopping cart bill
│   │   ├── Sidebar/             # Filter sidebar
│   │   ├── Toast/               # Toast notifications
│   │   ├── WishlistProductCard/ # Wishlist product display
│   │   └── ...
│   ├── Context/                 # React Context for state management
│   │   ├── cart-context.js
│   │   ├── user-login-context.js
│   │   ├── wishlist-context.js
│   │   ├── product-context.js
│   │   └── ...
│   ├── Pages/                   # Page components
│   │   ├── AuthenticationPages/ # Login & Signup pages
│   │   ├── Cart/                # Cart page
│   │   ├── Home/                # Home/Landing page
│   │   ├── Orders/              # Orders history page
│   │   ├── ProductPage/         # Single product details
│   │   ├── Shop/                # Shop/Browse products
│   │   └── Wishlist/            # Wishlist page
│   ├── UtilityFunctions/        # Helper functions
│   │   └── loadRazorpayScript.js
│   ├── App.js                   # Main App component
│   ├── App.css                  # App styles
│   ├── index.js                 # React entry point
│   └── index.css                # Global styles
├── public/                       # Static public assets
│   ├── index.html               # HTML template
│   ├── manifest.json            # PWA manifest
│   ├── favicon.ico              # Favicon
│   ├── robots.txt               # SEO robots file
│   └── ...
├── assets/                       # Media and static files
│   ├── icons/                   # Icon files (JSON, SVG)
│   ├── images/                  # Product images
│   └── screenshots/             # Documentation screenshots
├── .gitignore                    # Git ignore rules
├── package.json                  # Project dependencies
├── package-lock.json            # Dependency lock file
└── README.md                     # This file
```

---

## 🔌 API Endpoints

### User Endpoints
- `POST /api/users/signup` - User registration
- `POST /api/users/login` - User login
- `GET /api/users/profile` - Get user profile
- `PUT /api/users/profile` - Update user profile

### Product Endpoints
- `GET /api/products` - Get all products
- `GET /api/products/:id` - Get product details
- `GET /api/products/search?q=query` - Search products

### Cart Endpoints
- `GET /api/cart` - Get user cart
- `POST /api/cart/add` - Add item to cart
- `PUT /api/cart/:id` - Update cart item
- `DELETE /api/cart/:id` - Remove from cart

### Order Endpoints
- `GET /api/orders` - Get user orders
- `POST /api/orders/create` - Create new order
- `GET /api/orders/:id` - Get order details

---

## 🔐 Security Features

- ✅ JWT token-based authentication
- ✅ Password hashing with bcryptjs
- ✅ Secure payment processing with Razorpay
- ✅ CORS enabled for cross-origin requests
- ✅ Environment variable protection

---

## 🤝 Contributing

Contributions are welcome! Here's how to get started:

### 1. Fork the Repository
Click the "Fork" button on GitHub to create your copy.

### 2. Clone Your Fork
```bash
git clone https://github.com/yourusername/BookEnix.git
cd BookEnix
```

### 3. Create a Feature Branch
```bash
git checkout -b feature/your-feature-name
```

### 4. Make Your Changes
- Implement your feature
- Add meaningful commit messages (present tense)
- Write clean, well-commented code

### 5. Push to Your Fork
```bash
git push origin feature/your-feature-name
```

### 6. Create a Pull Request
- Open a PR against the `development` branch
- Describe your changes clearly
- Link any related issues

### 7. Code Review
- Wait for maintainer review
- Make necessary changes if requested
- Merge once approved

---

## 📝 Commit Message Guidelines

Always write commit messages in **present tense**:
- ✅ `Add user authentication feature`
- ✅ `Fix cart item quantity update bug`
- ✅ `Improve product filtering performance`
- ❌ `Added user authentication`
- ❌ `Fixed cart bug`

---

## 🐛 Issue Reporting

Found a bug? Have a suggestion? [Create an Issue](https://github.com/yourusername/BookEnix/issues)

When reporting issues, please include:
- Clear description of the problem
- Steps to reproduce
- Expected vs actual behavior
- Screenshots (if applicable)
- Browser/OS information

---

## 📄 License

This project is licensed under the **ISC License** - see the LICENSE file for details.

---

## 👥 Authors

- **Naman Saxena** - Project Creator & Lead Developer

---

## 🙏 Acknowledgments

- React.js community for amazing tools and resources
- Razorpay for payment integration
- MongoDB for database solutions
- All contributors who helped improve this project

---

## 📞 Support

Need help? Have questions?
- 📧 Email: [Create an Issue](https://github.com/yourusername/BookEnix/issues)
- 💬 GitHub Discussions: [Join our discussions](https://github.com/yourusername/BookEnix/discussions)
- 🌐 Live Demo: [BookEnix](https://bookztron-dev-branch.netlify.app/)

---

## 🚀 Future Enhancements

- [ ] Admin dashboard for inventory management
- [ ] Advanced analytics and reporting
- [ ] User reviews and ratings system
- [ ] Email notifications
- [ ] Push notifications
- [ ] Mobile app (React Native)
- [ ] Multiple payment gateway integration
- [ ] Inventory management system
- [ ] Recommendation engine
- [ ] Advanced search with filters

---

**Happy Coding! 🎉**

If you found this project helpful, consider giving it a ⭐ on GitHub!

# POS System- Frontend

[![React](https://img.shields.io/badge/React-19.2.1-blue.svg)](https://reactjs.org/)
[![Vite](https://img.shields.io/badge/Vite-7.2.4-646CFF.svg)](https://vitejs.dev/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-4.1.17-38B2AC.svg)](https://tailwindcss.com/)
[![Axios](https://img.shields.io/badge/Axios-1.13.2-5A29E4.svg)](https://axios-http.com/)

A modern, responsive React-based frontend application for managing products and users through a comprehensive admin dashboard. Built with cutting-edge technologies for optimal performance and developer experience, featuring role-based authentication, real-time data management, and intuitive user interfaces.

## ✨ Features

- **🔐 Authentication & Authorization**: Secure JWT-based login with granular role-based access control (Admin, Super Staff, Staff)
- **👥 User Management**: Complete CRUD operations for users with advanced search, filtering, pagination, and bulk actions
- **📦 Product Management**: Full product lifecycle management with search, categorization, and inventory tracking
- **📊 Admin Dashboard**: Comprehensive analytics dashboard with key metrics and insights
- **📱 Responsive Design**: Mobile-first approach ensuring seamless experience across all devices
- **🔄 Real-time Updates**: Live data synchronization with backend APIs using Axios interceptors
- **🎨 Modern UI**: Clean, intuitive interface built with Tailwind CSS 4
- **⚡ Performance**: Optimized with Vite's fast HMR and code splitting
- **🛡️ Security**: Protected routes, input validation, and secure API communication

## 🛠️ Tech Stack

### Core Framework
- **React 19.2.1** - Latest React with concurrent features and improved performance
- **Vite 7.2.4** - Next-generation frontend tooling for fast development

### Styling & UI
- **Tailwind CSS 4.1.17** - Utility-first CSS framework
- **PostCSS 8.5.6** - CSS processing tool
- **Autoprefixer 10.4.22** - Automatic CSS vendor prefixing

### Routing & State
- **React Router DOM 7.10.1** - Declarative routing for React
- **React Context** - State management for authentication

### HTTP & API
- **Axios 1.13.2** - Promise-based HTTP client with interceptors

### Development & Quality
- **ESLint 9.39.2** - Code linting with React-specific rules
- **Prettier 3.7.4** - Code formatting
- **TypeScript Types** - Type definitions for React ecosystem

## 🚀 Installation

### Prerequisites
- Node.js (v18 or higher)
- npm or yarn package manager
- Backend API server running (default: http://127.0.0.1:8000/api/)

### Setup Steps

1. **Clone the repository:**
   ```bash
   git clone <repository-url>
   cd frontend
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Configure environment:**
   Update `src/config.js` with your API endpoint:
   ```javascript
   export const API_BASE_URL = "http://127.0.0.1:8000/api/";
   ```

4. **Start development server:**
   ```bash
   npm run dev
   ```

5. **Access the application:**
   Open [http://localhost:5173](http://localhost:5173) in your browser.

## 📋 Usage

### Authentication
- Navigate to `/login` and authenticate with your credentials
- The app supports three user roles with different permission levels

### Admin Panel Navigation
- **Dashboard**: `/admin` - Overview and analytics
- **User Management**: `/admin/users` - User CRUD operations
- **Product Management**: `/admin/products` - Product CRUD operations
- **Profile**: `/change-password` - Password management

### Role-Based Permissions
- **Admin**: Full access to all features and user management
- **Super Staff**: Product management + limited user access
- **Staff**: Read-only access to users and products

## 📁 Project Structure

```
frontend/
├── public/
│   └── vite.svg              # Vite logo
├── src/
│   ├── assets/               # Static assets (images, icons)
│   ├── auth/                 # Authentication components & utilities
│   │   ├── Login.jsx         # Login page component
│   │   ├── ProtectedRoute.jsx # Route protection wrapper
│   │   └── roleUtils.js      # Role-based permission utilities
│   ├── components/           # Reusable UI components
│   │   ├── common/           # Shared components
│   │   │   └── Pagination.jsx # Pagination component
│   │   ├── layout/           # Layout components
│   │   │   ├── AdminLayout.jsx # Admin dashboard layout
│   │   │   ├── Breadcrumbs.jsx # Navigation breadcrumbs
│   │   │   └── Header.jsx    # Application header
│   │   └── tables/           # Data table components
│   │       ├── UserTable.jsx # User data table
│   │       └── ProductTable.jsx # Product data table
│   ├── context/              # React context providers
│   │   └── AuthContext.jsx   # Authentication context
│   ├── pages/                # Page components
│   │   ├── admin/            # Admin-specific pages
│   │   │   ├── Dashboard.jsx # Admin dashboard
│   │   │   ├── Products.jsx  # Product management page
│   │   │   ├── ProductForm.jsx # Product create/edit form
│   │   │   ├── Users.jsx     # User management page
│   │   │   └── UserForm.jsx  # User create/edit form
│   │   ├── ChangePassword.jsx # Password change page
│   │   └── CustomerBlank.jsx # Customer landing page
│   ├── services/             # API service modules
│   │   ├── api.js            # Base API configuration
│   │   ├── auth.service.js   # Authentication API calls
│   │   ├── user.service.js   # User management API calls
│   │   └── product.service.js # Product management API calls
│   ├── App.jsx               # Main application component
│   ├── App.css               # Global styles
│   ├── config.js             # Application configuration
│   ├── index.css             # Tailwind CSS imports
│   └── main.jsx              # Application entry point
├── index.html                # HTML template
├── package.json              # Dependencies and scripts
├── tailwind.config.js        # Tailwind CSS configuration
├── postcss.config.js         # PostCSS configuration
├── eslint.config.js          # ESLint configuration
└── README.md                 # Project documentation
```

## 🧪 Testing

Run the test suite to ensure all features work correctly:

```bash
# Run linting
npm run lint

# Build for production (tests build integrity)
npm run build

# Preview production build
npm run preview
```

### Manual Testing Checklist
- [ ] User authentication and role-based redirects
- [ ] CRUD operations for users and products
- [ ] Search and pagination functionality
- [ ] Responsive design on mobile devices
- [ ] Form validation and error handling

## 🚀 Deployment

### Build for Production
```bash
npm run build
```

The built files will be in the `dist/` directory, ready for deployment to any static hosting service.

### Environment Variables
For production deployment, ensure the API_BASE_URL in `src/config.js` points to your production backend.

## 🔌 API Integration

The application communicates with a REST API backend. Key endpoints include:

- `POST /api/auth/login` - User authentication
- `GET /api/users` - List users (paginated)
- `POST /api/users` - Create user
- `PUT /api/users/:id` - Update user
- `DELETE /api/users/:id` - Delete user
- `GET /api/products` - List products (paginated)
- `POST /api/products` - Create product
- `PUT /api/products/:id` - Update product
- `DELETE /api/products/:id` - Delete product

## 📝 Available Scripts

- `npm run dev` - Start development server with hot reload
- `npm run build` - Build application for production
- `npm run preview` - Preview production build locally
- `npm run lint` - Run ESLint for code quality checks

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Guidelines
- Follow React best practices and hooks guidelines
- Use Tailwind CSS utility classes for styling
- Ensure responsive design for all new components
- Write clean, readable, and well-documented code
- Test all new features thoroughly


---

**Built with ❤️ using React & Vite**

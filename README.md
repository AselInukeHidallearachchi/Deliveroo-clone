
# 🚀 Deliveroo Clone - React Food Delivery App

<img width="80%" alt="Deliveroo Clone Screenshot" src="https://github.com/user-attachments/assets/b376c7f6-4f93-4109-8036-6abc6c4b281a" />

A modern, responsive Deliveroo clone built with **React.js** that replicates the core functionality of a food delivery platform. This application features a beautiful UI/UX, user authentication, restaurant browsing, menu management, and a shopping cart system.

## ✨ Features

### 🔐 Authentication System
- **Email/Password Login**: Secure user authentication
- **Firebase Integration**: Google Sign-in support (configurable)
- **Protected Routes**: Private route protection for authenticated users
- **Redux State Management**: Persistent user session management

### 🍕 Restaurant & Menu Management
- **Dynamic Restaurant Page**: Featured restaurant with detailed information
- **Menu Categories**: Multiple food categories (Bundles, Salads, Hot Powder Bowls, Vegan Menu, Rainbow Wraps, Burgers, Snacks & Sides)
- **Product Details**: Detailed product information with allergen information
- **Customizable Orders**: Interactive product customization options
- **Smart Navigation**: Category-based menu navigation with smooth scrolling

### 🛒 Shopping Experience
- **Shopping Cart**: Add/remove items with basket management
- **Product Customization**: Choose bases, ingredients, and options
- **Responsive Design**: Mobile-first responsive design
- **Material-UI Components**: Modern, accessible UI components

### 🎨 User Interface
- **Professional Design**: Clean, modern interface inspired by Deliveroo
- **Interactive Components**: Smooth animations and transitions
- **Category Filtering**: Easy menu browsing with category chips
- **Mobile Responsive**: Optimized for all device sizes

## 🛠️ Technology Stack

### Frontend
- **React 18.2.0** - Modern React with hooks and functional components
- **React Router DOM 6.21.2** - Client-side routing and navigation
- **Material-UI 5.15.5** - Component library for consistent design
- **Redux Toolkit 2.1.0** - State management for user authentication and app state
- **React Bootstrap 2.9.2** - Additional UI components and layout

### Backend & Authentication
- **Firebase 10.7.1** - Authentication and backend services
- **Google Authentication** - OAuth integration for easy sign-up/sign-in

### Development & Build Tools
- **Create React App 5.0.1** - Development environment and build tooling
- **Bootstrap 5.3.2** - CSS framework for responsive design
- **ESLint** - Code linting and quality assurance

## 🚀 Getting Started

### Prerequisites
- **Node.js** (version 14.0.0 or higher)
- **npm** or **yarn** package manager
- **Git** for version control

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/AselInukeHidallearachchi/Deliveroo-clone.git
   cd Deliveroo-clone
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Start the development server**
   ```bash
   npm start
   ```

4. **Open your browser**
   Navigate to [http://localhost:3000](http://localhost:3000) to view the application.

## 🔑 Demo Credentials

For testing the authentication system, use these demo credentials:

- **Email**: `user@gmail.com`
- **Password**: `1234`

## 📱 Available Scripts

### Development
```bash
npm start          # Starts the development server on http://localhost:3000
npm test           # Launches the test runner in interactive watch mode
npm run build      # Builds the app for production to the `build` folder
npm run eject      # Ejects from Create React App (one-way operation)
```

### Production Build
```bash
npm run build      # Creates optimized production build
```

The build folder will contain the optimized files ready for deployment.

## 🏗️ Project Structure

```
src/
├── Components/           # Reusable UI components
│   ├── Navigation/      # Header navigation and authentication
│   ├── Restaurant/      # Restaurant information banner
│   ├── MenuList/        # Menu categories and items
│   ├── ProductDetails/  # Product customization modal
│   ├── Footer/          # Footer component
│   └── SideBar/         # Mobile sidebar navigation
├── Pages/               # Main application pages
│   ├── Home.jsx         # Main restaurant page
│   ├── Login.jsx        # Login page
│   ├── SignUp.jsx       # Registration page
│   └── InitialLogin.jsx # Landing/welcome page
├── Redux/               # State management
│   ├── store.js         # Redux store configuration
│   └── userSlice.js     # User authentication slice
├── Assets/              # Static assets (images, icons)
├── utils/               # Utility functions and helpers
│   └── PrivateRoutes.js # Route protection logic
├── data.js              # Mock data for menu items
├── firebase.js          # Firebase configuration
└── App.js              # Main application component
```

## 🔧 Configuration

### Firebase Setup
Update `src/firebase.js` with your Firebase configuration:

```javascript
const firebaseConfig = {
  apiKey: "your-api-key",
  authDomain: "your-auth-domain",
  projectId: "your-project-id",
  // ... other config
};
```

### Environment Variables
Create a `.env` file in the root directory for sensitive configuration:

```env
REACT_APP_FIREBASE_API_KEY=your_api_key
REACT_APP_FIREBASE_AUTH_DOMAIN=your_auth_domain
REACT_APP_FIREBASE_PROJECT_ID=your_project_id
```

## 🌐 Deployment

### Build for Production
```bash
npm run build
```

### Deploy to Popular Platforms
- **Netlify**: Drag and drop the `build` folder or connect your GitHub repository
- **Vercel**: Import your GitHub repository
- **Heroku**: Use the Create React App buildpack
- **AWS S3**: Upload the build folder contents

## 🔍 Key Features Explained

### Authentication Flow
1. **Landing Page**: Users arrive at the initial login page with social login options
2. **Email Login**: Users can sign in with email/password
3. **Protected Routes**: Home page is protected and requires authentication
4. **Session Management**: Redux maintains user state across page refreshes

### Menu System
1. **Category Navigation**: Horizontal scrollable category chips
2. **Dynamic Loading**: Menu items loaded from data structure
3. **Product Details**: Modal with customization options
4. **Cart Management**: Add items to basket with quantity controls

### Responsive Design
- **Mobile First**: Optimized for mobile devices
- **Tablet Support**: Adjusted layouts for tablet screens
- **Desktop Enhancement**: Enhanced experience on larger screens

## 🐛 Troubleshooting

### Common Issues

1. **Dependencies not installing**
   ```bash
   rm -rf node_modules package-lock.json
   npm install
   ```

2. **Firebase authentication not working**
   - Check Firebase configuration in `src/firebase.js`
   - Ensure Firebase project is properly set up
   - Verify authentication methods are enabled in Firebase console

3. **Build failures**
   ```bash
   npm run build --verbose
   ```

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. **Fork the repository**
2. **Create a feature branch**: `git checkout -b feature/AmazingFeature`
3. **Commit your changes**: `git commit -m 'Add some AmazingFeature'`
4. **Push to the branch**: `git push origin feature/AmazingFeature`
5. **Open a Pull Request**

### Development Guidelines
- Follow the existing code style and conventions
- Add comments for complex logic
- Test your changes thoroughly
- Update documentation as needed

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Deliveroo** - Inspiration for the design and user experience
- **Material-UI Team** - Excellent component library
- **Create React App** - Development environment and build tools
- **Firebase** - Authentication and backend services
- **Unsplash** - High-quality food images for menu items

## 📞 Support

If you encounter any issues or have questions:

1. **Check the Issues**: Browse existing GitHub issues
2. **Create New Issue**: Open a new issue with detailed description
3. **Documentation**: Review this README and inline code comments

---

**Built with ❤️ by [AselInukeHidallearachchi](https://github.com/AselInukeHidallearachchi)**

*Enjoy building your food delivery empire! 🍕📱*

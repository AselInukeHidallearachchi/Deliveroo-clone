# Deliveroo Clone - Restaurant Menu App

A modern, responsive React application that replicates the core functionality of Deliveroo's restaurant ordering interface. This project demonstrates advanced React concepts, state management, authentication, and modern UI/UX patterns.

![React](https://img.shields.io/badge/React-18.2.0-blue)
![Material-UI](https://img.shields.io/badge/Material--UI-5.15.5-blue)
![Redux](https://img.shields.io/badge/Redux-5.0.1-purple)
![Firebase](https://img.shields.io/badge/Firebase-10.7.1-orange)
![Bootstrap](https://img.shields.io/badge/Bootstrap-5.3.2-purple)

## 🚀 Live Demo

[View Live Demo](#) <!-- Add your deployment URL here -->

## 📋 Table of Contents

- [Features](#-features)
- [Technology Stack](#-technology-stack)
- [Key Implementations](#-key-implementations)
- [Project Structure](#-project-structure)
- [Installation](#-installation)
- [Usage](#-usage)
- [API Reference](#-api-reference)
- [Contributing](#-contributing)
- [License](#-license)

## ✨ Features

### 🍽️ Restaurant Experience

- **Interactive Menu Navigation**: Dynamic menu categories with smooth scrolling
- **IntersectionObserver Integration**: Automatic menu category highlighting based on scroll position
- **Product Detail Modals**: Responsive dialogs with comprehensive product information
- **Shopping Cart Simulation**: Visual basket component (UI ready for cart functionality)

### 🔐 Authentication System

- **Firebase Authentication**: Google OAuth integration
- **Multi-provider Login**: Facebook, Google, Apple, and email options
- **Protected Routes**: Private route implementation with Redux state management
- **User Session Management**: Persistent login state across app sessions

### 🎨 Modern UI/UX

- **Material-UI Components**: Professional UI component library
- **Responsive Design**: Mobile-first approach with breakpoint optimization
- **Bootstrap Integration**: Enhanced styling and layout system
- **Custom CSS Animations**: Smooth transitions and hover effects

### 📱 Mobile Optimization

- **Progressive Web App Ready**: Optimized for mobile devices
- **Touch-friendly Interface**: Large tap targets and gesture support
- **Responsive Navigation**: Collapsible sidebar and mobile-optimized layouts

## 🛠️ Technology Stack

### Core Technologies

- **React 18.2.0**: Modern React with hooks and functional components
- **React Router DOM 6.21.2**: Client-side routing and navigation
- **Redux Toolkit 2.1.0**: State management with modern Redux patterns
- **Firebase 10.7.1**: Authentication and backend services

### UI Framework & Styling

- **Material-UI 5.15.5**: Component library with theming
- **React Bootstrap 2.9.2**: Bootstrap components for React
- **CSS3**: Custom styling with flexbox and grid layouts

### Development Tools

- **React Scripts 5.0.1**: Create React App build tools
- **Jest & React Testing Library**: Unit and integration testing
- **ESLint**: Code quality and consistency

## 🔧 Key Implementations

### IntersectionObserver API

The application uses the **IntersectionObserver API** for advanced scroll-based interactions:

```javascript
// MenuListCategory.jsx - Smart category highlighting
const intersectionCallback = ([entry], observer) => {
  handleScroll(entry.isIntersecting, entry.target.getAttribute("data-name"));
};

useEffect(() => {
  const observer = new IntersectionObserver(intersectionCallback, {
    rootMargin: "-180px 0px -30% 0px",
  });

  if (ref != null && !isScrolling) observer.observe(ref.current);

  return () => {
    observer.disconnect();
  };
}, [isScrolling]);
```

**Key Features:**

- **Automatic Category Detection**: Highlights active menu category based on viewport
- **Smart Scroll Management**: Prevents conflicts during programmatic scrolling
- **Performance Optimization**: Efficient cleanup and observer management
- **Custom Root Margins**: Fine-tuned visibility detection zones

### Smart Menu Navigation

Dynamic category switching with smooth scrolling:

```javascript
// MenuList.jsx - Intelligent scrolling system
const scrollTo = (e) => {
  setIsScrolling(true);
  const target = e.target;

  let matchedRef = dataRefs.find(
    (ref) => ref.current?.getAttribute("data-name") === target.innerText
  );

  if (matchedRef && matchedRef.current) {
    setCurrentCategory(matchedRef.current.getAttribute("data-name") || "");
    matchedRef.current.scrollIntoView({ behavior: "smooth", block: "start" });

    window.addEventListener(
      "scrollend",
      () => {
        setIsScrolling((prevState) => !prevState);
      },
      { once: true }
    );
  }
};
```

### Redux State Management

Modern Redux implementation with Redux Toolkit:

```javascript
// userSlice.js - User authentication state
export const userSlice = createSlice({
  name: "user",
  initialState: {
    user: null,
  },
  reducers: {
    login: (state, action) => {
      state.user = action.payload;
    },
    logout: (state) => {
      state.user = null;
    },
  },
});
```

### Protected Routes Implementation

Secure routing with authentication guards:

```javascript
// PrivateRoutes.js - Route protection
const PrivateRoutes = () => {
  const user = useSelector(selectUser);
  let auth = { token: user };

  return auth.token ? <Outlet /> : <Navigate to="/" />;
};
```

### Responsive Dialog System

Mobile-first modal implementation:

```javascript
// ResponsiveDialog.jsx - Adaptive modal system
export default function ResponsiveDialog(props) {
  const theme = useTheme();
  const fullScreen = useMediaQuery(theme.breakpoints.down("md"));

  return (
    <Dialog fullScreen={fullScreen} open={open} onClose={handleClose}>
      {content}
    </Dialog>
  );
}
```

## 📁 Project Structure

```
src/
├── Components/
│   ├── Footer/                 # App footer with links and social media
│   ├── MenuList/              # Main menu display system
│   │   ├── MenuListCategory/  # Individual category components
│   │   └── MenuListItem/      # Menu item cards
│   ├── Navigation/            # Header navigation and authentication
│   ├── ProductDetails/        # Product detail modal content
│   ├── ResponsiveDialog/      # Reusable modal component
│   ├── Restaurant/            # Restaurant information banner
│   └── SideBar/              # Mobile sidebar navigation
├── Pages/
│   ├── Home.jsx              # Main restaurant page
│   ├── InitialLogin.jsx      # Landing page with auth options
│   ├── Login.jsx             # Email login form
│   └── SignUp.jsx            # User registration form
├── Redux/
│   ├── store.js              # Redux store configuration
│   └── userSlice.js          # User authentication slice
├── Assets/                   # Images, icons, and static files
├── utils/
│   └── PrivateRoutes.js      # Protected route component
├── data.js                   # Mock menu data
├── firebase.js               # Firebase configuration
└── App.js                    # Main app component and routing
```

## 🚀 Installation

### Prerequisites

- Node.js (v14 or higher)
- npm or yarn package manager
- Firebase account (for authentication)

### Setup Steps

1. **Clone the repository**

   ```bash
   git clone https://github.com/yourusername/deliveroo-clone.git
   cd deliveroo-clone
   ```

2. **Install dependencies**

   ```bash
   npm install
   ```

3. **Firebase Configuration**

   - Create a new Firebase project at [Firebase Console](https://console.firebase.google.com/)
   - Enable Authentication and configure providers (Google, Facebook, etc.)
   - Update `src/firebase.js` with your Firebase config:

   ```javascript
   const firebaseConfig = {
     apiKey: "your-api-key",
     authDomain: "your-auth-domain",
     projectId: "your-project-id",
     storageBucket: "your-storage-bucket",
     messagingSenderId: "your-messaging-sender-id",
     appId: "your-app-id",
   };
   ```

4. **Start the development server**

   ```bash
   npm start
   ```

5. **Open your browser**
   Navigate to `http://localhost:3000`

## 💻 Usage

### Demo Credentials

- **Email**: user@gmail.com
- **Password**: 1234

### Authentication Flow

1. **Landing Page**: Choose from multiple authentication providers
2. **Email Login**: Enter credentials (demo credentials above)
3. **Registration**: Create new account with email verification
4. **Dashboard Access**: Automatic redirect to restaurant menu

### Menu Navigation

1. **Category Selection**: Click category chips to jump to sections
2. **Scroll Navigation**: Automatic category highlighting while scrolling
3. **Product Details**: Click any menu item to view detailed information
4. **Basket Integration**: UI ready for cart functionality implementation

### Key User Interactions

- **Smooth Scrolling**: Categories auto-scroll into view
- **Responsive Modals**: Product details adapt to screen size
- **Touch Gestures**: Mobile-optimized touch interactions
- **State Persistence**: Login state maintained across sessions

## 🔍 API Reference

### Authentication Endpoints

- **Google OAuth**: Configured through Firebase
- **Email/Password**: Firebase Authentication API
- **Session Management**: Redux state with localStorage persistence

### Menu Data Structure

```javascript
{
  id: number,
  categoryTitle: string,
  items: [
    {
      itemID: number,
      title: string,
      description: string,
      price: string,
      imageURL: string
    }
  ]
}
```

## 🎯 Advanced Features

### IntersectionObserver Implementation

- **Smart Category Tracking**: Automatically highlights visible menu sections
- **Performance Optimized**: Efficient DOM observation with cleanup
- **Scroll Conflict Prevention**: Manages programmatic vs. user scrolling
- **Custom Thresholds**: Fine-tuned visibility detection

### State Management Patterns

- **Redux Toolkit**: Modern Redux with simplified syntax
- **Selector Pattern**: Efficient state subscription
- **Immutable Updates**: Safe state modifications
- **Middleware Integration**: Development tools and debugging

### Mobile-First Design

- **Breakpoint System**: Material-UI responsive breakpoints
- **Touch Optimization**: Large tap targets and gesture support
- **Progressive Enhancement**: Core functionality works on all devices
- **Performance**: Optimized bundle size and loading

## 🔧 Development

### Available Scripts

- `npm start`: Development server with hot reload
- `npm build`: Production build optimization
- `npm test`: Run test suite
- `npm eject`: Eject from Create React App (irreversible)

### Code Quality

- **ESLint**: Configured for React best practices
- **Component Testing**: Jest and React Testing Library
- **Type Safety**: PropTypes validation where applicable

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Development Guidelines

- Follow React best practices and hooks patterns
- Maintain responsive design principles
- Write comprehensive tests for new features
- Update documentation for significant changes

## 📝 License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

-

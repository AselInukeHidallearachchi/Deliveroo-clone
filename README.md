
# 🚀 Deliveroo Clone

<img width=80% alt="Screenshot 2025-09-22 at 15 25 28" src="https://github.com/user-attachments/assets/b376c7f6-4f93-4109-8036-6abc6c4b281a" />

A modern food delivery web application inspired by Deliveroo, built with React.js and Firebase. This project showcases a complete restaurant ordering system with user authentication, menu browsing, and order management.

## ✨ Features

- **User Authentication**
  - Sign up with email/password
  - Login with Google (Firebase Auth)
  - Protected routes for authenticated users
  - User session management with Redux

- **Restaurant Interface**
  - Browse restaurant menus by categories
  - View detailed product information
  - Interactive menu with pricing and descriptions
  - Responsive design for all devices

- **Menu System**
  - Categorized menu items (Bundles, Salads, Hot Bowls, etc.)
  - Product details with ingredients and nutritional information
  - Dynamic pricing and customization options
  - Food allergen information

- **User Experience**
  - Clean, modern UI built with Material-UI
  - Smooth navigation and transitions
  - Real-time updates with React state management
  - Mobile-responsive design

## 🛠️ Tech Stack

- **Frontend**: React.js, React Router DOM
- **State Management**: Redux Toolkit
- **UI Components**: Material-UI (@mui/material)
- **Authentication**: Firebase Auth
- **Styling**: CSS3, Bootstrap
- **Icons**: Material-UI Icons
- **Build Tool**: Create React App

## 📦 Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/AselInukeHidallearachchi/Deliveroo-clone.git
   cd Deliveroo-clone
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up Firebase**
   - Create a Firebase project at [Firebase Console](https://console.firebase.google.com/)
   - Enable Authentication with Email/Password and Google providers
   - Update the Firebase configuration in `src/firebase.js` with your project credentials

4. **Start the development server**
   ```bash
   npm start
   ```

5. **Open your browser**
   - Navigate to [http://localhost:3000](http://localhost:3000)

## 🚀 Usage

### Test Credentials
For testing purposes, you can use:
- **Email**: user@gmail.com
- **Password**: 1234

### Development Commands

- **Start development server**
  ```bash
  npm start
  ```

- **Build for production**
  ```bash
  npm run build
  ```

- **Run tests**
  ```bash
  npm test
  ```

- **Eject configuration** (⚠️ irreversible)
  ```bash
  npm run eject
  ```

## 📁 Project Structure

```
src/
├── Components/           # Reusable UI components
│   ├── Footer/          # Footer component
│   ├── MenuList/        # Menu listing and categories
│   ├── Navigation/      # Navigation bar
│   ├── ProductDetails/  # Product detail modal
│   ├── Restaurant/      # Restaurant info banner
│   └── SideBar/         # Sidebar navigation
├── Pages/               # Page components
│   ├── Home.jsx         # Main restaurant page
│   ├── InitialLogin.jsx # Social login options
│   ├── Login.jsx        # Email/password login
│   └── SignUp.jsx       # User registration
├── Redux/               # State management
│   ├── store.js         # Redux store configuration
│   └── userSlice.js     # User authentication slice
├── utils/               # Utility functions
│   └── PrivateRoutes.js # Route protection
├── firebase.js          # Firebase configuration
├── data.js             # Menu data
└── App.js              # Main application component
```

## 🔧 Configuration

### Firebase Setup
Update `src/firebase.js` with your Firebase project configuration:

```javascript
const firebaseConfig = {
  apiKey: "your-api-key",
  authDomain: "your-project.firebaseapp.com",
  projectId: "your-project-id",
  storageBucket: "your-project.appspot.com",
  messagingSenderId: "your-sender-id",
  appId: "your-app-id"
};
```

### Environment Variables
Create a `.env` file in the root directory for sensitive configuration:

```env
REACT_APP_FIREBASE_API_KEY=your-api-key
REACT_APP_FIREBASE_AUTH_DOMAIN=your-project.firebaseapp.com
REACT_APP_FIREBASE_PROJECT_ID=your-project-id
```

## 🤝 Contributing

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📋 Available Scripts

In the project directory, you can run:

- `npm start` - Runs the app in development mode
- `npm test` - Launches the test runner
- `npm run build` - Builds the app for production
- `npm run eject` - Ejects from Create React App (one-way operation)

## 🐛 Known Issues

- Some build warnings related to deprecated packages (inherited from Create React App)
- Test coverage could be improved
- Mobile responsiveness can be enhanced further

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 👨‍💻 Author

**Asel Inuke Hidallearachchi**
- GitHub: [@AselInukeHidallearachchi](https://github.com/AselInukeHidallearachchi)

## 🙏 Acknowledgments

- Inspired by [Deliveroo](https://deliveroo.com/)
- Built with [Create React App](https://github.com/facebook/create-react-app)
- UI components from [Material-UI](https://mui.com/)
- Authentication powered by [Firebase](https://firebase.google.com/)

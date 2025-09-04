AR Hub - Augmented Reality Social Platform

A modern, responsive social platform built with vanilla JavaScript and Firebase, featuring real-time interactions, user management, and comprehensive content sharing capabilities.

## 🚀 Features

### Core Functionality
- **User Authentication** - Secure login/registration with Firebase Auth
- **Real-time Messaging** - Instant messaging system with Firebase Realtime Database
- **Post Management** - Create, edit, delete posts with image support
- **Social Interactions** - Like, comment, follow/unfollow users
- **Search & Discovery** - Advanced search for users, posts, and hashtags
- **Notifications** - Real-time notification system
- **Profile Management** - Customizable user profiles with cover photos

### Technical Features
- **Responsive Design** - Mobile-first approach with smooth animations
- **Real-time Updates** - Live feed updates and notifications
- **Image Validation** - URL-based image sharing with validation
- **Content Moderation** - Report system and admin panel
- **Privacy Controls** - Public/private post settings
- **Data Export** - User data export functionality

### Admin Features
- **Admin Panel** - Comprehensive user and content management
- **Analytics Dashboard** - User engagement and platform statistics
- **Content Moderation** - Report management and user moderation tools
- **Notification Broadcasting** - Admin-to-user notification system

## 📁 Project Structure

```
ar-hub/
├── index.html              # Main feed/home page
├── login.html              # Authentication page
├── profile.html            # User profile page
├── search.html             # Search and discovery
├── message.html            # Messaging interface
├── notification.html       # Notifications center
├── settings.html           # User settings
├── admin.html              # Admin panel
└── README.md              # Project documentation
```

## 🛠️ Technologies Used

### Frontend
- **HTML5** - Semantic markup and structure
- **CSS3** - Custom styling with CSS variables and animations
- **Vanilla JavaScript** - Core functionality and Firebase integration
- **Font Awesome 6.6.0** - Icon library
- **Google Fonts (Inter)** - Modern typography

### Backend & Services
- **Firebase Authentication** - User management and security
- **Firebase Realtime Database** - Data storage and real-time updates
- **Firebase Analytics** - User behavior tracking
- **CDN Resources** - External libraries and assets

### Libraries & Frameworks
- **Tailwind CSS** - Utility-first CSS (settings page)
- **Chart.js 3.9.1** - Data visualization (admin panel)
- **Firebase SDK 11.0.1** - Backend services integration

## ⚙️ Setup Instructions

### Prerequisites
- Web browser with JavaScript enabled
- Firebase project setup
- Basic understanding of HTML/CSS/JavaScript

### Installation

1. **Clone or Download** the project files
   ```bash
   git clone <repository-url>
   cd ar-hub
   ```

2. **Firebase Configuration**
   - Create a new Firebase project at [Firebase Console](https://console.firebase.google.com/)
   - Enable Authentication with Email/Password and Google Sign-in
   - Set up Realtime Database with the following structure:
   ```json
   {
     "users": {},
     "posts": {},
     "messages": {},
     "notifications": {},
     "reports": {},
     "hashtags": {}
   }
   ```

3. **Update Firebase Config**
   - Replace the `firebaseConfig` object in all HTML files with your project credentials:
   ```javascript
   const firebaseConfig = {
     apiKey: "your-api-key",
     authDomain: "your-project.firebaseapp.com",
     databaseURL: "https://your-project-rtdb.firebaseio.com",
     projectId: "your-project-id",
     storageBucket: "your-project.appspot.com",
     messagingSenderId: "your-sender-id",
     appId: "your-app-id"
   };
   ```

4. **Deploy**
   - Upload files to your web server or hosting platform
   - Ensure HTTPS is enabled for Firebase Auth to work properly

### Database Structure

```json
{
  "users": {
    "user-email-com": {
      "displayName": "User Name",
      "bio": "User bio",
      "profilePic": "image-url",
      "coverPhoto": "image-url",
      "privacy": "public|private",
      "following": {
        "other-user-id": true
      },
      "notifications": {
        "message": true,
        "friendRequest": true
      }
    }
  },
  "posts": {
    "post-id": {
      "userId": "user-email",
      "content": "Post content",
      "image": "image-url",
      "privacy": "public|private",
      "timestamp": 1234567890,
      "likes": {
        "user-id": true
      },
      "comments": {
        "comment-id": {
          "userId": "user-email",
          "content": "Comment text",
          "timestamp": 1234567890
        }
      }
    }
  },
  "messages": {
    "chat-id": {
      "message-id": {
        "senderId": "user-id",
        "text": "Message text",
        "timestamp": 1234567890
      }
    }
  },
  "notifications": {
    "user-id": {
      "notification-id": {
        "message": "Notification text",
        "timestamp": 1234567890,
        "unread": true,
        "type": "like|comment|follow"
      }
    }
  }
}
```

## 🔐 Security Features

- **Input Sanitization** - XSS protection through content sanitization
- **Authentication Required** - Protected actions require user login
- **Rate Limiting** - Comment and action throttling
- **Content Validation** - Image URL and input validation
- **User Permissions** - Role-based access control for admin features

## 📱 Responsive Design

The platform is fully responsive with breakpoints for:
- **Desktop** (1200px+)
- **Tablet** (768px - 1199px)
- **Mobile** (480px - 767px)
- **Small Mobile** (<480px)

## 🎨 User Interface

### Design Principles
- **Modern Aesthetic** - Clean, professional design with smooth animations
- **Accessibility** - Proper contrast ratios and semantic markup
- **User Experience** - Intuitive navigation and clear visual hierarchy
- **Performance** - Optimized loading and minimal resource usage

### Color Palette
- **Primary**: `#6366f1` (Indigo)
- **Success**: `#22c55e` (Green)
- **Error**: `#ef4444` (Red)
- **Warning**: `#f59e0b` (Amber)
- **Text**: `#1e293b` (Slate)

## 🔧 Configuration Options

### Privacy Settings
- **Public Profile** - Visible to all users
- **Private Profile** - Visible only to user

### Notification Preferences
- **Message Notifications** - New message alerts
- **Friend Requests** - Follow request notifications
- **Update Notifications** - Platform update alerts

### Content Settings
- **Post Privacy** - Public or private posts
- **Image Validation** - Automatic image URL verification
- **Comment Moderation** - Spam and content filtering

## 📊 Analytics & Monitoring

The platform includes comprehensive analytics tracking:
- **User Engagement** - Login, post creation, interactions
- **Content Performance** - Post likes, comments, shares
- **Error Tracking** - JavaScript errors and failed operations
- **Performance Metrics** - Page load times and user flows

## 🛡️ Content Moderation

### Reporting System
- Users can report inappropriate content
- Admin panel for reviewing reports
- Automated flagging for high-report content

### Admin Controls
- User management (ban/suspend)
- Content moderation tools
- Notification broadcasting
- Analytics dashboard

## 🚀 Deployment

### Recommended Hosting
- **Firebase Hosting** - Seamless integration with Firebase services
- **Netlify** - Static site hosting with form handling
- **Vercel** - Fast deployment with automatic HTTPS
- **GitHub Pages** - Free hosting for public repositories

### Production Checklist
- [ ] Firebase security rules configured
- [ ] HTTPS enabled
- [ ] Analytics tracking verified
- [ ] Error monitoring setup
- [ ] Performance optimization completed
- [ ] Content security policy implemented

## 🤝 Contributing

This project welcomes contributions! Here's how you can help:

1. **Report Bugs** - Submit detailed bug reports
2. **Feature Requests** - Suggest new functionality
3. **Code Contributions** - Submit pull requests
4. **Documentation** - Improve README and code comments
5. **Testing** - Help test across different devices and browsers

### Development Guidelines
- Follow existing code style and conventions
- Test thoroughly across different browsers
- Ensure mobile responsiveness
- Maintain Firebase data structure consistency
- Include proper error handling

## 📄 License

This project is provided as-is for educational and development purposes. Please ensure you have proper licensing for any commercial use and comply with all applicable laws and regulations.

## 🐛 Known Issues

- Large image uploads may cause performance issues
- Real-time updates may have slight delays on slower connections
- Some features require modern browser support for optimal performance

## 🔮 Future Enhancements

- [ ] Video post support
- [ ] Advanced image editing
- [ ] Push notifications
- [ ] Progressive Web App (PWA) features
- [ ] Multi-language support
- [ ] Enhanced admin analytics
- [ ] API integration for external services
- [ ] Advanced search filters
- [ ] Group/community features
- [ ] Story/temporary post features

## 📞 Support

For questions, issues, or feature requests, please:
1. Check existing documentation
2. Search for similar issues
3. Create a detailed bug report
4. Include browser/device information
5. Provide steps to reproduce

---

**Built with ❤️ for the AR/VR community**
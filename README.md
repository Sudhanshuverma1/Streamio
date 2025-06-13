<h1 align="center">🎥 StreamIo</h1>

<p align="center">
  A full-stack movie and TV show discovery platform powered by <a href="https://www.themoviedb.org/">TMDB API</a>, built with <strong>React</strong>, <strong>Redux</strong>, <strong>Express</strong>, <strong>MongoDB</strong>, and <strong>Tailwind CSS</strong>.
</p>

<p align="center">
  <a href="https://streamio-tan.vercel.app/" target="_blank">Live Demo</a> | 
  <a href="#-features">Features</a> | 
  <a href="#-tech-stack">Tech Stack</a> | 
  <a href="#-getting-started">🚀 Getting Started</a>
</p>

---

## Overview

**StreamIo** lets users browse popular movies and TV shows, view detailed information, add media to favorites, write reviews, and securely manage their profiles. It's built with a clean architecture and follows modern full-stack development standards.

---

## Screenshots

<p align="center">
  <img src="https://github.com/user-attachments/assets/97cc281c-247d-4b43-9378-2b4c1bffc38b" alt="StreamIo Preview" />
</p>

---

##Features

- 🔐 **Authentication** – JWT-based secure login/signup  
- 📺 **Browse Media** – Discover trending movies & shows via TMDB  
- 🔍 **Search Functionality** – Search across all media types  
- 📝 **Reviews** – Post, read & manage reviews  
- ⭐ **Favorites** – Add/remove media to a personalized list  
- 🌈 **Responsive Design** – Fully responsive across devices  
- 🎨 **Modern UI** – Built with Tailwind CSS and dynamic interactions  

---

##Tech Stack

### Frontend
- **React.js** (w/ Hooks)
- **Redux Toolkit**
- **React Router DOM**
- **Tailwind CSS**
- **Axios**

### Backend
- **Node.js** + **Express**
- **MongoDB** + **Mongoose**
- **JWT Authentication**
- **dotenv**, **cookie-parser**, **cors**

### External APIs
- [TMDB API](https://www.themoviedb.org/documentation/api)

---

## 🗂 Project Structure
```
client/                          # Frontend React application
├── public/                      # Static public assets
├── src/                         # Application source code
│   ├── api/                     # API call wrappers
│   │   ├── client/              # Axios clients for public/private requests
│   │   │   ├── private.client.js
│   │   │   └── public.client.js
│   ├── configs/                 # Global config files
│   │   ├── tmdb.configs.js
│   ├── modules/                 # API services/modules grouped by feature
│   │   ├── favorite.api.js
│   │   ├── genre.api.js
│   │   ├── media.api.js
│   │   ├── person.api.js
│   │   ├── review.api.js
│   │   └── user.api.js
│   ├── components/
│   │   └── common/              # Shared and reusable UI components
│   │       ├── AuthModal.jsx
│   │       ├── AutoSwiper.jsx
│   │       ├── BackdropSlide.jsx
│   │       ├── CastSlide.jsx
│   │       ├── CircularRate.jsx
│   │       ├── Container.jsx
│   │       ├── Footer.jsx
│   │       ├── GlobalLoading.jsx
│   │       ├── HeroSlide.jsx
│   │       ├── ImageHeader.jsx
│   │       ├── Logo.jsx
│   │       ├── MediaGrid.jsx
│   │       ├── MediaItem.jsx
│   │       ├── MediaReview.jsx
│   │       ├── MediaSlide.jsx
│   │       ├── MediaVideosSlide.jsx
│   │       ├── NavigationSwiper.jsx
│   │       ├── PageWrapper.jsx
│   │       ├── PersonMediaGrid.jsx
│   │       ├── PosterSlide.jsx
│   │       ├── ProtectedPage.jsx
│   │       ├── RecommendSlide.jsx
│   │       ├── Sidebar.jsx
│   │       ├── SigninForm.jsx
│   │       ├── SignupForm.jsx
│   │       ├── TextAvatar.jsx
│   │       ├── Topbar.jsx
│   │       └── UserMenu.jsx
│   ├── layout/                  # Layout wrapper for pages
│   │   └── MainLayout.jsx
│   ├── configs/                 # UI/Theme/Menu configuration
│   │   ├── menu.configs.js
│   │   ├── theme.configs.js
│   │   └── ui.configs.js
│   ├── hooks/                   # Custom React hooks
│   │   └── usePrevious.jsx
│   ├── pages/                   # Application route components
│   │   ├── FavoriteList.jsx
│   │   ├── HomePage.jsx
│   │   ├── MediaDetail.jsx
│   │   ├── MediaList.jsx
│   │   ├── MediaSearch.jsx
│   │   ├── PasswordUpdate.jsx
│   │   ├── PersonDetail.jsx
│   │   └── ReviewList.jsx
│   ├── redux/                   # Redux store and slices
│   │   ├── features/
│   │   │   ├── appStateSlice.js
│   │   │   ├── authModalSlice.js
│   │   │   ├── globalLoadingSlice.js
│   │   │   ├── themeModeSlice.js
│   │   │   └── userSlice.js
│   │   └── store.js
│   ├── routes/                  # Route definitions
│   │   └── routes.jsx
│   ├── utils/                   # Utility functions
│   │   └── favorite.utils.js
│   ├── App.jsx                  # Root App component
│   └── index.jsx                # Entry point for React app
├── .gitignore                   # Files and folders to ignore in git
├── README.md
├── package.json                 # Frontend dependencies and scripts
└── yarn.lock                    # Yarn dependency lock file

server/                          # Backend Node.js server
├── src/
│   ├── axios/                   # Axios instance for TMDB API
│   │   └── axios.client.js
│   ├── controllers/             # Route logic/controllers
│   │   ├── favorite.controller.js
│   │   ├── media.controller.js
│   │   ├── person.controller.js
│   │   ├── review.controller.js
│   │   └── user.controller.js
│   ├── handlers/                # Custom response/request wrappers
│   │   ├── request.handler.js
│   │   └── response.handler.js
│   ├── middlewares/            # Express middlewares (auth, etc.)
│   │   └── token.middleware.js
│   ├── models/                  # Mongoose models and schema configs
│   │   ├── favorite.model.js
│   │   ├── model.options.js
│   │   ├── review.model.js
│   │   └── user.model.js
│   ├── routes/                  # API route handlers
│   │   ├── index.js
│   │   ├── media.route.js
│   │   ├── person.route.js
│   │   ├── review.route.js
│   │   └── user.route.js
│   ├── tmdb/                    # TMDB API helper layer
│   │   ├── tmdb.api.js
│   │   ├── tmdb.config.js
│   │   └── tmdb.endpoints.js
├── .gitignore
├── index.js                     # Server entry point
├── package.json                 # Backend dependencies and scripts
├── vercel.json                  # Vercel deployment config
├── yarn.lock
├── .gitattributes
├── LICENSE
└── README.md
```

## ⚙️ Environment Variables

Create a `.env` file in the `server/` directory:

```env
MONGODB_URL=your_mongodb_connection_string
PORT=5000
TOKEN_SECRET=your_secret
TMDB_BASE_URL=https://api.themoviedb.org/3/
TMDB_KEY=your_tmdb_api_key
```
Made with ❤️ by **Sudhanshu** • [Email](mailto:sudhanshuuu01@gmail.com)


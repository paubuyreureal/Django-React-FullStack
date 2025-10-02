# Notes App - Full Stack Application

A very basic full-stack notes application built with React (frontend) and Django REST Framework (backend). This is a simple web app that runs locally only and is **not deployed**. It serves as a foundational template for building more complex applications.

Users can register, login, and manage their personal notes with JWT authentication. 

> **Note**: This is a basic starter project. For a more complex example with advanced features and deployment, check out my [PasswordManager](https://github.com/paubuyreureal/PasswordManager) project which is deployed on GitHub Codespaces. 

## 🚀 Features

- **User Authentication**: Register and login with JWT tokens
- **Personal Notes**: Create, read, and delete your own notes
- **Secure**: User-specific data access and protected routes
- **Modern Stack**: React + Vite frontend, Django REST backend
- **Responsive**: Clean and simple user interface

## 🛠️ Tech Stack

### Frontend
- React 18
- Vite
- React Router DOM
- Axios
- JWT Decode

### Backend
- Django 4.2
- Django REST Framework
- Simple JWT
- SQLite Database
- CORS Headers

## 📋 Prerequisites

- Python 3.8+
- Node.js 16+
- npm or yarn

## 🔧 Installation & Setup

> **Note**: This application is configured to run locally only.

### 1. Clone the Repository
```bash
git clone <your-repo-url>
cd SimpleFullStackApp
```

### 2. Backend Setup

#### Navigate to backend directory
```bash
cd backend
```

#### Create and activate virtual environment
```bash
# Windows
python -m venv env
env\Scripts\activate

# macOS/Linux
python -m venv env
source env/bin/activate
```

#### Install dependencies
```bash
pip install -r requirements.txt
```

#### Create environment file
Create a `.env` file in the `backend/` directory:
```env
# Django Configuration
SECRET_KEY=your-secret-key-here
DEBUG=True
ALLOWED_HOSTS=localhost,127.0.0.1

# CORS Configuration  
CORS_ALLOWED_ORIGINS=http://localhost:5173,http://127.0.0.1:5173

# JWT Configuration
ACCESS_TOKEN_LIFETIME_MINUTES=30
REFRESH_TOKEN_LIFETIME_DAYS=1
```

#### Run migrations
```bash
python manage.py migrate
```

#### Start the backend server
```bash
python manage.py runserver
```
The backend will run on `http://localhost:8000`

### 3. Frontend Setup

#### Open a new terminal and navigate to frontend directory
```bash
cd frontend
```

#### Install dependencies
```bash
npm install
```

#### Start the frontend development server
```bash
npm run dev
```
The frontend will run on `http://localhost:5173`

## 🎯 Usage

1. **Access the application**: Open your browser and go to `http://localhost:5173`

2. **Register**: Create a new account with username and password (replace **/login** for **/register** in the URL bar)

3. **Login**: Sign in with your credentials

4. **Manage Notes**: 
   - Create new notes with title and content
   - View all your notes
   - Delete notes you no longer need

5. **Logout**: Use the logout option to end your session (**/logout** in the URL bar)

## 📁 Project Structure

```
SimpleFullStackApp/
├── backend/                 # Django REST API
│   ├── api/                # Main API app
│   │   ├── models.py       # Note model
│   │   ├── views.py        # API views
│   │   ├── serializers.py  # Data serializers
│   │   └── urls.py         # API routes
│   ├── backend/            # Django project settings
│   │   └── settings.py     # Main settings
│   ├── requirements.txt    # Python dependencies
│   ├── manage.py          # Django management
│   └── env.example        # Environment variables template
├── frontend/               # React application
│   ├── src/
│   │   ├── components/     # Reusable components
│   │   ├── pages/         # Page components
│   │   ├── styles/        # CSS files
│   │   ├── api.js         # API configuration
│   │   └── App.jsx        # Main app component
│   ├── package.json       # Node dependencies
│   └── vite.config.js     # Vite configuration
└── README.md              # This file
```

## 🔐 API Endpoints

### Authentication
- `POST /api/user/register/` - Register new user
- `POST /api/token/` - Login (get JWT tokens)
- `POST /api/token/refresh/` - Refresh access token

### Notes
- `GET /api/notes/` - Get user's notes
- `POST /api/notes/` - Create new note
- `DELETE /api/notes/delete/{id}/` - Delete specific note

## 🚨 Important Notes

- **Local Development Only**: This application is configured for local development
- **SQLite Database**: Uses SQLite for simplicity (data stored in `backend/db.sqlite3`)
- **Environment Variables**: Make sure to create the `.env` file in the backend directory
- **Virtual Environment**: Always activate the Python virtual environment before running the backend
- **CORS**: Frontend and backend must run on specified ports for CORS to work properly

## 🔧 Development Commands

### Backend
```bash
# Activate virtual environment (Windows)
env\Scripts\activate

# Run server
python manage.py runserver

# Create migrations (if models change)
python manage.py makemigrations

# Apply migrations
python manage.py migrate

# Create superuser (for admin access)
python manage.py createsuperuser
```

### Frontend
```bash
# Start development server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

## 📝 License

This project is for educational/personal use only.

## 🤝 Contributing

This is a basic project template. Feel free to fork and modify as needed!

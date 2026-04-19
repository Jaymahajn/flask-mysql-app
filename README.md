# Flask MySQL Login System

A simple login and registration system built with Flask and MySQL.

## Features

- User registration
- User login with session management
- Dashboard for logged-in users
- Clean, modern UI
- Environment-based configuration

## Tech Stack

- **Backend:** Flask (Python)
- **Database:** MySQL
- **Session Management:** Flask sessions
- **Environment Variables:** python-dotenv

## Prerequisites

- Python 3.8+
- MySQL 8.0+
- pip

## Installation

1. **Clone the repository:**
```bash
git clone https://github.com/yourusername/flask-mysql-login.git
cd flask-mysql-login
```

2. **Install dependencies:**
```bash
pip install -r requirements.txt
```

3. **Set up MySQL database:**
```bash
mysql -u root -p
```

Then run these SQL commands:
```sql
CREATE DATABASE mydb;
USE mydb;
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100) UNIQUE,
    password VARCHAR(100)
);
exit;
```

4. **Configure environment variables:**
```bash
cp .env.example .env
```

Edit `.env` and add your MySQL credentials:

DB_HOST=localhost
DB_USER=root
DB_PASSWORD=your_mysql_password
DB_NAME=mydb
SECRET_KEY=your-random-secret-key

5. **Run the application:**
```bash
python app.py
```

6. **Open your browser:**
http://localhost:5000

## Project Structure
flask-mysql-login/
├── app.py              # Main Flask application
├── requirements.txt    # Python dependencies
├── .env               # Environment variables (not in git)
├── .env.example       # Environment variables template
├── .gitignore         # Git ignore file
└── README.md          # This file

## Routes

- `/` - Home (redirects to login or dashboard)
- `/login` - Login page
- `/register` - Registration page
- `/dashboard` - User dashboard (requires login)
- `/logout` - Logout

## Usage

1. Register a new account at `/register`
2. Login with your credentials at `/login`
3. View your dashboard at `/dashboard`
4. Logout using the logout button

## Security Notes

⚠️ **This is a learning project. DO NOT use in production without:**
- Password hashing (use bcrypt)
- CSRF protection
- Input validation and sanitization
- SQL injection prevention (use parameterized queries properly)
- HTTPS
- Rate limiting
- Proper session management

## Database Schema

**users table:**
```sql
id       INT          PRIMARY KEY AUTO_INCREMENT
name     VARCHAR(100)
email    VARCHAR(100) UNIQUE
password VARCHAR(100)
```

## Environment Variables

| Variable | Description | Example |
|----------|-------------|---------|
| DB_HOST | MySQL host | localhost |
| DB_USER | MySQL username | root |
| DB_PASSWORD | MySQL password | password123 |
| DB_NAME | Database name | mydb |
| SECRET_KEY | Flask secret key | random-secret-key |

## Troubleshooting

**Can't connect to MySQL:**
- Make sure MySQL is running: `brew services start mysql`
- Check your credentials in `.env`

**Table doesn't exist:**
- Run the SQL commands in step 3 of Installation

**Module not found:**
- Install dependencies: `pip install -r requirements.txt`

## License

MIT

## Author

Jay Mahajan

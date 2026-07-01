# ⚽ GoalWorld — Backend API

REST API backend for GoalWorld sports app, built with Laravel, Sanctum Auth, and TheSportsDB API integration.

🌐 **Frontend:** [sports-frontend-eta.vercel.app](https://sports-frontend-eta.vercel.app)
👨‍💻 **Portfolio:** [abdulazis.my.id](https://abdulazis.my.id)

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Framework | Laravel 12 |
| Auth | Laravel Sanctum |
| Database | MySQL |
| External API | TheSportsDB API |

## 📡 API Endpoints

### Public
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/leagues` | Get all leagues |
| GET | `/api/leagues/{id}/teams` | Get teams by league |
| GET | `/api/teams/{id}` | Get team detail |
| GET | `/api/teams/{id}/previous-matches` | Get recent matches |
| GET | `/api/leagues/{id}/standings` | Get league standings |

### Protected (Auth Required)
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/register` | Register user |
| POST | `/api/login` | Login user |
| POST | `/api/logout` | Logout user |
| GET | `/api/me` | Get current user |
| GET | `/api/favorites` | Get favorite teams |
| POST | `/api/favorites` | Add favorite team |
| DELETE | `/api/favorites/{teamId}` | Remove favorite |

## ⚙️ Installation

```bash
git clone https://github.com/Abdulazis-m91/sports-backend.git
cd sports-backend
composer install
cp .env.example .env
php artisan key:generate
php artisan migrate:fresh
php artisan serve --port=8000
```

## 👨‍💻 Developer

**Abdul Azis, S.Kom.** — Full-Stack Web Developer
- 🌐 [abdulazis.my.id](https://abdulazis.my.id)
- 💼 [LinkedIn](https://www.linkedin.com/in/abdulazis-f91)
- 📧 abdulazis.dev1@gmail.com

# 🏆 Sports App - Backend (Laravel)

REST API Backend untuk aplikasi Sports App menggunakan Laravel, Sanctum Auth, dan integrasi TheSportsDB API.

## 📋 Teknologi yang Digunakan

- **PHP** 8.2
- **Laravel** 12
- **Laravel Sanctum** (Authentication)
- **MySQL** (Database)
- **TheSportsDB API** (Data olahraga)

## ⚙️ Persyaratan Sistem

- PHP >= 8.2
- Composer
- MySQL
- XAMPP (atau server lokal lainnya)

## 🚀 Cara Instalasi & Menjalankan

### 1. Clone Repository

```bash
git clone https://github.com/Abdulazis-m91/sports-backend.git
cd sports-backend
```

### 2. Install Dependencies

```bash
composer install
```

> Jika terjadi SSL error, jalankan:
> ```bash
> composer config -g disable-tls true
> composer config -g secure-http false
> composer install
> ```

### 3. Konfigurasi Environment

Salin file `.env.example` menjadi `.env`:

```bash
cp .env.example .env
```

Buka file `.env` dan sesuaikan konfigurasi database:

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=sports_db
DB_USERNAME=root
DB_PASSWORD=
```

Tambahkan juga di bagian bawah `.env`:

```env
SANCTUM_STATEFUL_DOMAINS=localhost:5173,localhost:8080
FRONTEND_URL=http://localhost:8080
```

### 4. Generate Application Key

```bash
php artisan key:generate
```

### 5. Buat Database

Buka phpMyAdmin (`http://localhost/phpmyadmin`) dan buat database baru bernama:

```
sports_db
```

### 6. Jalankan Migration

```bash
php artisan migrate:fresh
```

### 7. Jalankan Server

```bash
php artisan serve --port=8000
```

Server akan berjalan di `http://127.0.0.1:8000`

---

## 📡 API Endpoints

### Public Endpoints

| Method | Endpoint | Deskripsi |
|--------|----------|-----------|
| GET | `/api/leagues` | Daftar liga |
| GET | `/api/leagues/{leagueId}/teams` | Daftar tim per liga |
| GET | `/api/teams/{teamId}` | Detail tim |
| GET | `/api/teams/{teamId}/previous-matches` | Pertandingan terakhir |
| GET | `/api/leagues/{leagueId}/standings` | Klasemen liga |

### Protected Endpoints (Wajib Login)

| Method | Endpoint | Deskripsi |
|--------|----------|-----------|
| POST | `/api/register` | Registrasi user |
| POST | `/api/login` | Login user |
| POST | `/api/logout` | Logout user |
| GET | `/api/me` | Data user login |
| GET | `/api/favorites` | Daftar favorit |
| POST | `/api/favorites` | Tambah favorit |
| DELETE | `/api/favorites/{teamId}` | Hapus favorit |

---

## 🗄️ Struktur Database

- `users` - Data pengguna
- `personal_access_tokens` - Token Sanctum
- `favorites` - Tim favorit pengguna
- `cache` - Cache response API

---

## 👤 Author

**Abdul Azis** - [Abdulazis-m91](https://github.com/Abdulazis-m91)

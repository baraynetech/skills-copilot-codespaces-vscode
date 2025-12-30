# Laravel Starter Application - Project Structure

## Overview
This is a complete Laravel 12.x starter application with boilerplates ready for rapid application development.

## Project Information
- **Laravel Version:** 12.44.0
- **PHP Version:** 8.2+
- **Database:** SQLite (configurable)
- **Asset Bundler:** Vite with Tailwind CSS 4.0
- **Testing Framework:** PHPUnit

## Directory Structure

```
.
├── app/                    # Application core
│   ├── Http/              # HTTP layer (Controllers, Middleware)
│   ├── Models/            # Eloquent models (User model included)
│   └── Providers/         # Service providers
├── bootstrap/             # Framework bootstrap
├── config/                # Configuration files
│   ├── app.php           # Application configuration
│   ├── auth.php          # Authentication configuration
│   ├── database.php      # Database configuration
│   └── ...               # Other configs
├── database/             # Database files
│   ├── factories/        # Model factories
│   ├── migrations/       # Database migrations
│   └── seeders/          # Database seeders
├── public/               # Public web root
│   ├── index.php        # Application entry point
│   └── ...
├── resources/            # Raw assets and views
│   ├── css/             # CSS files
│   ├── js/              # JavaScript files
│   └── views/           # Blade templates
├── routes/              # Application routes
│   ├── console.php     # Console routes
│   └── web.php         # Web routes
├── storage/             # Generated files
│   ├── app/            # Application storage
│   ├── framework/      # Framework files
│   └── logs/           # Log files
└── tests/              # Automated tests
    ├── Feature/        # Feature tests
    └── Unit/           # Unit tests
```

## Key Features

### 1. Authentication Ready
- User model with authentication traits
- Password hashing configured
- Remember token support
- Email verification support (uncomment to enable)

### 2. Database Setup
- SQLite database configured (easy to switch to MySQL/PostgreSQL)
- Migrations for:
  - Users table with authentication fields
  - Cache table for application caching
  - Jobs table for queue management
- Database factory for User model
- Database seeder ready for data population

### 3. Asset Management
- Vite configured for fast builds
- Tailwind CSS 4.0 included
- Hot module replacement in development
- Optimized production builds

### 4. Testing Infrastructure
- PHPUnit configured
- Example feature test (tests homepage)
- Example unit test
- Test database configuration
- All tests passing

### 5. Development Tools
- Artisan CLI available
- Laravel Pint for code formatting
- Laravel Pail for log tailing
- Laravel Sail for Docker environment
- Laravel Tinker for REPL

### 6. Configuration Files
- `.env.example` - Environment template
- `.editorconfig` - Editor configuration
- `.gitignore` - Git ignore rules
- `.gitattributes` - Git attributes
- `phpunit.xml` - PHPUnit configuration
- `vite.config.js` - Vite configuration

## Quick Start

### 1. Install Dependencies
```bash
composer install
npm install
```

### 2. Environment Setup
```bash
cp .env.example .env
php artisan key:generate
```

### 3. Database Setup
```bash
php artisan migrate
```

### 4. Start Development
```bash
# Terminal 1: Start PHP server
php artisan serve

# Terminal 2: Start Vite dev server
npm run dev
```

### 5. Run Tests
```bash
php artisan test
```

## Available Artisan Commands

```bash
php artisan list              # List all commands
php artisan serve             # Start development server
php artisan migrate           # Run migrations
php artisan migrate:fresh     # Drop all tables and re-run migrations
php artisan db:seed           # Seed the database
php artisan make:controller   # Create a controller
php artisan make:model        # Create a model
php artisan make:migration    # Create a migration
php artisan route:list        # List all routes
php artisan test              # Run tests
```

## Available Routes

```
GET  /                # Welcome page (default Laravel view)
GET  /storage/{path}  # Local storage access
GET  /up              # Health check endpoint
```

## Configuration Highlights

### Database
- **Default:** SQLite (database/database.sqlite)
- **Sessions:** Database-backed
- **Cache:** Database-backed
- **Queue:** Database-backed

### Security
- **APP_KEY:** Generated and set
- **Environment:** Local development mode
- **Debug:** Enabled (disable in production)

### Services
- **Mail:** Log driver (emails written to logs)
- **Broadcasting:** Log driver
- **Queue:** Database driver

## Next Steps

1. **Add Authentication:**
   ```bash
   composer require laravel/breeze --dev
   php artisan breeze:install
   ```

2. **Create Your First Controller:**
   ```bash
   php artisan make:controller HomeController
   ```

3. **Create Your First Model:**
   ```bash
   php artisan make:model Post -m
   ```

4. **Add API Routes:**
   - Uncomment or create `routes/api.php`
   - Configure in `bootstrap/app.php`

5. **Configure Frontend:**
   - Edit `resources/views/` for Blade templates
   - Edit `resources/js/` for JavaScript
   - Edit `resources/css/` for styles

## Documentation

- [Laravel Documentation](https://laravel.com/docs)
- [Laravel News](https://laravel-news.com)
- [Laracasts](https://laracasts.com)

## License

MIT License - Same as Laravel Framework

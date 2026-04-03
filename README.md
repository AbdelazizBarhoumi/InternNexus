# InternNexus - Internship Management & Placement System

A comprehensive web application for managing internship listings, applications, and placements. InternNexus connects students with employers, streamlining the entire internship recruitment process.

## Features

### For Students
- Browse and search internship listings with advanced filters (location, duration, compensation)
- Create and manage student profiles with education, skills, and portfolio links
- Submit applications with resume, cover letter, and transcript uploads
- Track application status (pending, reviewing, interviewed, accepted, rejected)
- View application history and receive status updates

### For Employers
- Create and manage company profiles
- Post internship listings with tags, salary, schedule, and deadline information
- Feature internships for increased visibility
- Review and manage incoming applications
- Update application statuses and add notes
- Track view counts and application statistics

### For Administrators
- Comprehensive admin dashboard with analytics
- User management (promote/demote admins, suspend/activate accounts)
- Internship oversight and moderation
- Application management across all employers
- Account appeal handling for suspended users
- Monthly statistics and reporting

### General Features
- Tag-based internship categorization and filtering
- Advanced search with multiple filter options
- Email verification for new accounts
- Responsive design with Tailwind CSS
- Real-time form validation

## Tech Stack

- **Backend:** PHP 8.2+, Laravel 12
- **Frontend:** Blade Templates, Alpine.js, Tailwind CSS
- **Build Tools:** Vite, PostCSS
- **Database:** MySQL / SQLite
- **Authentication:** Laravel Breeze, Laravel Sanctum
- **Testing:** Pest PHP

## Requirements

- PHP >= 8.2
- Composer
- Node.js >= 18.x
- npm or yarn
- MySQL 8.0+ or SQLite

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/InternNexus.git
   cd InternNexus
   ```

2. **Install PHP dependencies**
   ```bash
   composer install
   ```

3. **Install Node.js dependencies**
   ```bash
   npm install
   ```

4. **Environment setup**
   ```bash
   cp .env.example .env
   php artisan key:generate
   ```

5. **Configure your database**
   
   Edit `.env` and set your database credentials:
   ```env
   DB_CONNECTION=mysql
   DB_HOST=127.0.0.1
   DB_PORT=3306
   DB_DATABASE=internnexus
   DB_USERNAME=your_username
   DB_PASSWORD=your_password
   ```
   
   Or for SQLite:
   ```env
   DB_CONNECTION=sqlite
   ```

6. **Run migrations**
   ```bash
   php artisan migrate
   ```

7. **Build frontend assets**
   ```bash
   npm run build
   ```

## Configuration

### Mail Configuration
Configure your mail settings in `.env` for email verification and notifications:
```env
MAIL_MAILER=smtp
MAIL_HOST=your-smtp-host
MAIL_PORT=587
MAIL_USERNAME=your-username
MAIL_PASSWORD=your-password
MAIL_FROM_ADDRESS=noreply@yourdomain.com
MAIL_FROM_NAME="${APP_NAME}"
```

### File Storage
Uploaded resumes, transcripts, and profile photos are stored in the `storage/app` directory. Run the following to create a symbolic link:
```bash
php artisan storage:link
```

## Usage

### Development Server
Start the development server with hot-reloading:
```bash
composer run dev
```

This will start:
- Laravel development server
- Queue listener
- Log viewer (Pail)
- Vite dev server

Or run individually:
```bash
php artisan serve
npm run dev
```

### Running Tests
```bash
composer run test
```

### Production Build
```bash
npm run build
php artisan config:cache
php artisan route:cache
php artisan view:cache
```

## User Roles

| Role | Capabilities |
|------|-------------|
| **Student** | Browse internships, submit applications, manage profile |
| **Employer** | All student capabilities + post internships, manage applications |
| **Admin** | All capabilities + user management, content moderation |
| **Super Admin** | All admin capabilities + promote/demote admins |

## Project Structure

```
├── app/
│   ├── Http/Controllers/    # Request handlers
│   ├── Models/              # Eloquent models
│   └── Policies/            # Authorization policies
├── database/
│   ├── migrations/          # Database schema
│   ├── factories/           # Model factories
│   └── seeders/             # Database seeders
├── resources/
│   └── views/               # Blade templates
├── routes/
│   ├── web.php              # Web routes
│   ├── application.php      # Application routes
│   ├── internship.php       # Internship routes
│   └── profile.php          # Profile routes
└── tests/                   # Test files
```

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).

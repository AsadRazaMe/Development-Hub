# DevHub - Full-Stack Developer Portfolio & Application Hub

[![PHP Version](https://img.shields.io/badge/PHP-8.2%2B-777BB4?style=flat-square&logo=php&logoColor=white)](https://php.net)
[![MySQL](https://img.shields.io/badge/MySQL-10.4%2B-4479A1?style=flat-square&logo=mysql&logoColor=white)](https://mariadb.org)
[![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Active-brightgreen?style=flat-square)]()

> **DevHub** is a comprehensive full-stack web application serving as both a personal portfolio showcase and a multi-application hub. Built with PHP, MySQL, and modern frontend technologies, it demonstrates full-stack development capabilities through integrated real-world applications.

---

## 🌟 Overview

DevHub is a personal development hub created by **Asad Raza** (Full-Stack Developer) that combines:
- **Portfolio Website** - Showcasing projects, skills, services, and resume
- **Home Expenditure Tracker** - Full-featured personal finance management
- **Contact Directory** - Multi-user telephone directory with role-based access
- **Feedback System** - User feedback collection and management
- **Admin Dashboard** - User management and system administration

---

## 🚀 Features

### 🎨 Portfolio Website (`index.html`)
- **Responsive Design** - Mobile-first approach with modern UI/UX
- **6 Color Themes** - Dark, Light, Blue, Green, Purple, Orange with persistent selection
- **Sections**: Projects, About Me, Services, Resume, Feedback, Contact
- **Interactive Elements** - Theme selector, smooth animations, project cards
- **Tech Stack Display** - Devicons integration for technology visualization

### 💰 Home Expenditure Tracker (`home-expenditure/`)
- **Income & Expense Management** - Categorized transaction tracking
- **Running Balance** - Real-time adjusted balance calculation
- **Category System** - Pre-defined income/expense categories with custom additions
- **User Management** - Multi-user support with role-based access
- **Data Export/Import** - Backup and restore capabilities
- **Password Management** - Secure password change functionality

### 📞 Contact Directory (`contact_directory/`)
- **Multi-User Directories** - Each admin can create their own directory
- **Contact Management** - Add, edit, view, delete contacts with detailed info
- **Member Approval** - Admin approval workflow for new members
- **Role-Based Access** - Super Admin, Admin, Directory Admin, Regular User
- **Rich Contact Details** - Multiple phones, emails, addresses, notes, DOB

### 💬 Feedback System (`feedback/`)
- **Public Submission** - Users can submit feedback/suggestions/bug reports
- **Admin Management** - Status tracking (pending/in_progress/resolved)
- **Admin Notes** - Internal notes for feedback handling
- **IP Tracking** - Basic spam prevention

### 🔐 Authentication & Security (`auth.php`, `login.php`, `signup.php`, `forgot-password.php`)
- **Secure Sessions** - HTTP-only cookies, CSRF protection, regeneration
- **Password Security** - bcrypt hashing (cost 12), strength validation
- **Role-Based Access Control** - 6 user roles (su, ad, ha, hu, ca, cu)
- **Password Reset** - Security question/answer based recovery
- **Brute Force Protection** - Rate limiting on auth endpoints

### ⚙️ Admin Panel (`admin.php`)
- **User Management** - Create, update, delete users
- **Role Assignment** - Assign application access per user
- **Super User Protection** - Immutable root account (ID: 1)
- **Audit Trail** - Flash messaging for all actions

---

## 🛠 Tech Stack

| Layer | Technologies |
|-------|-------------|
| **Backend** | PHP 8.2+, MySQL/MariaDB 10.4+ |
| **Frontend** | HTML5, CSS3, Vanilla JavaScript (ES6+) |
| **Styling** | Custom CSS, CSS Variables, Flexbox/Grid |
| **Icons** | Font Awesome 6.4, Devicons |
| **Fonts** | Google Fonts (Poppins) |
| **Database** | InnoDB, UTF8MB4, Foreign Keys, Indexes |
| **Security** | Prepared Statements, bcrypt, CSRF Tokens, HTTP-only Cookies |

---

## 📁 Project Structure

```
devhub/
├── index.html                 # Main portfolio page
├── admin.php                  # Admin dashboard
├── auth.php                   # Authentication library
├── dbconnect.php              # Database connection
├── login.php                  # User login
├── signup.php                 # User registration
├── logout.php                 # Session destruction
├── forgot-password.php        # Password reset
├── theme.php                  # Theme handling
├── theme-selector.php         # Theme API endpoint
├── save-theme.php             # Theme persistence
├── launcher.php               # App launcher/redirector
├── devhub_db.sql              # Complete database schema
├── assets/                    # Images, icons, static files
├── css/
│   ├── themes/                # 6 theme variations
│   ├── style2.css             # Main portfolio styles
│   └── theme-selector.css     # Theme picker component
├── home-expenditure/          # Finance tracker app
│   ├── css/
│   ├── exp-main.php           # Main dashboard
│   ├── categories.php         # Category management
│   ├── users.php              # User management
│   ├── change-password.php    # Password change
│   ├── exp-edit.php           # Transaction editing
│   ├── delete.php             # Transaction deletion
│   ├── categories-helper.php  # Category utilities
│   └── exp-db.php             # DB connection for app
├── contact_directory/         # Directory app
│   ├── style.css
│   ├── dashboard.php          # User dashboard
│   ├── view-contacts.php      # Contact listing
│   ├── view-details.php       # Contact details
│   ├── add-contact.php        # Add new contact
│   ├── edit-contact.php       # Edit contact
│   ├── save-contact.php       # Save contact
│   ├── update-contact.php     # Update contact
│   ├── delete-contact.php     # Delete contact
│   ├── approve-members.php    # Member approval
│   ├── create-user.php        # Create user
│   ├── save-user.php          # Save user
│   ├── change-password.php    # Password change
│   └── update-password.php    # Update password
└── feedback/                  # Feedback system
    ├── index.php              # Admin feedback view
    ├── submit-feedback.php    # Public submission
    ├── feedback-helper.php    # Helper functions
    └── style.css
```

---

## 🗄 Database Schema

The `devhub_db.sql` file contains the complete schema with 5 tables:

| Table | Purpose |
|-------|---------|
| `users` | Core user accounts, roles, app access, themes, security Q/A |
| `categories` | Income/Expense categories for finance tracker |
| `account_ledger` | Financial transactions with running balance |
| `contacts` | Contact directory entries linked to directories |
| `site_feedback` | User feedback with status tracking |

### User Roles (`app_name` enum)
- **`su`** - Super User (full system access)
- **`ad`** - Administrator (admin panel + all apps)
- **`ha`** - Home Admin (finance tracker admin)
- **`hu`** - Home User (finance tracker user)
- **`ca`** - Contact Admin (directory owner/admin)
- **`cu`** - Contact User (directory member)

---

## ⚡ Quick Start

### Prerequisites
- **PHP 8.2+** with PDO MySQL extension
- **MySQL 8.0+** or **MariaDB 10.4+**
- **Web Server** (Apache/Nginx) or PHP built-in server

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/devhub.git
   cd devhub
   ```

2. **Create database and import schema**
   ```bash
   mysql -u root -p < devhub_db.sql
   ```

3. **Configure database connection**
   Edit `dbconnect.php` with your credentials:
   ```php
   $host = 'localhost';
   $db   = 'devhub_db';
   $user = 'your_username';
   $pass = 'your_password';
   $charset = 'utf8mb4';
   ```

4. **Set up web server**
   - **Apache/Nginx**: Point document root to project directory
   - **PHP Built-in** (development only):
     ```bash
     php -S localhost:8000
     ```

5. **Access the application**
   - Portfolio: `http://localhost:8000/`
   - Admin: `http://localhost:8000/admin.php`
   - Finance: `http://localhost:8000/home-expenditure/exp-main.php`
   - Directory: `http://localhost:8000/contact_directory/dashboard.php`
   - Feedback: `http://localhost:8000/feedback/index.php`

### Default Credentials
| Role | Username | Password |
|------|----------|----------|
| Super User | `AsadRaza` | (set during install) |

> **Important**: Change default passwords immediately after first login!

---

## 🔧 Configuration

### Environment Variables (Recommended)
Create a `.env` file (not tracked by git):
```env
DB_HOST=localhost
DB_NAME=devhub_db
DB_USER=your_user
DB_PASS=your_password
APP_URL=http://localhost:8000
SESSION_LIFETIME=3600
```

### Theme Customization
Themes are defined in `css/themes/`:
- `theme-dark.css` (default)
- `theme-light.css`
- `theme-blue.css`
- `theme-green.css`
- `theme-purple.css`
- `theme-orange.css`

Modify CSS variables in each file to customize colors.

---

## 🔒 Security Features

- **SQL Injection Prevention** - All queries use prepared statements
- **XSS Protection** - Output escaping with `htmlspecialchars()`
- **CSRF Protection** - Token validation on all state-changing operations
- **Session Security** - HTTP-only, Secure, SameSite cookies; ID regeneration
- **Password Hashing** - bcrypt with cost factor 12
- **Access Control** - Role-based permissions at route and resource level
- **Input Validation** - Server-side validation on all user inputs

---

## 📸 Screenshots

> *Add screenshots here by placing images in `assets/screenshots/` and referencing them:*
> ```
> ![Portfolio Home](assets/screenshots/home.png)
> ![Finance Tracker](assets/screenshots/finance.png)
> ![Contact Directory](assets/screenshots/directory.png)
> ![Admin Panel](assets/screenshots/admin.png)
> ```

---

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Guidelines
- Follow PSR-12 coding standards for PHP
- Use semantic commit messages
- Maintain backward compatibility
- Add tests for new features
- Update documentation as needed

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

---

## 👨‍💻 Author

**Asad Raza** - Full-Stack Developer

- **Portfolio**: [Development Hub](https://your-portfolio-url.com)
- **GitHub**: [@yourusername](https://github.com/yourusername)
- **LinkedIn**: [Asad Raza](https://linkedin.com/in/yourprofile)
- **Email**: your.email@example.com

---

## 🙏 Acknowledgments

- [Font Awesome](https://fontawesome.com/) for icons
- [Devicons](https://devicon.dev/) for technology logos
- [Google Fonts](https://fonts.google.com/) for Poppins font family
- [PHP](https://php.net/) and [MariaDB](https://mariadb.org/) communities

---

## 📊 Project Stats

![Lines of Code](https://img.shields.io/badge/LOC-10k%2B-blue?style=flat-square)
![Files](https://img.shields.io/badge/Files-40%2B-orange?style=flat-square)
![Tables](https://img.shields.io/badge/DB_Tables-5-green?style=flat-square)
![Themes](https://img.shields.io/badge/Themes-6-purple?style=flat-square)

---

<div align="center">
  <strong>Built with ❤️ by Asad Raza</strong><br>
  <em>Full-Stack Developer | Problem Solver | Continuous Learner</em>
</div>

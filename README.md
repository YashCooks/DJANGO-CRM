# Django CRM - Customer Relationship Management System

A modern, full-featured Customer Relationship Management (CRM) system built with Django and Bootstrap. This application allows businesses to efficiently manage customer records with a clean, responsive web interface.

## 🌟 Features

### Customer Management
- **Complete CRUD Operations**: Create, Read, Update, and Delete customer records
- **Detailed Customer Profiles**: Store comprehensive customer information including:
  - Personal details (First name, Last name, Email)
  - Contact information (Phone number, Address)
  - Location data (City, State, ZIP code)
  - Automatic timestamps for record creation

### User Authentication & Security
- **User Registration**: New users can create accounts with custom signup forms
- **Secure Login/Logout**: Django's built-in authentication system
- **Session Management**: Automatic session handling and user state management
- **Access Control**: Protected routes that require authentication
- **Flash Messages**: Real-time feedback for user actions

### User Interface
- **Responsive Design**: Bootstrap-powered interface that works on all devices
- **Clean Navigation**: Intuitive navbar with user-friendly navigation
- **Professional Layout**: Modern design with proper spacing and typography
- **Interactive Tables**: Easy-to-read customer data presentation
- **Form Validation**: Client and server-side validation for data integrity

## 🚀 Quick Start

### Prerequisites
- Python 3.8 or higher
- Django 4.1 or higher
- Git (for version control)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/YashCooks/DJANGO-CRM.git
   cd DJANGO-CRM
   ```

2. **Install Django** (if not already installed)
   ```bash
   pip install django
   ```

3. **Run database migrations**
   ```bash
   python manage.py migrate
   ```

4. **Create a superuser account** (optional)
   ```bash
   python manage.py createsuperuser
   ```

5. **Start the development server**
   ```bash
   python manage.py runserver
   ```

6. **Access the application**
   - Main application: http://127.0.0.1:8000/
   - Admin panel: http://127.0.0.1:8000/admin/

## 📁 Project Structure

```
DJANGO-CRM/
│
├── dcrm/                     # Main Django project directory
│   ├── __init__.py
│   ├── settings.py           # Project settings and configuration
│   ├── urls.py              # Main URL routing
│   ├── wsgi.py              # WSGI configuration
│   └── asgi.py              # ASGI configuration
│
├── website/                  # Main application directory
│   ├── migrations/          # Database migration files
│   ├── templates/           # HTML templates
│   │   ├── base.html        # Base template with common elements
│   │   ├── navbar.html      # Navigation bar component
│   │   ├── home.html        # Homepage with customer list
│   │   ├── record.html      # Customer detail view
│   │   ├── register.html    # User registration form
│   │   ├── add_record.html  # Add new customer form
│   │   └── update_record.html # Update customer form
│   ├── __init__.py
│   ├── admin.py             # Django admin configuration
│   ├── apps.py              # App configuration
│   ├── forms.py             # Custom forms for user input
│   ├── models.py            # Database models
│   ├── tests.py             # Unit tests
│   ├── urls.py              # App-specific URL routing
│   └── views.py             # Business logic and view functions
│
├── manage.py                # Django management script
├── mydb.py                  # Database utilities
├── db.sqlite3               # SQLite database (created after migrations)
├── .gitignore               # Git ignore rules
└── README.md                # This file
```

## 🗄️ Database Schema

### Record Model
The core customer data model includes:

| Field | Type | Description |
|-------|------|-------------|
| `id` | AutoField | Primary key (auto-generated) |
| `created_at` | DateTimeField | Record creation timestamp |
| `first_name` | CharField(50) | Customer's first name |
| `last_name` | CharField(50) | Customer's last name |
| `email` | CharField(100) | Customer's email address |
| `phone` | CharField(15) | Customer's phone number |
| `address` | CharField(100) | Customer's street address |
| `city` | CharField(50) | Customer's city |
| `state` | CharField(50) | Customer's state/province |
| `zipcode` | CharField(20) | Customer's postal/ZIP code |

## 🔧 Configuration

### Database Settings
The project is configured to use SQLite for development by default. To change the database:

1. Open `dcrm/settings.py`
2. Modify the `DATABASES` configuration
3. Install the appropriate database adapter
4. Run migrations: `python manage.py migrate`

### Environment Variables
For production deployment, consider using environment variables for:
- `SECRET_KEY`: Django secret key
- `DEBUG`: Debug mode setting
- `ALLOWED_HOSTS`: Allowed host names
- Database credentials

## 🌐 URL Routing

| URL | View | Description |
|-----|------|-------------|
| `/` | `home` | Homepage with customer list and login |
| `/logout/` | `logout_user` | User logout |
| `/register/` | `register_user` | User registration |
| `/record/<int:pk>/` | `customer_record` | View specific customer |
| `/delete_record/<int:pk>/` | `delete_record` | Delete customer |
| `/add_record/` | `add_record` | Add new customer |
| `/update_record/<int:pk>/` | `update_record` | Update customer |
| `/admin/` | Django Admin | Admin interface |

## 🔐 Authentication & Authorization

### User Registration
- Custom signup form with enhanced validation
- Automatic login after successful registration
- Password confirmation and strength validation

### Login System
- Username and password authentication
- Session-based user management
- Automatic redirect after login
- "Remember me" functionality through sessions

### Access Control
- Protected views require authentication
- Automatic redirect to login for unauthorized access
- User-specific data access control

## 🎨 Frontend Features

### Bootstrap Integration
- Responsive grid system
- Modern UI components
- Mobile-first design approach
- Professional color scheme

### Interactive Elements
- Dynamic navigation based on auth status
- Real-time form validation feedback
- Hover effects and transitions
- Modal dialogs for confirmations

### User Experience
- Intuitive navigation flow
- Clear call-to-action buttons
- Consistent visual hierarchy
- Loading states and progress indicators

## 📱 Responsive Design

The application is fully responsive and optimized for:
- **Desktop**: Full-featured interface with sidebar navigation
- **Tablet**: Adapted layout with collapsible elements
- **Mobile**: Touch-friendly interface with optimized forms

## 🧪 Testing

### Running Tests
```bash
python manage.py test
```

### Test Coverage
The project includes tests for:
- Model functionality
- View logic and permissions
- Form validation
- URL routing

## 🚀 Deployment

### Production Checklist
- [ ] Set `DEBUG = False` in settings
- [ ] Configure `ALLOWED_HOSTS`
- [ ] Set up environment variables
- [ ] Configure production database
- [ ] Set up static file serving
- [ ] Configure HTTPS
- [ ] Set up monitoring and logging

### Recommended Platforms
- **Heroku**: Easy deployment with PostgreSQL
- **DigitalOcean**: VPS with full control
- **AWS**: Scalable cloud deployment
- **PythonAnywhere**: Beginner-friendly hosting

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Development Guidelines
- Follow PEP 8 style guidelines
- Write descriptive commit messages
- Include tests for new features
- Update documentation as needed

## 🆘 Support & Documentation

### Getting Help
- Check the [Django Documentation](https://docs.djangoproject.com/)
- Review existing [GitHub Issues](https://github.com/YashCooks/DJANGO-CRM/issues)
- Create a new issue for bugs or feature requests

### Common Issues
- **Migration errors**: Delete `db.sqlite3` and re-run migrations
- **Static files**: Run `python manage.py collectstatic` in production
- **Permission errors**: Check user authentication requirements

## 📊 Project Status

- ✅ **Stable**: Core functionality implemented and tested
- ✅ **Responsive**: Mobile and desktop optimized
- ✅ **Secure**: Authentication and authorization implemented
- 🔄 **Active Development**: Regular updates and improvements

## 👨‍💻 Author

**YashCooks**
- GitHub: [@YashCooks](https://github.com/YashCooks)
- Project: [Django CRM](https://github.com/YashCooks/DJANGO-CRM)

---

⭐ **If you find this project helpful, please consider giving it a star on GitHub!**

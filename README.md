# Tip Top - Freelance Earning Platform

A Django-based web application that allows users to earn coins through various activities and redeem them for money.

## Features

- **User Authentication**: Sign up, login, and password reset functionality
- **Coin Earning System**: Users can earn coins through various activities
- **Money Redemption**: Convert earned coins to real money
- **Ad Management**: Display and manage advertisements
- **Modern UI**: Responsive design with Bootstrap and custom CSS
- **Dashboard**: Comprehensive user dashboard with earning statistics

## Technology Stack

- **Backend**: Django 5.2.2
- **Database**: SQLite (development), PostgreSQL recommended for production
- **Authentication**: Django Allauth
- **Frontend**: HTML5, CSS3, JavaScript, Bootstrap 4.5.2
- **Email**: SMTP integration for password reset
- **Icons**: Font Awesome 6.4.0

## Project Structure

```
Tip Top/
├── mysite/            # Main Django project settings
├── coins/             # Coins app for earning/redeeming system
├── ads/               # Ads app for advertisement management
├── templates/         # HTML templates
├── static/            # CSS, JavaScript, and static files
├── manage.py          # Django management script
└── requirements.txt   # Python dependencies
```

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/FangScript/Tip-Top.git
   cd Tip-Top
   ```

2. **Create a virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up environment variables**
   Create a `.env` file in the project root:
   ```env
   SECRET_KEY=your-secret-key-here
   DEBUG=True
   EMAIL_HOST_USER=your-email@gmail.com
   EMAIL_HOST_PASSWORD=your-app-password
   ```

5. **Run migrations**
   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

6. **Create a superuser**
   ```bash
   python manage.py createsuperuser
   ```

7. **Run the development server**
   ```bash
   python manage.py runserver
   ```

## Configuration

### Email Settings
The application uses Gmail SMTP for sending password reset emails. Update the email settings in `mysite/settings.py`:

```python
EMAIL_HOST = 'smtp.gmail.com'
EMAIL_PORT = 587
EMAIL_HOST_USER = 'your-email@gmail.com'
EMAIL_HOST_PASSWORD = 'your-app-password'
EMAIL_USE_TLS = True
```


## Usage

### For Users
1. **Sign up** for a new account or **login** with existing credentials
2. **Earn coins** by completing various activities
3. **Redeem coins** for real money (100 coins = $1)
4. **View earnings** and transaction history in the dashboard

### For Administrators
1. **Manage users** through Django admin interface
2. **Upload ads** and manage advertisement content
3. **Monitor coin transactions** and user activities
4. **Configure earning rates** and redemption values

## API Endpoints

- `/signup/` - User registration and login
- `/dashboard/` - User dashboard (requires authentication)
- `/coins/earn/` - Earn coins (requires authentication)
- `/coins/redeem/` - Redeem coins for money (requires authentication)
- `/ads/` - View advertisements
- `/admin/` - Django admin interface

## Security Considerations

⚠️ **Important**: Before deploying to production:

1. **Change the SECRET_KEY** in settings.py
2. **Set DEBUG = False**
3. **Configure ALLOWED_HOSTS** properly
4. **Use environment variables** for sensitive data
5. **Enable HTTPS** for production deployment
6. **Use a production database** (PostgreSQL recommended)

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For support and questions, please open an issue on GitHub or contact the development team.

## Roadmap

- [ ] Enhanced earning activities (surveys, games, tasks)
- [ ] Payment gateway integration
- [ ] Mobile app development
- [ ] Advanced analytics dashboard
- [ ] Multi-language support
- [ ] API documentation
- [ ] Unit tests and CI/CD pipeline

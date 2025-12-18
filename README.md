# Django E-Commerce Platform

A full-featured e-commerce web application built with Django, featuring product management, shopping cart functionality, and PayPal payment integration.

## 🌟 Features

- **Product Management**: Browse products by categories with detailed descriptions and images
- **Shopping Cart**: Add, update, and remove items from your cart with real-time calculations
- **User Authentication**: Secure user registration, login, and profile management
- **User Profiles**: Customer profiles with shipping address and order history
- **Payment Integration**: PayPal payment gateway integration for secure transactions
- **Admin Dashboard**: Django admin interface for managing products, orders, and users
- **Responsive Design**: Mobile-friendly interface for seamless shopping experience

## 🛠️ Technology Stack

- **Backend**: Django 4.2.4
- **Database**: SQLite (Development) / PostgreSQL (Production ready)
- **Payment Gateway**: PayPal (django-paypal)
- **Static Files**: WhiteNoise for static file serving
- **Deployment**: Gunicorn WSGI server
- **Image Processing**: Pillow for product images

## 📋 Prerequisites

Before you begin, ensure you have the following installed:
- Python 3.x
- pip (Python package installer)
- Virtual environment (recommended)

## 🚀 Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd DBMS_project
   ```

2. **Create and activate virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up environment variables**
   - Create a `.env` file in the project root
   - Add the following variables:
   ```env
   DB_PASSWORD_YO=your_database_password
   SECRET_KEY=your_secret_key
   DEBUG=True
   ```

5. **Run migrations**
   ```bash
   python manage.py migrate
   ```

6. **Create a superuser**
   ```bash
   python manage.py createsuperuser
   ```

7. **Collect static files**
   ```bash
   python manage.py collectstatic
   ```

8. **Run the development server**
   ```bash
   python manage.py runserver
   ```

9. **Access the application**
   - Frontend: http://127.0.0.1:8000/
   - Admin Panel: http://127.0.0.1:8000/admin/

## 📁 Project Structure

```
DBMS_project/
├── cart/               # Shopping cart functionality
├── ecom/              # Main project configuration
│   ├── settings.py    # Project settings
│   ├── urls.py        # URL routing
│   └── wsgi.py        # WSGI configuration
├── payment/           # Payment processing
├── store/             # Product and store management
│   ├── models.py      # Database models
│   ├── views.py       # View functions
│   ├── forms.py       # Django forms
│   ├── urls.py        # Store URLs
│   └── templates/     # HTML templates
├── static/            # Static files (CSS, JS, images)
├── staticfiles/       # Collected static files
├── media/             # User uploaded files
├── db.sqlite3         # SQLite database
├── manage.py          # Django management script
├── requirements.txt   # Python dependencies
├── procfile           # Deployment configuration
└── runtime.txt        # Python runtime version
```

## 🗄️ Database Models

### Product
- Product information (name, price, description, image)
- Category association
- Sale pricing support

### Category
- Product categorization

### Profile
- Extended user information
- Shipping address details
- Order history

### Customer
- Customer account details

### Order
- Order tracking and management
- Product-customer relationship

## 🔧 Configuration

### Database
The project supports both SQLite (development) and PostgreSQL (production). To switch to PostgreSQL:

1. Uncomment the PostgreSQL configuration in `ecom/settings.py`
2. Set up your PostgreSQL credentials in environment variables
3. Run migrations

### PayPal Integration
Configure PayPal settings in `ecom/settings.py`:
- `PAYPAL_TEST = True` for sandbox mode
- `PAYPAL_RECEIVER_EMAIL` for your business account

## 🌐 Deployment

The project is configured for deployment on Railway:
- `procfile`: Defines the web server command
- `runtime.txt`: Specifies Python version
- WhiteNoise: Handles static files in production
- Gunicorn: Production WSGI server

### Deployment Steps:
1. Set `DEBUG = False` in production
2. Update `ALLOWED_HOSTS` with your domain
3. Configure `CSRF_TRUSTED_ORIGINS`
4. Set up environment variables in your hosting platform
5. Run `python manage.py collectstatic`
6. Deploy using the provided procfile

## 📝 Usage

### For Customers:
1. Browse products by category
2. Add items to cart
3. Register/Login to checkout
4. Complete profile information
5. Process payment via PayPal
6. Track orders

### For Administrators:
1. Access admin panel at `/admin`
2. Manage products, categories, and inventory
3. Process orders
4. Manage customer accounts

## 🔐 Security Notes

- Secret key is exposed in the code - **change it before deployment**
- Set `DEBUG = False` in production
- Configure proper `ALLOWED_HOSTS` for production
- Use environment variables for sensitive data
- Enable HTTPS in production

## 🤝 Contributing

Contributions are welcome! Please follow these steps:
1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Open a pull request

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 📧 Contact

For questions or support, please contact the project maintainer.

## 🙏 Acknowledgments

- Django Framework
- PayPal Developer Platform
- WhiteNoise for static file serving
- Railway for hosting platform


# ChatApp

A real-time chat application built with Django.

## Prerequisites

Make sure you have the following installed:
- Python 3.8+
- pip
- Virtualenv (optional but recommended)

## Setup Instructions

1. **Clone the Repository**

   ```bash
   git clone <repository-url>
   cd ChatApp
   ```

2. **Create a Virtual Environment**

   It's recommended to use a virtual environment to manage dependencies.

   ```bash
   # On macOS/Linux
   python3 -m venv venv
   source venv/bin/activate

   # On Windows
   python -m venv venv
   .\venv\Scripts\activate
   ```

3. **Install Dependencies**

   Install the required packages listed in `requirements.txt`.

   ```bash
   pip install -r requirements.txt
   ```

4. **Set Up Environment Variables**

   Create a `.env` file in the root directory to store environment variables. Add your configurations such as secret keys and database settings:

   ```plaintext
   SECRET_KEY=your-secret-key
   DEBUG=True
   ```

5. **Database Configuration**

   This project uses **SQLite** as the default database for demonstration purposes. SQLite is suitable for local development but not recommended for production.

   ### Replacing SQLite for Production
   - For production, consider replacing SQLite with a more robust database, like **PostgreSQL** or **MySQL**.
   - Update the `DATABASES` setting in `settings.py` with your chosen database configuration.

   Example configuration for PostgreSQL:
   ```python
   DATABASES = {
       'default': {
           'ENGINE': 'django.db.backends.postgresql',
           'NAME': 'your_db_name',
           'USER': 'your_db_user',
           'PASSWORD': 'your_password',
           'HOST': 'localhost',
           'PORT': '5432',
       }
   }
   ```

6. **Channel Layers Configuration**

   This project uses Django Channels with an **InMemoryChannelLayer** for demonstration. The `InMemoryChannelLayer` is a basic in-memory backend useful for development and testing.

   ### Replacing InMemoryChannelLayer for Production
   - For production, use **Redis** as the channel layer backend, which is more reliable for handling real-time events in a distributed system.
   - Update the `CHANNEL_LAYERS` setting in `settings.py`:

   Example configuration with Redis:
   ```python
   CHANNEL_LAYERS = {
       'default': {
           'BACKEND': 'channels_redis.core.RedisChannelLayer',
           'CONFIG': {
               "hosts": [('127.0.0.1', 6379)],
           },
       },
   }
   ```

7. **Apply Migrations**

   Run the following commands to set up the database schema:

   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

8. **Create a Superuser (Optional)**

   To access the Django admin interface, create a superuser account:

   ```bash
   python manage.py createsuperuser
   ```

9. **Run the Development Server**

   Start the Django development server to test your app locally.

   ```bash
   python manage.py runserver
   ```

10. **Access the Application**

    Open your browser and go to:

    ```
    http://127.0.0.1:8000
    ```


## License

This project is licensed under the MIT License.

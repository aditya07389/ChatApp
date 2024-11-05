
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

5. **Apply Migrations**

   Run the following commands to set up the database schema:

   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

6. **Create a Superuser (Optional)**

   To access the Django admin interface, create a superuser account:

   ```bash
   python manage.py createsuperuser
   ```

7. **Run the Development Server**

   Start the Django development server to test your app locally.

   ```bash
   python manage.py runserver
   ```

8. **Access the Application**

   Open your browser and go to:

   ```
   http://127.0.0.1:8000
   ```

## Additional Notes

- Ensure the `.env` file is listed in `.gitignore` to keep sensitive information secure.
- If using WebSockets or channels for real-time chat, make sure to configure Redis or any other message broker as required.

## License

This project is licensed under the MIT License.


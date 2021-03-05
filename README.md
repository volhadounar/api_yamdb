Service Yamdb
=================================

In a team with my colleagues we have written service – databases of reviewing films, books, music and
REST API for it. My role included registration and authentication system, access rights, work with a token, e-mail confirmation system.

Tech stack: Python3, Django Rest Framework, HTTP, HTTPS, SQLite3, Visual Studio
Code, Postman, Yandex Cloud.

Getting Started
===============

1.  You can build it in steps:
    1.  ``cd ...wherever...``
    2.  ``git clone https://github.com/volhadounar/api_yamdb.git``
    3.  ``cd api_yamdb``
    4.  ``pip install -r requirements.txt``  -- Should install everything you need
    5.  ``python3 manage.py migrate`` -- Reads all the migrations folders in the application folders and creates / evolves the tables in the database
    6.  ``python3 manage.py createsuperuser``
    7.  ``python manage.py loaddata dump.json`` -- To fill db with test data
    8.  ``python3 manage.py runserver`` -- Running localy
2. The usage:
    1. There you can read the documentation:
        http://localhost:8000/redoc/
    2. http://localhost:8000/admin -- Visit admin page to create items as admin
    3. Try e-mail confirmation system:
        1. In Postman make put request with body {"email":"some_email"} using:
        http://localhost:8000/api/v1/auth/email/
        2. Find confirmation code in the folder 'sent_emails'. Use it in the next step.
        3. Make put request with body {"email":"some_mail", "confirmation_code": "some_confcode_from_email"}:
        http://localhost:8000/api/v1/auth/token/
        4. Input token in the request headers: `Authorization: Bearer <token>`
        5. http://localhost:8000/api/v1/users/me/ -- Fetch current profile data
        
The project was deployed at the remote server on Yandex Cloud, check https://130.193.54.237/ or https://ilza.ga/, or https://www.ilza.ga/.


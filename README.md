# Django-Authorization
How to Implement Authorization in Django

# Hospital System

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://opensource.org/licenses/MIT)

## Description

A Django project for managing a hospital system using [Permit.io](https://app.permit.io/) for authorization. The project includes a RESTful API for managing patients, doctors, and appointments. The API is secured using ABAC (Attribute-Based Access Control) and RBAC (Role-Based Access Control) policies. The project also includes a PDP (Policy Decision Point) microservice for evaluating access control policies. 

## Features

- ABAC (Attribute-Based Access Control)
- CRUD operations
- RESTful API
- User authentication
- Role-based access control
- ReBAC (Relationship-Based Access Control)

## Installation

1. Clone the repository: `https://github.com/tyaga001/django-authorization.git`

2. **Cd into the project directory:**

    ```sh
    cd hsystem
    ```

3. **Create a virtual environment:**

    ```sh
    python3 -m venv venv
    ```

4. **Activate virtualenv:**

    For general use:
    
    ```sh
    source venv/bin/activate
    ```

    For zsh users:
    
    ```sh
    source venv/bin/activate.zsh
    ```

    For bash users:
    
    ```sh
    source venv/bin/activate.bash
    ```

    For fish users:
    
    ```sh
    source venv/bin/activate.fish
    ```

5. **Install the dependencies:**

    ```sh
    pip install -r requirements.txt
    ```

6. **Apply database migrations:**

    ```sh
    python manage.py migrate
    ```

    Or

    ```sh
    python manage.py migrate --run-syncdb
    ```

    Or

    ```sh
    python manage.py makemigrations hsystem
    python manage.py migrate
    ```

7. **Start the development server:**

    ```sh
    python manage.py runserver 5000
    ```



## Run your local PDP Microservice container

If you do not have Docker installed as of yet, click [here](https://docs.docker.com/get-docker/) to install Docker.

### Pull the container 

Run the following command to pull the PDP Microservice container:

```bash
docker pull permitio/pdp-v2:latest
```

### Run the container

Remember to replace <YOUR_API_KEY> with the Secret Key you obtained from your dashboard.

```bash

docker run -it -p 7766:7000 --env PDP_DEBUG=True --env PDP_API_KEY=<YOUR_API_KEY> permitio/pdp-v2:latest

```

## Usage

1. Create a superuser: `python manage.py createsuperuser`
2. Access the admin panel: `http://localhost:5000/admin/`
3. Access the API: `http://localhost:5000/api/`
4. Access the documentation: `http://localhost:5000/docs/` 

## Test the App

Run the following command in a separate terminal to test whether the app is working as expected:

```bash
curl -X GET http://localhost:5000/patients/1/

```

## License

This project is licensed under the [MIT License](LICENSE).

## Blog
[How to Implement Authorization with Django](https://www.permit.io/blog/fine-grained-authorization-with-django)

## Additional Resources

- Follow my articles on [freeCodeCamp](https://www.freecodecamp.org/news/author/theankurtyagi/).
- Visit my [personal blog](https://theankurtyagi.com/blog/) for more tech-related articles.

Thank you for reading, and happy coding.


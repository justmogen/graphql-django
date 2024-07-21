# Hacker News

A Django project that implements a simple news application with GraphQL support. This project demonstrates the use of Django and GraphQL for building APIs.

## Features

- User authentication with JWT
- Create and manage links
- Query users and links with GraphQL

## Requirements

- Python 3.6 or later
- Django 2.1.4
- Graphene-Django 2.2.0
- GraphQL-JWT

## Installation

1. **Clone the Repository**

    ```sh
    git clone https://github.com/yourusername/your-repo.git
    cd your-repo
    ```

2. **Set Up a Virtual Environment**

    ```sh
    python3 -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3. **Install Dependencies**

    ```sh
    pip install -r requirements.txt
    ```

4. **Apply Migrations**

    ```sh
    python manage.py migrate
    ```

5. **Create a Superuser (Optional)**

    ```sh
    python manage.py createsuperuser
    ```

6. **Run the Development Server**

    ```sh
    python manage.py runserver
    ```

    Open your browser and navigate to `http://127.0.0.1:8000/graphql/` to access the GraphQL API.

## Usage

- **GraphQL Endpoints**

  - **Query Links**

    ```graphql
    query {
      links {
        id
        url
        description
      }
    }
    ```

  - **Create a Link**

    ```graphql
    mutation {
      createLink(url: "https://example.com", description: "Example Link") {
        id
        url
        description
      }
    }
    ```

- **User Authentication**

  - **Obtain JSON Web Token**

    ```graphql
    mutation {
      tokenAuth(username: "yourusername", password: "yourpassword") {
        token
      }
    }
    ```

  - **Verify Token**

    ```graphql
    mutation {
      verifyToken(token: "yourjwt") {
        payload
      }
    }
    ```

  - **Refresh Token**

    ```graphql
    mutation {
      refreshToken(token: "yourjwt") {
        token
      }
    }
    ```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

- [Django](https://www.djangoproject.com/)
- [Graphene-Django](https://docs.graphene-python.org/projects/django/en/latest/)
- [GraphQL-JWT](https://github.com/flavors/django-graphql-jwt)


# Web Chat Backend System

This is the backend system for a Web Chat application built with Django, Django Channels, and WebSockets. The backend supports user authentication, chat messaging, and real-time communication features.

## Features

- JWT-based user authentication (using cookies)
- WebSocket integration for real-time messaging
- RESTful API for user and chat management
- PostgreSQL database for data storage
- Redis for handling WebSocket message broadcasting
- Google OAuth integration for Google login (optional)
  
## Tech Stack

- **Backend Framework:** Django, Django Channels
- **Database:** PostgreSQL
- **WebSockets:** Channels and Daphne
- **Redis:** For WebSocket management
- **Authentication:** Simple JWT (JSON Web Token)
  
## Setup Instructions

### Prerequisites

Ensure you have the following installed:

- [Python 3.10+](https://www.python.org/downloads/)
- [Docker](https://docs.docker.com/get-docker/) (optional, for containerized deployment)
- [PostgreSQL](https://www.postgresql.org/) (if not using Docker)
- [Redis](https://redis.io/) (if not using Docker)

### Installation

1. **Clone the repository:**
   ```bash
   git clone git@github.com:SulimanSagindykov/WebChatBackendSystem.git
   cd WebChatBackendSystem/backend
   ```

2. **Create a virtual environment and activate it**:

    ```bash
    python3 -m venv venv
    source venv/bin/activate
    ```
3. **Install the required dependencies:**

    ```bash
    pip install -r requirements.txt
    ```
Set up environment variables (if needed): You may need to set up environment variables such as POSTGRES_USER, POSTGRES_PASSWORD, etc., for local PostgreSQL usage.

4. **Run migrations: Initialize the database:**

```bash
python manage.py migrate
```

5. **Run the development server: Start the Django development server:**

```bash
python manage.py runserver
```
## Using Docker
To run the project using Docker:

1. **Build and run Docker containers:**

```bash
docker-compose up --build
```
2. **The backend will be available at http://localhost:8000/.**

## API Endpoints
Here are some of the key API endpoints:

- POST /api/register/ - Register a new user
- POST /api/login/ - Login a user and get JWT tokens
- POST /api/logout/ - Logout the user and clear cookies
- GET /api/user/ - Get the current logged-in user
- GET /api/user_chats/ - Get all chat groups for the current user
- POST /api/create_chat/ - Create a new chat group
- GET /api/chat/<id>/ - Get all messages for a chat group

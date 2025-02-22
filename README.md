# PizzaDelivery

## Overview
PizzaDelivery is a Django-based web application that provides a seamless food delivery experience. It integrates Django Rest Framework, Celery for background task processing, Redis for caching, and Elasticsearch for search capabilities.

## Features
- **User Authentication**: Secure login/logout using Django Rest Framework SimpleJWT.
- **Order Management**: Users can place, track, and cancel orders.
- **Real-time Updates**: Uses Django Channels and WebSockets for live order tracking.
- **Search Functionality**: Implements full-text search using Elasticsearch.
- **Task Scheduling**: Uses Celery and Django-Celery-Beat for task automation.
- **Admin Panel**: Includes Django Jet and Grappelli for enhanced admin interface.
- **Database Support**: Compatible with PostgreSQL and MySQL.
- **Background Processing**: Uses Celery and RabbitMQ for handling async tasks.

## Tech Stack
- **Backend**: Django 5.0.2, Django Rest Framework 3.15.2
- **Database**: PostgreSQL/MySQL
- **Caching**: Redis
- **Search**: Elasticsearch 8.14.0
- **Task Queue**: Celery 5.4.0, RabbitMQ
- **WebSockets**: Django Channels, Daphne
- **Testing & Monitoring**: Locust for load testing, Django Debug Toolbar
- **Automation**: Cron jobs using Django-Crontab

## Installation
### Prerequisites
- Python 3.10+
- PostgreSQL/MySQL
- Redis
- Elasticsearch
- RabbitMQ

### Setup
1. Clone the repository:
   ```sh
   git clone https://github.com/your-repo/pizzadelivery.git
   cd pizzadelivery
   ```
2. Create a virtual environment and install dependencies:
   ```sh
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   pip install -r requirements.txt
   ```
3. Configure environment variables:
   ```sh
   cp .env.example .env
   ```
4. Run database migrations:
   ```sh
   python manage.py migrate
   ```
5. Start Redis, Celery, and Django server:
   ```sh
   redis-server &
   celery -A pizzadelivery worker --loglevel=info &
   python manage.py runserver
   ```

## Usage
- Visit `http://127.0.0.1:8000/admin/` for the admin panel.
- API documentation available at `/api/docs/` if configured.
- Use Postman or a frontend client to interact with the API.

## Contributing
Contributions are welcome! To contribute:
1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes and commit (`git commit -m 'Add new feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Open a Pull Request.

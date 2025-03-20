# HBnB Project - Part 3: Enhanced Backend with Database Integration

This is the third part of the HBnB project, where we've enhanced the backend by adding:

1. **User Authentication** with JWT
2. **Database Integration** using SQLAlchemy 
3. **Role-based Access Control** for admin functionality
4. **Enhanced Security** with password hashing

## Features

- **JWT-based Authentication**: Secure API endpoints with JSON Web Tokens
- **Database Integration**: SQLite for development, configurable for MySQL in production
- **Role-based Access Control**: Admin users have additional permissions
- **Password Security**: Passwords are securely hashed using bcrypt
- **RESTful API**: Well-designed API endpoints following REST principles
- **Swagger Documentation**: Interactive API documentation via Swagger UI

## Tech Stack

- **Backend**: Flask, Flask-RESTx
- **Authentication**: Flask-JWT-Extended, Flask-Bcrypt
- **Database**: SQLAlchemy with SQLite/MySQL
- **API Documentation**: Swagger UI (via Flask-RESTx)

## Database Schema

The project uses the following database models:

- **User**: Stores user details including authentication info
- **Place**: Represents accommodation listings
- **Review**: Contains reviews for places
- **Amenity**: Represents features that places can have

The database schema is visualized in an ER diagram (see /docs/er_diagram.md)

## Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/holbertonschool-hbnb.git
cd holbertonschool-hbnb/part2
```

2. Create and activate a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Configure environment variables:
Copy `.env.example` to `.env` and update the variables as needed.

## Running the Application

1. Initialize the database:
```bash
python -m app.db_init
```

2. Run the application:
```bash
python run.py
```

The API will be available at http://localhost:5000 and the Swagger documentation at http://localhost:5000/

## API Endpoints

### Authentication
- `POST /api/v1/auth/login` - Login and get JWT token

### Users
- `POST /api/v1/users` - Create a new user
- `GET /api/v1/users` - Get all users (admin only)
- `GET /api/v1/users/{user_id}` - Get a specific user
- `PUT /api/v1/users/{user_id}` - Update a user

### Places
- `POST /api/v1/places` - Create a new place
- `GET /api/v1/places` - Get all places
- `GET /api/v1/places/{place_id}` - Get a specific place
- `PUT /api/v1/places/{place_id}` - Update a place

### Reviews
- `POST /api/v1/reviews` - Create a new review
- `GET /api/v1/reviews` - Get all reviews
- `GET /api/v1/reviews/{review_id}` - Get a specific review
- `PUT /api/v1/reviews/{review_id}` - Update a review

### Amenities
- `POST /api/v1/amenities` - Create a new amenity
- `GET /api/v1/amenities` - Get all amenities
- `GET /api/v1/amenities/{amenity_id}` - Get a specific amenity
- `PUT /api/v1/amenities/{amenity_id}` - Update an amenity

## Authentication

To access protected endpoints, include the JWT token in the Authorization header:

```
Authorization: Bearer your_token_here
```

You can get a token by logging in via the `/api/v1/auth/login` endpoint. 
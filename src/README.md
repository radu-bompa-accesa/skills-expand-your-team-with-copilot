# Mergington High School Activities

A FastAPI website for managing extracurricular activities at Mergington High School.

The site serves a single-page web interface at `/` (redirects to `/static/index.html`) and uses API endpoints for activity data and teacher authentication.

## Features

- Browse all extracurricular activities
- Search activities by name
- Filter activities by:
  - category (Sports, Arts, Academic, Community, Technology)
  - difficulty (Beginner, Intermediate, Advanced)
  - day of week
  - time range (Before School, After School, Weekend)
- Teacher login and session check
- Register and unregister students for activities (teacher-authenticated actions)
- Light and dark theme toggle in the web interface

## API Endpoints

### Activities

- `GET /activities`
  - Optional query parameters: `day`, `start_time`, `end_time`, `difficulty`
- `GET /activities/days`
- `POST /activities/{activity_name}/signup`
  - Query parameters: `email`, `teacher_username`
- `POST /activities/{activity_name}/unregister`
  - Query parameters: `email`, `teacher_username`

### Authentication

- `POST /auth/login`
  - Query parameters: `username`, `password`
- `GET /auth/check-session`
  - Query parameter: `username`

## Data Storage

- The application uses MongoDB (`mongodb://localhost:27017/`).
- On startup, sample activities and teacher accounts are inserted if the collections are empty.

## Development Guide

For detailed setup and development instructions, please refer to our [Development Guide](../docs/how-to-develop.md).

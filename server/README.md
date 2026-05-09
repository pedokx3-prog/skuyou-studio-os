# Skyou Studio Server

FastAPI backend server for Skyou Studio OS.

## Requirements

- Python 3.10+
- pip or poetry

## Setup

### Create Virtual Environment

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Configuration

Copy and configure the environment file:

```bash
cp ../.env.example .env
```

Update `.env` with your settings.

## Running the Server

### Development

```bash
uvicorn main:app --reload --port 8000
```

API runs on http://localhost:8000
API docs available at http://localhost:8000/docs

### Production

```bash
uvicorn main:app --host 0.0.0.0 --port 8000 --workers 4
```

## Project Structure

```
server/
├── main.py           # Application entry point
├── requirements.txt  # Python dependencies
├── config.py         # Configuration management
├── routers/          # API route handlers
├── models/           # Database models
├── schemas/          # Pydantic schemas
├── services/         # Business logic
└── database/         # Database configuration
```

## API Endpoints

### Health Check
- `GET /api/health` - Server health status

### Configuration
- `GET /api/config` - Get public configuration

## Important Notes

- **All API Keys**: Stored securely on the server only
- **CORS**: Configured to allow requests from web and Android clients
- **Authentication**: Use JWT tokens for secure endpoints
- **Database**: Configure via DATABASE_URL environment variable

## Testing

```bash
pytest
```

## Deployment

See production deployment guide for hosting on AWS, GCP, or DigitalOcean.
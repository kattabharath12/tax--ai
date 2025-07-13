# Tax Filing Backend API

Production-ready FastAPI backend for tax filing application with AWS integration.

## Features

- **Authentication & Authorization**: JWT-based auth with role-based access
- **Document Management**: S3 integration with presigned URLs
- **OCR Processing**: AWS Textract for document extraction
- **Payment Processing**: Stripe and PayPal integration
- **Tax Calculations**: Federal and state tax calculations
- **Security**: Field-level encryption, audit logging
- **Compliance**: PII/FTI protection, secure file handling

## Quick Start

### Prerequisites
- Python 3.11+
- PostgreSQL 13+
- Redis 6+
- AWS Account with configured services

### Installation

1. Clone the repository
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Set up environment variables:
   ```bash
   cp .env.example .env
   # Edit .env with your configuration
   ```

4. Run database migrations:
   ```bash
   alembic upgrade head
   ```

5. Start the server:
   ```bash
   uvicorn app.main:app --reload
   ```

### Docker Deployment

```bash
docker build -t tax-filing-backend .
docker run -p 8000:8000 tax-filing-backend
```

## API Documentation

Once running, visit:
- Swagger UI: http://localhost:8000/docs
- ReDoc: http://localhost:8000/redoc

## AWS Services Required

- **RDS**: PostgreSQL database
- **S3**: Document storage
- **Secrets Manager**: Encryption keys and credentials
- **Textract**: Document OCR processing
- **ECS/Fargate**: Container hosting (optional)

## Environment Variables

See `.env.example` for all required environment variables.

## Testing

```bash
pytest
```

## Security Features

- JWT authentication with configurable expiration
- Field-level encryption for PII/FTI
- Secure file uploads with type validation
- Audit logging for all actions
- CORS protection
- Rate limiting (via reverse proxy)

## Compliance

- PII/FTI encryption at rest
- Secure API endpoints
- Audit trail maintenance
- File access controls
- Data retention policies

## Production Deployment

1. Set up AWS infrastructure (see terraform/ directory)
2. Configure environment variables in AWS Secrets Manager
3. Deploy using ECS/Fargate or EC2
4. Set up monitoring and logging
5. Configure backup and disaster recovery

## Support

For issues and questions, please refer to the documentation or contact the development team.

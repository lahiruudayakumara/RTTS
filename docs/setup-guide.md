# RTTS Setup Guide

## 1. Prerequisites

Before setting up the project, ensure you have the following installed:

- **Golang** >= 1.21
- **Node.js** >= 20
- **PostgreSQL** >= 15
- **MongoDB** >= 6
- **Docker & Docker Compose**
- **Terraform** (for cloud deployment)

## 2. Backend Setup

Navigate to each microservice directory and run:

```bash
cd backend/services/taxpayer-service
go mod tidy
go run cmd/main.go
```

Repeat for other services: payment-service, compliance-service, spending-service, notification-service, analytics-service.

## 3. Frontend Setup (Web Portal)

Navigate to the frontend directory and install dependencies:

```bash
cd frontend/web
npm install
npm run dev
```

- The web portal runs on `http://localhost:3000` by default.

## 4. Mobile App Setup (React Native / Expo)

```bash
cd frontend/mobile
npm install
npx expo start
```

- The Expo development server will start and provide a QR code to run on iOS or Android.

## 5. Database Setup

- Run migration scripts (if any) in `backend/scripts/migrate.go`.
- Seed sample data using `backend/scripts/seed.go`.

## 6. Environment Variables

Create a `.env` file based on `.env.example` and set the following:

```
POSTGRES_USER=your_user
POSTGRES_PASSWORD=your_password
POSTGRES_DB=your_db
MONGO_URI=your_mongodb_uri
JWT_SECRET=your_jwt_secret
PAYMENT_GATEWAY_KEY=your_payment_key
```

## 7. Running All Services with Docker

To run all backend, frontend, and databases in Docker containers:

```bash
docker-compose up --build
```

- Services will be accessible on the ports defined in `docker-compose.yml`.

## 8. Testing

- Run unit and integration tests for backend and frontend:

```bash
# Backend tests
cd backend/services/taxpayer-service
go test ./...

# Frontend tests
cd frontend/web
npm test
```

## 9. Notes

- Ensure ports do not conflict with existing services.
- For production deployment, configure `.env.production` and use a reverse proxy or cloud deployment.
- Check `docs/setup-guide.md` for troubleshooting and advanced configurations.


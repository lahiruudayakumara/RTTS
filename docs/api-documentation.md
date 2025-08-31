# RTTS API Documentation

## Base URL

[https://api.rtts.example.com/v1](https://api.rtts.example.com/v1)

## Authentication

* JWT token required for all endpoints
* Role-based access: `citizen`, `officer`, `admin`
* Refresh tokens available via `POST /auth/refresh`

## Rate Limiting

* 100 requests per minute per user
* 429 response for exceeded limits

## Endpoints

### 1. Taxpayer Service

* `POST /taxpayers` – Create a new taxpayer profile
* `GET /taxpayers/{id}` – Retrieve taxpayer information
* `PUT /taxpayers/{id}` – Update taxpayer information
* `DELETE /taxpayers/{id}` – Remove a taxpayer
* `GET /taxpayers/{id}/filings` – List all tax filings for a taxpayer
* `POST /taxpayers/{id}/filings` – Submit a new tax filing

### 2. Payment Service

* `POST /payments` – Initiate a payment
* `GET /payments/{id}` – Retrieve payment status
* `GET /payments/history` – List all payments for the authenticated user
* `POST /payments/refund` – Request a refund

### 3. Compliance Service

* `GET /compliance/alerts` – Fetch all audit/fraud alerts
* `POST /compliance/trigger` – Trigger a new audit
* `GET /compliance/reports` – Retrieve audit reports

### 4. Spending Service

* `GET /spending/overview` – Get government spending summary
* `GET /spending/by-sector` – Get spending broken down by sector
* `GET /spending/{id}` – Details of a specific spending record

### 5. Notification Service

* `POST /notifications/send` – Send notifications to users
* `GET /notifications/history` – Retrieve notification logs
* `POST /notifications/schedule` – Schedule notifications for future delivery

### 6. Analytics Service

* `GET /analytics/tax-revenue` – Revenue trends by period
* `GET /analytics/payment-methods` – Stats on payment types
* `GET /analytics/compliance` – Audit and fraud analytics

## Request & Response Format

* **Request Headers**

```http
Authorization: Bearer <JWT_TOKEN>
Content-Type: application/json
```

* **Response Example**

```json
{
  "status": "success",
  "data": {},
  "message": "Operation completed successfully",
  "timestamp": "2025-08-31T10:00:00Z"
}
```

* **Error Response Example**

```json
{
  "status": "error",
  "error_code": "401_UNAUTHORIZED",
  "message": "Invalid or expired token",
  "timestamp": "2025-08-31T10:05:00Z"
}
```

## Pagination & Filtering

* Use `?page=1&limit=50` for paginated endpoints
* Filtering by query params, e.g., `/taxpayers?status=active&city=Colombo`

## Versioning

* v1: Stable release for core features
* v2: Upcoming release with extended analytics and mobile-first optimizations

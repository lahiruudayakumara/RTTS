# Revenue Tax & Transparency System (RTTS)

![License](https://img.shields.io/badge/License-Apache%202.0-blue)
![Backend](https://img.shields.io/badge/Backend-Golang-green)
![Frontend](https://img.shields.io/badge/Frontend-Next.js-yellow)
![Mobile](https://img.shields.io/badge/Mobile-React%20Native-blue)

---

## Project Overview

The **Revenue Tax & Transparency System (RTTS)** is an **open-source, modular platform** designed to:

- Simplify **tax filing** for citizens and businesses.
- Provide **real-time dashboards** for government officers.
- Enable **public transparency** of government spending.
- Support **multi-country adaptability** and **community contributions**.

RTTS is suitable for governments, NGOs, and civic-tech communities looking to **modernize tax collection and transparency**.

---

## Key Features

### Citizen Dashboard

- Multi-tax filing: Income, VAT, Property, Customs
- Digital receipts & payment history
- Mobile app (iOS/Android) with offline support
- Multi-language interface (Sinhala, Tamil, English)

### Government / Officer Portal

- Admin dashboards for tax monitoring
- AI-assisted fraud detection & audit triggers
- Payment reconciliation & reporting
- Officer mobile app for field operations

### Public Transparency Portal

- Sector-wise spending visualizations
- Open APIs for researchers & media
- Downloadable reports (CSV, PDF)

### Backend & Infrastructure

- Modular **Golang microservices**: taxpayer, payment, compliance, spending, notification, analytics
- Databases: PostgreSQL + MongoDB
- CI/CD, Docker, Kubernetes, Terraform for cloud deployment
- Integrations: GovPay, LankaQR, M-Pesa, National ID, IRD e-services

---

## Project Structure

```
RTTS/
├── backend/           # Golang microservices
├── frontend/          # Next.js web + React Native mobile apps
├── infra/             # DevOps: Docker, Kubernetes, Terraform, CI/CD
├── docs/              # Architecture, API docs, setup, roadmap, contributing
├── tests/             # Unit & integration tests
├── .gitignore
├── LICENSE
└── README.md
```

---

## Getting Started

### Prerequisites

- Golang >= 1.21
- Node.js >= 20
- PostgreSQL >= 15
- MongoDB >= 6
- Docker & Docker Compose
- Terraform (for cloud deployment)

### Backend Setup

```bash
cd backend/services/taxpayer-service
go mod tidy
go run cmd/main.go
```

### Web Frontend Setup

```bash
cd frontend/web
npm install
npm run dev
```

### Mobile App Setup

```bash
cd frontend/mobile
npm install
npx expo start
```

### Environment Variables

- Copy `.env.example` to `.env`
- Configure PostgreSQL, MongoDB, payment gateways, JWT secrets, etc.

### Running with Docker

```bash
docker-compose up --build
```

---

## Contributing

We welcome contributions! See [CONTRIBUTING.md](./docs/contributing.md) for detailed guidelines.

- Fork the repo
- Create a feature branch: `git checkout -b feature/your-feature`
- Submit pull requests with clear descriptions

---

## Roadmap

- Core microservices & mobile apps
- Frontend dashboards: citizen, admin, transparency
- Payment & National ID integrations
- Analytics & AI fraud detection
- Open-source release & multi-country support

See [ROADMAP.md](./docs/roadmap.md) for detailed milestones.

---

## License

This project is licensed under **Apache License 2.0**. See [LICENSE](./LICENSE) for details.

---

## Contact & Community

- Join the open-source community to contribute and discuss development
- Submit issues or feature requests on GitHub
- Collaborate on modules for new countries, payment integrations, and analytics

---


# ShopStack — Enterprise Multi-Vendor E-Commerce Platform

ShopStack is a multi-vendor e-commerce application built with **Spring Boot, Java, React, and PostgreSQL**. It is designed to support customers, vendors, administrators, and warehouse staff through separate dashboards and workflows.

## Live Demo

- **Frontend:** https://shop-stack-enterprise-multi-vendor-xi.vercel.app/
- **Backend:** https://13.48.47.35.sslip.io

## Tech Stack

| Component | Technologies |
|---|---|
| Backend | Java 21, Spring Boot |
| Frontend | React.js, Vite, JavaScript |
| Database | PostgreSQL |
| Data Access | Spring Data JPA, Hibernate |
| Security | Spring Security, JWT, BCrypt |
| API Communication | REST APIs, Axios |
| Payments | Razorpay integration |
| Testing | Postman |
| Version Control | Git, GitHub |

## Key Features

### Customer
- Account registration, login, and password recovery
- Product browsing and search
- Shopping cart and wishlist management
- Product reviews and ratings
- Multiple shipping addresses
- Order history and checkout
- Razorpay payments and Cash on Delivery
- Return and refund requests

### Vendor
- Product listing, editing, and deletion
- Product images, pricing, and discounts
- Inventory and stock management
- Sales analytics and order tracking
- Vendor settlement and payout history

### Administrator
- Product approval and rejection
- Vendor management
- Marketplace analytics and reports
- Commission and settlement management
- Payment monitoring
- Return and refund management

### Warehouse Staff
- Order dispatch and delivery status updates
- Inventory monitoring
- Return inspection and quality checks

## Architecture

The application uses a frontend-backend architecture:

- **React frontend:** Provides the user interface and role-specific dashboards.
- **Spring Boot backend:** Exposes REST APIs for authentication, products, orders, payments, and administration.
- **PostgreSQL database:** Stores application data using JPA entities and repositories.
- **Razorpay:** Supports online payment processing and payment verification.

## Project Structure

```text
ShopStack/
├── backend/
│   ├── src/
│   │   └── main/
│   │       ├── java/
│   │       └── resources/
│   ├── uploads/
│   ├── mvnw
│   ├── mvnw.cmd
│   └── pom.xml
├── frontend/
│   ├── src/
│   │   └── components/
│   ├── package.json
│   └── index.html
├── deploy/
├── docker-compose.yml
├── package.json
├── .env.example
└── README.md
```

## Running Locally

### Prerequisites

- Java 21
- Node.js and npm
- PostgreSQL
- Git

### 1. Configure the database

Create a PostgreSQL database named `shopstack_db`.

Configure the database connection and other required settings in the backend configuration. Use your own local credentials and keep actual secrets out of GitHub.

### 2. Start the backend

Open a terminal in the project root and run:

```powershell
cd backend
.\mvnw.cmd spring-boot:run
```

The backend is configured to run on port `8080`, subject to the application configuration.

### 3. Start the frontend

Open a second terminal in the project root:

```powershell
cd frontend
npm install
npm run dev
```

Open the local URL displayed by Vite in your terminal.

> Follow the project's environment configuration and deployment settings if any additional values are required.

## API Overview

The backend exposes REST APIs for the following operations:

| Area | Example endpoints |
|---|---|
| Authentication | `/api/auth/register`, `/api/auth/login` |
| Products | `/api/products`, `/api/products/search` |
| Customer | `/api/customer/{id}` |
| Payments | `/api/payment/create-order`, `/api/payment/verify-and-order` |
| Returns | `/api/payment/refund/request` |
| Administration | `/api/admin/dashboard-summary` |
| Vendor settlements | `/api/vendor/{vendorId}/settlements` |

See the backend controllers for the implemented routes, request formats, and access requirements.

## Testing

API testing can be performed using Postman. The project documentation includes workflows for authentication, product management, checkout, payment verification, inventory updates, returns, and settlements.

## Security Notes

- Do not commit real passwords, API keys, database credentials, or payment secrets.
- Configure environment-specific values before deployment.
- Test authentication, authorization, and payment verification before using the application with real customer data.

## License

See the [LICENSE](./LICENSE) file for the project's license terms.

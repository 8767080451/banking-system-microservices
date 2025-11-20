# Banking System – Microservices Architecture
A scalable and production-ready Banking System built using Spring Boot Microservices, featuring Account, Transaction, and Notification services. The system is fully containerized with Docker, uses Eureka Service Discovery, and exposes APIs through an API Gateway. Built by Chaitanya Vijay Chaudhari.

------------------------------------------------------------

## Architecture Overview

This project follows a modern microservices architecture with:

- Account Service – Manages user accounts, balances, account creation, and retrieval
- Transaction Service – Handles money transfers, deposits, withdrawals, and transaction history
- Notification Service – Sends alerts for transactions and account activities
- API Gateway – Unified entry point for all services with routing, load balancing, and security
- Service Registry (Eureka) – Enables dynamic service discovery
- MongoDB – NoSQL database for high-performance data storage
- Docker – Containerization for seamless deployment

------------------------------------------------------------

## Tech Stack

Core Framework: Spring Boot, Spring Cloud  
Microservices: Eureka, API Gateway, OpenFeign  
Database: MongoDB  
Deployment: Docker, Docker Compose  
Build Tool: Maven  
APIs: RESTful Services

------------------------------------------------------------

## System Design

API Gateway  
  |  
  |-- Account Service (MongoDB)  
  |-- Transaction Service  
  |-- Notification Service  
  |  
Eureka Discovery Server

------------------------------------------------------------

## Features

Account Service:
- Create new accounts
- Fetch user/account details
- View balance
- Update account information

Transaction Service:
- Deposit & withdrawal
- Transfer funds between accounts
- Maintain transaction history
- Balance validation with error handling

Notification Service:
- Send email/SMS alerts (mock)
- Event-driven structure

API Gateway:
- Centralized access
- Routing to microservices
- Load balancing & request filtering

Service Discovery (Eureka):
- Auto-registration of services
- Dynamic scaling of microservices

------------------------------------------------------------

## Installation & Setup

1. Clone the Repository:
git clone https://github.com/yourusername/banking-system-microservices.git

2. Start MongoDB (Docker):
docker run -d -p 27017:27017 --name mongo-db mongo

3. Run Eureka Server:
cd eureka-server  
mvn spring-boot:run

4. Start Microservices:
cd account-service  
mvn spring-boot:run  

cd transaction-service  
mvn spring-boot:run  

cd notification-service  
mvn spring-boot:run

5. Start API Gateway:
cd api-gateway  
mvn spring-boot:run

------------------------------------------------------------

## Docker Setup (Recommended)

Run the entire project with:
docker-compose up --build

------------------------------------------------------------

## API Endpoints

Account Service:
POST /accounts  
GET /accounts/{id}  
GET /accounts/{id}/balance  

Transaction Service:
POST /transactions/deposit  
POST /transactions/withdraw  
POST /transactions/transfer  
GET /transactions/{accountId}

------------------------------------------------------------

## Future Enhancements

- JWT Authentication & RBAC  
- Kafka for event-driven notifications  
- CI/CD Pipeline  
- Distributed tracing with Zipkin  
- Monitoring with Prometheus & Grafana

------------------------------------------------------------

## Contributing

Contributions and suggestions are welcome.

------------------------------------------------------------

## License

MIT License

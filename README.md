# Group Project: Microservices
## Team MetaCortex

This repository is part of a group project where we are developing a distributed application composed of several microservices. Each team member is collectively responsible for an API Gateway, aswell as individually responsible for a specific part of the system:

- [MetaCortex.Panther](https://github.com/anders0b/MetaCortex.Panther) - Maintained by the whole group, contains the Ocelot API Gateway.
- [MetaCortex.Customers](https://github.com/jesperwhendin/MetaCortex.Customers) - Maintained by [jesperwhendin](https://github.com/jesperwhendin) / Jesper Whendin, responsible for customer management.
- [MetaCortex.Orders](https://github.com/anders0b/MetaCortex.Orders) - Maintained by [Anders0b](https://github.com/anders0b) / Anders Öberg, responsible for order management.
- [MetaCortex.Payments](https://github.com/Heimbrand/MetaCortex.Payments) - Maintained by [Heimbrand](https://github.com/Heimbrand) / Olle Heimbrand, responsible for handling payments.
- [MetaCortex.Products](https://github.com/GabrielRai/MetaCortex.Products) - Maintained by [GabrielRai](https://github.com/GabrielRai) / Gabriel Raimondo, responsible for product information.

Together, these microservices, as well as an API-Gateway, form a complete system where each service has a clear role and responsibility.

# How to run

- Clone this repository
- Then through the terminal run: `docker-compose pull` followed by `docker-compose up -d`
- To launch all the services start them in this order:
  
`RabbitMq -> Databases(MongoDb) -> Gateway -> API-services -> Seeder(optional)`

  - The DeluxeSeeder is a console application that sends in dummy data to all the services in order to test all the functionality (db and message queues). Look through the logs of the seeder to see what is happening. To start seeding, just launch the application from docker, and shut it down to make it stop.

---

## Port Usage Documentation

### Services and Ports

#### Ocelot API Gateway
- **Service Name**: `ocelot-frontend`
- **Ports**: `5000:5000`
- **Description**: Acts as the API gateway, routing requests to backend services.

#### DeluxeSeeder
- **Service Name**: `metacortex-deluxeseeder`
- **Ports**: `5010:80`
- **Description**: Seeder service for initializing the application with sample data.

#### Payment Service
- **Service Name**: `metacortex-payments`
- **Ports**: `5001:80`
- **Description**: Manages payment-related operations.

#### Payment Database
- **Service Name**: `metacortex-payments-db`
- **Ports**: `1433:1433`
- **Description**: MongoDB instance for payment data.

#### Orders Service
- **Service Name**: `metacortex-orders`
- **Ports**: `5002:80`
- **Description**: Manages order-related operations.

#### Orders Database
- **Service Name**: `metacortex-orders-db`
- **Ports**: `1434:1433`
- **Description**: MongoDB instance for order data.

#### Customers Service
- **Service Name**: `metacortex-customers`
- **Ports**: `5003:80`
- **Description**: Manages customer-related operations.

#### Customers Database
- **Service Name**: `metacortex-customers-db`
- **Ports**: `1435:1433`
- **Description**: MongoDB instance for customer data.

#### Products Service
- **Service Name**: `metacortex-products`
- **Ports**: `5004:80`
- **Description**: Manages product-related operations.

#### Products Database
- **Service Name**: `metacortex-products-db`
- **Ports**: `1436:1433`
- **Description**: MongoDB instance for product data.

#### RabbitMQ Service
- **Service Name**: `rabbitmq-service`
- **Ports**:
  - `5672:5672`: RabbitMQ connection port.
  - `15672:15672`: RabbitMQ management console.
- **Description**: Message broker for inter-service communication.

---
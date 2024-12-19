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

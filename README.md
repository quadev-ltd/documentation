# QuaDev Organization's Repositories: A Research Project in Software Architecture

## Overview:
QuaDev's repositories are part of an ambitious research project focused on software architecture. This project uniquely blends Golang and Python microservices, facilitating inter-service communication through gRPC (a high-performance, open-source universal RPC framework).

## Architecture:
The architecture of our microservices is designed around the API Gateway pattern. This pattern acts as a single entry point for all client requests, offering optimized management and routing to various microservices. It enhances security and scalability in distributed systems.

### Authentication:
For secure authentication, we employ JWT (JSON Web Tokens) encrypted with RSA encryption mechanisms. This ensures a robust authentication process, critical for modern application security.  

### Security
The API Gateway uses the JWT tokens to authenticate the requests without any need to interact with any other services.
Internally, between microservices, TLS secured connections are used to provide a secure channel. TLS provides encryption for data in transit, ensuring that information exchanged between services remains confidential and tamper-proof. 

### Client Application:
On the client side, we use a React Native application. React Native allows for building native apps using React, a popular JavaScript library. Our client app is integrated with Firebase, a platform developed by Google for creating mobile and web applications, which helps in managing data real-time, user authentication, and hosting.

### Testing and CI/CD:
We are committed to best practices in software development. Our approach includes comprehensive testing at various levels - unit, integration, functional, and end-to-end. These tests are an integral part of our project pipelines, implemented using GitHub Actions for Continuous Integration and Continuous Deployment (CI/CD). This ensures code quality and efficient delivery.

## Golang micro services stack

### Unit Testing and Integration Testing
- **github.com/stretchr/testify**: A popular Go testing framework that provides a rich set of assertions and is commonly used to write unit tests. It simplifies the process of writing tests by allowing developers to write more expressive and readable tests. For integration testing, its mock package can be used to create mock objects and services.
github.com/tryvium-travels/memongo v0.11.0: A library for spinning up an in-memory MongoDB instance. It's useful for integration testing where tests need to interact with a MongoDB database without the overhead of connecting to a real database instance.
- **github.com/golang/mock**: A framework for writing mock objects in Go tests. It's used for creating mocks of interfaces, which is particularly useful for testing components in isolation, including mocking gRPC clients or servers in integration tests.

### gRPC Services Implementation
- **google.golang.org/grpc**: The official gRPC library for Go. It provides the necessary tools to implement gRPC servers and clients. It's used to define service endpoints, handle serialization and deserialization of messages, and manage client-server communication over HTTP/2.
- **protoc**: For a project utilizing gRPC for microservices communication, protoc is essential for generating the boilerplate code needed to implement the defined services and messages in Go.
- **buf**: Helps streamline the process of working with protocol buffers and gRPC services. In projects that heavily use protocol buffers, especially with multiple .proto files and dependencies, buf can simplify the code generation process, enforce best practices, and ensure compatibility across protobuf versions.

### Logging
- **github.com/rs/zerolog**: A fast and simple logger that provides JSON-formatted output. It's designed with performance and simplicity in mind, supporting structured logging and leveled logging. This library is used to log messages, errors, and other relevant information throughout the application, aiding in debugging and monitoring.

### JWT Tokens
- **github.com/golang-jwt/jwt**: A Go library to work with JSON Web Tokens (JWT). It's used for creating, parsing, and validating JWT tokens, which are crucial for implementing authentication and authorization mechanisms, including managing sessions, user authentication states, and securely transmitting user identity information.

### Mongo and ORM Functionalities
- **go.mongodb.org/mongo-driver**: The official MongoDB driver for Go. It provides a powerful and easy-to-use client to interact with MongoDB databases. It supports CRUD operations, filtering, aggregation, and more, allowing the application to interact with the database without the need for an additional ORM layer. It's used to store, update, retrieve, and delete user data and tokens in the MongoDB database.

## Containerization and Cloud Deployment Goals:
In alignment with modern development practices, our architecture is fully containerized using Docker Compose. This containerization strategy not only ensures consistency across various development and production environments but also simplifies the complexities associated with deploying microservices. By leveraging Docker Compose, we orchestrate our containers in a manner that allows for seamless integration and scalability of services. Looking ahead, we are focusing on adopting infrastructure as code (IaC) practices, specifically using Terraform. This shift is aimed at automating and managing our cloud infrastructure more efficiently. The ultimate objective is to deploy and scale our architecture on Amazon Web Services (AWS), benefiting from the robustness, scalability, and wide array of services that AWS offers. This move will enhance our ability to quickly adapt to changing requirements and scale our services globally, reinforcing our commitment to building resilient, cloud-native applications.

## Project Aim:
The primary goal of this project is to explore and enhance development practices while researching new technologies with a focus on AI. By doing so, we aim to offer a scalable architecture that can be easily adapted for diverse solutions. This project serves as a testbed for cutting-edge technologies and architectural approaches in software development.

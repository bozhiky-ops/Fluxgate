# Fluxgate

## Description

Fluxgate is a high-performance, distributed message queuing system designed for asynchronous communication between microservices and other applications. It provides reliable message delivery, flexible routing, and horizontal scalability. Fluxgate aims to simplify complex distributed architectures by offering a centralized and robust platform for managing message flow. It supports various message formats and delivery guarantees, allowing developers to build more resilient and responsive systems.

## Features

*   **Reliable Message Delivery:** Guarantees at-least-once or exactly-once message delivery through persistent storage and acknowledgements.
*   **Flexible Routing:** Supports various routing strategies, including topic-based, queue-based, and content-based routing.
*   **Horizontal Scalability:** Designed to scale horizontally by adding more broker nodes to the cluster.
*   **Message Persistence:** Stores messages persistently to prevent data loss in case of broker failures.
*   **Message Prioritization:** Allows prioritizing messages based on urgency.
*   **Dead-Letter Queue (DLQ):** Automatically routes messages that fail to be processed after multiple attempts to a DLQ for further analysis.
*   **Message Transformation:** Supports message transformation using configurable plugins.
*   **Real-time Monitoring:** Provides real-time monitoring and metrics through a web-based dashboard and API.
*   **Security:** Implements authentication and authorization mechanisms to secure message flow.
*   **Client Libraries:** Offers client libraries for various programming languages, including Python, Java, and Go.
*   **Clustering:** Supports clustering for high availability and fault tolerance.
*   **REST API:** Provides a REST API for managing queues, topics, and messages.
*   **Command-Line Interface (CLI):** Offers a CLI for managing and monitoring the Fluxgate system.

## Technologies Used

*   **Programming Language:** Go
*   **Database:** PostgreSQL (for message persistence and metadata storage)
*   **Message Broker:** RabbitMQ (for internal message routing and queuing)
*   **Web Framework:** Gin (for REST API)
*   **Frontend:** React (for the web-based dashboard)
*   **Build Tool:** Make
*   **Containerization:** Docker
*   **Orchestration:** Kubernetes (recommended for production deployments)

## Installation

### Prerequisites

*   Go (version 1.20 or higher)
*   Docker
*   Docker Compose (optional, for local development)
*   PostgreSQL (version 12 or higher)

### Steps

1.  **Clone the repository:**

    ```bash
    git clone https://github.com/[your_username]/Fluxgate.git
    cd Fluxgate
    ```

2.  **Configure PostgreSQL:**

    *   Create a PostgreSQL database named `fluxgate`.
    *   Create a user with appropriate privileges to access the database.
    *   Update the database connection string in the `config.yaml` file.

3.  **Build the application:**

    ```bash
    make build
    ```

    This will compile the Go source code and create an executable file named `fluxgate` in the `bin` directory.

4.  **Configure the application:**

    *   Copy the `config.example.yaml` file to `config.yaml`.
    *   Modify the `config.yaml` file to configure the application settings, such as the PostgreSQL connection string, RabbitMQ connection string, and API port.

5.  **Run the application:**

    ```bash
    ./bin/fluxgate server
    ```

    This will start the Fluxgate server.

### Using Docker Compose (for local development)

1.  **Navigate to the `docker-compose.yml` directory:**

    ```bash
    cd docker
    ```

2.  **Start the Docker Compose environment:**

    ```bash
    docker-compose up -d
    ```

    This will start the PostgreSQL database, RabbitMQ broker, and Fluxgate server in Docker containers.

### Kubernetes Deployment (recommended for production)

1.  **Build the Docker image:**

    ```bash
    docker build -t [your_dockerhub_username]/fluxgate .
    docker push [your_dockerhub_username]/fluxgate
    ```

2.  **Create Kubernetes deployment and service YAML files.** See the `kubernetes` directory for example files.
3.  **Apply the YAML files to your Kubernetes cluster:**

    ```bash
    kubectl apply -f kubernetes/deployment.yaml
    kubectl apply -f kubernetes/service.yaml
    ```

    Make sure to adjust the configuration parameters in the YAML files to match your environment.

## Usage

*   **Access the REST API:** The REST API is available at the configured API port (default: 8080). Refer to the API documentation for details on available endpoints. (Documentation to be created separately.)
*   **Access the web-based dashboard:** The web-based dashboard is available at the configured dashboard URL (usually on port 3000 if using the default React setup). (Instructions for running the frontend separately may be needed).
*   **Use the client libraries:** Integrate the client libraries into your applications to send and receive messages. Refer to the client library documentation for usage instructions. (Documentation to be created separately.)
*   **Use the CLI:** The CLI provides commands for managing and monitoring the Fluxgate system. Run `fluxgate help` to see available commands.

## Contributing

We welcome contributions to Fluxgate! Please follow these guidelines:

1.  Fork the repository.
2.  Create a new branch for your feature or bug fix.
3.  Make your changes and commit them with clear and descriptive commit messages.
4.  Submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE).
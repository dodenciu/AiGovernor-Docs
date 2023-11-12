```mermaid
graph LR;

  subgraph Client
    User -->|HTTP Request| APIGateway
  end

  subgraph APIGateway
    APIGateway -->|HTTP Request| APIServer
    APIGateway -->|Cache Request| Cache
  end

  subgraph APIServer
    APIServer -->|Database Query| Database
    APIServer -->|HTTP Response| APIGateway
  end

  subgraph Cache
    Cache -->|Cached Data| APIGateway
  end

  subgraph Database
    Database -->|Database Query| APIServer
  end

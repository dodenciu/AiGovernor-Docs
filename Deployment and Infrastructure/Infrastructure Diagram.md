```mermaid
flowchart TD

subgraph AWS Cloud
  subgraph API Servers
    A[API Server 1]
    B[API Server 2]
    C[API Server 3]
  end

  subgraph SQL Database
    D[SQL Database]
  end
end

subgraph Load Balanced Gateway
  E[Load Balancer]
end

subgraph Clients
  F[Client 1]
  G[Client 2]
  H[Client 3]
end

subgraph API Proxy Servers
  I[API Proxy Server 1]
  J[API Proxy Server 2]
end

subgraph Lambda Functions
  K[Lambda Function 1]
  L[Lambda Function 2]
end

subgraph Web Servers
  M[Web Server 1]
  N[Web Server 2]
end

subgraph AWS Cloudfront
  O[AWS Cloudfront CDN]
end

A --> D
B --> D
C --> D
F --> E
G --> E
H --> E
E --> A
E --> B
E --> C
A --> I
B --> J
K --> D
L --> D
M --> O
N --> O
O --> M
O --> N

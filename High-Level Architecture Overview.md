```mermaid
flowchart TD

subgraph API
A[API Server 1]
B[API Server 2]
C[API Server 3]
end

subgraph Storage
D[SQL Main]
Z[SQL Replica]
W[Object Storage]
S[KV Storage]
end

subgraph Gateway
  E[Load Balancer]
end

subgraph Users Europe Region
  F[User 1]
  G[User 2]
  H[User 3]
end

subgraph AI Proxies
  I[AI Proxy Service 1]
  J[AI Proxy Service 2]
end

subgraph Jobs
  K[Job 1]
  L[Job 2]
end

subgraph Web Servers
  M[Web Server 1]
  N[Web Server 2]
end

subgraph CDN
  O[AWS Cloudfront]
end

subgraph External Service
  X[Sync regions]
end

A --> D
B --> D
C --> D
F --> E
G --> E
H --> E
E --> M
E --> N
M --> A
M --> B
M --> C
A --> I
B --> J
K --> D
L --> D
O --> M
O --> N
D --> Z
X --> D
D --> X
A --> W
C --> W
A --> S

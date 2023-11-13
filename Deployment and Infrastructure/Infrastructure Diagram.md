```mermaid
flowchart TD

subgraph Global Regions
  subgraph Region 1
    subgraph Web Servers
      M[Web Server 1]
      N[Web Server 2]
    end

    subgraph API Servers
      A[API Server 1]
      B[API Server 2]
      C[API Server 3]
    end

    subgraph SQL Database
      D[SQL Database]
    end

    O[AWS Cloudfront CDN]
    M --> O
    N --> O
    F --> M
    G --> M
    H --> M
    I --> A
    J --> B
    K --> D
    L --> D
  end

  subgraph Region 2
    subgraph Web Servers
      M2[Web Server 1]
      N2[Web Server 2]
    end

    subgraph API Servers
      A2[API Server 1]
      B2[API Server 2]
      C2[API Server 3]
    end

    subgraph SQL Database
      D2[SQL Database]
    end

    O2[AWS Cloudfront CDN]
    M2 --> O2
    N2 --> O2
    F --> M2
    G --> M2
    H --> M2
    I --> A2
    J --> B2
    K --> D2
    L --> D2
  end
end

F[Client 1]
G[Client 2]
H[Client 3]
F --> M
G --> M
H --> M

graph TD
    subgraph "Prerequisites"
        A[Data Scientist / Analyst]
        B((IAM Roles Granted <br> 'Vertex AI User' <br> 'BigQuery Connection User'))
    end

    subgraph "Configuration in BigQuery"
        C{CREATE CONNECTION}
        D{CREATE MODEL}
    end
    
    E((Vertex AI Gemini Endpoint))

    A --> B
    A --"Runs SQL Command"--> C
    C --"Establishes secure link to"--> E
    A --"Runs SQL Command, using the connection"--> D
    D --"References"--> E

    style A fill:#e3f2fd,stroke:#333
    style E fill:#e8f5e9,stroke:#333

graph TD
    User[User] --> WebApp[Web Application]
    User --> MobileApp[Mobile Application]
    
    subgraph "Frontend"
        WebApp --> Auth[Authentication]
        MobileApp --> Auth
        Auth --> |SSO| VASSO[VA SSO]
        Auth --> |External| IDme[ID.me]
        Auth --> |RBAC| AzureAD[Azure AD]
    end
    
    subgraph "Core Application"
        Auth --> D365[Microsoft Dynamics 365]
        D365 --> ScholarshipMgmt[Scholarship Management]
        D365 --> WaiverMgmt[Waiver Management]
        D365 --> PowerApps[Microsoft Power Apps]
    end
    
    subgraph "Integration"
        D365 <--> APIM[Azure API Management]
        APIM <--> LogicApps[Azure Logic Apps]
        APIM <--> ServiceBus[Azure Service Bus]
    end
    
    subgraph "Data Storage"
        D365 --> SQL[Azure SQL Database]
        D365 --> CosmosDB[Azure Cosmos DB]
        D365 --> DataLake[Azure Data Lake]
        D365 --> BlobStorage[Azure Blob Storage]
    end
    
    subgraph "Analytics"
        SQL --> PowerBI[Power BI]
        CosmosDB --> PowerBI
        DataLake --> Synapse[Azure Synapse Analytics]
    end
    
    subgraph "Security & Compliance"
        SecCenter[Azure Security Center] --> D365
        KeyVault[Azure Key Vault] --> D365
        DDoS[Azure DDoS Protection] --> WebApp
        DDoS --> MobileApp
        FedRAMP[FedRAMP Controls] --> D365
    end
    
    subgraph "DevOps & Management"
        AzureDevOps[Azure DevOps] --> D365
        AzureMonitor[Azure Monitor] --> D365
        AppInsights[Application Insights] --> WebApp
        AppInsights --> MobileApp
    end
    
    subgraph "Backup & DR"
        AzureBackup[Azure Backup] --> SQL
        AzureBackup --> CosmosDB
        SiteRecovery[Azure Site Recovery] --> D365
    end

graph TB
  subgraph UI_Layer [User Interface Layer]
    UI1[Web Application (React.js)]
    UI2[Mobile Application (React Native)]
    UI3[Accessibility Layer (Section 508 compliance)]
  end
  
  subgraph Auth_Layer [Authentication and Authorization Layer]
    Auth1[VA Single Sign-On (SSO)]
    Auth2[ID.me integration]
    Auth3[Azure Active Directory (Azure AD)]
    Auth4[Multi-Factor Authentication (MFA)]
  end
  
  subgraph App_Layer [Application Layer]
    App1[Microsoft Dynamics 365]
    App2[Custom AMS modules]
    App3[Microsoft Power Apps]
    App4[Azure App Service]
  end
  
  subgraph Integration_Layer [Integration Layer]
    Int1[Azure API Management]
    Int2[Azure Logic Apps]
    Int3[Azure Service Bus]
    Int4[Custom API Endpoints]
  end
  
  subgraph Data_Layer [Data Layer]
    Data1[Azure SQL Database]
    Data2[Azure Cosmos DB]
    Data3[Azure Data Lake Storage]
    Data4[Azure Blob Storage]
  end
  
  subgraph Analytics_Layer [Analytics and Reporting Layer]
    Analytics1[Power BI]
    Analytics2[Azure Analysis Services]
    Analytics3[Azure Synapse Analytics]
  end
  
  subgraph Security_Layer [Security Layer]
    Sec1[Azure Security Center]
    Sec2[Azure Key Vault]
    Sec3[Azure DDoS Protection]
    Sec4[Azure Firewall]
  end
  
  subgraph Compliance_Layer [Compliance Layer]
    Comp1[FedRAMP controls]
    Comp2[Azure Policy]
    Comp3[Azure Compliance Manager]
  end
  
  subgraph DevOps_Layer [DevOps and Management Layer]
    DevOps1[Azure DevOps]
    DevOps2[Azure Monitor]
    DevOps3[Application Insights]
    DevOps4[Azure Automation]
  end
  
  subgraph Backup_Layer [Backup and Disaster Recovery Layer]
    Backup1[Azure Backup]
    Backup2[Azure Site Recovery]
    Backup3[Geo-redundant storage]
  end
  
  %% Interactions
  UI_Layer --> Auth_Layer
  UI_Layer --> App_Layer
  App_Layer --> Data_Layer
  App_Layer --> Integration_Layer
  App_Layer --> Analytics_Layer
  Data_Layer --> Analytics_Layer
  Security_Layer --> Data_Layer
  Security_Layer --> Integration_Layer
  Security_Layer --> Auth_Layer
  Compliance_Layer --> Security_Layer
  Compliance_Layer --> DevOps_Layer
  DevOps_Layer --> App_Layer
  DevOps_Layer --> Backup_Layer
  Backup_Layer --> Data_Layer
  Backup_Layer --> App_Layer

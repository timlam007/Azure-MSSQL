# Azure-MSSQL

| Control Family                            | Control Name(s)                              | Requirement ID | Requirements                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| ----------------------------------------- | -------------------------------------------- | -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Data security and information protection  | Protection Of Information At Rest            | R_2.9          | Data stored at rest within the Azure SQL database must be encrypted using Manulife-approved encryption mechanisms. If database contains PII data, then it must be encrypted using own keys for encryption and regular data can be encrypted using Microsoft generated keys.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Infrastructure protection                 | Transmission Confidentiality And Integrity   | R_2.12         | Access and connectivity to the Azure SQL Database must be restricted to only clients using Manulife approved protocol such as TLS 1.2 or above to ensure a secure connection.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Infrastructure protection                 | Network traffic filtering                    | R_2.13         | Manulife approved firewalls must be used to protect and limit network access to Azure SQL server and SQL Database                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Threat detection and monitoring           | Audit Events                                 | R_2.15         | Azure SQL auditing must be enabled to track database events. Logs must be forwarded to the Manulife approved log repository                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Threat detection and monitoring           | Audit Review, Analysis, And Reporting        | R_2.20         | A Manulife approved Threat Protection solution such as MICROSOFT DEFENDER FOR SQL for Azure SQL Database must be used to continuously monitor traffic for anomalous SQL database access attempts, prevent SQL injection attempts etc. A periodic recurring scan should be established                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Network traffic filtering                 | Network Security                             | R_2.25         | SQL Server default port ( TCP 1433 and UDP port 1434 ) must not be open from Internet                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Identity, access and privilege management |                                              | R_2.4          | Contained users must be created which are mapped to Azure AD identities.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Identity, access and privilege management | Access Control                               | R_2.1          | Access to Azure SQL server and underlying components must be granted following the principle of least privileged and segregation of duties. This can be achieved by using Azure roles. Azure roles are used for managing Azure Resources, and do not apply to database permissions. SQL DB Contributor- Privileged role SQL Server Contributor - Privileged role SQL Security Manager - Privileged role Access to privileged roles must be managed as per the established privileged access management process. Note: If DBA team requires to create Manulife custom role such as "MFC_DB_Custom_Contributor" role, then it must follow least privileged principal process.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Identity, access and privilege management | Identification and Authentication            | R_2.2          | Access to the SQL server and underlying components must be managed through the enterprise identity store such as Azure AD.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Identity, access and privilege management | Identification and Authentication            | R_2.3          | At the SQL database level, contained users must be created which are mapped to Azure AD identities.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Identity, access and privilege management | Usage of Role Based Access Control           | R_2.4          | At the SQL database level, fine grained access control must be implemented following the principle of least privileged and segregation of duties. This can be achieved by using database roles and permissions. Fixed database roles: db_owner - Privileged role - can perform all configuration and maintenance activities on the database, and can also drop the database in SQL Server. db_securityadmin - Privileged role - can modify role membership for custom roles only and manage permissions. Members of this role can potentially elevate their privileges. db_accessadmin - Privileged role - can add or remove access to the database db_backupoperator - can back up the database db_ddladmin - Privileged role - can run any Data Definition Language (DDL) command in a database. db_datawriter - Privileged role - can add, delete, or change data in all user tables db_datareader - can read all data from all user tables and views. db_denydatawriter - cannot add, modify, or delete any data in the user tables within a database db_denydatareader - cannot read any data from the user tables and views within a database Custom roles should be created to enforce the least privilege principle where a fixed role is not sufficient. |
| Identity, access and privilege management | Identification and Authentication            | R_2.5          | Azure Active Directory admin for Azure SQL is a privileged account at the server level which gives access to all the databases on that server. Assignment and access to privileged account must be managed as per the established privileged access management process.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Identity, access and privilege management | Identification and Authentication            | R_2.6          | Local authentication for Azure SQL database must be disabled                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Identity, access and privilege management | Identification and Authentication            | R_2.7          | Access to Azure data sources (such as storage, key vault) from Azure SQL server must be managed using system managed identity.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Data security and information protection  | Data Classification                          | R_2.8          | Implement controls such as automated data discovery solution for discovering and classifying organization data stored in SQL databases. Note: Currently Manulife doesn't have a tool or porcess to meet this requirements. Untill tool or porcess is established, this requirement is exepted.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Infrastructure protection                 | Network traffic filtering                    | R_2.10         | Ensure Azure SQL database is accessible through a private endpoint such that access to the Azure SQL database is restricted to Manulife’s private networks.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Data security and information protection  | Data Confidentiality                         | R_2.11         | Manulife must employ data anonymization techniques such as data masking to protect the confidentiality and integrity of the data.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Infrastructure protection                 | Network traffic filtering                    | R_2.14         | Public network access to Azure SQL server and database must not be allowed.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Threat detection and monitoring           | Audit Events                                 | R_2.16         | Auditing of Microsoft support operations must be enabled to track operations performed by Microsoft support on the SQL server. Logs must be forwarded to the Manulife approved log repository Note: Auditing of Microsoft support operations tracks Microsoft support engineers' (DevOps) operations on Manulife's server and writes them to an audit log in Manulife's Azure Storage account                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Threat detection and monitoring           | Audit Events                                 | R_2.17         | Ensure to collect logs from the Azure SQL Database and store them in the Manulife approved log repository                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Threat detection and monitoring           | Audit Record Retention                       | R_2.18         | Store the audit and security logs for a period as defined by Manulife's policy.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Threat detection and monitoring           | Audit Events                                 | R_2.19         | Security logs must be ingested into the SIEM solution for analysis and monitoring.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Vulnerability Management                  | Vulnerability identification and remediation | R_2.21         | Manulife approved vulnerability scanning solution must be implemented to identify database related vulnerabilities.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Governance                                | Approved Resources                           | R_2.22         | Provisioning Azure SQL Database resources must follow Manulife Sevice Now porcess                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Cloud deployment                          | Usage of Version Control System              | R_2.23         | Azure SQL Database resources provisioning code must be stored in Manulife approved version control software with access granted to the required stakeholders only.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Cloud deployment                          | Resource Provisioning                        | R_2.24         | Azure SQL Database resources must be provisioned following the established cloud resources provisioning process.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |

# Cloud Database Deployment — Bank/Fintech Platform

## 1. Introduction

The Bank/Fintech Platform uses a relational database for structured account and transaction data. A document-oriented database was also implemented to demonstrate an alternative data model.

## 2. Cloud Services Used

### PostgreSQL on Neon

Neon was used to host the PostgreSQL database. The database contains the relational tables for customers, accounts, transactions, transaction logs, and transfers.

The implementation demonstrated account operations, transaction processing, constraints, indexing experiments, and transaction-isolation testing.

### MongoDB Atlas

MongoDB Atlas was used to host the NoSQL demonstration. The `bank_fintech` database contains a `transactions` collection with sample deposit, withdrawal, and transfer documents.

Queries were executed to retrieve successful transactions and filter deposit transactions.

## 3. Benefits of Cloud Deployment

- **Accessibility:** The databases can be accessed through web-based interfaces without requiring a local database server.
- **Reduced setup effort:** The hosted services provide managed database environments.
- **Scalability options:** Cloud database services may provide ways to increase capacity as workloads grow, depending on the service and plan.
- **Operational management:** Managed services can provide infrastructure-management features, although their availability depends on the selected configuration and plan.

## 4. Limitations and Verification

This exercise confirms that hosted PostgreSQL and MongoDB environments were used for the project. It does not, by itself, establish that replication, sharding, high availability, or disaster recovery were configured.

Those capabilities must be verified through the relevant service configuration or documented as theoretical concepts.

## 5. Conclusion

The project demonstrates cloud database deployment using Neon and MongoDB Atlas. These hosted environments supported the relational and document-oriented exercises. Further configuration and verification would be required to demonstrate specific distributed database mechanisms in operation.

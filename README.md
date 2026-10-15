# Portfolio 5: Distributed and Cloud Database Exercise

## 1. Case Study

The Bank/Fintech Platform manages customers, accounts, deposits, withdrawals, transfers, and transaction logs.

## 2. Objective

This portfolio examines how cloud database services and distributed database concepts can support the availability, scalability, and reliability of a financial application.

## 3. Cloud Database Deployment

The PostgreSQL relational database was deployed using Neon, while MongoDB Atlas was used for the document-oriented NoSQL demonstration. These services provide hosted database environments that can be accessed through web interfaces.

## 4. Distributed Database Concepts

This portfolio will examine:

- **Replication:** Maintaining copies of data to support availability and recovery.
- **Sharding:** Distributing data across partitions to support growth and workload management.
- **Availability:** Designing systems to remain accessible during failures.
- **Consistency:** Ensuring that users and operations observe data according to the database's consistency guarantees.

## 5. Financial-System Considerations

Financial transfers require careful consistency controls. Replication and sharding do not automatically guarantee correct balances or prevent duplicate transactions. A real deployment must account for transaction boundaries, recovery, access control, backups, and monitoring.

## 6. Evidence

Screenshots and documentation of the cloud database deployments and the distributed database concepts will be added as the exercise progresses.

## 7. Conclusion

This portfolio will evaluate how cloud-hosted databases and distributed database techniques can support a Bank/Fintech Platform, while recognising the trade-offs between availability, consistency, scalability, and operational complexity.

## Documentation

- [Cloud Database Deployment](cloud-deployment.md) — describes the hosted PostgreSQL and MongoDB environments, their use in the project, and deployment limitations.
- [Distributed Database Concepts](distributed-concepts.md) — discusses replication, sharding, availability, consistency, and how they relate to the Bank/Fintech Platform.

## Evidence Checklist

- [ ] Neon PostgreSQL project/dashboard screenshot.
- [ ] MongoDB Atlas cluster/dashboard screenshot.
- [ ] Evidence of database tables and transaction operations in PostgreSQL.
- [ ] Evidence of the MongoDB `bank_fintech` database, `transactions` collection, inserted documents, and query results.
- [ ] Screenshots linked in this README or clearly referenced from the relevant portfolio folders.

## Implementation Status

This project demonstrates the use of hosted PostgreSQL and MongoDB databases. It also includes practical PostgreSQL transaction and isolation exercises and MongoDB document queries.

Replication, sharding, failover, and disaster recovery have not been claimed as implemented unless supported by separate configuration evidence and tests. The distributed concepts document distinguishes the discussion of these mechanisms from the work demonstrated in this project.

## Conclusion

The Bank/Fintech Platform portfolio demonstrates relational and document-oriented database approaches using hosted services. It considers how distributed database concepts could support reliability, scalability, and data consistency in a financial application.

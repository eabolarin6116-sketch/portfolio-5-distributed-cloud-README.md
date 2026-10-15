# Distributed Database Concepts — Bank/Fintech Platform

## 1. Introduction

A bank or fintech platform must store account information and process financial transactions reliably. Distributed database concepts are important because they help systems manage data across infrastructure, support service availability, and handle growing workloads.

This section discusses replication, sharding, availability, and consistency in relation to the Bank/Fintech Platform. These concepts are discussed for learning purposes; this project does not claim that all four mechanisms were configured and tested.

## 2. Replication

Replication involves maintaining copies of data on multiple database servers or locations. It can support recovery and availability if one server becomes unavailable, depending on the replication design.

**Application to the case study:** Replication could help keep account and transaction data available if a database server fails. However, financial records must remain consistent, and replication delays or conflicting updates must be handled carefully.

**Project evidence:** PostgreSQL was hosted on Neon, and MongoDB was hosted on MongoDB Atlas. Using these cloud services does not, by itself, prove that a particular replication configuration was inspected or tested.

## 3. Sharding

Sharding divides a dataset into smaller portions distributed across multiple servers. It can help a database handle a larger volume of data and requests.

**Application to the case study:** Transaction history could potentially be partitioned by customer, account, or another suitable key. The choice must account for how frequently the application retrieves data and whether transfers require information from different partitions.

**Considerations:** Poor shard-key selection can create uneven workloads or make queries more complicated. Cross-shard financial transactions may also require additional coordination.

**Project evidence:** This project created and queried a MongoDB collection and implemented relational database tables in PostgreSQL. It did not demonstrate a configured and tested sharding arrangement.

## 4. Availability

Availability refers to the ability of a database service to respond to requests when needed. Failover, redundant infrastructure, backups, and recovery procedures can contribute to availability, depending on how they are configured.

**Application to the case study:** Customers may need to check balances or view transaction histories at any time. A production fintech platform should plan for service interruptions and establish appropriate recovery procedures.

**Project evidence:** The project used hosted database services. No independent failover or disaster-recovery test was performed as part of the documented exercises, so those capabilities are not claimed as verified results.

## 5. Consistency

Consistency concerns whether database operations preserve required data rules and whether users observe the expected state of data. In financial systems, correct balances and reliable transaction outcomes are particularly important.

**Application to the case study:** A transfer should debit the source account and credit the destination account as one logical operation. If a failure occurs, the system should avoid leaving only one side of the transfer applied.

The PostgreSQL implementation used transaction processing, rollback testing, row locking with `SELECT ... FOR UPDATE`, and a repeatable-read demonstration. These exercises provide practical evidence of transaction control and isolation behaviour in the implemented database.

**Design consideration:** The appropriate consistency and isolation strategy depends on the operation. Financial balance updates require careful coordination, while some reporting or analytics workloads may tolerate a delay in reflecting new data.

## 6. Comparison of the Implemented Databases

| Area | PostgreSQL on Neon | MongoDB Atlas |
|---|---|---|
| Data model | Relational tables | Document collection |
| Project use | Customers, accounts, transactions, logs, and transfers | Sample transaction documents |
| Demonstrated operations | SQL queries, account operations, constraints, rollback, indexing experiments, and isolation testing | Inserted sample documents and filtered transactions |
| Suitability in this project | Primary store for structured financial records and transactional operations | Complementary model for flexible transaction-history documents |
| Distributed features verified by this project | No independent replication or failover test documented | No independent sharding or failover test documented |

## 7. Conclusion

The project demonstrates the use of two hosted database platforms for a Bank/Fintech Platform. PostgreSQL supports the relational model and transactional exercises, while MongoDB demonstrates a document-oriented approach to transaction-history data.

Replication, sharding, availability, and consistency are important considerations when designing a distributed financial data system. However, the project evidence should distinguish the concepts discussed from the configurations and behaviours actually tested. Further service-specific configuration checks and failure tests would be needed to demonstrate additional distributed mechanisms in operation.

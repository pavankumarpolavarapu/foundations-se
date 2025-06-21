# Core Database Principles: ACID

## 🏦 What is a Transaction?
- A single, logical unit of work that may consist of multiple operations.
- **Example**: A bank transfer (a debit AND a credit).
- **Goal**: To ensure data remains correct and reliable.

## ⚛️ A - Atomicity
- **Concept**: Transactions are indivisible.
- **Motto**: "All or Nothing."
- **Analogy**: The bank transfer either fully completes (money moves) or it's fully cancelled (money stays put). There's no in-between.
- **Protects Against**: Partial updates and data corruption.

## ✅ C - Consistency
- **Concept**: The database moves from one valid state to another.
- **Motto**: "The Rules are Never Broken."
- **Analogy**: A transaction that would make an account balance negative is blocked before it can start. The database remains consistent with its rules.
- **Protects Against**: Data integrity violations (e.g., negative inventory, duplicate primary keys).

## 🚧 I - Isolation
- **Concept**: Concurrent transactions don't interfere with each other.
- **Motto**: "Transactions Don't Step on Each Other's Toes."
- **Analogy**: Two people trying to book the last airplane seat. Isolation ensures only one person can successfully complete the booking.
- **Protects Against**: Race conditions, "dirty reads" (reading uncommitted data), and lost updates.

## 💾 D - Durability
- **Concept**: Once a transaction is committed, it's permanent.
- **Motto**: "Once Saved, It Stays Saved."
- **Analogy**: You get a receipt from the ATM. Even if the power goes out a second later, your deposit is safe because it was written to a permanent log.
- **Protects Against**: Data loss due to system crashes or power failures.
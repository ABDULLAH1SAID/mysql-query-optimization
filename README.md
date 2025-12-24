# 🚀 MySQL Performance Tuning

> A hands-on lab created while studying SQL query optimization concepts,  
> inspired by the following YouTube playlist:  
> ▶️ [MySQL Performance Tuning – High-Performance Programming](https://www.youtube.com/watch?v=TukZd6LjeBc&list=PLBrWqg4Ny6vXQZqsJ8qRLGRH9osEa45sw&index=1)

This repository focuses on **practical experiments**, **execution plan analysis** using  
`EXPLAIN`, and **performance comparisons** in MySQL, with the goal of understanding  
how different queries and indexing strategies impact database performance.

---

## 📚 What I Learned from This Playlist

Through this playlist and hands-on practice, I learned how to:

🔍 **Analyze Query Performance**
- Use `EXPLAIN` to read and understand execution plans
- Interpret important metrics such as cost, rows, and access types

⚠️ **Identify Performance Bottlenecks**
- Full Table Scans
- Inefficient or missing indexes
- High-cost Nested Loop Joins

🧠 **Understand MySQL Optimizer Behavior**
- How MySQL chooses indexes
- When and why indexes are ignored
- Difference between clustered and non-clustered access

⚡ **Optimize Queries Effectively**
- Create proper indexes (Single & Composite)
- Use Covering Indexes
- Optimize `WHERE`, `JOIN`, `ORDER BY`, and `LIMIT` clauses

📊 **Measure Real Improvements**
- Compare query performance **before and after optimization**
- Detect real-world performance issues using execution plans

🛠 **Learn Performance Tuning Basics**
- Introduction to MySQL server-level configuration related to performance

---

## 🎯 Goal of This Repository

The main goal of this repository is to build a **practical reference** for  
**SQL query optimization**, focusing on **real performance improvements**  
rather than theoretical explanations.

This repo will serve as:
- A learning log
- A reference for common optimization patterns
- A showcase of hands-on MySQL performance tuning skills

---

## 🗄️ Database Schema (Test Data)

This repository uses a **sample `userinfo` table** to simulate real-world workloads
and test different query optimization and indexing strategies.

The table is intentionally designed to:
- Contain **millions of rows** (for realistic performance testing)
- Include columns commonly used in:
  - `WHERE` clauses
  - `JOIN` operations
  - `ORDER BY` and `LIMIT`
- Highlight the impact of **indexes vs full table scans**

### 📌 Table: `userinfo`

```sql
CREATE TABLE userinfo (
    id INT NOT NULL AUTO_INCREMENT,
    name VARCHAR(64) NOT NULL DEFAULT '',
    email VARCHAR(64) NOT NULL DEFAULT '',
    password VARCHAR(64) NOT NULL DEFAULT '',
    dob DATE NULL,
    address VARCHAR(255) NOT NULL DEFAULT '',
    city VARCHAR(64) NOT NULL DEFAULT '',
    state_id SMALLINT NOT NULL DEFAULT 0,
    zip VARCHAR(8) NOT NULL DEFAULT '',
    country_id SMALLINT NOT NULL DEFAULT 0,
    account_type VARCHAR(32) NOT NULL DEFAULT '',
    closest_airport VARCHAR(3) NOT NULL DEFAULT '',
    PRIMARY KEY (id)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;
```

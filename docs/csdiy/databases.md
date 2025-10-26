---
title: Databases
parent: CS DIY
nav_order: 1
toc: true
---

# Databases
{: .no_toc}

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Phase 1: SQL Proficiency

**Goal:** Get comfortable writing and optimizing SQL queries

**Resources:**
- [SQL Bolt](https://sqlbolt.com/) - Complete all lessons (4 hours)
- [LeetCode SQL Top 50](https://leetcode.com/studyplan/top-sql-50/) - Solve all problems (10 hours)
- [Mode Analytics SQL Tutorial](https://mode.com/sql-tutorial/) - Skim for advanced patterns (1 hour)

**Daily commitment:** 1 hour/day for 2 weeks

---

## Phase 2: Database Fundamentals

**Goal:** Understand how databases work internally

**Read "Designing Data-Intensive Applications" (DDIA):**
- Chapter 1: Foundations (2 hours)
- Chapter 2: Data Models & Query Languages (3 hours)
- **Chapter 3: Storage & Retrieval** ← Critical (4 hours)
- **Chapter 7: Transactions** ← Critical (4 hours)
- Chapter 8: Distributed Systems Intro (3 hours)

**Watch [CS186](https://cs186berkeley.net/sp21/) Lectures:**
- Lectures 11-12: Query Optimization (4 hours)

**Weekly commitment:** 5 hours/week for 4 weeks

## Phase 3: Time-Series Specialization

**Goal:** Understand financial data storage

### Columnar vs Row Storage (Foundation)

**Free Articles:**
- [AWS: Columnar Storage for Databases](https://aws.amazon.com/nosql/columnar/) - Overview (15 min)
- [The Basics of Column-Oriented Databases](https://www.vertabelo.com/blog/column-store-databases/) - Easy explanation (20 min)
- **DDIA Chapter 3** (pages 95-104 in the book you already need to read) - Best technical explanation

**Video:**
- [Row vs Column Oriented Databases](https://www.youtube.com/watch?v=Vw1fCeD06YI) - Visual explanation (8 min)

### TimescaleDB (PostgreSQL for Time-Series)

**Official Tutorials:**
- [TimescaleDB Docs - Introduction](https://docs.tigerdata.com/getting-started/latest/) - Start here
- [TimescaleDB Tutorial](https://docs.tigerdata.com/tutorials/latest/) - Hands-on examples
- [Time-Series Data: Why and How to Use a Relational Database](https://www.tigerdata.com/blog/time-series-data-why-and-how-to-use-a-relational-database-instead-of-nosql-d0cd6975e87c) - Excellent blog post (30 min)

**Specific Topics:**
- [Hypertables Explained](https://docs.tigerdata.com/use-timescale/latest/hypertables/) - Core concept
- [Time-Series Queries](https://docs.tigerdata.com/use-timescale/latest/query-data/) - Practical examples

### ClickHouse (Columnar Database)

**Official Resources:**
- [ClickHouse Documentation - Introduction](https://clickhouse.com/docs/en/intro) - Start here
- [ClickHouse for Time-Series](https://clickhouse.com/docs/en/guides/developer/time-series) - Key use case
- [ClickHouse vs Traditional Databases](https://clickhouse.com/docs/en/concepts/why-clickhouse-is-so-fast) - Understanding the architecture

**Practical Guides:**
- [Getting Started with ClickHouse](https://clickhouse.com/docs/en/getting-started/quick-start) - Hands-on tutorial
- [ClickHouse for Financial Data](https://clickhouse.com/blog/clickhouse-for-financial-data) - Directly relevant blog post

**Video:**
- [ClickHouse Introduction](https://www.youtube.com/watch?v=JjFJfPP66Ug) - Overview (20 min)

### kdb+/q (Finance Industry Standard)

**Free Learning Resources:**
- [Q for Mortals](https://code.kx.com/q4m3/) - **THE definitive free book** (read Chapters 1-3, 9)
- [KX Academy - Free Courses](https://kx.com/academy/) - Official training (requires free account)
- [Learn q in Y Minutes](https://learnxinyminutes.com/docs/q/) - Quick syntax overview (30 min)

**Introductory Materials:**
- [Introduction to kdb+](https://code.kx.com/q/learn/) - Official getting started
- [Q Phrasebook](https://code.kx.com/q/basics/by-topic/) - Quick reference for common operations
- [Simple Guide to kdb+ and q](https://kx.com/blog/simple-guide-kdb-q/) - Beginner-friendly blog

**Why kdb+ Matters:**
- Used by major banks and HFT firms
- Extremely fast for time-series data
- In-memory columnar database
- **Good to know, not required to master**

**Video:**
- [kdb+ Introduction](https://www.youtube.com/watch?v=8eoysfqO3UY) - Basic concepts (15 min)

### General Time-Series Concepts

**Articles:**
- [Time-Series Database Fundamentals](https://www.influxdata.com/time-series-database/) - InfluxDB blog (good concepts even if you don't use InfluxDB)
- [How to Choose a Time-Series Database](https://medium.com/@leventov/comparison-of-the-open-source-olap-systems-for-big-data-clickhouse-druid-and-pinot-8e042a5ed1c7) - Comparison article
- [Time-Series Data at Scale](https://netflixtechblog.com/scaling-time-series-data-storage-part-i-ec2b6d44ba39) - Netflix engineering blog

**Academic/Reference:**
- [Time-Series Databases: A Survey](https://arxiv.org/abs/2203.04197) - Research paper (skim for concepts, not implementation details)

### Connect to Your DolphinDB Experience

**DolphinDB Resources:**
- [DolphinDB Documentation](https://docs.dolphindb.com/en/index.html) - Revisit with CS knowledge
- [DolphinDB vs Traditional Databases](https://docs.dolphindb.com/en/db_distr_comp/db_comparison.html) - Architecture comparison
- [Time-Series in DolphinDB](https://docs.dolphindb.com/en/tutorials/streaming_tutorial.html) - Streaming data

**Your advantage:** You already used DolphinDB - now understand WHY it's designed that way

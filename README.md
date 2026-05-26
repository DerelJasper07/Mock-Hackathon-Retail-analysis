# Retail Sales Data Warehouse & Fraud Analytics Platform

## Project Overview

This project is a Cloud-Based Retail Sales Data Warehouse & Analytics Platform developed using Snowflake and Power BI. The platform is designed for a multi-branch retail company to manage retail sales analytics, fraud monitoring, automated ELT pipelines, and executive reporting.

The system supports scalable cloud analytics with secure governance, automated transformations, fraud detection workflows, and interactive business intelligence dashboards.

---

# Objectives

The project was developed to achieve the following objectives:

* Build a scalable retail data warehouse using Snowflake
* Implement automated ELT pipelines using Streams and Dynamic Tables
* Perform data transformation and cleaning
* Detect suspicious and fraudulent retail transactions
* Create STAR schema-based analytics architecture
* Build interactive executive dashboards using Power BI
* Implement RBAC and data masking policies
* Support structured and semi-structured data ingestion

---

# Technologies Used

## Snowflake

* Warehouses
* Databases
* Schemas
* Tables
* Streams
* Dynamic Tables
* Views
* Materialized Views
* Masking Policies
* Time Travel
* Zero-Copy Cloning

## Power BI

* Data Transformation using Power Query
* DAX Measures
* Interactive Dashboard Development
* KPI Reporting
* Slicers and Filters
* Fraud Analytics Visualizations


# Architecture

## Multi-Layer Data Warehouse Architecture

```text
RAW LAYER  →  CORE LAYER  →  MART LAYER  →  POWER BI DASHBOARD
```

---

# RAW Layer

The RAW layer stores ingested source files without transformation.

## RAW Tables

* RAW_USERS
* RAW_CUSTOMERS
* RAW_PRODUCTS
* RAW_SALES_TRANSACTIONS
* RAW_FRAUD_SALES_ALERT

## Data Types Loaded

* CSV Files
* JSON Files

## Snowflake Features Used

* Internal Stages
* File Formats
* COPY INTO Commands

---

# CORE Layer

The CORE layer performs cleaned and validated transformations.

## CORE Tables

* CORE_USERS
* CORE_CUSTOMERS
* CORE_PRODUCTS
* CORE_SALES_TRANSACTIONS
* CORE_FRAUD_SALES_ALERT

## Transformations Applied

### Sales Validation

* Sales amount greater than 0

### Duplicate Prevention

* Duplicate transaction IDs removed using QUALIFY ROW_NUMBER()

### Product Validation

* Negative stock quantities removed

### Customer Validation

* Duplicate customer emails removed

### Fraud Processing

* Fraud alerts marked for analyst review

## Snowflake Features Used

* Streams
* Dynamic Tables
* Window Functions
* Conditional Logic

---

# MART Layer

The MART layer implements STAR schema architecture optimized for analytics and reporting.

## Dimension Tables

### DIM_CUSTOMER

Contains:

* Customer details
* Customer type
* Location details

### DIM_PRODUCT

Contains:

* Product details
* Product categories
* Brand information

### DIM_BRANCH

Contains:

* Branch locations

### DIM_DATE

Contains:

* Date
* Month
* Year
* Day information

## Fact Table

### FACT_SALES

Contains:

* Transaction information
* Sales metrics
* Profit metrics
* Payment information

---

# STAR Schema Design

```text
                 DIM_CUSTOMER
                        |
                        |
DIM_PRODUCT ---- FACT_SALES ---- DIM_BRANCH
                        |
                        |
                    DIM_DATE
```

---

# Dynamic Tables

Dynamic Tables were used instead of Tasks for automated refresh and transformation.

Benefits:

* Automatic refresh
* Simplified pipeline management
* Near real-time updates
* Reduced orchestration complexity

---

# Views Created

## VW_TOTAL_SALES

Provides daily sales and profit summary.

## VW_TOP_PRODUCTS

Provides highest revenue-generating products.

## VW_FRAUD_TRANSACTIONS

Displays fraud alerts pending review.

---

# Materialized Views

## MV_MONTHLY_REVENUE

Optimized monthly revenue aggregation for faster dashboard performance.

Benefits:

* Faster aggregation queries
* Dashboard optimization
* Reduced query execution time

---

# Security and Governance

## RBAC Roles Implemented

* ACCOUNTADMIN
* SYSADMIN
* SECURITYADMIN
* DATA_ANALYST
* BUSINESS_MANAGER

## Masking Policies

Dynamic masking policies were implemented for:

* Customer Emails
* User Emails
* Fraud Scores

Benefits:

* Data privacy
* Role-based access control
* Secure analytics

---

# Time Travel

Snowflake Time Travel was implemented for data recovery.

Benefits:

* Recover deleted data
* Historical data access
* Data rollback capability

---

# Zero-Copy Cloning

Zero-copy cloning was implemented for rapid environment duplication.

Benefits:

* Instant cloning
* No additional storage usage
* Development and testing support

---

# Power BI Dashboard

## Dashboard Features

The Power BI dashboard provides:

* Executive KPI Reporting
* Sales Analytics
* Fraud Monitoring
* Product Insights
* Customer Analytics
* Geographic Analysis
* Payment Analysis
* Interactive Filtering

---

# Dashboard KPIs

* Total Sales
* Total Profit
* Profit Percentage
* Total Orders
* Total Customers
* Fraud Count
* High Risk Alerts

---

# Dashboard Visuals

## Charts Used

* KPI Cards
* Line Charts
* Bar Charts
* Column Charts
* Donut Charts
* Pie Charts
* Maps
* Tables

---

# Dashboard Filters

## Slicers

* Date
* Branch
* Category
* Payment Mode
* Customer Type
* Fraud Status

## Global Filters

Applied for:

* Year filtering
* Completed transactions

## Component Filters

Applied for:

* Top 10 products
* High-risk fraud transactions

---

# Power Query Transformations

The following transformations were applied:

* Data type correction
* Null value handling
* Text standardization
* Fraud status classification
* Age group categorization
* Time slot categorization
* Date extraction

---

# DAX Measures

## Important Measures

* TOTAL SALES
* TOTAL PROFIT
* PROFIT %
* TOTAL TRANSACTIONS
* FRAUD COUNT
* HIGH RISK ALERTS
* AVG SALES

---

# Business Rules Implemented

* Sales amount must be greater than 0
* Duplicate transactions are invalid
* Product stock cannot become negative
* Customer email must be unique
* Fraud alerts require analyst review

---

# Key Features

## Fraud Detection

Fraud transactions were identified using:

* Fraud labels
* Fraud score analysis
* Payment behavior analysis
* Time-based fraud analytics

## Interactive Analytics

Dashboard supports:

* Cross-filtering
* Drill-down analysis
* Interactive visualizations
* Dynamic slicing

## Enterprise Data Warehouse

The solution follows:

* STAR schema architecture
* ELT pipeline methodology
* Cloud-native analytics
* Secure governance principles

---

# Project Outcomes

The project successfully demonstrates:

* Snowflake architecture understanding
* Data warehouse modeling
* SQL transformation skills
* Dynamic Table implementation
* Power BI dashboard development
* Fraud analytics implementation
* Governance and security implementation
* Cloud-based retail analytics

---

# Future Enhancements

Possible future improvements:

* Real-time streaming analytics
* Machine learning fraud prediction
* Snowpipe auto-ingestion
* Advanced forecasting models
* Row-level security in Power BI
* Predictive customer analytics

---

# Conclusion

This project successfully implements a complete Retail Sales Data Warehouse and Fraud Analytics Platform using Snowflake and Power BI. The platform demonstrates enterprise-level cloud data warehousing, automated ELT pipelines, fraud detection workflows, governance implementation, and professional executive reporting.

The solution provides scalable analytics capabilities for retail business operations while ensuring security, performance optimization, and interactive business intelligence reporting.

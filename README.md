# 🚚 Last-Mile Delivery Analytics using MySQL

## 📌 Project Overview

**Last-Mile Delivery Analytics** is a SQL-based data analytics project developed using **MySQL** to analyze delivery operations and generate business insights.

The project uses a relational database containing information about **customers, orders, deliveries, drivers, and vehicles**. SQL queries are used to analyze customer demand, order value, delivery performance, driver workload, vehicle usage, and delivery problems.

---

## 🎯 Business Problem

Last-mile delivery operations generate large amounts of data related to customers, orders, drivers, vehicles, and delivery execution.

The objective of this project is to use SQL to answer important business questions such as:

* Which delivery zones have the highest demand?
* Which service types are most popular?
* Which customers generate the highest order value?
* How efficiently are deliveries being completed?
* Which drivers handle the most deliveries?
* Which vehicle types are used the most?
* Which orders require multiple delivery attempts?
* Which zones have more delivery problems?

---

## 📊 Dataset Overview

The project contains five CSV datasets:

| Dataset    | Records | Description                                             |
| ---------- | ------: | ------------------------------------------------------- |
| Customers  |     400 | Customer information and delivery zones                 |
| Orders     |   3,000 | Order details, service types, priorities and values     |
| Deliveries |   3,500 | Delivery execution and performance data                 |
| Drivers    |      80 | Driver details, ratings and employment information      |
| Vehicles   |      50 | Vehicle type, fuel type, capacity and depot information |

The database is named **`last_mile`**.

---

## 🗂️ Database Structure

### 1. Customers

Contains customer information such as:

* Customer ID
* Customer name
* City
* Delivery zone
* Preferred time slot
* Customer type
* Account since

### 2. Orders

Contains:

* Order ID
* Customer ID
* Order date
* Delivery zone
* Package weight
* Service type
* Priority
* Total order value

### 3. Deliveries

Contains:

* Delivery ID
* Order ID
* Driver ID
* Vehicle ID
* Assigned date
* Actual delivery date
* Delivery status
* Delivery attempts
* Distance
* Delivery duration

### 4. Drivers

Contains:

* Driver ID
* Driver name
* Hire date
* Rating
* Employment type
* Active status

### 5. Vehicles

Contains:

* Vehicle ID
* Vehicle type
* Fuel type
* Maximum payload
* Depot
* Last service date
* Active status

---

## 🔗 Database Relationships

The database uses primary and foreign keys to connect the tables.

```text
Customers
    │
    │ customer_id
    ▼
Orders
    │
    │ order_id
    ▼
Deliveries
   / \
  /   \
 ▼     ▼
Drivers  Vehicles
```

* `customers.customer_id` → `orders.customer_id`
* `orders.order_id` → `deliveries.order_id`
* `drivers.driver_id` → `deliveries.driver_id`
* `vehicles.vehicle_id` → `deliveries.vehicle_id`

---

## 🧹 Data Quality Checks

Before performing the analysis, SQL was used to check data quality.

The checks included:

* Record counts
* NULL values
* Duplicate primary keys
* Sample records
* Table-level row counts

This helped validate the database before performing business analysis.

---

# 🔍 SQL Analysis

The project contains **34 business questions** divided into five major analysis areas.

## 1️⃣ Delivery Demand Analysis

Questions include:

* Which delivery zones have the highest number of orders?
* Which service types have the highest demand?
* Which priority level has the highest number of orders?
* How does order volume change over time?
* Which service type generates the highest order value?

---

## 2️⃣ Customer Order Behaviour

Questions include:

* Which customers place the most orders?
* Which customers have the highest total order value?
* Which customer type generates more orders and value?
* How does customer activity vary across delivery zones?
* How does customer ordering change over time?

---

## 3️⃣ Delivery Performance

Questions include:

* What is the distribution of delivery statuses?
* How does delivery performance vary by zone?
* What is the average delivery duration?
* What is the average delivery distance?
* Which service types have longer delivery durations?
* How does delivery performance change over time?

---

## 4️⃣ Driver & Vehicle Performance

Questions include:

* Which drivers handle the most deliveries?
* How do delivery outcomes vary by driver?
* What is the average delivery duration for each driver?
* Which vehicle types are used the most?
* How does vehicle performance differ by vehicle type?

---

## 5️⃣ Delivery Problem Analysis

Questions include:

* Which orders required multiple delivery attempts?
* Which deliveries have more than one attempt?
* What are the common delivery statuses and problem patterns?
* How does performance differ for orders with multiple attempts?
* Which zones experience more delivery problems?

---

# 🛠️ SQL Concepts Used

The project demonstrates practical use of:

* `SELECT`
* `WHERE`
* `DISTINCT`
* `COUNT()`
* `SUM()`
* `AVG()`
* `GROUP BY`
* `HAVING`
* `ORDER BY`
* `JOIN`
* `CASE`
* `YEAR()`
* `MONTH()`
* Primary Keys
* Foreign Keys
* NULL checks
* Duplicate checks

## The SQL analysis uses joins to combine customers, orders, deliveries, drivers and vehicles for business-level analysis.

# 📈 Key Findings

Based on the dataset analysis:

### 📍 Demand

* **ZONE0005** has the highest order volume with **240 orders**.
* **Standard** delivery has the highest number of orders with **620 orders**.
* The dataset contains **3,000 orders** across multiple delivery zones and service types.

### 👤 Customer Value

* Customer **DLVCUST0000055** has the highest number of orders with **19 orders**.
* The same customer has the highest total order value of approximately **43,779.25**.

### 🚚 Delivery Performance

* There are **3,500 delivery records**.
* Average delivery duration is approximately **47.19 minutes**.
* Average delivery distance is approximately **15.83 km**.
* Delivery statuses include **Delivered, Rescheduled, Pending, and Failed**.

### 👨‍💼 Driver Operations

* The dataset contains **80 drivers**.
* **75 drivers** are currently marked as active.

### 🚗 Vehicle Operations

* The dataset contains **50 vehicles**.
* Vehicle types include **Cargo Bike, Truck, Car, Motorbike, Van, and Electric Van**.

### ⚠️ Delivery Problems

* **613 delivery records** have either `Failed` or `Rescheduled` status.
* Multiple delivery attempts are also present in the dataset.
* The maximum recorded delivery attempt is **3**.

---

# 💡 Business Recommendations

Based on the analysis, the following actions can help improve delivery operations:

1. **Focus capacity on high-demand zones** such as zones with consistently high order volume.

2. **Monitor high-value customers** and understand their ordering behaviour to support customer retention.

3. **Review failed and rescheduled deliveries** to identify operational causes.

4. **Balance driver workload** by monitoring delivery volume and average delivery duration.

5. **Reduce multiple delivery attempts** by identifying reasons for unsuccessful first attempts.

6. **Optimize vehicle usage** by considering vehicle type, distance, delivery duration and payload capacity.

---

# 📁 Project Structure

```text
last-mile-delivery-sql-analysis/
│
├── README.md
│
├── sql/
│   └── sql_project.sql
│
├── dataset/
│   ├── customers.csv
│   ├── orders.csv
│   ├── deliveries.csv
│   ├── drivers.csv
│   └── vehicles.csv
│
├── presentation/
│   └── Last_Mile_Delivery_SQL_Project.pptx
│
└── screenshots/
```

---

# 🎓 Skills Demonstrated

**SQL | MySQL | Data Analysis | Database Design | Data Quality Checks | Relational Databases | Business Analysis | Data Exploration**

---

# 👩‍💻 Author Name 

**Shrapti Bedre**


Data Analytics Course Project

---

# 📌 Conclusion

This project demonstrates how **MySQL and SQL can be used to transform raw delivery data into meaningful business insights**.

The analysis covers customer demand, order value, delivery efficiency, driver performance, vehicle usage, and delivery problems, providing a practical understanding of how SQL can support operational decision-making.

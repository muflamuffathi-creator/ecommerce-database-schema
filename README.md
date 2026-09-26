# 🗄️ E-Commerce Database Schema

MySQL schema and sample data for a computer hardware e-commerce platform — includes categories, products, customers, orders, and order items with relational constraints.

## 📋 Overview

This repository contains the relational database design for a computer hardware e-commerce system, built with MySQL/MariaDB. It models a real-world online store: browsing products by category, placing orders, and tracking order status.

## 🧩 Tables

| Table | Description |
|---|---|
| 🏷️ **categories** | Product categories (Laptops, Accessories, Components) |
| 💻 **products** | Hardware items with price, stock quantity, and category link |
| 👤 **customers** | Customer records — name, email, phone, address |
| 📦 **orders** | Orders with status tracking (`Pending` → `Processing` → `Shipped` → `Delivered` / `Cancelled`) |
| 🧾 **order_items** | Line items linking each order to its products, quantity, and unit price |

## 🔗 Relationships

- One **customer** → many **orders**
- One **order** → many **order_items**
- One **product** → many **order_items**
- One **category** → many **products**
- Foreign keys enforce referential integrity (`ON DELETE CASCADE` / `SET NULL`)

## ⚙️ Setup

1. Create a database in MySQL/MariaDB (e.g. via phpMyAdmin or CLI):
```sql
   CREATE DATABASE ecommerce_db;
```
2. Import the schema and sample data:
```bash
   mysql -u root -p ecommerce_db < ecommerce_db.sql
```
3. Done! The database will be populated with sample categories, products, customers, and orders for testing.

## 🛠️ Tech

- **Database:** MySQL / MariaDB
- **Charset:** utf8mb4

## 📄 License

Feel free to use this schema as a reference or starting point for your own projects.

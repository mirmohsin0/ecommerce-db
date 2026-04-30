# 🛒 E-Commerce Database System (MySQL)

A production-style relational database designed to simulate a real-world e-commerce platform.  
This project demonstrates database design, normalization, and advanced SQL querying.

---

## 📌 Overview

This database models the core functionality of an e-commerce system, including:

- User management  
- Product catalog  
- Order processing  
- Sales tracking  

---

## 🗂️ Database Schema

### 📦 Tables Included

| Table Name     | Description |
|----------------|------------|
| Users          | Stores customer information |
| Products       | Stores product details |
| Orders         | Stores order transactions |
| Order_Items    | Stores items within each order |

---

## 🔗 Relationships

- One **User** → Many **Orders**
- One **Order** → Many **Order_Items**
- One **Product** → Many **Order_Items**

---

## 🔥 Features

- ✅ Well-structured relational schema  
- ✅ Use of Primary & Foreign Keys  
- ✅ Normalized database design  
- ✅ Sample data for testing  
- ✅ Supports analytical SQL queries  

---

## 📊 Example Queries

```sql
-- Total Sales
SELECT SUM(total_amount) AS total_sales FROM Orders;

-- Top Selling Products
SELECT p.name, SUM(oi.quantity) AS total_sold
FROM Order_Items oi
JOIN Products p ON oi.product_id = p.id
GROUP BY p.name
ORDER BY total_sold DESC;

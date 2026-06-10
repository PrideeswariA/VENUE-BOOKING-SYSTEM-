# 📅 Venue Booking System — Java

![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)
![JDBC](https://img.shields.io/badge/JDBC-007396?style=flat-square&logo=java&logoColor=white)
![Swing](https://img.shields.io/badge/Java_Swing-GUI-FF6F00?style=flat-square&logo=java&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-38BDAE?style=flat-square)
![Course](https://img.shields.io/badge/Course-Java_Programming-6E40C9?style=flat-square)

A complete **Java-based Venue Booking Management System** developed as part of the Java Programming course (EGB1201) at M. Kumarasamy College of Engineering. The system automates the entire venue booking process for events like weddings, conferences, parties, and meetings.

---

## 📌 Project Overview

The Venue Booking System replaces traditional manual booking methods with a digital platform where:
- **Customers** can browse venues, view details, and book events
- **Organizers** can manage venues, food items, equipment, and events
- **Admins** can oversee all bookings, manage users, and generate reports

---

## 🎯 Objectives

- ✅ Eliminate manual booking errors and double-booking conflicts
- ✅ Provide real-time venue availability to users
- ✅ Enable secure user registration and login
- ✅ Allow admin to manage venues, bookings, and customer data
- ✅ Automate cost calculation including event, food, and equipment costs
- ✅ Deliver a user-friendly GUI using Java Swing

---

## 🧩 Modules

| Module | Description |
|---|---|
| 👤 **User Management** | Registration, login, profile management for customers |
| 🏛️ **Venue Management** | Add, update, delete venue details (location, capacity, cost) |
| 🔍 **Search & Booking** | Browse venues, select dates, book events |
| 💳 **Payment Module** | Cost calculation and payment status tracking |
| 🔧 **Admin Panel** | Manage all users, venues, bookings, and reports |
| 🍽️ **Food & Equipment** | Manage catering options and event equipment |

---

## 💻 Tech Stack

| Layer | Technology |
|---|---|
| **Backend** | Java (OOP) |
| **Database** | MySQL |
| **Connectivity** | JDBC (Java Database Connectivity) |
| **GUI** | Java Swing / JavaFX |
| **Concepts** | OOP, Collections, Exception Handling, Abstraction |

---

## 🏗️ Java Concepts Used

```java
// OOP Concepts Applied:
// ✅ Classes & Objects   → User, Venue, Booking, Member
// ✅ Inheritance         → Admin and Customer extend User
// ✅ Polymorphism        → calculatePrice() varies by booking type
// ✅ Encapsulation       → Private variables with getters/setters
// ✅ Abstraction         → Interfaces for payment, abstract booking base class

// Collections Framework:
// ✅ ArrayList & HashMap → Store users, venues, and booking details

// Exception Handling:
// ✅ Try-catch blocks    → Handle invalid inputs, login errors, booking conflicts

// JDBC:
// ✅ MySQL Connection    → Manage users, venues, and transactions

// Packages:
// ✅ user / venue / booking / admin → Clean modular structure
```

---

## 🏛️ System Architecture

```
┌─────────────────────────────────────────────┐
│              VENUE BOOKING SYSTEM            │
├──────────────┬──────────────┬───────────────┤
│     USER     │   ORGANIZER  │     ADMIN      │
├──────────────┼──────────────┼───────────────┤
│ Registration │ Manage Venue │ Manage Users   │
│ Login        │ Manage Food  │ View Reports   │
│ Book Event   │ Manage Equip │ Handle Booking │
│ Make Payment │ Manage Event │ System Config  │
│ View Bookings│ View Bookings│                │
│ Logout       │              │                │
└──────────────┴──────────────┴───────────────┘
                      │
              ┌───────────────┐
              │  MySQL Database│
              │  (JDBC Layer)  │
              └───────────────┘
```

---

## 📁 Project Structure

```
VENUE-BOOKING-SYSTEM/
│
├── src/
│   ├── user/
│   │   ├── User.java          # Base user class
│   │   ├── Customer.java      # Customer (extends User)
│   │   └── Admin.java         # Admin (extends User)
│   ├── venue/
│   │   └── Venue.java         # Venue entity class
│   ├── booking/
│   │   └── Booking.java       # Booking entity class
│   ├── payment/
│   │   └── Payment.java       # Payment interface & implementation
│   └── db/
│       └── DBConnection.java  # JDBC MySQL connection
│
├── database/
│   └── venue_booking.sql      # Database schema & sample data
│
├── screenshots/               # Application screenshots
│
└── README.md
```

---

## 🗄️ Database Schema

```sql
-- Core Tables
CREATE TABLE users (
    user_id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100),
    email VARCHAR(100) UNIQUE,
    password VARCHAR(255),
    role ENUM('customer', 'admin', 'organizer')
);

CREATE TABLE venues (
    venue_id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100),
    location VARCHAR(200),
    capacity INT,
    cost_per_day DECIMAL(10,2),
    availability BOOLEAN
);

CREATE TABLE bookings (
    booking_id INT PRIMARY KEY AUTO_INCREMENT,
    user_id INT,
    venue_id INT,
    event_name VARCHAR(100),
    event_date DATE,
    guest_count INT,
    food_cost INT,
    equipment_cost INT,
    total_cost INT,
    payment_status VARCHAR(20),
    FOREIGN KEY (user_id) REFERENCES users(user_id),
    FOREIGN KEY (venue_id) REFERENCES venues(venue_id)
);
```

---

## 🚀 How to Run

### Prerequisites
- Java JDK 8 or higher
- MySQL Server
- IDE (Eclipse / IntelliJ IDEA)
- MySQL Connector JAR

### Steps

**1. Clone the repository**
```bash
git clone https://github.com/PrideeswariA/VENUE-BOOKING-SYSTEM.git
cd VENUE-BOOKING-SYSTEM
```

**2. Set up the database**
```bash
mysql -u root -p
source database/venue_booking.sql
```

**3. Configure JDBC connection**
```java
// DBConnection.java
String url = "jdbc:mysql://localhost:3306/venue_booking";
String user = "root";
String password = "your_password";
```

**4. Run the application**
```bash
javac src/**/*.java
java src/Main
```
---

## 📚 Key Features

- 🔐 Secure login & registration system
- 🏛️ Browse venues with details (location, capacity, cost)
- 📅 Real-time booking with date selection
- 💰 Automatic cost calculation (venue + food + equipment)
- 🍽️ Catering and equipment management
- 👑 Admin dashboard for complete system control
- ❌ Double-booking prevention
- 📊 Booking history for users

---

## 👩‍💻 Author

**Prideeswari A** (Roll No: 927624BEV031)
B.E. Electronics Engineering — VLSI Design & Technology
M. Kumarasamy College of Engineering, Karur

**Guide:** Mrs. K.V. Priyadharshini M.E., (Ph.D.), Assistant Professor/IT

[![GitHub](https://img.shields.io/badge/GitHub-PrideeswariA-181717?style=flat-square&logo=github)](https://github.com/PrideeswariA)
[![Portfolio](https://img.shields.io/badge/Portfolio-Visit-FF6F00?style=flat-square&logo=netlify)](https://phenomenal-heliotrope-c53716.netlify.app)

---

## 📄 License

This project is submitted as part of the academic course **EGB1201 - Java Programming** at M. Kumarasamy College of Engineering (2025–2026).

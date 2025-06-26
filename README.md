# Class Fund Management Application

[![Status](https://img.shields.io/badge/status-completed-brightgreen)](https://github.com/ardorianda/managementKasKelas)
[![Java](https://img.shields.io/badge/language-Java-blue.svg)](https://www.java.com/)
[![MySQL](https://img.shields.io/badge/database-MySQL-orange.svg)](https://www.mysql.com/)

## 📋 Project Description

This project is an academic OOP assignment to develop a desktop application for class fund management using Java Swing and MySQL. The application helps class treasurers efficiently track student payments, manage expenses, and monitor the overall class balance.

A simple desktop application built with Java Swing to manage class funds. It helps treasurers track student payments, record expenses, and monitor the overall balance efficiently.

## ✨ Features

-   **Payment Tracking**: Track student payments and view individual payment status (paid, due, and arrears).
-   **Expense Management**: Record and manage all class expenses with details like amount, date, and purpose.
-   **Automated Balance Calculation**: Automatically calculates and displays the current balance, total income, and total expenses.
-   **Student Profiles**: View student details, including their name, student ID (NIM), and profile picture.
-   **User-Friendly Interface**: A clean, tabbed interface built with custom components for an enhanced user experience.

## 🛠️ Tech Stack

-   **Core**: Java
-   **GUI**: Java Swing
-   **Database**: MySQL
-   **Build Tool**: Apache Maven
-   **UI Components**: KGradientPanel, KControls
-   **Database Connector**: MySQL Connector/J

## 📋 Prerequisites

Before you begin, ensure you have the following installed on your system:
-   Java Development Kit (JDK) 17 or newer.
-   MySQL Server.
-   An IDE that supports Maven, such as Apache NetBeans or IntelliJ IDEA.

## 🚀 Getting Started

Follow these steps to get the project up and running on your local machine.

1.  **Clone the Repository**
    ```sh
    git clone https://github.com/TWO-ONE-21/managementKasKelas.git
    cd managementKasKelas
    ```

2.  **Database Setup**
    -   Ensure your MySQL server is running.
    -   Create a new database named `managementkas`.
        ```sql
        CREATE DATABASE managementkas;
        ```
    -   Import the provided SQL file (`managementkas.sql`) to set up the tables and initial data. You can use a tool like phpMyAdmin or run the following command in your terminal:
        ```sh
        mysql -u root -p managementkas < ...managementKasKelas/src/main/resource/managementkas.sql
        ```
    -   Make sure your MySQL user is `root` with an empty password, or update the connection details in `src/main/java/com/mycompany/managementkaskelas/main.java`:
        ```java
        // in private void connection()
        con = DriverManager.getConnection("jdbc:mysql://localhost/managementKas", "your_username", "your_password");
        ```

3.  **Run the Application**
    -   Open the project folder in your IDE (e.g., NetBeans).
    -   The IDE will automatically resolve the Maven dependencies listed in `pom.xml`.
    -   Locate and run the main class: `com.mycompany.managementkaskelas.ManagementKasKelas`.

## 🗃️ Database Schema

The application uses the following tables to store data:

-   `mahasiswa`: Stores student information.
    -   `nim` (Primary Key): Student ID.
    -   `nama`: Student's full name.
    -   `foto`: Profile picture (stored as BLOB).
    -   `total_pembayaran`: The number of weekly payments made.
-   `pengeluaran`: Logs all class expenses.
    -   `id` (Primary Key): Unique ID for the expense.
    -   `jumlah`: The amount of money spent.
    -   `tanggal`: The date of the transaction.
    -   `tujuan`: The purpose of the expense.

## 🧑‍💻 Author

-   **Ardo Rianda** - *Initial Work*


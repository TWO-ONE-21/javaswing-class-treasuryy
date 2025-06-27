# Class Fund Management Application

[![Status](https://img.shields.io/badge/status-completed-brightgreen)](https://github.com/ardorianda/managementKasKelas)
[![Java](https://img.shields.io/badge/language-Java-blue.svg)](https://www.java.com/)
[![MySQL](https://img.shields.io/badge/database-MySQL-orange.svg)](https://www.mysql.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## 📋 Project Description

This project is a desktop application developed as an academic assignment for an Object-Oriented Programming (OOP) course. Built with Java Swing and backed by a MySQL database, it provides a solution for class treasurers to manage finances. The application aims to streamline the process of tracking student fee payments, managing expenses, and monitoring the overall class fund balance efficiently and accurately.

## ✨ Key Features

-   **Student Payment Tracking**: Monitor the payment status of each student, including paid status, outstanding dues, and the total amount of arrears.
-   **Expense Management**: Record and manage all class-related expenses with details such as amount, date, and purpose.
-   **Automated Balance Calculation**: Dynamically calculates and displays the current cash balance based on total income and total expenses.
-   **Automatic Date Stamping**: Utilizes the `java.time` library to automatically record the transaction date for expenses based on the system time, ensuring chronological data integrity.
-   **Student Profiles**: View detailed student information, including Name, Student ID Number (NIM), and a profile picture retrieved from the database.
-   **Intuitive User Interface**: Designed with a clean, tabbed interface and custom components for an enhanced user experience.

## 🛠️ Tech Stack

-   **Core Language**: Java
-   **GUI Framework**: Java Swing
-   **Database**: MySQL
-   **Build Tool**: Apache Maven
-   **Database Connector**: MySQL Connector/J
-   **Custom UI Components**:
    -   [KGradientPanel](https://github.com/k33ptoo/KControls) & [KControls](https://github.com/k33ptoo/KControls) for gradient effects and modern components.
    -   [Custom Tabbed Pane](https://github.com/DJ-Raven/java-tabbed-custom) for an enhanced tab navigation.
-   **Core Java Libraries**:
    -   `java.time`: For precise date and time management.
    -   `javax.imageio.ImageIO`: For processing and converting images (from `BLOB` data type) from the database.

## 📋 Prerequisites

Before you begin, ensure your system meets the following requirements:

-   Java Development Kit (JDK) 17 or newer.
-   An active and running MySQL Server.
-   An IDE (Integrated Development Environment) that supports Maven, such as Apache NetBeans or IntelliJ IDEA.

## 🚀 Getting Started

Follow these steps to configure and run the project on your local machine.

1.  **Clone the Repository**
    Use `git` to download the project's source code.
    ```sh
    git clone [https://github.com/TWO-ONE-21/managementKasKelas.git](https://github.com/TWO-ONE-21/managementKasKelas.git)
    cd managementKasKelas
    ```

2.  **Database Setup**
    -   Ensure your MySQL service is running.
    -   Create a new database named `managementkas`.
        ```sql
        CREATE DATABASE managementkas;
        ```
    -   Import the schema and initial data from the provided SQL file (`managementkas.sql`). You can use a tool like phpMyAdmin or DBeaver, or run the following command in your terminal:
        ```sh
        mysql -u root -p managementkas < path/to/managementKasKelas/src/main/resource/managementkas.sql
        ```
    -   **Important:** Avoid hardcoding database credentials. Instead of editing them directly in the source code, create a file at `src/main/resources/config.properties` and fill in your connection details.
        ```properties
        # Example content for config.properties
        db.url=jdbc:mysql://localhost:3306/managementkas
        db.username=root
        db.password=your_secret_password
        ```
        This approach is significantly more secure and flexible.

3.  **Run the Application**
    -   Open the project in your preferred IDE (e.g., NetBeans or IntelliJ IDEA).
    -   The IDE will automatically download and manage the dependencies listed in the `pom.xml` file using Maven.
    -   Locate and run the main class: `com.mycompany.managementkaskelas.ManagementKasKelas`.

## 🗃️ Database Schema

The application uses two primary tables for data persistence.

-   `mahasiswa`: Stores fundamental student information.
    -   `nim` (Primary Key): Student ID Number.
    -   `nama`: Student's full name.
    -   `foto`: Profile picture (stored as `BLOB`).
    -   `total_pembayaran`: The number of weekly fees paid.
-   `pengeluaran`: Logs all expense transactions.
    -   `id` (Primary Key): Unique identifier for each expense.
    -   `jumlah`: The amount of money spent.
    -   `tanggal`: The date of the transaction.
    -   `tujuan`: A description of the expense.

> **Note on Design Reflection:** The current schema is functional. However, for future development, consider normalizing the database. For example, replacing the `total_pembayaran` column with a separate `payment_transactions` table to log each payment individually would improve data integrity and system scalability.

## 🚧 Limitations & Future Work

-   **Student Management**: The application currently lacks a feature to add or modify student data through the user interface. These operations must be performed directly in the database. As the number of students in a class is generally static, this feature was not deemed critical for the initial release.
-   **Development Roadmap**: The top priority for future development is to implement a full CRUD (Create, Read, Update, Delete) module for student data. This will make the application more self-contained and less dependent on direct database intervention.

## ⚖️ License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## 🧑‍💻 Author

-   **Ardo Rianda** - *Initial Work*

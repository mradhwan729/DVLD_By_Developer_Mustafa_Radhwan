# 🚗 Driving & Vehicle Licensing Department (DVLD) System

A comprehensive Desktop Enterprise Solution built to streamline and automate all operations of the **Driving & Vehicle Licensing Department**. The system covers the entire workflow from applicant intake, multi-tier test scheduling, and examination processing, to license issuance, renewals, replacements, and international license tracking.

---

## 🌟 Key Features & Functional Scope

* **Application Lifecycle Management:**
  * Complete workflow for Local Driving License Applications (LDL Apps) and International Licenses.
  * System-enforced status tracking (New, Cancelled, Completed).

* **Multi-Stage Test Engine & Scheduling:**
  * Support for sequential testing pipelines: **Vision Test ➔ Written Test ➔ Street Test**.
  * Dynamic retake test application handling with integrated fee calculations.
  * System-level constraints preventing duplicate active appointments, skipping required test prerequisites, or modifying locked/attended test sessions.

* **License & Fine Enforcement System:**
  * License issuance, renewal, replacement for damaged/lost licenses, and license detaining/releasing with fee collection workflows.

* **User & Security Management:**
  * Role-based user authentication, password management, user status flags (Active/Inactive), and global user session management.

* **Integrated People Directory:**
  * Centralized registry for personal profiles with photo management, age validation, and national ID uniqueness checks.

---

## 🛠️ Architecture & Core Skills Demonstrated

This project demonstrates strong software engineering practices, clean code design, and robust desktop application development:

### 📐 1. Multi-Tier System Architecture (3-Tier)
Built using a clear separation of concerns to maximize maintainability, scalability, and reusability:
* **Presentation Layer (UI):** Built with C# Windows Forms using a modular design approach with reusable custom `UserControls` (e.g., `ctrlScheduleTest`, `ctrlDrivingLicenseApplicationInfo`).
* **Business Logic Layer (BLL):** Object-Oriented C# classes wrapping business rules, validations, and state transitions.
* **Data Access Layer (DAL):** ADO.NET data access encapsulation providing direct, optimized interaction with SQL Server.

### 🧠 2. Advanced Object-Oriented Programming (OOP)
* **Design Patterns & Encapsulation:** Extensive use of static factory methods (e.g., `clsLocalDrivingLicenseApplications.Find()`), strong encapsulation, properties, custom Enums, and domain entities.
* **State & Lifecycle Control:** Robust state transitions managing complex business invariants across test attempts and application states.

### 🗄️ 3. Database Engineering & SQL Server
* Relational database design with Foreign Key integrity, indexing, joins, and aggregate tracking (e.g., test attempts count, pass/fail histories).
* Parameterized SQL queries using ADO.NET to guarantee execution safety and prevent SQL Injection attacks.

### 🛡️ 4. Exception Handling & Defensive Programming
* Comprehensive error-handling and defensive null checks across form boundaries, event loops, and control initialization.
* Event-driven data refreshment paradigms across parent forms and child modal dialogs (`ShowDialog()`).

---

## 💻 Tech Stack & Tools

* **Language:** C# (.NET Framework)
* **UI Technology:** Windows Forms (WinForms), Custom User Controls
* **Database:** Microsoft SQL Server
* **Data Access:** ADO.NET (`SqlConnection`, `SqlCommand`, `SqlDataReader`)
* **IDE:** Microsoft Visual Studio 2022
* **Version Control:** Git & GitHub

---

## 🚀 Getting Started

### Prerequisites
1. **Visual Studio 2022** (with .NET Desktop Development workload installed).
2. **Microsoft SQL Server** (LocalDB or SQL Express).

### Database Setup
1. Open SQL Server Management Studio (SSMS).
2. Execute the included database schema script (`DVLD.sql`) to create the database tables, constraints, and initial data.
3. Update the Connection String inside the Data Access Layer (`clsDataAccessSettings.cs`) to point to your local SQL Server instance:
   ```csharp
   public static string ConnectionString = "Server=.;Database=DVLD;Integrated Security=True;";

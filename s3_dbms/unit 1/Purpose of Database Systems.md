# Purpose of Database Systems

## 1. Introduction

Before the invention of DBMS, organizations stored data in **files and folders**.
This “file-based approach” worked fine when data was small (like a personal notepad). But as soon as data grew in size and multiple users needed access, **problems appeared**:

* Duplication of data
* Inconsistent updates
* Hard to search, modify, or secure
* No centralized control

To solve these issues, **Database Management Systems (DBMS)** were introduced.
The **purpose** of a database system is to provide a **structured, reliable, and secure** way to manage data for multiple users and applications.

---

## 2. Problems with File-Based Systems (Why DBMS is Needed)

Let’s imagine CodingGita stores student details in three separate files:

1. **Student\_Info.txt** – Roll No, Name, Phone
2. **Fee\_Record.txt** – Roll No, Fee Paid/Not Paid
3. **Exam\_Result.txt** – Roll No, Subject, Marks

### Problems:

1. **Data Redundancy (Duplication)**

   * The same Roll No and Name repeated in all files.
   * If Mahir changes his phone number, we must update in every file.

2. **Data Inconsistency**

   * If Mahir’s phone number is updated in one file but not in others, data becomes inconsistent.

3. **No Centralized Security**

   * Anyone with file access can read or change data.
   * Students could edit marks if files are unprotected.

4. **Difficult to Search & Retrieve**

   * Want all students with pending fees? You’d have to scan **all files manually**.

5. **Concurrency Issues**

   * Two admins trying to edit the same file at the same time may corrupt data.

6. **Backup & Recovery Problems**

   * If one file gets deleted, all related information may be lost.

👉 Clearly, file systems fail in large organizations like CodingGita with hundreds of students.

---

## 3. How Database Systems Solve These Problems

A DBMS introduces **organized storage with rules** that eliminate the above issues.

* **Redundancy Control:** Store data once in a table and reference it everywhere.
* **Consistency:** If Mahir’s phone number is updated, it is updated everywhere automatically.
* **Security:** Role-based access → students can view only their marks, faculty can update grades, admin can manage fees.
* **Efficient Search:** SQL queries can instantly fetch pending fees or top scorers.
* **Concurrency Control:** Multiple users can safely access/update data at once.
* **Backup & Recovery:** Automatic logs/checkpoints ensure no permanent loss.

---

## 4. Data Abstraction (Key Purpose of DBMS)

One of the **most important roles of DBMS** is to provide **data abstraction**.
Users should not worry about **how data is stored physically**; they should only focus on **what data they need**.

### Three Levels of Data Abstraction:

1. **Physical Level (Lowest)**

   * Describes how data is actually stored (files, indexes, disks).
   * Example: “Student records are stored in B+ trees on disk.”
   * **Users:** Database administrators (DBAs).

2. **Logical Level (Middle)**

   * Describes **what data is stored** and **what relationships exist**.
   * Example: Student table has attributes → RollNo, Name, Phone, CourseID.
   * **Users:** Database designers.

3. **View Level (Highest)**

   * Describes how users see the data.
   * Example:

     * Student sees only their marks.
     * Teacher sees marks of students in their subject.
     * Admin sees fees + exam results.
   * **Users:** End users.

---

## 5. Diagram – 3 Levels of Data Abstraction (Textual Representation)

```
+-------------------------------+
|        View Level             |
|  (User-specific views)        |
|  e.g., Student sees own marks |
+-------------------------------+
|        Logical Level          |
|  (Tables + Relationships)     |
|  e.g., Student table, Course  |
+-------------------------------+
|        Physical Level         |
|  (How data is stored)         |
|  e.g., Files, indexes, blocks |
+-------------------------------+
```

👉 This separation ensures **security, flexibility, and simplicity**.

---

## 6. Advantages of Database Systems

Now let’s summarize why DBMS is essential:

1. **Minimal Data Redundancy**

   * No repeated student info across multiple files.

2. **Data Consistency**

   * A single updated record reflects everywhere.

3. **Improved Data Sharing**

   * Different users (students, teachers, admin) access the same central data.

4. **Enhanced Security**

   * Controlled access (Role-based permissions).

5. **Backup & Recovery**

   * Automatic data recovery after crash or failure.

6. **Concurrency Control**

   * Multiple users can register for courses simultaneously without data corruption.

7. **Scalability**

   * Can handle growth from 100 students to 10,000 without system breakdown.

8. **Data Independence**

   * Applications do not need to change if physical storage changes.

---

## 7. Real-Life Examples (Purpose of DBMS in Action)

* **CodingGita Student Management System**

  * Students → view courses, marks, fees
  * Teachers → upload marks, assign grades
  * Admin → check fee status, generate reports

* **Banking System**

  * DBMS ensures if ₹500 is debited from Arjun’s account, it is **credited to Priyesha’s account at the same time**.

* **E-commerce (Amazon, Flipkart)**

  * Manages product inventory, customer orders, delivery tracking in a central database.

* **Social Media (Instagram, Facebook)**

  * Posts, likes, comments all stored in a scalable DBMS with high concurrency.

---

## 8. Summary

* File-based systems suffer from redundancy, inconsistency, poor security, and scalability issues.
* DBMS solves these problems by providing **centralized, consistent, secure, and scalable** data storage.
* **Data abstraction** (Physical, Logical, View) is a fundamental purpose of DBMS, allowing different users to see different levels of detail.
* Advantages of DBMS include **data consistency, concurrency control, backup & recovery, scalability, and security**.
* Real-world applications like **CodingGita, Banks, E-commerce, Social Media** rely heavily on DBMS.

---

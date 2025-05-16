# Course-Schedule
Course Scheduler Desktop Application

Course Scheduler is a Java Swing–based desktop application designed to manage academic schedules, semesters, courses, classes, and student enrollments. With a user-friendly tabbed interface and robust database integration, the application streamlines administrative tasks such as adding sessions, registering students, and tracking waitlists.

Features

Semester Management: Create and view academic terms.

Course & Class Definitions:

Define courses with codes and descriptions (CourseEntry, ClassDescription).

Offer specific class sections per semester with seat counts (ClassEntry).

Student Management:

Register students with IDs, first/last names.

Retrieve full student list for enrollment operations.

Enrollment Operations:

Enroll or drop students from classes; updates status (ScheduleEntry).

View scheduled students and waitlists by class (via MultiTableQueries).

Persistence Layer (DAO Pattern):

Encapsulated SQL operations in CourseQueries, ClassQueries, and MultiTableQueries.

Centralized JDBC connection management in DBConnection.

Swing GUI:

Tabbed panes for separate workflows (Add, View, Enroll, Drop).

Dynamic JTable models for displaying query results.

Utility Functions:

Base64 encoding/decoding for secure storage of credentials or tokens.

File I/O for import/export of configuration or logs.

Robust Error Handling:

Input validation and exception dialogs to guide users.
src/
├── model/
│   ├── ClassDescription.java   # Holds course code, description, seat count
│   ├── ClassEntry.java         # Section data: semester, course code, seats
│   ├── CourseEntry.java        # Course metadata: code and description
│   └── ScheduleEntry.java      # Enrollment record: timestamp, student, class, status
├── dao/
│   ├── ClassQueries.java       # SQL for class-related CRUD
│   ├── CourseQueries.java      # SQL for course-related CRUD
│   └── MultiTableQueries.java  # Joins across tables for reporting
│   └── StudentQueries.java     # SQL for student CRUD and retrieval
├── util/
│   └── DBConnection.java       # Singleton JDBC connection manager
└── ui/
    ├── MainFrame.java          # Entry point & Swing UI logic
    └── MainFrame.form          # NetBeans GUI form definitions

Technologies & Libraries

Java SE 8+: Core language features and collections.

Swing: GUI framework for desktop applications.

JDBC: Database connectivity via DriverManager and PreparedStatement.

NetBeans Form Editor: Visual layout for the UI components.

SQL: Schema design, normalization, multi-table joins.

Base64 & File I/O: Utility for encoding credentials and handling text files.

Setup & Usage

Prerequisites: Java JDK 8 or higher; relational database (e.g., MySQL, PostgreSQL).

Configure Database:

Edit DBConnection.java with your JDBC URL, username, and password.

Ensure tables exist: students, courses, classes, schedules—each matching the model fields.

Build & Run:

IDE: Import project into NetBeans/Eclipse; run MainFrame.

Command Line:

javac -d out src/**/*java
java -cp out ui.MainFrame

Skills & Techniques Learned

Object-Oriented Design: Designed clear data models and encapsulated behavior.

DAO Pattern & SQL Mastery: Abstracted database operations and wrote complex join queries.

Swing UI Development: Created responsive, event-driven interfaces with JTabbedPane and JTable.

Exception Handling & Validation: Implemented user-friendly error dialogs and robust input checks.

File I/O & Encoding: Managed file-based configurations and secure Base64 encoding.

Version Control: Structured commits for feature additions and bug fixes.

This application showcases a comprehensive Java desktop solution for academic scheduling and enrollment workflows.

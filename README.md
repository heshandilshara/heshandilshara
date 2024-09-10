- 👋 Hi, I’m @heshandilshara
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
heshandilshara/heshandilshara is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview 
Based on the requirements, I'll outline an ER (Entity-Relationship) diagram for your system. This will include entities for students, lecturers, technical officers, course units, exam marks, and attendance, as well as their relationships. Here's how you can structure the ER diagram:

Entities and Attributes
Student

StudentID (Primary Key)
FirstName
LastName
DateOfBirth
Email
Phone
Address
Lecturer

LecturerID (Primary Key)
FirstName
LastName
Email
Phone
Department
OfficeRoom
Technical Officer

TOID (Primary Key)
FirstName
LastName
Email
Phone
Department
OfficeRoom
CourseUnit

CourseCode (Primary Key)
CourseName
Credits
TheoryOrPractical (Theory/Practical)
LecturerID (Foreign Key referencing Lecturer)
ExamMarks

ExamID (Primary Key)
StudentID (Foreign Key referencing Student)
CourseCode (Foreign Key referencing CourseUnit)
QuizMarks
AssessmentMarks
MidSemesterTheoryMarks
MidSemesterPracticalMarks
FinalTheoryMarks
FinalPracticalMarks
Attendance

AttendanceID (Primary Key)
StudentID (Foreign Key referencing Student)
CourseCode (Foreign Key referencing CourseUnit)
Date
Status (Present/Absent)
User

UserID (Primary Key)
Username
Password
Role (Admin, Dean, Lecturer, Technical Officer, Student)
AssociatedID (ID of the associated entity: Admin, Dean, Lecturer, TO, Student)
Relationships
Student-CourseUnit

Many-to-Many relationship (a student can enroll in multiple courses, and a course can have multiple students)
Implemented via a join table (Enrollment)
Enrollment
EnrollmentID (Primary Key)
StudentID (Foreign Key referencing Student)
CourseCode (Foreign Key referencing CourseUnit)
Lecturer-CourseUnit

One-to-Many relationship (a lecturer can teach multiple courses, but each course is taught by only one lecturer)
Technical Officer-Attendance

Read, write, and update permissions are given for the attendance table to Technical Officers.
User Role Management

The User table manages the role-based access to various parts of the system.
Example ER Diagram
Here’s how you can visualize the ER diagram:

sql
Copy code
+--------------------+       +-------------------+
|    Student         |       |   Enrollment      |
|--------------------|       |-------------------|
| StudentID (PK)     |       | EnrollmentID (PK) |
| FirstName          |       | StudentID (FK)    |
| LastName           |       | CourseCode (FK)   |
| DateOfBirth        |       +-------------------+
| Email              |       
| Phone              |              
| Address            |
+--------------------+
         |
         | 1
         |
         | n
+--------------------+       +-------------------+
|   CourseUnit       |       |   ExamMarks       |
|--------------------|       |-------------------|
| CourseCode (PK)    |       | ExamID (PK)       |
| CourseName         |       | StudentID (FK)    |
| Credits            |       | CourseCode (FK)   |
| TheoryOrPractical  |       | QuizMarks         |
| LecturerID (FK)    |       | AssessmentMarks   |
+--------------------+       | MidSemesterTheoryMarks|
         |                 | MidSemesterPracticalMarks|
         | 1               | FinalTheoryMarks   |
         |                 | FinalPracticalMarks|
         | n               +-------------------+
         |
         | 1
+--------------------+
|   Lecturer         |
|--------------------|
| LecturerID (PK)    |
| FirstName          |
| LastName           |
| Email              |
| Phone              |
| Department         |
| OfficeRoom         |
+--------------------+

+--------------------+
|   Attendance       |
|--------------------|
| AttendanceID (PK)  |
| StudentID (FK)     |
| CourseCode (FK)    |
| Date               |
| Status             |
+--------------------+

+--------------------+
| Technical Officer  |
|--------------------|
| TOID (PK)          |
| FirstName          |
| LastName           |
| Email              |
| Phone              |
| Department         |
| OfficeRoom         |
+--------------------+

+--------------------+
|       User         |
|--------------------|
| UserID (PK)        |
| Username           |
| Password           |
| Role               |
| AssociatedID       |
+--------------------+
Notes:
Student-CourseUnit is a many-to-many relationship facilitated by the Enrollment table.
Lecturer-CourseUnit is a one-to-many relationship.
Technical Officer has special permissions on the Attendance table.
The User table centralizes user management and roles, linking to the other entities.
You can use a diagramming tool like Lucidchart, Draw.io, or Microsoft Visio to create a visual representation of this ER diagram[mini project.txt](https://github.com/user-attachments/files/16943322/mini.project.txt)
link to take a look at your changes.
--->

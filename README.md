
# **_Database Design Model for Zen Class Task_**

# **MySQL**

+ MySQL is an open-source Relational Database Management System (RDBMS) that enables users to store, manage, and retrieve structured data efficiently. 
+ It is widely used for various applications, from small-scale projects to large-scale websites and enterprise-level solutions.

# **_Database Design_**

+ Data consistency and integrity must be maintained.
+ Security measures should be taken by enforcing various integrity constraints. 
+ Data should be stored in fragmented bits of information in the most atomic format possible.
+ to achieve a good Database Design
  - Data consistency and integrity must be maintained.
  - Low Redundancy
  - Faster searching through indices
  - Security measures should be taken by enforcing various integrity constraints.
  - Data should be stored in fragmented bits of information in the most atomic format possible.

# **_Technology Used_**

+ MySQL

### **_To CREATE a TABLE Called Users_**

> CREATE TABLE Users (user_id INT PRIMARY KEY, 
username VARCHAR(50), 
email VARCHAR(50), 
phone_number INT, 
password VARCHAR(50) );

### **_To CREATE a TABLE Called Learners_**

> CREATE TABLE Learners ( learner_id INT PRIMARY KEY, 
user_id INT, 
first_name VARCHAR(50), 
last_name VARCHAR(50),
address VARCHAR(50), 
phone_number VARCHAR(15), 
FOREIGN KEY (user_id) REFERENCES Users (user_id));

### **_To CREATE a TABLE Called Mentors_**

> CREATE TABLE Mentors(mentor_id INT PRIMARY KEY, 
user_id INT, 
first_name VARCHAR(50), 
last_name VARCHAR(50),
address VARCHAR(50), 
phone_number VARCHAR(15), 
FOREIGN KEY (user_id) REFERENCES Users (user_id));

### **_To CREATE a TABLE Called Topics_**

> CREATE TABLE Topics(topic_id INT PRIMARY KEY, 
topic_name VARCHAR(50), 
topic_description TEXT, 
sessions INT,
mentor_id INT, 
FOREIGN KEY (mentor_id) REFERENCES Mentors (mentor_id));

### **_To CREATE a TABLE Called Tasks_**

> CREATE TABLE Tasks(task_id INT PRIMARY KEY, 
topic_id INT, 
task_name VARCHAR(50), 
task_description TEXT,
task_deadline DATE, 
FOREIGN KEY (topic_id) REFERENCES Topics (topic_id));

### **_To CREATE a TABLE Called Marks_**

> CREATE TABLE Marks(user_id INT, 
topic_id INT,
mark_status VARCHAR(10), 
FOREIGN KEY (topic_id) REFERENCES Topics (topic_id),
FOREIGN KEY (user_id) REFERENCES Users (user_id));


![Database Design-Table](<Database Design/Table.png>)
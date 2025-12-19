
# programstudent

![image-alt](https://github.com/mayankpra84-ai/programstudent/blob/e49fc27cfb69d55e2505e054f3986c7f58e06b76/How-to-set-up-GitHub-Continuous-Integration-pipelines-with-self-hosted-runners-on-Ubuntu-22-1.webp)

# Ritika
![image-alt](https://github.com/mayankpra84-ai/programstudent/blob/3e279aad5f0e740e5c51b1d97d1c7f1be935cbad/download.webp)

# Tanishka
The Face Recognition Based Attendance System is an automated attendance tracking application built using Python, Flask, OpenCV, and MySQL. Instead of taking attendance manually, this system uses advanced face recognition technology to identify students in real time through a webcam or camera feed and automatically logs their attendance in the database. This saves time, eliminates errors, and ensures a reliable attendance record.

The system provides a secure Admin Panel where administrators or teachers can manage student profiles, train the face recognition model, and review attendance records with intuitive dashboards and reports. The model is trained using the students’ face images, and every time a student appears in front of the camera, the system recognizes the face and marks them as present.

A key enhancement in this system is the Low Attendance Email Alert Feature. The system continuously calculates attendance percentages for all students and, if a student’s attendance falls below a predefined threshold (for example 75%), it automatically sends them an email warning about their low attendance. This email alert is generated using SMTP (such as Gmail or institutional email) and contains a personalized message that notifies the student about their current attendance percentage and urges them to improve before it affects their academic standing.

Administrators can configure the attendance threshold, schedule automatic checks, and view sent alerts within the admin dashboard. Overall, this project integrates computer vision for real-time recognition, backend logic for attendance management, and automated communication to improve student accountability, making it a comprehensive attendance solution for educational institutions.

# Jahnavi 

🤖 Face Recognition Module

Implements LBPH (Local Binary Pattern Histogram) algorithm for accurate and real-time face recognition

Uses Haar Cascade Classifier for efficient face detection

Attendance is marked only after continuous face detection for 7 seconds, ensuring authenticity and preventing false entries

📧 Email Notification System

Automatically sends an email notification to the student once attendance is successfully recorded

Helps students stay informed and provides instant confirmation of attendance

📌 Future Enhancements

🔐 Secure Authentication using password hashing and encryption

📊 Attendance Reports generation in CSV / Excel format

👥 Role-Based Access Control (Admin / Faculty / Student)

☁️ Cloud Deployment for scalability and remote acc
🎨 Enhanced User Interface for better usability and experience

# kashish

 
## 🗄️ Database Schema

The database is designed to manage **users**, **attendance records**, and **admin accounts**.  
It ensures data integrity and prevents duplicate attendance entries for the same user on the same day.

---

### 👤 Users Table (`users`)

Stores user registration and authentication details.

| Column Name | Data Type     | Key | Description                    |
|------------|--------------|-----|--------------------------------|
| rollno     | INT          | PK  | Unique roll number of the user |
| name       | VARCHAR(100) | —   | Full name of the user          |
| email      | VARCHAR(200) | —   | User email address             |
| password   | VARCHAR(100) | —   | User login password            |
| date       | DATE         | —   | User registration date         |

---

### 📅 Attendance Table (`atten`)

Stores daily attendance records of users.

| Column Name | Data Type     | Key | Description                              |
|------------|--------------|-----|------------------------------------------|
| rollno     | INT          | FK  | References `users.rollno`                |
| name       | VARCHAR(100) | —   | Name of the user                         |
| date       | DATE         | —   | Attendance date                           |

**Constraint:**  
- Each user can mark attendance **only once per day**  
- Attendance entries are **unique for (`rollno`, `date`)**

---

### 🔐 Admins Table (`admins`)

Stores administrator account details.

| Column Name | Data Type     | Key | Description                    |
|------------|--------------|-----|--------------------------------|
| username   | VARCHAR(100) | PK  | Unique admin username          |
| password   | VARCHAR(100) | —   | Admin login password           |
| email      | VARCHAR(200) | —   | Admin email address            |

---

### 🔗 Schema Relationships

- `atten.rollno` → `users.rollno`  
- A user can have **multiple attendance records on different dates**  
- **Duplicate attendance on the same date is not allowed**

---
#  Kashish & Tanishka

🧠 Attendance System - Working Flow
Step-by-Step Flow

🧑‍🎓 Student Registration & Dataset Collection

Student signs up.

Face dataset is captured for training.

🖥️ Model Training (Admin)

Admin trains the face recognition model using collected datasets.

📸 Camera Initialization (Admin)

Admin starts the camera for live recognition.

🔍 Face Detection & Recognition

System detects and recognizes faces in real-time.

⏱️ Attendance Marking

If face is recognized for 7 seconds, attendance is marked.

📧 Email Confirmation

Student receives confirmation email.

# Ritika

<<<<<<< HEAD
## 🛠 Technolgies Used

* Python
* Flask (Web Framework)
* OpenCV (Face Detection & Dataset Collection)
* MySQL (Database Management System)
* HTML (Web Page Structure)
* CSS (Page Styling)
* JavaScript (Client-side Scripting)
* SMTP (Gmail) (Email Notifications)
* MySQL Connector (Python–MySQL Connectivity)
* Schedule & Threading (Automated Background Tasks)

---

## 📂 Project Structure

attendance-system
- app.py                (Main Flask application)
- dataset/              (Collected face images)
- lbph_trained.yml      (Trained face recognition model)
- labels.pkl            (Label to RollNo mapping)
- templates/            (HTML files)
- static/               (CSS and JavaScript files)
- README.md             (Project documentation)

-----

# Saurabh singh kushwah

⚙️ Installation & Setup (Enhanced)

This section explains how to set up the Face Recognition Based Attendance System on a local machine for development and testing.

1️⃣ Clone the Repository

Clone the project source code from GitHub and navigate to the project directory:

git clone https://github.com/your-username/attendance-system.git
cd attendance-system

Note: Ensure Git is installed on your system.
Verify using: git --version

2️⃣ Create a Virtual Environment (Recommended)

Using a virtual environment prevents dependency conflicts and ensures a clean setup.

python -m venv venv


Activate the virtual environment:

Windows

venv\Scripts\activate


Linux / macOS

source venv/bin/activate


Skipping this step won’t break the project, but it’s bad practice.

3️⃣ Install Required Python Packages

Install all dependencies using pip:

pip install flask opencv-python opencv-contrib-python mysql-connector-python numpy schedule


Verify successful installation:

python -c "import cv2, flask, mysql.connector, numpy"


If no errors appear, dependencies are correctly installed.

4️⃣ Setup MySQL Database
Create Database

Login to MySQL and create the database:

CREATE DATABASE online_attendance;
USE online_attendance;

Create Required Tables
CREATE TABLE users (
    rollno INT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(200),
    password VARCHAR(100),
    date DATE
);

CREATE TABLE atten (
    rollno INT,
    name VARCHAR(100),
    date DATE
);

CREATE TABLE admins (
    username VARCHAR(100) PRIMARY KEY,
    password VARCHAR(100),
    email VARCHAR(200)
);


⚠️ Foreign keys and password hashing are intentionally omitted to keep the system simple for academic use.

5️⃣ Configure Database Credentials

Open app.py and update the MySQL connection details:

db = mysql.connector.connect(
    host="localhost",
    user="root",
    password="1234",
    database="online_attendance"
)


Ensure:

MySQL service is running

Credentials are correct

Port 3306 is open (default)

6️⃣ Configure Email (SMTP – Gmail)

The system uses Gmail SMTP to send attendance confirmation emails.

Steps to Enable Email Notifications

Enable 2-Step Verification in your Gmail account

Generate an App Password

Use the generated password in the email configuration function

Example:

EMAIL_ADDRESS = "your_email@gmail.com"
EMAIL_PASSWORD = "your_app_password"


❗ Never hard-code real passwords in public repositories.

7️⃣ Dataset Directory Structure

Ensure the dataset folder exists:

dataset/
├── 101/
│   ├── img1.jpg
│   ├── img2.jpg
├── 102/


Each folder represents a student roll number.

▶️ Running the Application
Start the Flask Server

Run the application using:

python app.py


If everything is configured correctly, you should see:

Running on http://127.0.0.1:5000/

Access the Web Application

Open a browser and navigate to:

http://127.0.0.1:5000/

✅ Post-Setup Checklist

Before using the system, confirm:

✔ Camera is connected and accessible
✔ MySQL server is running
✔ Dataset folders exist
✔ LBPH model is trained
✔ Email credentials are valid
s
⚠️ Common Issues & Fixes
Issue	Cause	Solution
Camera not opening	Webcam busy	Close other camera apps
Email not sent	App password incorrect	Regenerate Gmail App Password
Face not recognized	Poor dataset	Capture clearer images
Database error	Wrong credentials	Recheck MySQL config

>>>>>>> 0e77b90 (saurabh modifyREADME)

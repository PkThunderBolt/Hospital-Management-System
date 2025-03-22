# Hospital Management System 🏥  

A **Java-based console application** for managing hospital operations, including **patient registration, doctor management, and appointment booking**. The system uses **MySQL as the database** and connects via **JDBC** for data storage and retrieval.

## 📌 Features  

- **Patient Management** 🏥  
  - Add new patients with details (Name, Age, Gender).  
  - View all registered patients.  

- **Doctor Management** 👨‍⚕️  
  - View the list of available doctors and their specializations.  
  - Fetch doctor details by ID.  

- **Appointment Booking** 📅  
  - Patients can book an appointment with a doctor.  
  - Checks doctor availability before scheduling an appointment.  

## 🛠️ Technologies Used  

- **Java** (Core Java, OOPs)  
- **MySQL** (Database)  
- **JDBC** (Database connectivity)  

## 📂 Project Structure  

HospitalManagementSystem/
│── src/
│   ├── HospitalManagementSystem.java   # Main program
│   ├── Doctor.java                     # Doctor management
│   ├── Patient.java                    # Patient management
│── hospital_db.sql                      # Database schema
│── README.md                            # Project documentation
│── pom.xml (if using Maven)             
└── .gitignore                           



## 💾 Database Schema  

```sql
CREATE TABLE patients (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100),
    age INT,
    gender VARCHAR(10)
);

CREATE TABLE doctors (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100),
    specialization VARCHAR(100)
);

CREATE TABLE appointments (
    id INT PRIMARY KEY AUTO_INCREMENT,
    patient_id INT,
    doctor_id INT,
    appointment_date DATE,
    FOREIGN KEY (patient_id) REFERENCES patients(id),
    FOREIGN KEY (doctor_id) REFERENCES doctors(id)
);



# Al-Awad Dating App

## Overview

**Al-Awad Dating App** is designed to revolutionize the dating experience within the Islamic community by prioritizing acceptance, user experience, and safety. The project combines meticulous planning, robust database design, and a user-friendly web interface to deliver a trusted platform for meaningful connections. Key features include precise matchmaking, strong privacy and security, and a business model tailored to the Islamic market through subscription-based services[1].

---

## Table of Contents

- [Features](#features)
- [System Architecture](#system-architecture)
- [Getting Started](#getting-started)
- [Database Design](#database-design)
- [Data Collection & Preprocessing](#data-collection--preprocessing)
- [Usage](#usage)
- [Business and Operational Requirements](#business-and-operational-requirements)
- [Troubleshooting](#troubleshooting)

---

## Features

- **User Registration & Authentication:** Secure sign-up and login.
- **Profile Creation:** Users can create detailed profiles with preferences.
- **Advanced Matchmaking:** Algorithms for precise, values-based matching.
- **Communication:** Messaging features for matched users.
- **Privacy & Security:** Robust controls to protect user data.
- **Subscription Model:** Revenue generation through premium features.
- **Continuous Improvement:** Feedback-driven updates.

---

## System Architecture

- **Frontend:** User-friendly website interface for registration, profile management, matchmaking, and communication.
- **Backend:** Robust server handling authentication, matchmaking logic, and messaging.
- **Database:** Structured relational database designed with SQL for efficient storage and retrieval of user and interaction data.
- **Data Collection:** Google Forms used for initial user data gathering and requirements analysis[1].

---

## Getting Started

### Prerequisites

- Python 3.8+ (for backend scripts)
- Node.js & npm (if frontend uses a JavaScript framework)
- SQL database (e.g., MySQL or PostgreSQL)
- Git

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/MariamAsall/Al-Awad_App.git
   cd Al-Awad_App
   ```

2. **Set up the backend environment:**
   - Install dependencies:
     ```bash
     pip install -r requirements.txt
     ```
   - Configure database connection in `config.py` or `.env` as needed.

3. **Set up the frontend (if applicable):**
   - Navigate to the frontend directory and install dependencies:
     ```bash
     cd frontend
     npm install
     ```

4. **Initialize the database:**
   - Run provided SQL scripts to create tables and relationships.

---

## Database Design

- **Schema:** Built using SQL, designed for scalability and privacy.
- **Key Tables:**
  - `users`: Stores profile and authentication data.
  - `preferences`: User preferences for matchmaking.
  - `matches`: Records successful matches.
  - `messages`: Stores user communications.
- **Design Process:** ER diagrams and normalization to ensure data integrity and efficiency[1].

---

## Data Collection & Preprocessing

- **Collection:** Initial user and requirement data gathered via Google Forms.
- **Cleaning:** Data cleaned for duplicates, missing values, and inconsistencies.
- **Preprocessing:** Data formatted and normalized before being imported into the SQL database for use by the app backend[1].

---

## Usage

1. **Register:** New users sign up and verify their accounts.
2. **Create Profile:** Fill in personal details, preferences, and upload a profile photo.
3. **Matchmaking:** The app suggests matches based on preferences and compatibility algorithms.
4. **Connect:** Users can message matches within the platform.
5. **Subscription:** Access premium features via subscription (if enabled).

---

## Business and Operational Requirements

- **Market Focus:** Tailored for the Islamic community, respecting cultural and religious values.
- **Revenue Model:** Subscription-based, with potential for premium features.
- **Stakeholder Needs:** User-friendly interface, robust security, privacy controls, and reliable performance.
- **Continuous Feedback:** Mechanisms for user feedback and iterative improvement[1].

---

## Troubleshooting

- **Database Connection Errors:** Ensure credentials in config files match your local database setup.
- **Dependency Issues:** Run `pip install -r requirements.txt` or `npm install` in the correct directories.
- **Frontend/Backend Communication:** Check API endpoints and CORS settings if the frontend cannot reach the backend.
- **Data Import:** Verify that CSV/SQL files match the expected schema before importing.

---

## Sample SQL Table Creation

```sql
CREATE TABLE users (
    id INT PRIMARY KEY AUTO_INCREMENT,
    username VARCHAR(50) UNIQUE NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    password_hash VARCHAR(255) NOT NULL,
    gender VARCHAR(10),
    age INT,
    location VARCHAR(100),
    religious_level VARCHAR(50),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE preferences (
    user_id INT,
    preferred_gender VARCHAR(10),
    min_age INT,
    max_age INT,
    location VARCHAR(100),
    FOREIGN KEY (user_id) REFERENCES users(id)
);

CREATE TABLE matches (
    id INT PRIMARY KEY AUTO_INCREMENT,
    user1_id INT,
    user2_id INT,
    matched_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (user1_id) REFERENCES users(id),
    FOREIGN KEY (user2_id) REFERENCES users(id)
);

CREATE TABLE messages (
    id INT PRIMARY KEY AUTO_INCREMENT,
    match_id INT,
    sender_id INT,
    message TEXT,
    sent_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (match_id) REFERENCES matches(id),
    FOREIGN KEY (sender_id) REFERENCES users(id)
);
```

---

## Sample User Flow

1. **User Registration:**  
   User signs up, verifies email, and completes profile.
2. **Profile Creation:**  
   User sets preferences and uploads a photo.
3. **Matching:**  
   Algorithm suggests matches based on preferences and mutual compatibility.
4. **Messaging:**  
   Once matched, users can communicate securely within the app.
5. **Subscription:**  
   Users can upgrade for additional features.

---

## Sample Results

- **User Growth:** 500+ initial sign-ups via Google Forms.
- **Match Success Rate:** 70% of active users matched within first month.
- **User Feedback:** High satisfaction with privacy and culture-sensitive features.

---

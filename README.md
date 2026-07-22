# InnovateIQ Backend & Administration Control Desk

InnovateIQ Backend is a dynamic PHP RESTful API and Web Administration Portal designed to manage candidate registrations and Campus Ambassador programs in real time. Built using a clean **Controller-Service-Repository** architectural pattern, it connects directly to a MySQL database to serve dynamic analytics, status tracking, and participant dossier management.

---

## 🌟 Key Features

- **Student Registration Management**: Full CRUD operations for managing participant profiles across 40 database columns.
- **Campus Ambassador Console**: Complete tracking for Campus Ambassadors, including referral metrics, institution breakdowns, and onboarding statuses.
- **Dynamic Analytics & Metrics**:
  - Live candidate signups count and custom date-range filtering.
  - Automatic calculation of **Verification Rates** (excluding rejected applicants).
  - Dynamic **Popular Track** and program distribution breakdown with max-height scrollable containers.
  - Pan-India college count and referral metrics aggregation.
- **Robust Error & Configuration Handling**:
  - Internal PDO connection exception catching to prevent fatal PHP crashes.
  - Unconditional `.env` file override parser to resolve web server configuration conflicts.
- **Modern UI Dashboards**: Styled with Tailwind CSS, Chart.js trend visualizations, and Vanta.js dynamic animated backgrounds.

---

## 🛠️ Technology Stack

- **Backend**: PHP 8.x (Vanilla PHP using OOP Architecture: Controllers, Services, Repositories, Helpers)
- **Database**: MySQL (PDO Driver)
- **Frontend**: HTML5, Vanilla JavaScript (Async/Await Fetch API), Tailwind CSS, Chart.js, FontAwesome
- **Environment**: Apache / XAMPP / PHP Built-in CLI Server

---

## 📁 Project Structure

```text
InnovateIQ-Backend/
├── app/
│   ├── config/
│   │   └── database.php             # PDO Connection & Exception handling
│   ├── controllers/
│   │   ├── RegistrationController.php
│   │   ├── CampusAmbassadorController.php
│   │   ├── DashboardController.php
│   │   └── AuthController.php
│   ├── repositories/
│   │   ├── RegistrationRepository.php
│   │   └── CampusAmbassadorRepository.php
│   ├── services/
│   │   ├── RegistrationService.php
│   │   └── CampusAmbassadorService.php
│   └── helpers/
│       └── Response.php             # JSON HTTP Response wrapper
├── public/
│   ├── index.php                    # Front Controller & .env Parser
│   ├── login.html                   # Admin Authentication Page
│   ├── registrations_dashboard_admin.html # Student Registration Control Desk
│   ├── campus_ambassador_admin.html # Campus Ambassador Console
│   └── registration.html           # Public Candidate Registration Form
├── routes/
│   ├── api.php                      # REST API Endpoint Routing
│   └── web.php                      # Web Interface Page Routing
├── .env                             # Environment Variables
├── database.sql                     # Database Schema SQL Export
└── README.md                        # Documentation

⚙️ Installation & Local Setup
1. Clone & Place Project
Place the project folder inside your web server root (e.g., d:/xampp/htdocs/InnovateIQ-Backend).

2. Configure Environment (.env)
Create or verify the .env file in the root directory:

ini


DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=innovate_iq_db
DB_USERNAME=root
DB_PASSWORD=
3. Database Setup
Import database.sql into MySQL using phpMyAdmin or the MySQL Command Line:

bash


mysql -u root -p -e "CREATE DATABASE IF NOT EXISTS innovate_iq_db;"
mysql -u root -p innovate_iq_db < database.sql
4. Running the Application
Option A: Via XAMPP (Apache)
Open your browser and navigate to:

text


http://localhost/InnovateIQ-Backend/public/registrations_dashboard_admin.html
Option B: Via PHP Built-in Server
Run the following command from the project root:

bash


php -S localhost:8000 -t public
Then visit: http://localhost:8000/registrations_dashboard_admin.html

📡 API Endpoints Reference
All API requests accept and return JSON formatted payloads (Content-Type: application/json).

1. Student Registrations APIs
Method	Endpoint	Description
GET	/api/registrations	Fetch all student registrations
POST	/api/register	Register a new student candidate
POST	/api/registrations/update-status	Update candidate status (Pending, Approved, Rejected)
POST	/api/registrations/update	Update candidate profile details
Payload Example: Update Student Status
json


{
  "registration_code": "REG-2026-0015",
  "academic_status": "Approved"
}
2. Campus Ambassador APIs
Method	Endpoint	Description
GET	/api/ambassadors	Fetch all campus ambassador registrations
POST	/api/ambassadors/register	Register a new campus ambassador
POST	/api/ambassadors/update-status	Update ambassador application status
POST	/api/ambassadors/update	Update ambassador profile details
Payload Example: Register Campus Ambassador
json


{
  "full_name": "Venkatesh Prasad",
  "gender": "Male",
  "date_of_birth": "2004-09-18",
  "mobile_number": "8877665544",
  "email_address": "venkat.p@example.com",
  "residential_address": "Hyderabad, Telangana",
  "college_name": "VNR VJIET",
  "course_name": "B.Tech",
  "branch_specialization": "IT",
  "year_of_study": "3rd Year",
  "declaration_accepted": 1
}


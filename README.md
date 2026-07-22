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

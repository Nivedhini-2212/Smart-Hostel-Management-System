🏠 Hostel Management System
A full-stack web application for managing hostel operations, developed as a Software Engineering mini project. It provides separate access for Administrators, Wardens, and Students, using a React frontend, Node.js/Express backend, and MySQL database.

✨ Features
- JWT-based login and role-based authorization for Admin, Warden, and Student accounts
- Separate Admin, Warden, and Student dashboards
- Student, hostel, room, and bed management
- Room/bed allocation and bed availability updates
- Fee management and payment-status tracking
- Complaint submission and status management
- Leave request submission and approval/rejection
- Visitor record management
- Notice management, with read-only access for students
- Protected backend APIs and student-specific data filtering


🧰 Technology Stack
Layer	Technologies
Frontend	React, Vite, JavaScript, CSS, Lucide React
Backend	Node.js, Express.js
Database	MySQL 8
Authentication	JSON Web Tokens (JWT)
Database driver	MySQL2
Other packages	bcryptjs, CORS, dotenv


🏗️ Architecture
Frontend (React + Vite)
          |
       REST API
          |
Backend (Node.js + Express)
 Authentication + Authorization
          |
      SQL queries
          |
     MySQL Database

👥 User Roles
Administrator
- Manage students, hostels, rooms, and beds
- Manage allocations, fees, complaints, leave requests, visitors, and notices
- View dashboard statistics
Warden
- Manage day-to-day hostel activities
- Handle allocations, fees, complaints, leave requests, visitors, and notices
- View hostel-related statistics
Student
- View personal profile and allocation
- View own fee records
- Submit and view own complaints and leave requests
- Access own visitor records according to the implemented workflow
- View notices
- Cannot access administrative modules or perform staff-only actions

🗃️ Database
Database name: hostel_management
Tables:
- users
- students
- hostels
- rooms
- beds
- room_allocations
- fees
- complaints
- leave_requests
- visitors
- notices
These tables store user accounts, student details, hostel/room/bed information, allocations, fee records, complaints, leave requests, visitor details, and notices.

📁 Project Structure
Hostel-Management-System/
├── backend/
│   ├── config/
│   │   └── db.js
│   ├── middleware/
│   │   └── authMiddleware.js
│   ├── routes/
│   ├── controllers/
│   ├── package.json
│   └── server.js
├── database/
│   ├── schema.sql
│   └── sample_data.sql
├── Documentation/
│   ├── 01_Project_Overview.docx
│   ├── 02_SRS.docx
│   ├── 03_Database_Design.docx
│   └── 04_ER_Diagram/
└── frontend/
    └── Hostel-Management-System-frontend/
        ├── src/
        ├── package.json
        ├── index.html
        └── README.md
Your local folder/file names may vary slightly. Verify the structure before uploading the repository.

🚀 Getting Started
Prerequisites
- Node.js and npm
- MySQL Server
- MySQL Workbench
- A modern web browser
1. Clone the repository
Replace YOUR-USERNAME with your GitHub username and adjust the repository URL if needed.
git clone https://github.com/YOUR-USERNAME/Hostel-Management-System.git
cd Hostel-Management-System
2. Create and populate the database
In MySQL Workbench, run:
CREATE DATABASE hostel_management;
Then execute/import the SQL files from the database/ directory, if included. Ensure the schema and sample data are loaded before starting the application.
3. Configure the database connection
Open backend/config/db.js and configure your local MySQL connection. Keep your real password private.
Example configuration:
const mysql = require('mysql2');

const db = mysql.createPool({
    host: 'localhost',
    user: 'root',
    password: process.env.DB_PASSWORD,
    database: 'hostel_management',
    waitForConnections: true,
    connectionLimit: 10,
    queueLimit: 0
});

module.exports = db;
Preserve the connection logic used in your project and adapt the configuration as required. If using environment variables, create a local .env file and ensure it is listed in .gitignore.
Never upload real database passwords, JWT secrets, or private credentials to GitHub.
4. Install and start the backend
From the repository root:
cd backend
npm install
node server.js
The backend should run at:
http://localhost:5000
5. Install and start the frontend
Open a second terminal from the repository root:
cd frontend/Hostel-Management-System-frontend
npm install
npm run dev
Vite normally displays a local address such as:
http://localhost:5173
Open that address in your browser. Keep both terminals running while using the application.

🔐 Security Notes
- Authentication uses JWT tokens.
- Protected backend routes verify tokens and user roles.
- Student-facing APIs filter records by the authenticated student's identity where implemented.
- Frontend navigation restrictions are supported by backend authorization.
- Demo accounts, if included in sample data, are for local development only.
- Before real deployment, use strong passwords, environment variables, HTTPS, secure token-secret management, and production security practices.

🧪 Current Project Status
Implemented
- React frontend and Express backend
- MySQL database integration
- JWT-based login
- Admin, Warden, and Student roles
- Separate dashboards
- CRUD operations for major hostel modules
- Student-specific access restrictions
- Allocation and bed-availability workflow
- Fee, complaint, leave, visitor, and notice management

🔮 Future Developments
The following are planned enhancements and are not claimed as completed features:
- Online fee payment gateway and digital receipts
- Email/SMS notifications for fees, leave, complaints, and notices
- Advanced search, filtering, and sorting
- Occupancy analytics and visual reports
- Automated room/bed allocation based on availability and preferences
- QR-code visitor passes and verification
- Maintenance request and tracking module
- Mess management, menu, and food feedback
- Hostel attendance and out-pass tracking
- Downloadable PDF/Excel reports
- Forgot-password and email/OTP-based password reset
- Database backups and audit logs
- Cloud deployment and production configuration
- Further mobile-responsive improvements or a dedicated mobile app

🎯 Learning Outcomes
This project demonstrates practical application of:
- Full-stack web development
- Relational database design
- REST API development
- Authentication and role-based authorization
- CRUD operations
- Multi-role application design
- Frontend, backend, and database integration

🤝 Contributing
This is an academic project. Suggestions and improvements are welcome. To contribute, fork the repository, create a feature branch, and submit a pull request.

📄 License
Developed for academic and educational purposes. Add a license file if you intend to distribute it under a specific open-source license.

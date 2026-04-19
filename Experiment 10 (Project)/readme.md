# 🚗 Vehicle Service Booking System

> A scalable microservices-based vehicle service booking platform with secure authentication, booking management, and email-based password recovery.

---

## 🌟 Features

### 👤 User
- Secure Registration & Login (JWT based)
- Book vehicle services
- View & manage bookings
- Forgot Password (Email reset link)

### 🔧 Mechanic
- View assigned services
- Update service status
- Manage availability

### 🛠️ Admin
- Manage users & services
- Monitor bookings & reports

### 🔐 Security
- JWT Authentication
- Role-Based Access Control (RBAC)
- Password hashing (BCrypt)
- Secure password reset (Token-based)

---

## 🏗️ Architecture

- Microservices Architecture
- API Gateway (Routing + Security + Load Balancing)
- Services:
  - User Service
  - Customer Service
  - Mechanic Service
  - Admin Service
  - Forgot Password Service
- SMTP Email Integration

---

## 📊 System Flow

User → API Gateway → Services → Database

Key Flows:
- Login → JWT Token
- Booking → Customer Service → Database
- Mechanic Assignment → Mechanic Service
- Forgot Password → Email → Reset

---

## 🧱 Tech Stack

Frontend: React.js / Tailwind CSS  
Backend: Spring Boot (Java)  
Database: MySQL  
Authentication: JWT  
Email: SMTP (Gmail / SendGrid)  
Architecture: Microservices  

---

## 🔌 API Endpoints

Auth APIs:
POST /api/auth/register  
POST /api/auth/login  
POST /api/auth/forgot-password  
POST /api/auth/reset-password  

Booking APIs:
POST /api/bookings/create  
GET /api/bookings/user/{id}  
DELETE /api/bookings/{id}  

Mechanic APIs:
GET /api/mechanic/requests  
PUT /api/mechanic/update-status/{id}  
GET /api/mechanic/availability  

Admin APIs:
GET /api/admin/users  
POST /api/admin/services  
DELETE /api/admin/users/{id}  
GET /api/admin/reports  

---

## 🗄️ Database Design

User:
- user_id (PK)
- name
- email (unique)
- password (hashed)
- role (USER / ADMIN / MECHANIC)
- created_at

Booking:
- booking_id (PK)
- user_id (FK)
- mechanic_id (FK)
- service_type
- status (Pending / In Progress / Completed)
- booking_date

Mechanic:
- mechanic_id (PK)
- name
- email
- availability (Available / Busy)

Service:
- service_id (PK)
- service_name
- price
- description

Password Reset:
- token (PK)
- user_id (FK)
- expiry_time
- used (true/false)

---

## 🔒 Security Features

- JWT-based authentication
- Role-based authorization
- Token expiry for password reset
- Encrypted password storage (BCrypt)
- HTTPS communication

---

## ⚡ Performance & Scalability

- API Gateway Load Balancing
- Independent Microservice Scaling
- Optimized database queries
- Fast response time (< 2 seconds)

---

## 📧 Forgot Password Flow

User → Request Reset → Token Generated → Email Sent → Reset Password

- Secure token (JWT/UUID)
- Expiry-based validation (15–30 minutes)
- One-time use token

---

## 🚀 How to Run

Backend (Spring Boot):
mvn clean install  
mvn spring-boot:run  

Frontend:
npm install  
npm run dev  

---

## 📌 Future Enhancements

- Real-time notifications  
- Payment Integration  
- Live tracking of mechanics  
- AI-based service recommendations  

---

## 🤝 Contributing

Pull requests are welcome. For major changes, open an issue first.

---

## 📜 License

MIT License

---

## 👨‍💻 Author

Prabhakar Kumar Jha  
Chandigarh University  

---

## ⭐ Support

If you like this project, give it a ⭐ on GitHub!

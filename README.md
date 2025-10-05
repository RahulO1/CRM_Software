# 🗂️ CRM Software

A secure and scalable **full-stack Customer Relationship Management (CRM) system** built with:

- **Backend:** Java (Spring Boot)
- **Frontend:** React.js
- **Database:** MySQL
- **Authentication:** JWT + Spring Security

This system allows **Admins** and **Sales Reps** to manage customers, leads, tasks, and sales pipelines with **role-based access control**.

---

## 🚀 Features

### 🔑 User Management & Authentication
- Register new users (Admin / Sales)
- Login with JWT token authentication
- Role-based API restrictions with Spring Security
- User profile retrieval (`/api/users/me`)
- React frontend stores JWT in `localStorage`

### 👥 Customer Management
- CRUD operations for customers
- Fields: name, email, phone, company, address, assigned sales rep, notes

### 🧲 Lead Management
- Manage and track leads
- Lead attributes: name, contact info, source (Referral, Ads, Web), status (New, Contacted, Converted, Lost)

### ✅ Task Management
- Create and manage tasks
- Task details: title, description, due date, priority, assigned user, status (Open, In Progress, Completed)

### 💰 Sales Management
- Track deals and pipeline stages
- Sales attributes: customer, amount, status (Proposal, Negotiation, Closed-Won, Closed-Lost), assigned sales rep

### 🛡️ Security
- JWT-based authentication
- Spring Security for role-based access
- Protected React routes with React Router

---

## 🗄️ Database Schema (MySQL)

**Tables:**
- `users`
- `customers`
- `leads`
- `tasks`
- `sales`

**Relationships:**
- A sales rep can be assigned to leads, customers, tasks, and sales.
- Sales are linked to customers.

---

## 📡 API Endpoints (Sample)

### Authentication
- `POST /api/register` → Register a new user
- `POST /api/login` → Authenticate and return JWT
- `GET /api/users/me` → Fetch logged-in user profile

### Customers
- `GET /api/customers`
- `GET /api/customers/{id}`
- `POST /api/customers`
- `PUT /api/customers/{id}`
- `DELETE /api/customers/{id}`

(Similar CRUD endpoints exist for **Leads**, **Tasks**, and **Sales**.)

---

## 🖥️ Frontend (React.js)
- Login & Registration pages
- Dashboard: overview of sales, leads, and tasks
- Customers page (list, add, edit, delete)
- Leads page (filter by status, assign to sales rep)
- Tasks page (view my tasks, assign tasks, mark as completed)
- Sales page (track deals, update status)
- Role-based rendering (Admin vs Sales Rep views)

---

## 🏗️ Project Structure

### Backend (Spring Boot)
crm-backend/
- ├── controller/
- ├── service/
- ├── repository/
- ├── model/
- ├── security/
- ├── dto/
- └── application.properties

### Frontend (React)
crm-frontend/
- ├── src/
- │ ├── components/
- │ ├── pages/
- │ ├── services/ # Axios API calls
- │ ├── utils/
- │ └── App.js


---

## 📅 Project Timeline (4 Weeks)

| Week | Backend | Frontend |
|------|---------|-----------|
| 1 | User Auth + JWT + DB setup | Login / Register pages |
| 2 | CRUD for Customers & Leads | Customer & Lead pages |
| 3 | Tasks & Sales Modules | Task & Sales pages |
| 4 | Swagger, Pagination, Tests | Dashboard, UX, Final Polish |

---

## 📖 API Documentation
- **Swagger/OpenAPI** auto-generated documentation available at:  
  [http://localhost:8080/swagger-ui.html](http://localhost:8080/swagger-ui.html)

---

## 🧪 Testing
- **Backend:** JUnit + Mockito
- **API Testing:** Postman / Swagger UI
- **Frontend:** Manual testing (Jest optional)

---

## 🎁 Deliverables
- Complete source code (frontend + backend)
- Postman Collection for API testing
- Swagger API docs
- Fully running full-stack CRM system
- GitHub repository

---

## 🌟 Optional Enhancements
- Task notifications
- Email follow-ups
- Export reports (CSV, PDF)
- Dark mode toggle
- Dashboard charts (sales stats)

---

## ⚙️ How to Run

### Backend
```bash
cd crm-backend
mvn spring-boot:run

cd crm-frontend
npm install
npm start

docker run --name crm-mysql \
  -e MYSQL_ROOT_PASSWORD=root \
  -e MYSQL_DATABASE=crm \
  -e MYSQL_USER=crm_user \
  -e MYSQL_PASSWORD=crm_pass \
  -p 3306:3306 -d mysql:8

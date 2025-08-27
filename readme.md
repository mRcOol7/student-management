# Student Management System (CRUD Web Application)

A simple **Student Management System** built with **Spring Boot (Java 17+)**, **MySQL**, **React.js**, and **Tailwind CSS**.  
This project demonstrates **CRUD operations** (Create, Read, Update, Delete) and deployment on **Google App Engine (Standard, Java)**.

---

## 🛠 Technology Stack

| Layer          | Technology / Tools                     |
|----------------|---------------------------------------|
| Backend        | Java 17+, Spring Boot, Spring Data JPA|
| Frontend       | React.js, HTML, Tailwind CSS           |
| Database       | MySQL, MySQL Workbench                 |
| Deployment     | Google App Engine (Standard, Java)    |
| Development IDE| VS Code (with optional GitHub Copilot) |

---

## 📂 Project Structure

```
student-crud/
├─ backend/        # Spring Boot backend
│  ├─ src/main/java/com/example/studentapi/
│  │   ├─ model/       # Student entity
│  │   ├─ repo/        # Spring Data repository
│  │   └─ web/         # REST API controllers
│  ├─ src/main/resources/
│  │   └─ application.properties # DB & server config
│  └─ pom.xml         # Maven dependencies
├─ frontend/       # React.js frontend
│  ├─ src/
│  │   └─ App.jsx    # Main UI
│  ├─ index.html
│  ├─ package.json
│  └─ tailwind.config.js
└─ README.md       # Project documentation
```

---

## ⚙️ Setup Instructions

### 1️⃣ Backend (Spring Boot)

1. Open terminal in `backend/` folder.
2. Configure **MySQL** in `application.properties`:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/sms?useSSL=false&serverTimezone=UTC
spring.datasource.username=sms_user
spring.datasource.password=sms_pass
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
server.port=8080
```

3. Run the backend:
```bash
mvn spring-boot:run
```
4. Test APIs (Postman / cURL):
```bash
# Create student
POST http://localhost:8080/api/students
Body: { "name": "Asha", "email": "asha@example.com", "course": "Math" }

# Get all students
GET http://localhost:8080/api/students
```

---

### 2️⃣ Frontend (React + Tailwind)

1. Open terminal in `frontend/` folder.
2. Install dependencies:
```bash
npm install
```
3. Start frontend development server:
```bash
npm run dev
```
4. Open browser at `http://localhost:5173` to see the app.  
5. Use the form to **Add students**, view table, and delete entries.

---

### 3️⃣ Deployment (Google App Engine)

1. Build the backend JAR:
```bash
cd backend
mvn -DskipTests package
```
2. Copy `target/student-api-0.0.1-SNAPSHOT.jar` to `backend/` folder (next to `app.yaml`).
3. Create `app.yaml` in `backend/`:

```yaml
runtime: java21  # or java17
env: standard
entrypoint: 'java -jar student-api-0.0.1-SNAPSHOT.jar'
```
4. Initialize Google Cloud SDK & App Engine:
```bash
gcloud auth login
gcloud config set project YOUR_GCP_PROJECT_ID
gcloud app create --region=asia-south1
```
5. Deploy backend:
```bash
gcloud app deploy app.yaml
```
6. Open deployed app:
```bash
gcloud app browse
```

> **Optional:** Use **Cloud SQL (MySQL)** for production database instead of local MySQL.

---

## ✅ Features

- Add new students
- View list of students
- Update student information
- Delete students
- Responsive UI with Tailwind CSS
- RESTful API powered by Spring Boot
- Full CRUD with MySQL database

---

## 📸 Screenshots

![Add Student](screenshots/add_student.png)  
![Student List](screenshots/student_list.png)

---

## 🔗 References & Resources

- [Spring Boot Guide](https://spring.io/guides)  
- [Google App Engine Java Docs](https://cloud.google.com/appengine/docs/standard/java)  
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)  
- [React.js Documentation](https://react.dev/learn)  
- [MySQL Workbench](https://www.mysql.com/products/workbench/)

---

## 💡 Notes

- Backend runs on **http://localhost:8080**  
- Frontend runs on **http://localhost:5173**  
- Make sure both backend and frontend servers are running together for full functionality.

---

## 📦 Submission

- GitHub repository link: `[Add your repo URL here]`  
- Or zip the project folder and submit.


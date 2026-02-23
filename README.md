🧠 Student REST API ด้วย Gin & SQLite

REST API สำหรับจัดการข้อมูลนักศึกษา พัฒนาด้วย:

-   Gin Framework
-   SQLite Database
-   Layered Architecture (Handler / Service / Repository / Model)

------------------------------------------------------------------------

🚀 วิธีรันโปรเจกต์ (How to Run)

1️⃣ ติดตั้ง Dependencies

ตรวจสอบว่าเครื่องมี Go ติดตั้งแล้ว จากนั้นรัน:

go mod tidy

------------------------------------------------------------------------

2️⃣ รันเซิร์ฟเวอร์

go run main.go

หากรันสำเร็จ จะเห็นข้อความ:

Listening and serving HTTP on :8080

เซิร์ฟเวอร์จะทำงานที่:

http://localhost:8080

------------------------------------------------------------------------

📡 API Endpoints ที่ใช้งานได้

------------------------------------------------------------------------

✅ ดึงข้อมูลนักศึกษาทั้งหมด

GET /students

ตัวอย่าง:

GET http://localhost:8080/students

------------------------------------------------------------------------

✅ ดึงข้อมูลนักศึกษาตาม ID

GET /students/:id

ตัวอย่าง:

GET http://localhost:8080/students/6609650749

------------------------------------------------------------------------

✅ เพิ่มข้อมูลนักศึกษา

POST /students

POST http://localhost:8080/students Content-Type: application/json

Request Body:

{ “id”: “6609650749”, “name”: “Autthapinya”, “major”: “comsci”, “gpa”:
2.5 }

------------------------------------------------------------------------

✅ แก้ไขข้อมูลนักศึกษา

PUT /students/:id

PUT http://localhost:8080/students/6609650749 Content-Type:
application/json

Request Body:

{ “name”: “Updated Name”, “major”: “Updated Major”, “gpa”: 3.5 }

------------------------------------------------------------------------

✅ ลบข้อมูลนักศึกษา

DELETE /students/:id

DELETE http://localhost:8080/students/6609650749

Response:

204 No Content

------------------------------------------------------------------------

⚠️ รูปแบบ Error Response

{ “error”: “Student not found” }

------------------------------------------------------------------------

✅ กฎการตรวจสอบข้อมูล (Validation Rules)

-   ID ต้องไม่เป็นค่าว่าง
-   Name ต้องไม่เป็นค่าว่าง
-   GPA ต้องอยู่ระหว่าง 0.00 – 4.00

------------------------------------------------------------------------

🧪 วิธีทดสอบ API

สามารถทดสอบได้ด้วย:

-   VS Code REST Client (.http file)
-   Postman
-   curl

------------------------------------------------------------------------

🏗️ โครงสร้างโปรเจกต์

go-api-gin/ ├─ main.go ├─ models/ ├─ repositories/ ├─ services/ ├─
handlers/ └─ students.db
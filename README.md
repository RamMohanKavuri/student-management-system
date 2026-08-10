# AWS Student Management System

A serverless Student Management System built using AWS services.  
The application allows users to add, view, update, and delete student records through a web interface.

## 🚀 Project Overview

This project demonstrates how to build a serverless CRUD application using AWS.

The frontend communicates with Amazon API Gateway, which invokes AWS Lambda functions. Lambda performs CRUD operations on Amazon DynamoDB.

## 🏗️ Architecture

```text
                    ┌──────────────────┐
                    │      User        │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │   index.html     │
                    │    Frontend      │
                    └────────┬─────────┘
                             │
                             │ HTTP Requests
                             ▼
                    ┌──────────────────┐
                    │  API Gateway     │
                    │   REST API       │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │   AWS Lambda     │
                    │  CRUD Operations │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │ Amazon DynamoDB  │
                    │ Student Records  │
                    └──────────────────┘☁️ AWS Services Used
AWS Service	Purpose
Amazon API Gateway	Exposes REST API endpoints
AWS Lambda	Executes backend CRUD operations
Amazon DynamoDB	Stores student information
Amazon S3	Can be used to host the frontend
AWS IAM	Controls permissions between AWS services
✨ Features
Add a new student
View all students
Update student information
Delete a student
REST API integration
DynamoDB database integration
CORS enabled
Serverless backend
Responsive web interface
🔄 CRUD Operations

The application supports the following operations:

Operation	HTTP Method	Description
Create	POST	Add a new student
Read	GET	Retrieve student records
Update	PUT	Update an existing student
Delete	DELETE	Delete a student
📁 Project Structure
student-management-system/
│
├── index.html
├── README.md
├── .gitignore
│
└── screenshots/
    ├── Add Student.png
    ├── Adding student.png
    ├── api-gateway.png
    ├── application.png
    ├── Dynamodb.png
    ├── lambda.png
    └── students list.png
🔌 API Integration

The frontend sends HTTP requests to the API Gateway endpoint.

Example:

GET     /students
POST    /students
PUT     /students/{id}
DELETE  /students/{id}

The API Gateway invokes the Lambda function, and Lambda communicates with DynamoDB.

🗄️ DynamoDB

Student records are stored in Amazon DynamoDB.

Example student record:

{
  "id": "101",
  "name": "Ram",
  "email": "ram@example.com",
  "course": "AWS",
  "age": 22
}
🔐 CORS

CORS (Cross-Origin Resource Sharing) is enabled on the API so that the frontend can communicate with the API Gateway endpoint from a different origin.

The API allows the required HTTP methods:

GET
POST
PUT
DELETE
OPTIONS
🖥️ Application Screenshots
Application

Add Student

Adding Student

Students List

☁️ AWS Screenshots
API Gateway

AWS Lambda

DynamoDB

🔧 Technologies Used
HTML5
CSS3
JavaScript
REST API
Amazon API Gateway
AWS Lambda
Amazon DynamoDB
Amazon S3
AWS IAM
⚙️ Application Flow
1. User opens the Student Management application.
                         ↓
2. User performs an operation.
                         ↓
3. Frontend sends an HTTP request.
                         ↓
4. API Gateway receives the request.
                         ↓
5. API Gateway invokes Lambda.
                         ↓
6. Lambda processes the request.
                         ↓
7. Lambda reads/writes DynamoDB.
                         ↓
8. Response is returned to the frontend.
                         ↓
9. Updated student information is displayed.
🛠️ Deployment Steps
Step 1: Create DynamoDB Table

Create a DynamoDB table for storing student records.

Configure the required partition key according to the Lambda implementation.



Create an AWS Lambda function containing the backend CRUD logic.

The Lambda function handles:

GET
POST

PUT
DELETE
Step 3: Configure API Gateway

Create an API Gateway REST API and configure the required routes.

Example:

GET     /students
POST    /students
PUT     /students/{id}
DELETE  /students/{id}

Integrate the API routes with the Lambda function.

Step 4: Enable CORS

Enable CORS for the API Gateway routes so that the frontend can communicate with the backend API.


Step 5: Configure Frontend

Update the API Gateway URL in index.html.

Example:

const API_URL = "YOUR_API_GATEWAY_URL";
Step 6: Host the Frontend

The frontend can be hosted using Amazon S3 static website hosting or another web hosting service.

🔒 Security

The following security practices should be followed:

Do not commit AWS access keys.
Do not commit .pem files.
Use IAM roles for Lambda permissions.
Follow the principle of least privilege.
Restrict DynamoDB access to required operations.
Configure CORS according to application requirements.
📌 Important

Replace:

YOUR_API_GATEWAY_URL

with your actual API Gateway endpoint before deploying the application.

Do not upload AWS credentials, secret keys, .pem files, or other sensitive information to GitHub.

🎯 Learning Outcomes

This project demonstrates practical experience with:

AWS serverless architecture
AWS Lambda
Amazon API Gateway
Amazon DynamoDB
REST APIs
CORS
CRUD operations
IAM permissions
Frontend and backend integration
Git and GitHub
👨‍💻 Author

Ram Mohan Kavuri

GitHub:
https://github.com/RamMohanKavuri


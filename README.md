AWS Lost & Found Application
Project Overview

The AWS Lost & Found Application is a cloud-based web application that helps users report and search for lost items. Users can upload an image, enter item details, and search for previously reported items. The application is built using AWS services to provide a secure, scalable, and serverless backend.

Features
  - Report a lost or found item
  - Upload item images
  - Store images securely in Amazon S3
  - Store item information in Amazon RDS (MySQL)
  - Detect image labels automatically using Amazon Rekognition
  - REST APIs using API Gateway
  - Backend processing using AWS Lambda (Python)
  - Search items by item name or category
  - Delete resolved items
  - Monitor logs using CloudWatch

Service	Purpose
  Amazon EC2 -	Hosts the frontend (HTML, CSS, JavaScript)
  Amazon S3	- Stores uploaded images
  Amazon API Gateway	- Provides REST APIs
  AWS Lambda - Backend business logic (Python)
  Amazon DynamoDB - Stores item details
  IAM	- Secure permissions between AWS services
  CloudWatch - Logging and monitoring

Implementation
  1. Frontend Development
  
  Built a responsive user interface using HTML, CSS, and JavaScript and hosted it on an Amazon EC2 instance. Users can report lost/found items, upload images, search items, and delete resolved items.
  
  2. REST API Creation
  
  Created REST APIs using Amazon API Gateway to handle requests from the frontend:
  
  POST /report – Submit a lost/found item
  GET /items – Retrieve all reported items
  GET /item – Search an item by name
  DELETE /item – Remove a claimed item
  3. Backend Processing
  
  Implemented backend logic using AWS Lambda (Python). Lambda validates requests, processes uploaded data, interacts with AWS services, and returns responses to the frontend.
  
  4. Image Storage
  
  When a user uploads an image, the Lambda function stores it in an Amazon S3 bucket and generates an image URL for future access.
  
  5. Database Storage
  
  All item information—including item name, description, location, contact details, image URL,are stored in an DynamoDB database.
  
  6. Search and Retrieval
  
  Users can search for lost or found items. The frontend sends a request to API Gateway, which invokes a Lambda function to fetch matching records from RDS and return them to the user.
  
  7. Logging and Monitoring
  
  All Lambda executions, API requests, and errors are logged in Amazon CloudWatch, making it easier to monitor application performance and troubleshoot issues.
  
  8. Security
  
  IAM Roles and Policies are used to grant secure, least-privilege access between Lambda, S3, DynamoDB and CloudWatch. The S3 bucket is configured with appropriate access controls.

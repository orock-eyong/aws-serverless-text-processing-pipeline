# 🚀AWS Serverless Text Processing Pipeline

![AWS](https://img.shields.io/badge/AWS-Serverless-orange)
![Python](https://img.shields.io/badge/Python-3.11-blue)
![AWS Lambda](https://img.shields.io/badge/AWS-Lambda-yellow)
![API Gateway](https://img.shields.io/badge/AWS-API_Gateway-red)
![S3](https://img.shields.io/badge/AWS-S3-green)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

## Overview

This project demonstrates a serverless text processing pipeline using AWS Lambda, API Gateway, and Amazon S3.

The system automatically processes uploaded `.txt` files, extracts metadata, persists results, and generates real-time notifications — without provisioning or managing servers.

The architecture follows cloud-native design principles including:

- Event-driven workflows
- Service decoupling
- Managed services
- Horizontal scalability
- Operational visibility

---

## 🏗️ Architecture

<p align="center">
  <img src="architecture.png" width="600">
</p>

### Flow

1. A user uploads a `.txt` file to the S3 upload bucket  
2. S3 triggers a Lambda function  
3. The Lambda function:
   - Counts words in the file  
   - Stores metadata in DynamoDB  
   - Writes processed output to a separate S3 bucket  
   - Publishes an SNS notification  
4. Deletion events from the processed bucket trigger additional SNS alerts  

---

## AWS Services Used

- Amazon S3
- AWS Lambda
- Amazon DynamoDB
- Amazon SNS
- Amazon CloudWatch Logs

Region: **eu-north-1 (Stockholm)**

---

## Technical Highlights

- Fully serverless architecture
- Event-driven processing model
- DynamoDB metadata persistence
- Automated notification system
- Structured logging via CloudWatch
- Separation of upload and processed storage tiers
- Delete-event monitoring

---

## Repository Structure


---

## Design Considerations

- Stateless compute via AWS Lambda
- Managed NoSQL storage with DynamoDB
- Decoupled notification service (SNS)
- Clear separation of ingestion and processed data
- CloudWatch logging for observability

---

## Future Enhancements

- Introduce Amazon SQS for message buffering and decoupling
- Add API Gateway for querying metadata
- Implement IAM least-privilege policies
- Convert infrastructure to Infrastructure-as-Code (Terraform or CloudFormation)
- Add automated tests and CI/CD pipeline

---

## Author

Built as a hands-on cloud engineering project to demonstrate practical serverless architecture skills.

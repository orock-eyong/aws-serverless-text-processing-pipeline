# 🚀 Serverless File Processing Pipeline

A fully serverless event-driven pipeline built on AWS that 
automatically processes uploaded text files, counts words, 
stores metadata and notifies via email.

## 🏗️ Architecture
![Pipeline Architecture](architecture/pipeline-diagram.svg)

## ⚙️ Services Used
- **S3** — File upload & processed output storage
- **SQS** — Event queue with Dead Letter Queue
- **Lambda** — Serverless file processing (Python 3.11)
- **DynamoDB** — Metadata storage
- **SNS** — Email notifications
- **CloudWatch** — DLQ monitoring & alerting

## 🔄 How It Works
1. User uploads a text file to S3
2. S3 triggers an SQS notification
3. Lambda processes the file and counts words
4. Results saved to S3 processed bucket
5. Metadata saved to DynamoDB
6. SNS email notification sent on success
7. Failed messages routed to DLQ with CloudWatch alarm

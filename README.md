# QuickDataProcessor (QDP)

## Overview
QuickDataProcessor (QDP) is a serverless cloud-based data processing system designed to enable users to process their data on-demand. Built with a multi-cloud deployment and Backend-as-a-Service (BaaS) architecture, QDP offers robust features for data analysis, virtual assistance, and secure multi-factor authentication.

## Key Features
- **Multi-factor Authentication**: Provides three levels of authentication, including security questions and math-based challenges.
- **Virtual Assistant**: Uses Google Dialogflow and AWS Lambda to handle user queries and provide task updates in real-time.
- **Message Passing Module**: Facilitates real-time communication between users and agents via GCP Pub/Sub and Firestore.
- **Data Processing**: Automated data transformation with AWS Glue, Google NLP, and Google Cloud services for JSON-to-CSV conversion, text analysis, and word cloud generation.
- **Notifications**: Real-time updates via AWS SNS for login, sign-up, and task completions.
- **Data Analysis Dashboard**: Visualizes feedback and word frequencies using Looker Studio.

## System Architecture
The architecture is designed with a multi-cloud approach:
- **AWS**: Manages user authentication (Cognito), message queueing (SQS), serverless functions (Lambda), and NoSQL database (DynamoDB).
- **Google Cloud**: Handles real-time communication (Pub/Sub), virtual assistant queries (Dialogflow), and frontend/backend deployment (Cloud Run and Cloud Build).
- **CI/CD**: Fully automated deployment pipeline using Docker, Artifact Registry, and Cloud Build.

![System Architecture](/QuickDataProcessor%20Architecture.png)  

## Modules
### 1. User Management and Authentication
- **AWS Cognito**: Secure login and sign-up with email/password.
- **Security Questions**: Second-factor authentication with custom questions stored in DynamoDB.
- **Math Verification**: A simple math-based third-factor challenge.

### 2. Virtual Assistant
- Built with **Dialogflow** for intuitive natural language processing.
- Provides real-time status updates and task navigation.

### 3. Message Passing
- Uses GCP Pub/Sub for asynchronous communication.
- Logs user-agent interactions in Firestore.

### 4. Data Processing
- **DP1**: JSON-to-CSV conversion using AWS Glue.
- **DP2**: Text entity extraction with Google NLP and CSV output to S3.
- **DP3**: Word cloud generation with Cloud Run and visualization in Looker Studio.

### 5. Notifications
- **AWS SNS**: Sends email updates for task status, login, and sign-up events.

### 6. Data Analysis
- Integrated Looker Studio dashboard for visualizing feedback and processing insights.

## Deployment
### Prerequisites
- AWS and GCP accounts with required services enabled.
- Docker installed on your local machine.
🚀 AWS 3-Tier Architecture | Scalable & Highly Available Web Application

📌 Project Overview

This project demonstrates the design and implementation of a **production-style AWS 3-Tier Architecture** for a web application.
The goal of this project is to simulate a **real-world cloud environment** with high availability, scalability, monitoring, logging, and secure networking.

The application is deployed using **AWS managed services** and follows **industry-standard DevOps and SRE practices**.

---

🧱 Why 3-Tier Architecture?

A 3-tier architecture separates concerns into independent layers, which improves:

* **Scalability** – each layer can scale independently
* **Availability** – failures in one layer do not bring down the system
* **Security** – controlled access between layers
* **Maintainability** – easier updates and troubleshooting

### The three tiers are:

1. Presentation Layer
2. Application Layer
3. Data Layer

---

🏗️ Architecture Breakdown

### 1️⃣ Presentation Layer (Client Access Tier)

**Purpose:**
Handles incoming user traffic and distributes it across application servers.

**AWS Services Used:**

* **Application Load Balancer (ALB)**

**How it works:**

* The ALB receives HTTP requests from users over the internet.
* It routes traffic to healthy EC2 instances using target groups.
* Health checks ensure traffic is sent only to healthy instances.
* ALB enables fault tolerance and high availability.

---

### 2️⃣ Application Layer (Business Logic Tier)

**Purpose:**
Processes application logic and handles user requests.

**AWS Services Used:**

* **Amazon EC2**
* **Auto Scaling Group**
* **Launch Template**

**How it works:**

* EC2 instances host the web application.
* Instances are launched using a **Launch Template** to maintain consistency.
* Auto Scaling Group automatically:

  * Adds instances during high traffic
  * Removes instances during low traffic
* This ensures performance optimization and cost efficiency.

---

### 3️⃣ Data Layer (Database Tier)

**Purpose:**
Stores application data securely and persistently.

**AWS Services Used:**

* **Amazon RDS (MySQL)**

**How it works:**

* User data (name, age, profession) is stored in RDS.
* The database is deployed in a private network within the VPC.
* Only application EC2 instances can access the database.
* Ensures data persistence even if EC2 instances are terminated.

---

🌐 Networking & Security

**AWS Services Used:**

* **Amazon VPC**
* **Security Groups**
* **IAM Roles & Policies**

### VPC Design:

* Public subnets for ALB
* Private subnets for EC2 and RDS
* Controlled routing using security groups

### Security:

* IAM roles allow EC2 to interact with AWS services securely
* No hardcoded credentials
* Principle of least privilege applied

---

📊 Monitoring, Logging & Observability

🔍 Monitoring

**Service Used:** Amazon CloudWatch

* CPU utilization metrics are monitored
* CloudWatch alarms trigger when CPU crosses defined thresholds
* Alarms are connected to Auto Scaling actions

📝 Logging

**Service Used:** Amazon S3

* ALB access logs are enabled
* Logs are stored in an S3 bucket
* Useful for traffic analysis, debugging, and audits

---

🔄 Application Workflow

1. User accesses the application using ALB DNS
2. ALB routes the request to a healthy EC2 instance
3. EC2 processes the request
4. User data is stored in Amazon RDS
5. CloudWatch monitors system metrics
6. Auto Scaling adjusts EC2 capacity based on load
7. ALB logs requests and stores them in S3

---

🛠️ AWS Services Used

* Amazon EC2
* Application Load Balancer (ALB)
* Auto Scaling Group
* Launch Templates
* Amazon RDS (MySQL)
* Amazon S3
* Amazon CloudWatch
* Amazon VPC
* IAM Roles & Policies

---

🎯 Key Learning Outcomes

* Designed a **real-world AWS 3-tier architecture**
* Implemented **high availability and auto scaling**
* Gained hands-on experience with **monitoring and logging**
* Applied **security best practices using IAM**
* Built a **production-ready DevOps portfolio project**

---

🚀 Future Improvements

* Add HTTPS using ACM & Route 53
* Implement CI/CD pipeline (GitHub Actions / GitLab CI)
* Add containerization using Docker
* Use Terraform for full infrastructure automation
* Introduce WAF for enhanced security

---

👤 Author

**Pandian M**
Cloud & DevOps Engineer


# AWS-CloudWatch-Resource-Monitoring-Alarms-Dashboard
Hands-on AWS lab demonstrating how to monitor EC2 resources using Amazon CloudWatch, create alarms for CPU utilization, send notifications with SNS, and visualize metrics through CloudWatch Dashboards.
# Using CloudWatch for Resource Monitoring: Alarms and Dashboards

## Overview

This project demonstrates how to monitor AWS resources using **Amazon CloudWatch**, create **CloudWatch alarms**, configure **SNS notifications**, and visualize metrics through **CloudWatch dashboards**.

Monitoring is essential in cloud environments because infrastructure is dynamic and scalable. CloudWatch provides visibility into system performance and allows administrators to detect issues early.

This lab focuses on monitoring **EC2 CPU utilization** and triggering alerts when resource usage exceeds a defined threshold.

---

# Lab Title

Using CloudWatch for Resource Monitoring, Creating CloudWatch Alarms and Dashboards

---

# Objective

The goal of this lab is to learn how to:

- Monitor EC2 performance using CloudWatch
- Create SNS topics for alert notifications
- Configure CloudWatch alarms
- Trigger alarms based on CPU utilization
- Visualize metrics using CloudWatch dashboards

---

# AWS Services Used

- Amazon EC2
- Amazon CloudWatch
- Amazon SNS
- IAM
- Linux / SSH

---

# Architecture

EC2 Instance  
↓  
CloudWatch Metrics (CPU Utilization)  
↓  
CloudWatch Alarm  
↓  
SNS Topic  
↓  
Email Notification  

Metrics can also be visualized in a **CloudWatch Dashboard**.

---

# Lab Tasks

### 1 Create an EC2 Instance

Launch an EC2 instance to simulate a resource that will be monitored.

---

### 2 Connect via SSH

SSH into the EC2 instance and install tools needed to generate CPU load.

Example tool:

---

### 3 Create an SNS Topic

Create an SNS topic to receive alert notifications.

Steps:

- Navigate to SNS
- Create a topic
- Add an email subscription
- Confirm subscription

---

### 4 Check EC2 Metrics in CloudWatch

Navigate to:

CloudWatch → Metrics → EC2

Monitor metrics such as:

- CPUUtilization
- NetworkIn
- NetworkOut
- DiskReadOps

---

### 5 Create a CloudWatch Alarm

Create an alarm based on the **CPUUtilization metric**.

Example configuration:

Metric: CPUUtilization  
Threshold: Greater than 70%  
Evaluation Period: 1 minute  

Alarm Action:

Send notification to SNS topic.

---

### 6 Stress the EC2 CPU

Simulate high CPU usage:

This causes CPU utilization to increase and triggers the CloudWatch alarm.

---

### 7 Verify Alarm Trigger

When the threshold is exceeded:

CloudWatch Alarm → State changes to **ALARM**

SNS sends an **email notification**.

---

### 8 Check CloudWatch Alarm Graph

View the alarm graph to analyze:

- CPU utilization spike
- alarm threshold
- alarm trigger point

---

### 9 Create CloudWatch Dashboard

Create a dashboard to visualize metrics in real time.

Dashboard widgets include:

- EC2 CPU utilization
- Alarm status
- Network activity

Dashboards provide a centralized monitoring interface.

---

# Why This Lab Matters

Cloud environments scale rapidly, and resource usage can change quickly.

Without monitoring systems in place:

- performance issues may go unnoticed
- systems may become overloaded
- operational failures may occur

CloudWatch helps detect abnormal behavior early and provides actionable alerts.

---

# Security Relevance

Monitoring metrics is not only important for performance but also for **security visibility**.

Abnormal resource usage may indicate:

- misconfigured applications
- crypto-mining malware
- denial-of-service activity
- compromised workloads

CloudWatch alarms enable faster detection and response to such anomalies.

---

# Skills Demonstrated

AWS Monitoring  
CloudWatch Alarms  
CloudWatch Dashboards  
SNS Notifications  
EC2 Performance Monitoring  
Cloud Security Observability

---

# Lessons Learned

- Monitoring is essential for reliable cloud infrastructure
- CloudWatch alarms allow automated incident detection
- Dashboards provide real-time system visibility
- Alerts help administrators respond quickly to issues

---

# Future Improvements

- Send logs to Amazon S3
- Analyze logs using Athena
- Integrate alerts with Slack
- Implement automated remediation using Lambda


Smart Guard - Computer Vision-Based Smart Security/Monitoring System

Table of Contents
Project Overview
Features
System Architecture
Modules
Installation
Usage
Datasets
Results
Future Improvements
References
Project Overview

Smart Guard is an AI-powered surveillance system designed to detect abnormal and violent behaviors in real-time. Using advanced deep learning models, the system provides alerts to security personnel via web push notifications and email when suspicious activities are detected. It is validated on real-world surveillance footage to ensure reliability and strong generalization.

This system is ideal for malls, schools, public spaces, and factories where continuous monitoring is required.

Features
Real-time detection of abnormal and violent behavior
High accuracy and strong generalization to external datasets
Web-based dashboard for monitoring live feed and alerts
Notifications via email and web push when confidence exceeds a set threshold
Easy integration with existing CCTV systems
System Architecture
Camera Feed --> Preprocessing --> AI Model (Violence Detection) 
           --> Alerts & Notification (Email / Web Push)
           --> Dashboard Visualization

Key Components:

Data Module – Handles video capture and preprocessing (frame extraction, resizing, normalization).
AI Model Module – Detects abnormal behavior using deep learning models CNN+BiLSTM+Multi-Head Attention.
Backend Module – Handles server operations, APIs, and integration with notification services.
Alerts & Notification Module – Sends web push and email alerts for confidence > 70%.
Dashboard Module – Visualizes live feeds, alert history, and performance metrics.
Modules
1. Data Preprocessing
Video frames are extracted and resized
Normalization and augmentation applied for better generalization
2. AI Model
Uses multiple models for improved accuracy:
Model A: YOLOv8 for motion detection
Model B: CNN classifier for violent vs non-violent frames
Model C: External dataset for generalization Test
3. Backend
FastAPI server handles requests from dashboard and notification modules
Connects to database to store alerts and event history
4. Alerts & Notifications
Web push notifications using Push API
Email alerts using SMTP
Trigger threshold configurable (default 70% confidence)
5. Dashboard
Visual interface to monitor camera feeds and alerts
Graphs and charts showing recent events
Filterable by camera, date, and severity
Installation
Prerequisites
Python 3.9+
Node.js 18+ (for React frontend)
Git
Backend Setup
git clone <repo-url>
cd Smart-Guard/Backend
pip install -r requirements.txt
uvicorn main:app --host 0.0.0.0 --port 8000
Frontend Setup
cd Smart-Guard/Frontend
npm install
npm run dev
Optional
Configure SMTP credentials in config.json for email alerts
Set web push credentials for notifications
Usage
Launch backend server
Launch frontend dashboard
Connect cameras or upload video files
Monitor real-time alerts on the dashboard
Receive notifications for any detected abnormal behavior
Datasets
RWF-2000 dataset for violence detection
External surveillance videos for robustness testing
~150 surveillance videos collected and annotated manually
Results
Test Accuracy: 91%
F1 Score: 85.35% on external dataset
Validated on external real-world videos to ensure strong generalization
Alerts triggered automatically for events with confidence > 70%
Future Improvements
Integration with multiple camera systems
Mobile app for real-time alerts
Continuous learning from new video feeds
Expansion to detect other abnormal behaviors (e.g., theft, fire)

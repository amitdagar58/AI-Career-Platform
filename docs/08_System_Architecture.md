# AI Career Platform

# System Architecture

**Document Version:** 1.0

**Last Updated:** 04 August 2026

**Prepared By:** Amit Dagar

---
# What is System Architecture?

System Architecture shows how different parts of the project work together.

It answers questions like:

How does the frontend communicate with the backend?
Where is the database?
Where does the AI model run?
How does the user interact with the system?

---

# 1. Introduction

This document describes the overall architecture of the AI Career Platform. It explains how different components of the system interact to provide intelligent career guidance.

The platform follows a modular architecture, where each component has a specific responsibility.

---

# 2. Architecture Overview

The AI Career Platform consists of the following major components:

- Frontend
- Backend
- Database
- Machine Learning Module
- AI Services

These components communicate through REST APIs to provide a scalable and maintainable system.

---

# 3. System Components

## Frontend

The frontend is developed using React.

Responsibilities:

- User Interface
- User Authentication
- Resume Upload
- Dashboard
- Display Recommendations

---

## Backend

The backend is developed using FastAPI.

Responsibilities:

- Business Logic
- API Development
- Authentication
- Database Communication
- AI Integration

---

## Database

The project uses MySQL.

Responsibilities:

- Store User Information
- Store Resume Data
- Store Job Information
- Store Analysis Results

---

## Machine Learning Module

Responsibilities:

- Salary Prediction
- Job Recommendation
- Skill Gap Analysis

---

## AI Module

Responsibilities:

- Resume Analysis
- Career Guidance
- Interview Question Generation

---

# 4. Data Flow

The overall system workflow is:

User

↓

React Frontend

↓

FastAPI Backend

↓

MySQL Database

↓

Machine Learning Models

↓

AI Services

↓

Response to User

---

# 5. Benefits of the Architecture

- Modular Design
- Easy Maintenance
- High Scalability
- Better Performance
- Independent Development of Components
- Easy Future Expansion

---

# Conclusion

The modular architecture of the AI Career Platform ensures scalability, maintainability, and flexibility. Each component performs a dedicated role while communicating efficiently through REST APIs.